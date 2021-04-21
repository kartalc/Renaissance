<template>
    <div class="container-fluid mt-5 d-flex flex-wrap justify-content-center align-items-center">
<section>
    <div class="container">
        <div class="row">
            <div v-for="(currentPost, index) in allPosts" :key="index" class="col-sm-5 col-md-6 col-12 pb-4">
                <h1>Comments</h1>
                <div class="comment mt-4 text-justify float-left">
                    <h4>{{ currentPost.author }}</h4> <span><br>{{ currentPost.title}}</span> <br>
                    <p>{{ currentPost.text }}</p>
                </div>
            </div>
            
<div class="col-lg-4 col-md-5 col-sm-4 offset-md-1 offset-sm-1 col-12 mt-4">
<form id="algin-form" style="width: 500px" @submit.prevent="onSubmit">
        <fieldset>
            <legend class="text-center text-white" v-if="isUpdate" >Eintrag bearbeiten</legend>
            <legend class="text-center text-white" v-else>Neuer Eintrag</legend>
            <div class="form-group">
                <label>Name</label>
                <input v-model="post.author" type="text" class="form-control" placeholder="Vor- und Nachname">
            </div>
            <div class="form-group">
                <label>Titel</label>
                <input v-model="post.title" type="text" class="form-control" placeholder="Was ist die wictigste Information!">
            </div>
            <div class="form-group">
                <label>E-Mail Adresse</label>
                <input v-model="post.subTitle" type="text" class="form-control" placeholder="Ihre E-Mail Adresse">
            </div>
            <div class="form-group">
                <label>Fügen Sie eine Rezension hinzu</label>
                <textarea v-model="post.text" class="form-control" rows="5">Was hat Ihnen gefallen oder missfallen?</textarea>
            </div>
            <button @click="$router.push('/admin')" class="btn btn-danger">Abbrechen</button>
            <button type="submit" class="btn btn-primary">Senden</button>
        </fieldset>
    </form>
        </div>

        </div>
    </div>
</section>

</div>
</template>

<script>
export default {
    data(){
        return {
            post : {
                title : null,
                subTitle : null,
                author : null,
                text : null,
            },
            allPosts: []
        }
    },
    props : {
        isUpdate : {
            type : Boolean,
            required : false,
            default : false
        }
    },
    methods : {
            onSubmit(){
                console.log(this.post);
                this.allPosts.push({...this.post});
                this.post = {title : null,
                subTitle : null,
                author : null,
                text : null,}
                // this.$emit("submit", this.post)
        }
    },
}
</script>

<style scoped>




.comment {
    border: 1px solid rgba(16, 46, 46, 1);
    background-color: rgba(16, 46, 46, 0.973);
    float: left;
    border-radius: 5px;
    padding-left: 40px;
    padding-right: 30px;
    padding-top: 10px
}

.comment h4,
.comment span,
.darker h4,
.darker span {
    display: inline
}

.comment p,
.comment span,
.darker p,
.darker span {
    color: rgb(184, 183, 183)
}

h1,
h4 {
    color: white;
    font-weight: bold
}

label {
    color: rgb(250, 243, 243)
}

.form-group p a {
    color: white
}


.form-group input,
.form-group textarea {
    background-color: black;
    border: 1px solid rgba(16, 46, 46, 1);
    border-radius: 12px
}

form {
    border: 1px solid rgba(16, 46, 46, 1);
    background-color: rgba(16, 46, 46, 0.973);
    border-radius: 5px;
    padding: 20px
}
</style>