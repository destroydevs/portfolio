<template>
  <div class="header">
    <boxed>
        <m-text @mousemove="changeTextFrom" @mouseleave="changeTextTo" >{{ headerText }}</m-text>
    </boxed>

  </div>
</template>

<script>
import BoxedVue from './items/Boxed.vue'
import SecondTextVue from './items/SecondText.vue'
import TextVue from './items/Text.vue'
export default {
    components: {
        "sc-text": SecondTextVue,
        "m-text": TextVue,
        "boxed": BoxedVue
    },
    data() {
        return {
            headerText: "WHAT IS THIS?"
        }
    },
    methods: {
        changeTextFrom() {
            this.headerText = "DDEVS.RU"
        },
        changeTextTo() {
            this.headerText = "WHAT IS THIS?"
        }
    }
}
</script>

<style scoped>

.header {
    /* size */
    width: 60%;
    height: 60px;

    background-color: rgba(23, 23, 23, 0.725);

    /* centering items */
    justify-content: center;
    align-items: center;
    display: flex;

    /* centering header */
    margin-left: auto;
    margin-right: auto;

    border-radius: 0 0 10px 10px;

    z-index: 1000;
}

@media (max-width: 480px) {
  .header {
    width: 85%;
    flex-direction: column;
  }
}

@media (min-width: 481px) and (max-width: 768px) {
  .header {
    width: 85%;
    flex-direction: column;
  }
}

@media (min-width: 769px) and (max-width: 1024px) {
  .header {
    width: 70%;
    flex-direction: column;
  }
}

</style>