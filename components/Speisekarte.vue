<template>
   <div class="container-fluid mt-5 d-flex flex-wrap justify-content-center align-items-center">
    <div v-for="(currentPost, index) in allPosts" :key="index" class="col-sm-5 col-md-6 col-12 pb-4">
                <h1>Comments</h1>
                <div class="comment mt-4 text-justify float-left">
                    <h4>{{ currentPost.gericht }}</h4> 
                    <p>{{ currentPost.quantity }} </p> 
                    <span>{{ currentPost.preis}} €</span>
                </div>
            </div>
    
    <!--menüler burda başlar// --> 
    <div class="card mr-3 mb-3 card-success" style="width: 20rem;">
            <div class="card-body">
            <h5 class="card-title">Crema di Pomodoro</h5>
            <h6 class="card-subtitle mb-2 text-muted">Suppe</h6>
            <p class="card-text">Tomatencremesuppe</p>
            <img src="~/static/images/pomodoro.jpg" width=150 height=auto /><br>
            <input type="quantity" v-model="quantity" placeholder="stück eingeben"><br>
            <button @click="onSubmit('Suppe', 5)" type="submit" class="btn btn-outline-danger btn-sm">Bestellen</button>
    </div>
    </div>
        <div class="card mr-3 mb-3 card-success" style="width: 20rem;">
            <div class="card-body">
            <h5 class="card-title">Minestrone</h5>
            <h6 class="card-subtitle mb-2 text-muted">Suppe</h6>
            <p class="card-text">Gemüsesuppe</p>
            <img src="~/static/images/minestrone.jpg" width=180 height=auto /><br>
            <input type="quantity" v-model="quantity" placeholder="stück eingeben"><br>
            <button @click="onSubmit('Suppe', 4)" type="submit" class="btn btn-outline-danger btn-sm">Bestellen</button>
    </div>
    </div>
    <div class="card mr-3 mb-3 card-success" style="width: 20rem;">
            <div class="card-body">
            <h5 class="card-title">Insalata Mista</h5>
            <h6 class="card-subtitle mb-2 text-muted">Salate</h6>
            <p class="card-text">gemischter Salat</p>
            <img src="~/static/images/mista.jpg" width=150 height=auto /><br>
            <input type="quantity" v-model="quantity" placeholder="stück eingeben"><br>
            <button @click="onSubmit('Salate', 6)" type="submit" class="btn btn-outline-danger btn-sm">Bestellen</button>
    </div>
    </div>
    <div class="card mr-3 mb-3 card-success" style="width: 20rem;">
            <div class="card-body">
            <h5 class="card-title">Insalata Italiana</h5>
            <h6 class="card-subtitle mb-2 text-muted">Salate</h6>
            <p class="card-text">eine besondere Salat-Kreation des Chefs</p>
            <img src="~/static/images/italiana.jpg" width=190 height=auto /><br>
            <input type="quantity" v-model="quantity" placeholder="stück eingeben"><br>
            <button @click="onSubmit('Salate', 7)" type="submit" class="btn btn-outline-danger btn-sm">Bestellen</button>
    </div>
    </div>
    <div class="card mr-3 mb-3 card-success" style="width: 20rem;">
            <div class="card-body">
            <h5 class="card-title">Spaghetti alla Carbonara</h5>
            <h6 class="card-subtitle mb-2 text-muted">Pasta</h6>
            <p class="card-text">Nudeln mit Ei und Speck</p>
            <img src="~/static/images/carbonara.jpg" width=190 height=auto /><br>
            <input type="quantity" v-model="quantity" placeholder="stück eingeben"><br>
            <button @click="onSubmit('Nudeln', 8)" type="submit" class="btn btn-outline-danger btn-sm">Bestellen</button>
    </div>
    </div>
    <div class="card mr-3 mb-3 card-success" style="width: 20rem;">
            <div class="card-body">
            <h5 class="card-title">Linguine Scampi</h5>
            <h6 class="card-subtitle mb-2 text-muted">Pasta</h6>
            <p class="card-text">Nudeln mit Scampis</p>
            <img src="~/static/images/scampi.jpg" width=190 height=auto /><br>
            <input type="quantity" v-model="quantity" placeholder="stück eingeben"><br>
            <button @click="onSubmit('Nudeln', 13)" type="submit" class="btn btn-outline-danger btn-sm">Bestellen</button>
    </div>
    </div>
    <div class="card mr-3 mb-3 card-success" style="width: 20rem;">
            <div class="card-body">
            <h5 class="card-title">Pizza dello Chef</h5>
            <h6 class="card-subtitle mb-2 text-muted">Pizza</h6>
            <p class="card-text">mit Tomatensauce, Käse, Champignons</p>
            <img src="~/static/images/chef.jpg" width=150 height=auto /><br>
            <input type="quantity" v-model="quantity" placeholder="stück eingeben"><br>
            <button @click="onSubmit('Pizza', 11)" type="submit" class="btn btn-outline-danger btn-sm">Bestellen</button>
    </div>
    </div>
    <div class="card mr-3 mb-3 card-success" style="width: 20rem;">
            <div class="card-body">
            <h5 class="card-title">Costata alla griglia</h5>
            <h6 class="card-subtitle mb-2 text-muted">Grill</h6>
            <p class="card-text">Rumpsteak vom Grill</p>
            <img src="~/static/images/grill.jpg" width=150 height=auto /><br>
            <input type="quantity" v-model="quantity" placeholder="stück eingeben"><br>
            <button @click="onSubmit('Grill', 18)" type="submit" class="btn btn-outline-danger btn-sm">Bestellen</button>
    </div>
    </div>


    </div>

</template>

<script>
export default {
    data(){
        return {
            quantity: '',
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
            onSubmit(gericht, preis){
                console.log(this.post);
                const bestellung = {gericht: gericht, preis: preis, quantity: this.quantity }
                this.allPosts.push({...bestellung});
                this.post = {title : null,
                subTitle : null,
                author : null,
                text : null,}
                console.log(this.allPosts);
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

.card{
border-radius: 3px;
box-shadow: 1px;
width: 40%;
height: 20rem;
margin: 1rem;

/* height: 200px;
width: 100px;
background-position: center center;
background-repeat: no-repeat;
background-size: cover; */
}
</style>