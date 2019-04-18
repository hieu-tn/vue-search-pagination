<template>
  <div>
    <div class="container">
      <h1>Integrate search and pagination into VueJS</h1>
      <div class="form-group">
        <label for="query">Enter query</label>
        <input type="text" class="form-control" id="query" placeholder="Enter your query" v-model="s" />
      </div>

      <div class="table-responsive">
        <table class="table table-striped table-hover table-bordered">
          <thead>
            <tr class="thead-dark">
              <th scope="col">tconst</th>
              <th scope="col">Title Type</th>
              <th scope="col">Original Title</th>
              <th scope="col">Runtime Minutes</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="(item, index) in displayedList" :key="index">
              <td>{{ item.tconst }}</td>
              <td>{{ item.titleType }}</td>
              <td>{{ item.originalTitle }}</td>
              <td>{{ item.runtimeMinutes }}</td>
            </tr>
          </tbody>
        </table>
      </div>

      <nav aria-label="Page navigation example">
        <ul class="pagination">
          <li class="page-item" :class="{ 'disabled': this.currentPage <= 0 }" @click="prevPage"><a class="page-link" href="#">Previous</a></li>
          <li class="page-item" :class="{ 'active': currentPage == page - 1 }" v-for="(page, index) in totalPages" :key="index" @click="moveToPage($event, page)"><a class="page-link" href="#">{{ page }}</a></li>
          <li class="page-item" :class="{ 'disabled': this.currentPage >= this.totalPages - 1 }" @click="nextPage"><a class="page-link" href="#">Next</a></li>
        </ul>
      </nav>
    </div>
  </div>
</template>

<script>
/* eslint-disable */
export default {
  name: 'Pagination',
  props: {
    list: {
      type: Array,
      default: function () {
        return []
      }
    },
  },
  data () {
    return {
      s: '',
      itemsPerPage: 5,
      currentPage: 0
    }
  },
  computed: {
    filteredList: function() {
      let resultList = []
      for (let item of this.list) {
        for (let property in item) {
          if (new RegExp(this.s.toLowerCase()).test(item[property])) {
            resultList.push(item)
            break
          }
        }
      }
      return resultList
    },
    displayedList: function() {
      return this.filteredList.slice(this.currentPage * this.itemsPerPage, (this.currentPage + 1) * this.itemsPerPage)
    },
    totalPages: function() {
      this.currentPage = 0
      return Math.ceil(this.filteredList.length / this.itemsPerPage)
    }
  },
  methods: {
    moveToPage: function(e, page) {
      e.preventDefault()
      if (0 <= page && page <= this.totalPages)
        this.currentPage = page - 1
    },
    prevPage: function(e) {
      e.preventDefault()
      if (this.currentPage > 0)
        this.currentPage--
    },
    nextPage: function(e) {
      e.preventDefault()
      if (this.currentPage < this.totalPages - 1)
        this.currentPage++
    }
  }
}
</script>

<style lang="scss" scoped>

</style>
