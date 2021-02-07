<template>
  <v-container class="mx-auto my-auto">
    <v-form ref="input">
      <v-text-field
        label="あなたのあだ名"
        outlined
        color="purple"
        autofocus
        append-icon="mdi-account-arrow-right"
        :rules="[rule]"
        @click:append="start()"
        @keypress.enter.prevent
        @keypress.enter="start()"
      ></v-text-field>
    </v-form>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      rule: (v) => !!v || "ちゃんと入力！",
    };
  },
  methods: {
    start() {
      if (this.$refs.input.validate()) {
        console.log("start");
      }
    },
  },
};
</script>