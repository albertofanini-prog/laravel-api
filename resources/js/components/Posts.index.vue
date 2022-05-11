<template>
    <div>
        <div class="container">
            <h1 class="text-4xl py-5">
                Ultimi post
            </h1>
        </div>
        <div class="container grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-5">
            <PostCard v-for="post in posts" :key="post.id" :post="post"/>
        </div>

    </div>
</template>

<script>
import PostCard from '../components/PostCard.vue' //uscire da views/andare in components/prendere componente

export default {
    components:{
        PostCard
    },
    data(){
        return{
            posts: []
        }
    },
    methods: {
        fetchPosts(){
            //axios.get
            //chiamata axios
            //recuperare i post
            axios.get('/api/posts')
            .then(res=>{
                // console.log(res.data.posts)
                //recuperare proprietà (array) posts in res.data
                const {posts} = res.data
                //salvare i posts
                this.posts = posts.data
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