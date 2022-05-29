<template>
  <div class="toptour">
    <div class="toptour-header">
      <h2 class="heading">Top Tour</h2>
      <p class="sub-heading">Keep calm &amp; travel on</p>
    </div>
    <div class="toptour-slide">
      <VueSlickCarousel v-bind="settings">
        <div
          class="toptour-slide-item"
          v-for="(item, index) in dataTopTour"
          :key="index"
        >
          <img :src="item.img" alt="" />
          <div class="item-detail d-flex flex-column justify-content-between">
            <span>{{ item.country }}</span>
            <div class="item-info">
              <h4 class="item-name">{{ item.country }}</h4>
              <p class="item-amount">{{ item.country }}</p>
            </div>
          </div>
        </div>
      </VueSlickCarousel>
    </div>
    <div class="toptour-list">
      <div class="toptour-list-item" v-for="(item, index) in dataTopTour_mb" :key="index">
        <img :src="item.img" alt="" />
        <div class="item-detail d-flex flex-column justify-content-between">
          <span>{{ item.country }}</span>
          <div class="item-info">
            <h4 class="item-name">{{ item.country }}</h4>
            <p class="item-amount">{{ item.country }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import VueSlickCarousel from "vue-slick-carousel";
import "vue-slick-carousel/dist/vue-slick-carousel.css";
// optional style for arrows & dots
import "vue-slick-carousel/dist/vue-slick-carousel-theme.css";
import toptour1 from "@/assets/img/toptour1.jpeg";
import toptour2 from "@/assets/img/toptour2.jpeg";
import toptour3 from "@/assets/img/toptour3.jpeg";

export default {
  name: "TopTour",
  data() {
    return {
      toptour1,
      toptour2,
      toptour3,
      settings: {
        accessibility: true,
        arrows: true,
        focusOnSelect: true,
        infinite: true,
        speed: 500,
        slidesToShow: 3,
        slidesToScroll: 1,
        touchThreshold: 3,
        touchMove: true,
        swipe: true,
        swipeToSlide: true,
        autoplay: true,
        autoplaySpeed: 2000,
      },
      dataTopTour: [
        {
          img: toptour1,
          country: "Japan",
          name: "Tokyo",
          amount: "10 Popular Places",
        },
        {
          img: toptour2,
          country: "Indonesia",
          name: "Bali",
          amount: "10 Popular Places",
        },
        {
          img: toptour3,
          country: "Spain",
          name: "Barcelona",
          amount: "10 Popular Places",
        },
        {
          img: toptour1,
          country: "Japan",
          name: "Tokyo",
          amount: "10 Popular Places",
        },
        {
          img: toptour2,
          country: "Indonesia",
          name: "Bali",
          amount: "10 Popular Places",
        },
        {
          img: toptour3,
          country: "Spain",
          name: "Barcelona",
          amount: "10 Popular Places",
        },
      ],
      dataTopTour_mb: [
        {
          img: toptour1,
          country: "Japan",
          name: "Tokyo",
          amount: "10 Popular Places",
        },
        {
          img: toptour2,
          country: "Indonesia",
          name: "Bali",
          amount: "10 Popular Places",
        },
        {
          img: toptour3,
          country: "Spain",
          name: "Barcelona",
          amount: "10 Popular Places",
        },]
    };
  },
  components: { VueSlickCarousel },
};
</script>

<style lang="scss" scoped>
.toptour {
  max-width: 1200px;
  margin: 40px auto 70px;
  @media (max-width: 450px) {
    margin: 10px auto 40px;
  }
  &-header {
    padding: 0 15px;
    margin-bottom: 40px;
    @media (max-width: 450px) {
      text-align: center;
      margin-bottom: 20px;
    }
    .heading {
      font-size: 48px;
      font-weight: 700;
      color: #23262f;
      line-height: 1.5;
      letter-spacing: -0.005em;
      margin-bottom: 12px;
    }
    .sub-heading {
      display: inline-block;
      font-size: 16px;
      font-weight: 400;
      font-family: "Poppins", sans-serif;
      color: #84878b;
      line-height: 1.5;
    }
  }
  &-slide {
    position: relative;
    padding: 0 16px;
    height: 500px;
    width: 100%;
    @media (max-width: 450px) {
      display: none;
    }
    &-item {
      position: relative;
      overflow: hidden;
      img {
        border-radius: 16px;
        width: 360px;
        height: 500px;
        background: linear-gradient(
          175.54deg,
          rgba(2, 0, 14, 0.13) 9.38%,
          rgba(42, 34, 101, 0) 47.26%,
          rgba(15, 11, 44, 0.6) 92.77%
        );
        object-fit: cover;
      }
      .item-detail {
        position: absolute;
        padding: 35px;
        bottom: 0;
        height: 100%;
        span {
          padding: 12px 28px;
          background: rgba(20, 20, 22, 0.2);
          backdrop-filter: blur(4px);
          border-radius: 50px;
          font-size: 20px;
          font-weight: bold;
          color: #e9ebf3;
          text-align: center;
        }
        .item-info {
          color: #ffffff;
          line-height: 1.5;
          .item-name {
            font-weight: 700;
            font-size: 34px;
          }
          .item-amount {
            margin-bottom: unset;
          }
        }
      }
    }
  }
  &-list {
    display: none;
    position: relative;
    padding: 0 20px;
    height: 100%;
    width: 100%;
    @media (max-width: 450px) {
      display: block;
    }
    &-item {
      position: relative;
      overflow: hidden;
      margin-top: 20px;
      img {
        border-radius: 16px;
        width: 100%;
        height: 500px;
        background: linear-gradient(
          175.54deg,
          rgba(2, 0, 14, 0.13) 9.38%,
          rgba(42, 34, 101, 0) 47.26%,
          rgba(15, 11, 44, 0.6) 92.77%
        );
        object-fit: cover;
      }
      .item-detail {
        position: absolute;
        padding: 35px;
        bottom: 0;
        height: 100%;
        span {
          padding: 12px 28px;
          background: rgba(20, 20, 22, 0.2);
          backdrop-filter: blur(4px);
          border-radius: 50px;
          font-size: 20px;
          font-weight: bold;
          color: #e9ebf3;
          text-align: center;
        }
        .item-info {
          color: #ffffff;
          line-height: 1.5;
          .item-name {
            font-weight: 700;
            font-size: 34px;
          }
          .item-amount {
            margin-bottom: unset;
          }
        }
      }
    }
  }
}
</style>