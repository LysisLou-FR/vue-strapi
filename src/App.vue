<template>
  <div id="app">
    <div v-if="error">
      {{ error }}
    </div>
    <div v-else>
      <ul>
        <li v-for="jeu in jeux" :key="jeu.id">
          {{ jeu.attributes.name }}
        </li>
      </ul>
      <form id="form" v-on:submit="handleSubmit">
        <label for="name">Name</label>
        <input id="name" v-model="modifiedData.data.name" type="text" name="name">

        <label for="description">Description</label>
        <input id="description" v-model="modifiedData.data.description" type="text" name="description">

        <input type="submit" value="Submit">
      </form>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'App',
  data () {
    return {
      jeux: [],
      modifiedData: {
        data: {
          name: '',
          description: '',
        },
      },
      error: null
    }
  },
  async mounted () {
    try {
      const response = await axios.get('http://145.239.198.154:1337/api/jeux')
      this.jeux = response.data.data
    } catch (error) {
      this.error = error;
    }
  },
  methods: {
    handleSubmit: async function(e) {
      e.preventDefault();
      try {
        const response = await axios.post('http://145.239.198.154:1337/api/jeux', this.modifiedData, {
        headers: {
          Authorization:
            'Bearer 10d2330bd8506f357c95a619e64ac8fc4ed2e86e956f08228abad1c5a9bf38dea7f87066b5b947cd81008e1d4e12b6534754f13411369a9e43967dd5e9871806f8fbb2424bae4e61d8f32df2719feea77fb0d624e1c1ae4d670750964d4cc1ab0a005e4d02553b13a6b1c71383878c943e1c385588d0eff52ba0cd0ad4e20f87',
        },
      })
        console.log(response);
      } catch(error) {
        this.error = error;
      }
    }
  }
}
</script>
