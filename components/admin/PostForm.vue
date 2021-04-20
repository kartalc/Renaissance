<template>
    <div class="container-fluid mt-5 d-flex flex-wrap justify-content-center align-items-center">
    <form style="width: 500px" @submit.prevent="onSubmit">
        <fieldset>
            <legend v-if="isUpdate" >Köse Yazısı Düzenle</legend>
            <legend v-else>Neuer Eintrag</legend>
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
                <label>Fügen Sie eine schriftliche Rezension hinzu</label>
                <textarea v-model="post.text" class="form-control" rows="5">Was hat Ihnen gefallen oder missfallen?</textarea>
            </div>
            <button @click="$router.push('/admin')" class="btn btn-danger">Abbrechen</button>
            <button type="submit" class="btn btn-primary">Senden</button>
        </fieldset>
    </form>
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
            }
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
                this.$emit("submit", this.post)
        }
    }
}
</script>