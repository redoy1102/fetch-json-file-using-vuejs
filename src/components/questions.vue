<template>
  <div class="container">
    <div class="row">
      <div class="col-12">
        <div v-for="data in myJson" :key="data.id" class="card mx-2 my-2" style="width: 100%;">
          <div class="card-body">
            <h5 class="card-title" v-html="data.question"></h5>
            <v-radio-group v-model="data.userAnswer">
              <v-radio
                  :label="data.a"
                  :value="data.a"
              ></v-radio>
              <v-radio
                  :label="data.b"
                  :value="data.b"
              ></v-radio>
              <v-radio
                  :label="data.c"
                  :value="data.c"
              ></v-radio>
              <v-radio
                  :label="data.d"
                  :value="data.d"
              ></v-radio>
            </v-radio-group>
          </div>
        </div>
        <div class="text-center my-5">
          <v-btn
              color="blue"
              class="ma-2 white--text"
              @click="submitBtn"
          >
            Submit
            <span><i class="fa fa-paper-plane mx-1" aria-hidden="true"></i></span>
          </v-btn>
        </div>
      </div>
    </div>

  </div>
</template>

<script>
import json from '../assets/data.json'

export default {
  name: "questions",
  data() {
    return {
      myJson: json,
    }
  },
  methods: {
    submitBtn() {

    },
    isCorrect(data){
      return data.userAnswer === data.answer
    }
  },
  computed: {
    mark(){
      let total = 0
          this.myJson.forEach(function (data) {
            if (data.answer === data.userAnswer){
              total++
            }
          })
      return total;
    }
  }
}
</script>

<style scoped>

</style>