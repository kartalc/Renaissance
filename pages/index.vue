<template>
    <div>
    <Banner />        
<!--<PostList :posts="fetchedPosts"/> -->
    <a style="text-align:left">Adresse: Bahnhofstaße 1 | 31134 Hildesheim<br></a>
<!--     <a style="text-align:right">Öffnungszeiten: Mo.-Sa. 17- 22:30 | So. 12-15 &amp; 17-22 Uhr</a>
 -->
    <About />
 <!--    <Kontakt />  -->
    </div>
</template>
<script>
    import PostList from "@/components/post/PostList.vue"
    import About from "@/pages/About.vue"
    import Kontakt from "@/components/kontakt/Kontakt"
    import Banner from "@/components/common/Banner"

        export default {
        components : {
            PostList,
            About,
            Banner,
            /* Kontakt */ 
        },
        data(){
            return {
                fetchedPosts : [ ]
            }
        },
        created() {
        }, 
        asyncData(context){
            console.log(context)
            return new Promise((resolve, reject) => {
                resolve(
                    {
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
                }
                )
            })
                .then( data =>{
                    console.log(data);
                })
                .catch(e => {
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