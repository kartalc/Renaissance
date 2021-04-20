<template>
    <PostDetail :post="fetchedPost"/>
</template>

<script>
import PostDetail from "@/components/post/PostDetail"
export default {
    components : {
        PostDetail
    },
    asyncData(context, callback){
        setTimeout(() => {
            callback(null, {
                fetchedPost : {
                    id : "1",
                    title : "canikom",
                    subTitle : "sdasdad",
                    author : "CK"
                }
            })
        }, 1500)

    } 
}
</script>