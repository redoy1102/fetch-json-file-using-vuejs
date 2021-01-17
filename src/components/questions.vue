<template>
  <div class="container">
  <div class="row">
    <div class="col-12">
      <div v-for="{question,id,a,b,c,d,answer} in myJson" :key="id" class="card mx-2 my-2" style="width: 100%;">
        <div class="card-body">
          <h5 class="card-title" v-html="question"></h5>
              <v-radio-group v-model="radioGroup">
                <v-radio
                    :key="a"
                    :label="a"
                    :value="a"
                ></v-radio>
                <v-radio
                    :key="b"
                    :label="b"
                    :value="b"
                ></v-radio>
                <v-radio
                    :key="c"
                    :label="c"
                    :value="c"
                ></v-radio>
                <v-radio
                    :key="d"
                    :label="d"
                    :value="d"
                ></v-radio>
              </v-radio-group>
          <p class="green--text font-weight-light font-weight-bold ">Ans: {{answer}}</p>
        </div>
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
      myJson: json
    }
  },
}
</script>

<style scoped>

</style>