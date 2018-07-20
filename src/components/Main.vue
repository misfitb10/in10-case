<template>
    <section class="content-wrapper">
        <Featured></Featured>
        <Activities></Activities>
    </section>
</template>

<script lang="ts">
    import { Component, Vue } from "vue-property-decorator";
    import Featured from "./featured/Featured.vue";
    import Activities from "./activities/Activities.vue";

    @Component({
        components: {Activities, Featured}
    })

    export default class Main extends Vue {

    }
</script>

<style scoped lang="scss">

</style>