<template>
  <div class="top">
    <v-row
      class="mx-0" style="height: 200px;"
      justify="center" align-content="center"
    >
      <h1 class="display-3 text-center">ANALYZEES</h1>
    </v-row>

    <v-row
      class="mx-0" style="height: 200px;"
      justify="center" align-content="center"
    >
      <h2 class="headline text-center">
        数百社のエントリーシートのデータを学習したAI(Doc2Vecモデル)が<br>
        入力した文章に対してどの企業のエントリーシートに似ているか判定します
      </h2>
    </v-row>

    <v-row
      align="center"
      justify="space-around"
    >
      <v-btn
        tile
        color="success"
        to="/analyze"
      >
        <v-icon left>
          mdi-pencil
        </v-icon>
        解析する
      </v-btn>
    </v-row>
  </div>
</template>
