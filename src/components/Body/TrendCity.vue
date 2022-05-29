<template>
  <div class="trendcity">
    <div class="trendcity-container">
      <div class="trendcity-header">
        <h2 class="heading">Trending cites</h2>
        <p class="sub-heading">The most searched for cities on TripGuide</p>
      </div>
      <b-container class="trendcity-list">
        <b-row>
          <b-col
            cols="12"
            lg="6"
            v-for="(item, index) in dataTrendcity"
            :key="index"
          >
            <div class="trendcity-list-item">
              <div class="item-info d-flex justify-content-left">
                <img :src="item.img" alt="" />
                <div
                  class="item-detail d-flex flex-column justify-content-between"
                >
                  <p class="item-name">{{ item.name }}</p>
                  <div class="item-point">
                    <font-awesome-icon icon="fas fa-star"></font-awesome-icon>
                    <span>{{ item.point }}</span
                    >({{ item.review }})
                  </div>
                  <div class="item-price">
                    ${{ item.price }}<span>/night</span>
                  </div>
                  <button class="item-booking">Book Now</button>
                </div>
              </div>
            </div>
          </b-col>
        </b-row>
      </b-container>
    </div>
  </div>
</template>

<script>
import trendcity1 from "@/assets/img/trendcity1.jpg";
import trendcity2 from "@/assets/img/trendcity2.jpg";
import trendcity3 from "@/assets/img/trendcity3.jpg";
import trendcity4 from "@/assets/img/trendcity4.jpg";
import trendcity5 from "@/assets/img/trendcity5.jpg";
import trendcity6 from "@/assets/img/trendcity6.jpg";
export default {
  name: "TrendCity",
  data() {
    return {
      trendcity1,
      trendcity2,
      trendcity3,
      trendcity4,
      trendcity5,
      trendcity6,
      dataTrendcity: [
        {
          img: trendcity1,
          name: "Manila",
          point: "4.91",
          review: "147",
          price: "250.00",
        },
        {
          img: trendcity2,
          name: "San Francisco",
          point: "4.91",
          review: "147",
          price: "250.00",
        },
        {
          img: trendcity3,
          name: "Frankfurt main",
          point: "4.91",
          review: "147",
          price: "250.00",
        },
        {
          img: trendcity4,
          name: "Washington",
          point: "4.91",
          review: "147",
          price: "250.00",
        },
        {
          img: trendcity5,
          name: "Stockholm",
          point: "4.91",
          review: "147",
          price: "250.00",
        },
        {
          img: trendcity6,
          name: "Seattle",
          point: "4.91",
          review: "147",
          price: "250.00",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.trendcity {
  background: #f5f5f5;
  &-container {
    max-width: 1200px;
    margin: 0 auto;
    padding-bottom: 25px;
    @media (max-width: 450px) {
      padding-bottom: 5px;
    }
    .trendcity-header {
      padding: 60px 15px 0;
      margin-bottom: 40px;
      text-align: center;
      @media (max-width: 450px) {
        padding: 15px 20px 0;
        margin-bottom: 30px;
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
        font-size: 24px;
        font-weight: 400;
        font-family: "Poppins", sans-serif;
        color: #84878b;
        line-height: 1.5;
        @media (max-width: 450px) {
          font-size: 14px;
        }
      }
    }
    .trendcity-list {
      @media (max-width: 450px) {
        padding: 0 20px;
      }
      .trendcity-list-item {
        .item-info {
          height: 216px;
          background: #ffffff;
          border-radius: 20px;
          padding: 24px;
          margin-bottom: 35px;
          @media (max-width: 450px) {
            padding: 16px;
            margin-bottom: 20px;
          }
          img {
            width: 160px;
            height: 168px;
            border-radius: 15px;
            object-fit: cover;
            margin-right: 30px;
            @media (max-width: 450px) {
              height: 184px;
              margin-right: 20px;
            }
          }
          .item-detail {
            word-break: break-all;
            white-space: nowrap;
            word-wrap: break-word;
            text-overflow: ellipsis;
            overflow: hidden;
            .item-name {
              margin-bottom: unset;
              font-size: 24px;
              font-weight: 700;
            }
            .item-point {
              font-size: 16px;
              color: #84878b;
              svg {
                color: yellow;
              }
              span {
                color: #3b3e44;
                font-weight: 500;
                margin-left: 8px;
                margin-left: 3px;
              }
            }
            .item-price {
              font-size: 25px;
              font-family: "Poppins", sans-serif;
              color: #3b3e44;
              font-weight: 600;
              @media (max-width: 450px) {
                font-size: 18px;
              }
              span {
                font-size: 16px;
                font-weight: 500;
                color: #84878b;
              }
            }
            button {
              background: #316bff;
              border-radius: 6px;
              border: none;
              height: 33px;
              color: #fff;
              width: 100px;
              @media (max-width: 450px) {
                font-size: 14px;
              }
            }
          }
        }
      }
    }
  }
}
</style>