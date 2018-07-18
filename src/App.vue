<template>
    <main class="main-content is-centered">
        <section class="content-wrapper">
            <Main></Main>
        </section>
    </main>
</template>

<script lang="ts">
    import {Component, Vue} from "vue-property-decorator";
    import Main from "./components/Main.vue";

    @Component({
        components: {
            Main
        }
    })

    export default class App extends Vue {

    }
</script>

<style lang="scss">

</style>
