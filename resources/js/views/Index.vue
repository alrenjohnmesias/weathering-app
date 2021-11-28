<template>
  <div class="wrapper">
    <parallax class="page-header header-filter" :style="headerStyle">
      <div class="md-layout">
        <div class="md-layout-item">
          <div class="image-wrapper">
            <div class="brand">
              <h1>Japan Travel</h1>
              <h3>Tokyo | Yokohama | Kyoto | Osaka | Sapporo | Nagoya</h3>
            </div>
          </div>
        </div>
      </div>
    </parallax>
    <div class="main main-raised">
      <div class="section section-basic">
        <div class="container">
          <div class="title">
            <h2>Discover more...</h2>
          </div>
          <country-information></country-information>
        </div>
      </div>

        <div class="section section-basic">
        <div class="container">
          <div class="title">
            <h2>Discover more...</h2>
          </div>
          <home-carousel></home-carousel>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import CountryInformation from "./components/HomeCountryInfo";
import HomeCarousel from "./components/HomeCarouselsection";
import { LoginCard } from "../components";

export default {
  components: {
    CountryInformation,
    HomeCarousel
  },
  name: "index",
  bodyClass: "index-page",
  props: {
    image: {
      type: String,
      default: require("../../assets/img/japan_travel_bg.webp")
    },
    signup: {
      type: String,
      default: require("../../assets/img/city.jpg")
    },
    landing: {
      type: String,
      default: require("../../assets/img/landing.jpg")
    },
    profile: {
      type: String,
      default: require("../../assets/img/profile.jpg")
    }
  },
  data() {
    return {
      firstname: null,
      email: null,
      password: null,
      leafShow: false
    };
  },
  methods: {
    leafActive() {
      if (window.innerWidth < 768) {
        this.leafShow = false;
      } else {
        this.leafShow = true;
      }
    }
  },
  computed: {
    headerStyle() {
      return {
        backgroundImage: `url(${this.image})`
      };
    },
    signupImage() {
      return {
        backgroundImage: `url(${this.signup})`
      };
    }
  },
  mounted() {
    this.leafActive();
    window.addEventListener("resize", this.leafActive);
  },
  beforeDestroy() {
    window.removeEventListener("resize", this.leafActive);
  }
};
</script>
<style lang="scss">
.section-download {
  .md-button + .md-button {
    margin-left: 5px;
  }
}

@media all and (min-width: 991px) {
  .btn-container {
    display: flex;
  }
}
</style>
