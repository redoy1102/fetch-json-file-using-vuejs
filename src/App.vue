<template>
  <v-app>

    <v-main>
      <questions></questions>
    </v-main>
  </v-app>
</template>

<script>
import questions from "@/components/questions";

export default {
  name: 'App',
  data: () => ({
    //
  }),
  components: {
    questions,
  }
};
</script>
