<template>
    <PostForm @submit="savePost($event)"/>
</template>

<script>
import PostForm from "@/components/Gästebuch"
export default {
    name: "geschichte",
    layout: "gaestebuch",
    components : {
        PostForm
    },
    methods : {
        savePost(post){
            console.log(post)
        }
    }
}
</script>
