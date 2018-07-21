<template>
    <div class="activities__wrapper">
        <section class="activities">
            <h1 class="activities__head-title" v-if="activitiesHeading">{{activitiesHeading}}</h1>

            <p v-if="error">
                Sorry, op dit moment is er een fout opgetreden met dit onderdeel van de website. <br/>
                Voor developers: staat CORS aan?
            </p>

            <ol class="activities__list" v-if="articles.length">
                <li class="activities__list-item is-main" v-for="article in articles">
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

                <!--<li class="activities__list-item">-->
                    <!--<div class="activities__secondary-content">-->
                        <!--<div class="activities__date-and-time">-->
                            <!--<span class="activities__date text&#45;&#45;date">t/m 5 maart 2017</span>-->
                            <!--<span class="activities__time">13.00 - 14.30 uur</span>-->
                        <!--</div>-->
                    <!--</div>-->

                    <!--<div class="activities__primary-content">-->
                        <!--<div class="activities__info">-->
                            <!--<h1 class="activities__title">Kleinkunstig</h1>-->
                            <!--<h2 class="activities__subtitle">Kijk en doeboekje</h2>-->
                            <!--<p class="activities__category">Kinderen en families</p>-->
                        <!--</div>-->
                    <!--</div>-->
                <!--</li>-->
            </ol>

            <a href="#" class="activities__show-all-link" v-if="showAllActivitiesButton">{{showAllActivitiesButton}}</a>
        </section>
    </div>
</template>

<script lang="ts">
    import axios from 'axios'

    export default {
        data: function() {
            return  {
                articles: [],
                showAllActivitiesButton: '',
                activitiesHeading: 'Activities',
                error: false
            }
        },
        mounted() {
            axios
                .get('https://www.bilal.wtf/projects/in10-case/api/api.json')
                .then(response => {
                    this.articles = response.data.activities.articles;
                    this.showAllActivitiesButton = response.data.activities.moreButton;
                })
                .catch(error => {
                    console.log(error);
                    this.error = true
                })
        }
    }
</script>

<style scoped lang="scss">
    @import "../../scss/base/__base";
    @import "../../scss/components/_activities";
</style>
