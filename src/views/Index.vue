<template>
  <div class="wrapper">
    <parallax class="page-header header-filter" :style="headerStyle">
      <div class="md-layout">
        <div class="md-layout-item">
          <div class="image-wrapper">
            <div class="brand">
              <h1>NFT Market Place</h1>
              <h3>This is NFT market place landing page</h3>
            </div>
          </div>
        </div>
      </div>
    </parallax>
    <div class="main main-raised">
      <div class="section">
        <div class="md-layout md-gutter market-layout">
          <div class="md-layout-item md-size-100">
            <div class="title container">
              <h1>NFT Market Items</h1>
            </div>
          </div>
          <div class="md-layout-item md-size-20">
            <div class="title">
              <h3>Search and Filter</h3>
            </div>
          </div>
          <div class="md-layout-item md-size-80">
            <market-list></market-list>
          </div>
          
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import MarketList from "./marketcomponent/MarketList";
export default {
  components: {
    MarketList
  },
  name: "index",
  bodyClass: "index-page",
  props: {
    image: {
      type: String,
      default: require("@/assets/img/vue-mk-header.jpg")
    }
  },
  computed: {
    headerStyle() {
      return {
        backgroundImage: `url(${this.image})`
      };
    }
  },
  mounted() {
    // this.leafActive();
    window.addEventListener("resize", this.leafActive);
  }
};
</script>

<style lang="scss">
.section-download {
  .md-button + .md-button {
    margin-left: 5px;
  }
}

.market-layout {
  margin: 0 !important;
}


// @media all and (min-width: 991px) {
//   .btn-container {
//     display: flex;
//   }
// }
</style>
