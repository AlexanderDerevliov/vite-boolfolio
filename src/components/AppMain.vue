<script>
import axios from 'axios';


export default{
    data() {
        return{
           baseUrl: 'http://127.0.0.1:8000'
        }
    },
    created () {
      axios.get(`${this.baseUrl}/api/posts`)
      .then((resp) => {
        console.log(resp);
      })
    }
}



</script>


<template>

<h2>main page</h2>

</template>


<style lang="scss" scoped>

</style>