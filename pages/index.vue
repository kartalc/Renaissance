<template>
    <div>
    <PostList />
    <!-- <About /> -->
    <Kontakt /> 
    </div>
</template>
<script>
    import PostList from "@/components/post/PostList.vue"
    import About from "@/components/home/About.vue"
    import Kontakt from "@/components/kontakt/Kontakt"
        export default {
        components : {
            PostList,
            // About,
            Kontakt 
        }
    }
</script>
<style scoped></style>