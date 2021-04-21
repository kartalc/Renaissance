<template>
  <div>
    <Header />
    <Banner />
    <Nuxt />
  </div>
</template>
<script>
  import Header from "@/components/common/Header"
  import Banner from "@/components/common/speisekarte-banner"
  export default {
    components : {
      Header,
      Banner
      }
  }
</script>