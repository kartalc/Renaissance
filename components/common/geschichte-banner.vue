<template>
<div class="container-fluid bg p-0 d-flex justify-content-center align-items-center">
<div class="overlay"></div>
<h1 class="text-center text-white">Geschichte des Restaurants</h1>
</div>
</template>
<style scoped>
        .bg{
            background-image: url(../../static/images/geschichte.jpg);
            height: 500px;
            position: relative;
            background-position: center center;
            background-repeat: no-repeat;
            background-attachment: fixed;
            background-size: cover;
            background-color: #464646;
        }
        .bg h1{
            z-index: 1;
            font-size: 90px;
            }
        .overlay{
            width: 100%!important;
            height: 100%!important;
            background-color: rgba(0,0,0,.4);
            position: absolute;
            top: 0px;
            left:0px;
        }
</style>