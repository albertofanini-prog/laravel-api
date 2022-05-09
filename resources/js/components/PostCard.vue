<template>
    <div class="card post">
        <div class="card_body">
            <h4 class="post_title">
                {{post.title}}
            </h4>
            <p v-if="post.category">
                {{post.category.name}}
            </p>
            <ul class="tags">
                <li class="tag" v-for="tag in post.tag" :key="tag.id">
                    {{tag.name}}
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    props:{
        post: {
            type: Object,
            required: false
        }
    }
}
</script>

<style lang="scss" scoped>

</style>