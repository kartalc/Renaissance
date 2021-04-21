<template>
    <PostForm :is-update="true" />
</template>

<script>
import PostForm from "@/components/Gästebuch"
export default {
    components : {
        PostForm
    }
}
</script>