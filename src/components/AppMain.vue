<script>
import axios from 'axios';


export default {
    data() {
        return {
            baseUrl: 'http://127.0.0.1:8000',
            posts: []
        }
    },
    created() {
        axios.get(`${this.baseUrl}/api/posts`)
            .then((resp) => {
                this.posts = resp.data.result.data;
            })
    }
}



</script>


<template>
    <div class="container">

        <h3 class="mt-5">Posts List</h3>

        <div class="row row-cols-1 row-cols-md-3 row-cols-lg-4 g-3">
             <div class="col" v-for="post in posts" :key="post.id">
                <div class="card mt-3 h-100">
                    <div class="card-body">
                        <h4>{{ post.title }}</h4>
                    </div>

                </div>
             </div>
        </div>

    </div>
</template>


<style lang="scss" scoped></style>