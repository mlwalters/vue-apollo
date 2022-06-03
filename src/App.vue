<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/>
  {{ message }}
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import { ref } from 'vue'
import { useQuery } from '@vue/apollo-composable'
import allCharactersQuery from './graphql/allCharacters.query.gql'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  setup() {
    const message = ref('Hello World')
    const { result } = useQuery(allCharactersQuery)
    return { message }
  },
  // data() {
  //   return {
  //     message: 'Hello World'
  //   }
  // }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
