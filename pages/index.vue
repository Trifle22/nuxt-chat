<template>
  <v-layout
    column
    justify-center
    align-center
  >
    <v-flex
      xs12
      sm8
      md6
    >
      <v-btn @click="message">
        new message
      </v-btn>
    </v-flex>
  </v-layout>
</template>

<script>

export default {
  sockets: {
    connect() {
      console.log('IO connected')
    },
  },
  methods: {
    message() {
      this.$socket.client.emit('createMessage', {text: 'from client'})
    }
  }
}
</script>
