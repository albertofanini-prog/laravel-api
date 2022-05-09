<template>
    <div class="card post rounded-lg border border-black overflow-hidden">
        <img src="https://picsum.photos/450/250" class="w-full object-cover">
        <div class="card_body p-6">
            <h4 class="post_title mb-4 text-xl">
                {{post.title}}
            </h4>
            <p class="text-sky-800 mb-2" v-if="post.category">
                {{post.category.name}}
            </p>
            <ul class="tags flex flex-wrap gap-4 items-center">
                <li class="tag bg-white/30 rounded-full text-sm p-1 block" v-for="tag in post.tags" :key="tag.id">
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