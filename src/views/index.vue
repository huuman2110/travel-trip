<template>
  <div>
    <Header />
    <Banner/>
    <BestPlace/>
    <FeaturedDestination/>
    <TopTour/>
    <Explore/>
    <TrendCity/>
    <TravelPassion/>
    <Footer/>   
    </div>
</template>

<script>
import Header from "../components/Header/index.vue";
import Footer from "../components/Footer/index.vue";
import Banner from "../components/Body/Banner.vue";
import BestPlace from "../components/Body/BestPlace.vue";
import FeaturedDestination from "../components/Body/FeaturedDestination.vue";
import TopTour from "../components/Body/TopTour.vue";
import Explore from "../components/Body/Explore.vue";
import TrendCity from "../components/Body/TrendCity.vue"
import TravelPassion from "../components/Body/TravelPassion.vue"
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Main",
  components: {
    Header,
    Footer,
    Banner,
    BestPlace,
    FeaturedDestination,
    TopTour,
    Explore,
    TrendCity,
    TravelPassion,
  },
};
</script>

<style>
</style>