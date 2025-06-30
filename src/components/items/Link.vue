<template>
  <a class="link" :href="link">
    <slot></slot>
  </a>
</template>

<script>
export default {
    props: {
        link: String
    }
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Onest:wght@100..900&display=swap');
.link {
    color: #dddddd;

    font-size: 16px;

    font-family: Onest;

    text-decoration: none; 
}

.link:hover {
    text-decoration: underline; 

    text-decoration-color: #007bff;

    color: #218cffa3;

    cursor: pointer;
}

</style>