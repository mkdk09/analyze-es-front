<template>
  <v-container fluid>
    <v-row align="start" justify="center">
      <v-col cols="10">
        <v-textarea
        outlined
        background-color="white"
        name="input-7-4"
        label="エントリーシートの内容を入力してください"
        v-model="InputText"
        ></v-textarea>
      </v-col>
      <v-col cols="2">
        <v-select
          v-model="topn"
          :items="maxResult"
          label="件数"
          number
        ></v-select>
        <v-btn outlined @click="SendData">
          解析する
        </v-btn>
      </v-col>
    </v-row>

    <v-row align="start" justify="center">
      <v-col cols="6">
        <Loading v-show="!resultShow"></Loading>
        <SimilarityResult v-show="resultShow" :items=items></SimilarityResult>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import axios from 'axios'
import Loading from '@/components/Loading'
import SimilarityResult from '@/components/SimilarityResult'
const maxResult = [...Array(51).keys()]
maxResult.splice(0, 1)

export default {
  name: 'App',

  data () {
    return {
      // 入力データ
      InputText: '',
      topn: 10,
      maxResult: maxResult,
      items: [],
      resultShow: false
    }
  },

  methods: {
    SendData: function () {
      this.resultShow = false
      var data = {
        text: this.InputText,
        topn: this.topn
      }

      axios
        // .post('http://127.0.0.1:5000/', data)
        // .post('https://analyze-es.herokuapp.com/', data)
        .post(process.env.VUE_APP_API_URL, data)
        .then(response => {
          this.items = response.data
          this.resultShow = true
        })
        .catch(err => {
          alert('APIサーバと接続できません')
          err = null
        })
    }
  },
  components: {
    Loading,
    SimilarityResult
  }
}
</script>
