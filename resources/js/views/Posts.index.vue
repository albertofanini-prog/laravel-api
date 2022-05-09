<template>
    <div>
        <div class="container">
            <h1>
                Ultimi post
            </h1>
        </div>
        <div class="container">
            <div v-for="post in posts" :key="post.id">
                {{ post.title }}
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return{
            posts: []
        }
    },
    methods: {
        fetchPosts(){
            //axios.get
            //recuperare i post
            axios.get('/api/posts')
            .then(res=>{
                // console.log(res.data.posts)
                //recuperare array di posts
                const {posts} = res.data
                //salvare i posts
                this.posts = posts
            })
            .catch(err=>{
                console.warn(err)
            })
        }
    },
    mounted(){
        this.fetchPosts();
    }
}
</script>

<style lang="scss" scoped>

</style>