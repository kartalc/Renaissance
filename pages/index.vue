<template>
    <div>
    <PostList :posts="fetchedPosts"/>
    <About />
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
            About,
            Kontakt 
        },
        data(){
            return {
                fetchedPosts : [ ]
            }
        },
        created() {
        }, 
        asyncData(context, callback){
            return new Promise((resolve, reject) => {
                
            }).catch(e => {
                context.error(new Error());
            })
            setTimeout(() => {
                callback(null, {
                    fetchedPosts : [
                        {
                            id : 1,
                            title : "Bir Küçük Aslancık varmış",
                            subTitle : "Kırlarda koşar koşar oynarmış",
                            text : "Küçük kurbağa güççük gurbaa kuyruğun nerede!!!",
                            author : "CK"
                        },
                        {
                            id : 2,
                            title : "İki incatçı keçi",
                            subTitle : "Köprüde denk gelir",
                            text : "Bir köprüde karşılaşmış iki inatçı geççi!!!",
                            author : "Anonim"
                        },
                                    ]
                })
            })
        }
    }
</script>
<style scoped></style>