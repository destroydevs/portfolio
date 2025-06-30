<template>
  <div class="project" @click="redirect(projectLink)">
    <div class="icon">
        <imagev class="image" :imgLink="img"></imagev>
    </div>
    <div class="disc">
        <textv :link="linkUrl">{{ linkName }}</textv>
        <sc-text>{{ disc }}</sc-text>
    </div>
  </div>
</template>

<script>
import ImageVue from './items/Image.vue'
import SecondTextVue from './items/SecondText.vue'
import TextVue from './items/Text.vue'
export default {
    components: {
        "textv": TextVue,
        "sc-text": SecondTextVue,
        "imagev": ImageVue
    },
    methods: {
        redirect(to) {
            window.location.href = to;
        }
    },
    props: {
        projectLink: {
            type: String,
            default: "https://google.com"
        },
        img: String,
        linkName: {
            type: String,
            default: "Not Found"
        },
        linkUrl: String,
        disc: {
            type: String,
            default: "Not Found"
        }


    }
}
</script>

<style scoped>

.icon {
    width: 30%;
    height: 100%;

    justify-content: center;
    align-items: center;

    display: flex;
}

.image {
    width: 90%;
    height: 90%;

    border-radius: 5px;
}

.disc {
    width: 80%;
    height: 100%;

    display: flex;
    flex-direction: column;

    margin: 6px;
}

.project {

    width: 200px;
    height: 55px;

    background-color: rgba(23, 23, 23, 0.733);

    border-radius: 10px 0 0 10px;

    box-shadow: 3px 3px 0 rgb(21, 21, 21);

    display: flex;

    flex-direction: row-reverse;

    margin: 5px;

    cursor: pointer;

}

.project:hover {
    background-color: rgb(0, 0, 0);

    box-shadow: 3px 3px 0 rgb(0, 0, 0);
}
</style>