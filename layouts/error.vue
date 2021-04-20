<template>
    <div class="error-page">
        <h1>Hayda!!</h1>
        <p>Bu sayfa bulunamadı</p>
    </div>
</template>
<script>
        export default {
        layout: "error"
    }
</script>
<style scoped>
.error-page{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

</style>