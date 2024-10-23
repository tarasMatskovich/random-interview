<template>
  <v-container class="fill-height">
    <v-responsive
      class="align-centerfill-height mx-auto"
      max-width="900"
    >
      <v-card
        class="mx-auto my-8"
        elevation="16"
        max-width="344"
      >
        <v-card-item>
          <v-card-title>
            Random interview
          </v-card-title>
        </v-card-item>

        <v-card-text>
          <v-btn @click="start">
            Start
          </v-btn>
        </v-card-text>

        <v-card-text v-if="text" v-html="text">
        </v-card-text>
      </v-card>
    </v-responsive>
  </v-container>
</template>

<script setup>
  import {ref} from "vue";

  const users = [
    'Matskovych Taras',
    'Kovalenko Borys',
    'Vitvytskyi Stanislav'
  ]
  const text = ref('')
  function start(event) {
    const copyUsers = [...users]
    const i = Math.floor(Math.random() * copyUsers.length);
    const first = copyUsers[i];
    copyUsers.splice(i, 1)
    const j = Math.floor(Math.random() * copyUsers.length);
    const second = copyUsers[j];
    text.value = `<b>${first}</b> will interview <b>${second}</b>`
  }
</script>
