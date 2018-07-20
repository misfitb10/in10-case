<template>
    <!--
        Is there something like `Fragment` in vue?
        Because now, we have to use an empty div in order to contain the two components.
    -->
    <div>
        <Featured></Featured>
        <Activities></Activities>
    </div>
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