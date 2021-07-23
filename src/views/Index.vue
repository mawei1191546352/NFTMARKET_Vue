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
            <div class="container">
              <div class="title">
                <h3>Search</h3>
              </div>
              <md-field class="md-form-group" slot="inputs">
                <md-icon>search</md-icon>
                <label>Search...</label>
                <md-input
                  v-model="searchtxt"
                  type="text"
                ></md-input>
              </md-field>
              <div class="title">
                <h3>Filter</h3>
              </div>
              <md-checkbox v-model="array" value="1">Mostly</md-checkbox>
              <md-checkbox v-model="array" value="2">Recently</md-checkbox>
              <md-checkbox v-model="array" value="3">Oldest</md-checkbox>
              <md-checkbox v-model="array" value="4">Sort</md-checkbox>
              <div class="action">
                <md-button class="md-round md-sm md-success md-lg">
                  Search & Filter
                </md-button>
              </div>
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
    },
    leaf4: {
      type: String,
      default: require("@/assets/img/leaf4.png")
    },
    leaf3: {
      type: String,
      default: require("@/assets/img/leaf3.png")
    },
    leaf2: {
      type: String,
      default: require("@/assets/img/leaf2.png")
    },
    leaf1: {
      type: String,
      default: require("@/assets/img/leaf1.png")
    },
  },
  data() {
    return {
      leafShow: false,
      searchtxt: "",
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
