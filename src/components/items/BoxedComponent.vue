<template>
    <div class="boxedcmp">
        <slot></slot>
    </div>
</template>

<script>
export default {

}
</script>

<style scoped>
.boxedcmp {
    width: 60%;
    height: 100%;

    background-color: rgba(23, 23, 23, 0.725);

    /* centering header */
    margin-top: 12px;
    margin-bottom: 12px;
    margin-left: auto;
    margin-right: auto;

    display: flex;

    border-radius: 12px;

    justify-content: center;
    align-items: center;

}

@media (max-width: 480px) {
  .boxedcmp {
    width: 85%;
    flex-direction: column;
  }
}
@media (min-width: 481px) and (max-width: 768px) {
  .boxedcmp {
    width: 85%;
    flex-direction: column;
  }
}

@media (min-width: 769px) and (max-width: 1024px) {
  .boxedcmp {
    width: 70%;
  }
}
</style>