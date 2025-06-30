<template>
  <img :src="imgLink" alt="">
</template>

<script>
export default {
    props: {
        imgLink: {
            type: String,
            default: "/public/none.webp"
        }
    }
}
</script>

<style scoped>

</style>