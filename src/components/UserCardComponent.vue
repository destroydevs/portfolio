<template>
  <bc>

    <div class="profile">
        <img class="icon" src="https://avatars.githubusercontent.com/u/108214550?v=4" alt="">
        <linkv link="https://github.com/destroydevs">@destroydevs</linkv>
        <sc-text>Java & Rust Developer</sc-text>

    </div>

    <div class="text-in-profile">
        <m-text class="text">
            I'm a Java Developer with about 4 years of experience.
I enjoy developing plugins for Minecraft and working on various backend projects.
        </m-text>
    </div>

    <div class="projects">
        <project projectLink="https://github.com/destroydevs/primeseller" img="https://www.spigotmc.org/data/resource_icons/108/108813.jpg?1679683984" linkName="PrimeSeller" disc="Written on Java"></project>
        <project projectLink="https://github.com/destroydevs/TikFetchBot" img="/rustlang.jpeg" linkName="TikFetchBot" disc="Written on Rust"></project>
        <project projectLink="https://github.com/reptide-vpn" img="/Reptide-Ava-2.png" linkName="Reptide" disc="Written on Rust"></project>
    </div>

  </bc>
</template>

<script>
import BoxedComponentVue from './items/BoxedComponent.vue'
import LinkVue from './items/Link.vue'
import SecondTextVue from './items/SecondText.vue'
import TextVue from './items/Text.vue'
import ProjectComponentVue from './ProjectComponent.vue'

export default {
    components: {
        "m-text": TextVue,
        "sc-text": SecondTextVue,
        "project": ProjectComponentVue,
        "linkv": LinkVue,
        "bc": BoxedComponentVue
    },
    data() {
        return {
            loading: true
        }
    },
    methods: {
        async preload(src) {
            try {
                await fetch(src);
                this.loading = false;
            } catch (e) {
                // ignore it
            }
        }
    }
}

</script>

<style scoped>

.profile {
    width: 25%;
    height: 100%;

    /* justify-content: center; */
    align-items: center;

    display: flex;

    flex-direction: column;
}

.profile .icon {
    margin-top: 10px;
    border-radius: 10px;

    width: 115px;
    height: 115px;
}

.text-in-profile {
    width: 40%;
    height: 100%;

    text-align: left;

    border-left: 3px #2b2a34 solid;
}

.text-in-profile .text {
    margin: 8px;
}

.projects {
    width: 35%;
    height: 100%;

    justify-content: center;
    align-items: center;


    display: flex;

    flex-direction: column;

    border-left: 3px #2b2a34 solid;
}

@media (max-width: 480px) {
  .text-in-profile {
    width: 70%;
  }
  .projects {
    width: 70%;
  }
  .profile {
    width: 70%;
  }

}

@media (min-width: 481px) and (max-width: 768px) {
  .text-in-profile {
    width: 70%;
  }
  .projects {
    width: 70%;
  }
  .profile {
    width: 70%;
  }
}

</style>