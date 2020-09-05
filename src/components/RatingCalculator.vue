<template>
    <div>
        <div>Top Rated Movies Among Friends</div>
        <div>Insert user ID:</div>
        <label>
            <input v-model="input"/>
        </label>
        <div v-if="topRatedList.length">
            <ol>
                <li v-for="movie in topRatedList" :key="movie">
                    {{movie}}
                </li>
            </ol>
        </div>
        <div v-else>
            No result found
        </div>
    </div>
</template>

<script>
    import MoviesAnalyzer from "@/analyzers/MoviesAnalyzer";
    export default {
        name: "RatingCalculator",
        data() {
            return {
                input: ''
            }
        },
        computed: {
            topRatedList: function () {
                return MoviesAnalyzer.topRatedMoviesAmongFriends(parseInt(this.input))
            }
        }
    }
</script>

<style scoped>

</style>