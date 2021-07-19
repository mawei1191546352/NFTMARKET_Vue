<template>
  <div class="wrapper">
    <div  class="md-layout md-gutter md-alignment-center">
      <div
        class="md-layout-item md-medium-size-33 md-small-size-50 md-xsmall-size-100"
        v-for='index in 20' :key='index'
      >
        <md-card>
        <md-card-media-cover>
          <md-card-media md-ratio="4:5">
            <img
              src="https://lh3.googleusercontent.com/RZ9t1F2tmKCcuyJxcUj111ORWrvz1fwEkglzGSgBaTCF0iac0HGa1EMq5Ts8wxJg9NVAyUGW3ZT9Mgg2btmeLOXNNA29eFsoOcvl=s288"
              alt="nftToken"
            />
          </md-card-media>

          <md-card-area>
            <md-card-header>
              <span class="md-title">Without text background</span>
              <span class="md-subhead">I bet you can't read this</span>
            </md-card-header>

          </md-card-area>
        </md-card-media-cover>
      </md-card>
      </div>
    </div>
    <div class="container">
      <pagination
        class="pagination-info"
        v-model="infoPagination"
        with-text
        :page-count="totalPages"
        @nextPage="nextpage()"
        >
      </pagination>
    </div>
  </div>
</template>

<script>
import { Pagination } from "@/components";
export default {
  name: "market-list",
  components: {
    Pagination
  },
  data() {
    return {
      defaultPagination: 3,
      infoPagination: 3,
      totalPages: 10,
    }
  },
  methods: {
    nextpage(){
      console.log(this.infoPagination);
    }
  }
};
</script>

<style scoped>
 .md-layout {
  background-color: white;
  min-height: 100px;
  border-color: black;
  align-items: center;
  justify-content: center;
  /*border-style: dotted;*/
  border-width: 1px;
  padding: 8px;
}

.md-layout-item{
  margin-bottom: 30px;
}

 .md-card {
    width: 300px;
    margin: 4px;
    display: inline-block;
    vertical-align: top;
  }
  .md-card-header {
    padding: 20px !important;
    margin: 0 !important;
    background: #00000044 !important;
    margin-bottom: 0px !important;
  }
  .pagination-info{
    margin: auto;
  }
</style>
