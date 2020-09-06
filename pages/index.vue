<template>
  <v-layout
    column
    justify-center
    align-center
  >
    name
    <v-text-field v-model="name" />

    <br />
    <br />

    data
    <v-text-field v-model="bpData" />
    <br />

    <v-btn @click="createBP()">POST</v-btn>
  </v-layout>
</template>

<script>


export default {
  data(){
    return {
      name:"",
      bpData:""
    }
  },
  methods:{
    async createBP(){
      try{
        let results = await this.$axios.post("/api/blueprints", {name:this.name, data:this.bpData})
        console.info(results)
      }catch(e){
        console.error(e)
      }
    }
  },
  components: {

  }
}
</script>


