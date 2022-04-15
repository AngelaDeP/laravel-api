<template>
    <div class="container">
                    <div class="card-header m-3 text-center">
                        <h1>Posts Full List</h1>
                    </div>

                    <div class="row">
                        <div class="col-4 mt-5" v-for="post in posts" :key="post.id">
                            <div class="card">
                                <div class="card-body">
                                    <h5 class="card-title">{{post.title}}</h5>
                                    <p class="card-text">{{post.content}}</p>
                                    <a href="#" class="btn btn-primary">View all</a>
                                </div>
                            </div>
                        </div>
                    </div>

    </div>
</template>

<script>
    export default {
        name: 'MyMain',
        
        data() {
            return {
                posts: []
            }
        },
        created() {
            axios.get('/api/posts').then((response) => {
                this.posts = response.data.results;
            });
        }
    }
</script>
