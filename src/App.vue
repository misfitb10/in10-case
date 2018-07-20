<template>
    <main class="main-content is-centered">
        <Main></Main>
    </main>
</template>

<script lang="ts">
    import {Component, Vue} from "vue-property-decorator";
    import Main from "./components/Main.vue";

    @Component({
        components: {Main}
    })

    export default class App extends Vue {

    }
</script>

<style lang="scss">
    @import "./scss/base/__base";
    @import "./scss/components/_main-content";
</style>
