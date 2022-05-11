<template>
    <div class="app bg-green-100">
        <header>
            <nav class="container">
                <ul>
                    <li>Home</li>
                    <li>Posts</li>
                    <li>Categories</li>
                </ul>
            </nav>
        </header>
        <PostsGrid/>
        <footer>
            <div class="container py-5">
                &copy; Boolpress 2022
            </div>
        </footer>
    </div>
</template>

<script>
    import PostsGrid from '../components/Posts.index.vue'

    export default{
        components: {
            PostsGrid,
        }
    }
</script>

<style lang="scss" scoped>
.app{
    min-height: 100vh;
}
</style>