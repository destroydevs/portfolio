<template>
  <div class="boxed">

    <slot></slot>

  </div>
</template>

<script>
export default {

}
</script>

<style scoped>

.boxed {
    background-color: rgba(94, 94, 94, 0.363);

    padding: 3px;

    box-shadow: 4px 4px 0 rgb(24, 24, 24);

    border-radius: 5px;

    /* transition: 1s ease; */
}

</style>