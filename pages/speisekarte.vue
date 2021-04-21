<template>
    <PostForm @submit="savePost($event)"/>
</template>

<script>
import PostForm from "@/components/Speisekarte"
export default {
    name: "speisekarte",
    layout: "speisekarte",
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