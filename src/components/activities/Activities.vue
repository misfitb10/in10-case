<template>
    <div class="activities__wrapper">
        <section class="activities">
            <h1 class="activities__head-title">Activiteiten</h1>

            <ol class="activities__list">
                <li class="activities__list-item is-main">
                    <div class="activities__secondary-content">
                        <img class="activities__image" alt="Vaste collectie"
                             src="/assets/images/introductiecursus-gek-van-surrealisme.png"/>
                    </div>

                    <div class="activities__primary-content">
                        <div class="activities__date-and-time">
                            <span class="activities__date text--date">24 februari 2017</span>
                            <span class="activities__time">13.00 - 14.30 uur</span>
                        </div>

                        <h1 class="activities__title">Introductiecursus Gek van surrealisme</h1>
                        <h2 class="activities__subtitle">Grafiek van Max Klinker</h2>

                        <table class="activities__table-courses">
                            <tbody>
                            <tr>
                                <td class="activities__table-courses-subject">Cursussen</td>
                                <td>&euro; 75,-</td>
                            </tr>
                            </tbody>
                        </table>
                    </div>
                </li>

                <li class="activities__list-item">
                    <div class="activities__secondary-content">
                        <div class="activities__date-and-time">
                            <span class="activities__date text--date">t/m 5 maart 2017</span>
                            <span class="activities__time">13.00 - 14.30 uur</span>
                        </div>
                    </div>

                    <div class="activities__primary-content">
                        <div class="activities__info">
                            <h1 class="activities__title">Kleinkunstig</h1>
                            <h2 class="activities__subtitle">Kijk en doeboekje</h2>
                            <p class="activities__category">Kinderen en families</p>
                        </div>
                    </div>
                </li>
            </ol>

            <a href="#" class="activities__show-all-link">Bekijk alle activiteiten</a>
        </section>
    </div>
</template>

<script lang="ts">
    import {Component, Vue} from "vue-property-decorator";

    @Component
    export default class Activities extends Vue {

    }
</script>

<style scoped lang="scss">

</style>
