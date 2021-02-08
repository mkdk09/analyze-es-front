<template>
  <v-app>
    <v-container fluid>
      <v-row align="start" justify="center">
        <v-col cols="10">
          <v-textarea
          outlined
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
          <v-btn outlined @click="SendData"> 解析する </v-btn>
        </v-col>
      </v-row>

      <v-row align="start" justify="center">
        <v-col cols="6">
          <v-card
            max-width="450"
            class="mx-auto"
          >
            <v-toolbar
              dark
            >
              <v-toolbar-title>Result</v-toolbar-title>
            </v-toolbar>

            <v-list three-line>
              <template v-for="(item, index) in items">
                <v-list-item
                  :key="item"
                >
                  <v-list-item-content>
                    <v-list-item-title >{{ index }}: {{ item }}</v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
                <v-divider
                  :key="index"
                ></v-divider>
              </template>
            </v-list>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-app>
</template>

<script>
import axios from 'axios'
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
      items: []
    }
  },

  methods: {
    SendData: function () {
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
        })
        .catch(err => {
          alert('APIサーバと接続できません')
          err = null
        })
    }
  }
}
</script>
