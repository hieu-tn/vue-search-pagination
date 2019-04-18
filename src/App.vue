<template>
  <div id="app">
    <pagination :list="imdb">
    </pagination>
  </div>
</template>

<script>
import Pagination from './components/Pagination.vue'

export default {
  name: 'app',
  components: {
    Pagination
  },
  data () {
    return {
      imdb: [
        {
          tconst: "tt10008984",
          titleType: "short",
          originalTitle: "Laisse Yves tranquille",
          runtimeMinutes: "\\N"
        },
        {
          tconst: "tt10061540",
          titleType: "short",
          originalTitle: "Very Important Message",
          runtimeMinutes: "\\N"
        },
        {
          tconst: "tt10075980",
          titleType: "short",
          originalTitle: "Les visiteurs",
          runtimeMinutes: "\\N"
        },
        {
          tconst: "tt10088286",
          titleType: "short",
          originalTitle: "Le confessionnal",
          runtimeMinutes: "\\N"
        },
        {
          tconst: "tt10124684",
          titleType: "tvEpisode",
          originalTitle: "Une chance sur deux",
          runtimeMinutes: "\\N"
        },
        {
          tconst: "tt10163196",
          titleType: "tvSeries",
          originalTitle: "The Benza",
          runtimeMinutes: "\\N"
        },
        {
          tconst: "tt9129986",
          titleType: "short",
          originalTitle: "Molly",
          runtimeMinutes: "10"
        },
        {
          tconst: "tt9630260",
          titleType: "tvEpisode",
          originalTitle: "No Sleep Sleepover",
          runtimeMinutes: "\\N"
        },
        {
          tconst: "tt9630288",
          titleType: "tvEpisode",
          originalTitle: "Camp Unikitty",
          runtimeMinutes: "11"
        },
        {
          tconst: "tt9659750",
          titleType: "tvEpisode",
          originalTitle: "Unfairgrounds Part 1",
          runtimeMinutes: "\\N"
        },
        {
          tconst: "tt9659756",
          titleType: "tvEpisode",
          originalTitle: "Unfairgrounds Part 2",
          runtimeMinutes: "\\N"
        },
        {
          tconst: "tt9659762",
          titleType: "tvEpisode",
          originalTitle: "Hawkodile Sensei",
          runtimeMinutes: "11"
        },
        {
          tconst: "tt9659798",
          titleType: "tvEpisode",
          originalTitle: "Beep",
          runtimeMinutes: "\\N"
        },
        {
          tconst: "tt9659820",
          titleType: "tvEpisode",
          originalTitle: "Safety First",
          runtimeMinutes: "\\N"
        },
        {
          tconst: "tt9805804",
          titleType: "tvMovie",
          originalTitle: "Potpisani 08 - Treger",
          runtimeMinutes: "57"
        }
      ]
    }
  }
}
</script>

<style>
@import "~bootstrap/dist/css/bootstrap.min.css";
#app {
  margin-top: 60px;
}
</style>
