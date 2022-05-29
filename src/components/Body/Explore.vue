<template>
  <div class="explore">
    <div class="explore-header">
      <h2 class="heading">Explore The World</h2>
      <p class="sub-heading">10,788 beautiful places to go</p>
    </div>
    <div class="explore-slide">
      <VueSlickCarousel v-bind="settings">
        <div
          class="explore-slide-item"
          v-for="(item, index) in dataExplore"
          :key="index"
        >
          <img :src="item.img" alt="" />
          <div class="item-info">
            <div class="item-point">
              <font-awesome-icon icon="fas fa-star" />
              <span>{{ item.point }}</span
              >({{ item.review }})
            </div>
            <div class="item-name">
              {{ item.name }}
              <span>${{ item.price }}</span>
            </div>
            <div class="item-distance">{{ item.disable }}</div>
            <div class="item-location">
              <font-awesome-icon icon="fas fa-map-marker-alt" />
              {{ item.location }}
            </div>
            <div class="item-room">
              <font-awesome-icon icon="far fa-hospital" />
              Rooms available: {{ item.room }}
            </div>
          </div>
        </div>
        <template #prevArrow="arrowOption">
          <div class="custom-arrow">
            {{ arrowOption.currentSlide }}/{{ arrowOption.slideCount }}
          </div>
        </template>
        <template #nextArrow="arrowOption">
          <div class="custom-arrow">
            {{ arrowOption.currentSlide }}/{{ arrowOption.slideCount }}
          </div>
        </template>
      </VueSlickCarousel>
    </div>
    <div class="explore-list">
      <div
        class="explore-list-item"
        v-for="(item, index) in dataExplore"
        :key="index"
      >
        <img :src="item.img" alt="" />
        <div class="item-info">
          <div class="item-point">
            <font-awesome-icon icon="fas fa-star" />
            <span>{{ item.point }}</span
            >({{ item.review }})
          </div>
          <div class="item-name">
            {{ item.name }}
            <span>${{ item.price }}</span>
          </div>
          <div class="item-distance">{{ item.disable }}</div>
          <div class="item-location">
            <font-awesome-icon icon="fas fa-map-marker-alt" />
            {{ item.location }}
          </div>
          <div class="item-room">
            <font-awesome-icon icon="far fa-hospital" />
            Rooms available: {{ item.room }}
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
import explore1 from "@/assets/img/toptour1.jpg";
import explore2 from "@/assets/img/trendcity6.jpg";
import explore3 from "@/assets/img/trendcity2.jpg";
import explore4 from "@/assets/img/trendcity4.jpg";

export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Explore",
  data() {
    return {
      explore1,
      explore2,
      explore3,
      explore4,
      settings: {
        accessibility: true,
        arrows: true,
        focusOnSelect: true,
        infinite: true,
        speed: 500,
        slidesToShow: 4,
        slidesToScroll: 1,
        touchThreshold: 3,
        touchMove: true,
        swipe: true,
        swipeToSlide: true,
        autoplay: true,
        autoplaySpeed: 2000,
      },
      dataExplore: [
        {
          img: explore1,
          point: "4.91",
          review: "147",
          name: "Comfort Space",
          price: "210",
          distance: "1.2 km to Town Center",
          location: "Turkey, Mamaris",
          room: "375",
        },
        {
          img: explore2,
          point: "4.91",
          review: "147",
          name: "Comfort Space",
          price: "210",
          distance: "1.2 km to Town Center",
          location: "Turkey, Mamaris",
          room: "375",
        },
        {
          img: explore3,
          point: "4.91",
          review: "147",
          name: "Comfort Space",
          price: "210",
          distance: "1.2 km to Town Center",
          location: "Turkey, Mamaris",
          room: "375",
        },
        {
          img: explore4,
          point: "4.91",
          review: "147",
          name: "Comfort Space",
          price: "210",
          distance: "1.2 km to Town Center",
          location: "Turkey, Mamaris",
          room: "375",
        },
        {
          img: explore1,
          point: "4.91",
          review: "147",
          name: "Comfort Space",
          price: "210",
          distance: "1.2 km to Town Center",
          location: "Turkey, Mamaris",
          room: "375",
        },
        {
          img: explore2,
          point: "4.91",
          review: "147",
          name: "Comfort Space",
          price: "210",
          distance: "1.2 km to Town Center",
          location: "Turkey, Mamaris",
          room: "375",
        },
        {
          img: explore3,
          point: "4.91",
          review: "147",
          name: "Comfort Space",
          price: "210",
          distance: "1.2 km to Town Center",
          location: "Turkey, Mamaris",
          room: "375",
        },
        {
          img: explore4,
          point: "4.91",
          review: "147",
          name: "Comfort Space",
          price: "210",
          distance: "1.2 km to Town Center",
          location: "Turkey, Mamaris",
          room: "375",
        },
      ],
    };
  },
  components: { VueSlickCarousel },
};
</script>

<style lang="scss" scoped>
.explore {
  max-width: 1200px;
  margin: 40px auto 70px;
  @media (max-width: 450px) {
    margin: 40px auto 30px;
  }
  &-header {
    padding: 0 15px;
    margin-bottom: 40px;
    @media (max-width: 450px) {
      text-align: center;
    }
    .heading {
      font-size: 48px;
      font-weight: 700;
      color: #23262f;
      line-height: 1.5;
      letter-spacing: -0.005em;
      margin-bottom: 12px;
      @media (max-width: 450px) {
        font-size: 30px;
      }
    }
    .sub-heading {
      display: inline-block;
      font-size: 16px;
      font-weight: 400;
      font-family: "Poppins", sans-serif;
      color: #84878b;
      line-height: 1.5;
      @media (max-width: 450px) {
        font-size: 14px;
      }
    }
  }
  &-slide {
    position: relative;
    padding: 0 15px;
    height: 362px;
    width: 100%;
    @media (max-width: 450px) {
      display: none;
    }
    .slick-prev {
      background: #f4f5f6 !important;
      border: 1px solid #e6e8ec !important;
      color: #b1b5c4 !important;
    }
    // .slick-arrow {
    //   height: 36px;
    //   width: 36px;
    // }
    .slick-next {
      // display: flex;
      // justify-content: center;
      // align-items: center;
      border-radius: 100%;
      background: #e6e8ec !important;
      border: 1px solid #e6e8ec !important;
    }
  }
  &-list {
    position: relative;
    padding: 0 20px;
    height: 362px;
    width: 100%;
    display: none;
    @media (max-width: 450px) {
      display: flex;
      flex-wrap: nowrap;
      overflow-x: auto;
      &::-webkit-scrollbar {
        display: none;
        -ms-overflow-style: none; /* IE and Edge */
        scrollbar-width: none; /* Firefox */
      }
    }
  }
  &-slide,
  &-list {
    &-item {
      position: relative;
      height: 362px;
      width: calc(100% - 23px) !important;
      padding: 14px;
      background-color: #ffffff;
      border: 1px solid #e7ecf3;
      border-radius: 20px;
      @media (max-width: 450px) {
        flex: 1 0 270px;
        margin-right: 20px;
        &:last-child {
          margin-right: 0;
        }
      }
      img {
        background: linear-gradient(
          175.54deg,
          rgba(2, 0, 14, 0.13) 9.38%,
          rgba(42, 34, 101, 0) 47.26%,
          rgba(15, 11, 44, 0.6) 92.77%
        );
        border-radius: 16px;
        transform: matrix(-1, 0, 0, 1, 0, 0);
        height: 155px;
        width: 100%;
        object-fit: cover;
      }
      .item-info {
        margin-top: 20px;
        color: #84878b;
        .item-point {
          font-size: 14px;
          margin-bottom: 12px;
          svg {
            color: yellow;
          }
          span {
            color: #3b3e44;
            font-weight: 600;
            margin-left: 8px;
            margin-right: 3px;
          }
        }
        .item-name {
          font-size: 20px;
          font-weight: bold;
          color: #3b3e44;
          margin-bottom: 10px;
          span {
            float: right;
            font-size: 18px;
            background: rgba(49, 107, 255, 0.2);
            border-radius: 6px;
            color: #316bff;
            padding: 3px 10px;
            line-height: normal;
          }
        }
        .item-distance {
          font-size: 14px;
          font-weight: 500;
          margin-bottom: 14px;
        }
        .item-location {
          margin-bottom: 8px;
          font-size: 14px;
          svg {
            height: 18px;
            width: 14px;
            margin-right: 12px;
          }
        }
        .item-room {
          font-size: 14px;
          svg {
            height: 18px;
            width: 14px;
            margin-right: 10px;
          }
        }
      }
    }
  }
}
</style>