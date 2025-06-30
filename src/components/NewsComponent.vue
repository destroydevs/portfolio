<template>
<bc>
    <div class="loading" v-if="loading">
        <textv>Loading...</textv>
    </div>

    <div class="loaded" v-else>
        <textv class="newscard">News</textv>
        <div class="post" v-for="post in posts" :key="post.date">

            <boxed class="boxed">
                <textv class="title">{{ post.title }}</textv>

                <sc-text class="date"> {{ post.date }} </sc-text>
            </boxed>

            <div class="desc">
                <sc-text v-for="(d, index) in post.description" :key="index">{{ d }}</sc-text>
            </div>

        </div>

    </div>
</bc>
</template>

<script>
import BoxedVue from './items/Boxed.vue';
import BoxedComponentVue from './items/BoxedComponent.vue';
import SecondTextVue from './items/SecondText.vue';
import TextVue from './items/Text.vue';
export default {
    components: {
        "sc-text": SecondTextVue,
        "textv": TextVue,
        "boxed": BoxedVue,
        "bc": BoxedComponentVue
    },
    mounted() {
        this.loadNews();
    },
    methods: {
        async loadNews() {

            let response = await fetch("http://185.103.103.120:8000/posts");

            if (response.ok) {
                this.posts = await response.json();
            }

            console.log(this.posts);

            this.loading = false;
        }
    },
    data() {
        return {
            loading: true,
            posts: []
        }
    }
}
</script>

<style scoped>

.loading {
    z-index: 1000;
    background-color: rgb(79, 79, 79, 0.725);
    width: 90%;
    height: 100%;

    padding: 50px;
    margin: 10px 0 10px 0;

    border-radius: 12px;

    display: flex;
    justify-content: center;
    align-items: center;

    background: linear-gradient(45deg, #3f3f3f, #2c2c2c, #585858, #181818);
    background-size: 300% 300%;
    animation: gradientFlow 2s ease infinite;
}

.loaded {
    width: 90%;
    height: 100%;

    display: flex;
    justify-content: center;
    align-items: center;

    flex-direction: column;
}

.post {
    background-color: rgba(23, 23, 23, 0.893);
    width: 95%;
    height: 95%;

    margin: 10px 0 10px 0;
    padding: 15px;

    border-radius: 12px;

    display: flex;

    flex-direction: column;

    align-items: center;
}

.desc {
    margin-top: 15px;
}

.date {
    font-size: 10px;
}

.boxed {
    width: 50%;
    height: 50%;
    display: flex;

    flex-direction: column;

    align-items: center;

    text-align: center;
}
.newscard {
    font-size: 24px;
    margin: 10px;
}
</style>
