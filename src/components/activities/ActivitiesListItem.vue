<template>
    <li class="activities__list-item">
        <div class="activities__secondary-content">
            <!-- TODO: And maybe make it with an API call with different screens (s, m, l) and 'retina' -->
            <img class="activities__image"
                 alt="Vaste collectie"
                 src="/assets/images/introductiecursus-gek-van-surrealisme.png"/>
        </div>

        <div class="activities__primary-content">
            <div class="activities__date-and-time" v-if="article.date || article.time">
                <span class="activities__date text--date" v-if="article.date">{{article.date}}</span>
                <span class="activities__time" v-if="article.time">{{article.time}}</span>
            </div>

            <h1 class="activities__title" v-if="article.title">{{article.title}}</h1>
            <h2 class="activities__subtitle" v-if="article.subtitle">{{article.subtitle}}</h2>

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
</template>

<script lang="ts">
    export default {
        props: ['article']
    }
</script>

<style scoped lang="scss">
    @import "../../scss/base/__base";
    @import "../../scss/components/_activities";
</style>
