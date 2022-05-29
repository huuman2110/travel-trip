<template>
  <div class="featured-destination">
    <div class="featured-destination-header">
      <h2 class="heading">Featured Destinations</h2>
      <p class="sub-heading">
        Popular destinations open to visitors from Indonesia
      </p>
    </div>
    <b-container class="featured-destination-list">
      <b-row>
        <b-col cols="12" lg="9">
          <div class="list-left d-flex flex-wrap">
            <div class="item-top w-100">
              <img :src="featured1" alt="" />
              <div
                class="
                  item-top-detail
                  d-flex
                  flex-column
                  justify-content-between
                "
              >
                <span class="item-point">3.5</span>
                <div class="item-info">
                  <p class="item-name">Barcelona Tour</p>
                  <div class="item-activity d-flex align-items-center">
                    <img :src="avataractive" alt="" />
                    <p>196 Activities</p>
                  </div>
                </div>
              </div>
            </div>
            <div class="item-bottom-left">
              <img :src="featured2" alt="" />
              <div
                class="
                  item-bottom-left-detail
                  d-flex
                  flex-column
                  justify-content-between
                "
              >
                <span class="item-point">3.5</span>
                <div class="item-info">
                  <p class="item-name">London, United State</p>
                  <div class="item-activity d-flex align-items-center">
                    <img :src="avataractive" alt="" />
                    <p>196 Activities</p>
                  </div>
                </div>
              </div>
            </div>
            <div class="item-bottom-right">
              <img :src="featured3" alt="" />
              <div
                class="
                  item-bottom-right-detail
                  d-flex
                  flex-column
                  justify-content-between
                "
              >
                <span class="item-point">3.5</span>
                <div class="item-info">
                  <p class="item-name">Australia Tour</p>
                  <div class="item-activity d-flex align-items-center">
                    <img :src="avataractive" alt="" />
                    <p>196 Activities</p>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </b-col>
        <b-col cols="12" lg="3">
          <div class="list-right">
            <div
              class="item"
              v-for="(item, index) in dataFeatetured"
              :key="index"
            >
              <img :src="item.img" alt="" />
              <div
                class="item-detail d-flex flex-column justify-content-between"
              >
                <span class="item-point">{{ item.point }}</span>
                <div class="item-info">
                  <p class="item-name">{{ item.name }}</p>
                  <div
                    class="
                      item-activity item-activity
                      d-flex
                      align-items-center
                    "
                  >
                    <img :src="item.avatar" alt="" />
                    <p>{{ item.activity }}</p>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import featured1 from "@/assets/img/featured1.jpeg";
import featured2 from "@/assets/img/featured2.jpeg";
import featured3 from "@/assets/img/featured3.jpeg";
import avataractive from "@/assets/img/avatar-activity.png";
export default {
  name: "FeaturedDestination",
  data() {
    return {
      featured1,
      avataractive,
      featured2,
      featured3,
      dataFeatetured: [
        {
          img: featured3,
          point: "3.5",
          name: "Australia Tour",
          avatar: avataractive,
          activity: "196 Activities",
        },
        {
          img: featured2,
          point: "3.5",
          name: "Barcelona",
          avatar: avataractive,
          activity: "196 Activities",
        },
        {
          img: featured1,
          point: "3.5",
          name: "Barcelona",
          avatar: avataractive,
          activity: "196 Activities",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.featured-destination {
  max-width: 1200px;
  margin: 0 auto;
  &-header {
    padding: 0 15px;
    margin-bottom: 40px;
    @media (max-width: 450px) {
      text-align: center;
      width: 250px;
      margin: 0 auto 20px;
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
  &-list {
    @media (max-width: 450px) {
      padding: 0 20px;
    }
    .list-left {
      .item-top {
        height: 280px;
        position: relative;
        overflow: hidden;
        border-radius: 20px;
        margin-bottom: 30px;
        @media (max-width: 450px) {
          margin-bottom: 20px;
        }
        img {
          width: 100%;
          height: 100%;
          object-fit: cover;
        }
        &-detail {
          position: absolute;
          color: #fff;
          top: 0;
          left: 0;
          padding: 20px 0 15px 20px;
          height: 100%;
          .item-point {
            padding: 2px 0;
            background-color: #ffffff;
            font-size: 18px;
            line-height: normal;
            font-weight: bold;
            color: #ff543d;
            border-radius: 50px;
            width: 66px;
            text-align: center;
          }
          .item-info {
            .item-name {
              font-size: 40px;
              font-weight: bold;
              color: #ffffff;
              margin-bottom: unset;
              @media (max-width: 450px) {
                font-size: 24px;
              }
            }
            .item-activity {
              img {
                border-radius: 100%;
                height: 28px;
                width: 28px;
                object-fit: cover;
                margin-right: 8px;
              }
              p {
                margin-bottom: unset;
              }
            }
          }
        }
      }
      .item-bottom-left {
        margin-right: 27px;
        @media (max-width: 450px) {
          margin-right: unset;
          margin-bottom: 20px;
        }
      }
      .item-bottom-right {
        margin-left: 27px;
        @media (max-width: 450px) {
          margin-left: unset;
          margin-bottom: 20px;
        }
      }

      .item-bottom-left,
      .item-bottom-right {
        height: 408px;
        width: calc(50% - 27px);
        position: relative;
        overflow: hidden;
        border-radius: 20px;
        @media (max-width: 450px) {
          width: 100%;
        }
        img {
          width: 100%;
          height: 100%;
          object-fit: cover;
        }
        &-detail {
          position: absolute;
          color: #fff;
          top: 0;
          left: 0;
          padding: 20px 0 15px 20px;
          height: 100%;
          .item-point {
            padding: 2px 0;
            background-color: #ffffff;
            font-size: 18px;
            line-height: normal;
            font-weight: bold;
            color: #ff543d;
            border-radius: 50px;
            width: 66px;
            text-align: center;
          }
          .item-info {
            .item-name {
              font-size: 24px;
              font-weight: bold;
              color: #ffffff;
              margin-bottom: unset;
            }
            .item-activity {
              img {
                border-radius: 100%;
                height: 20px;
                width: 20px;
                object-fit: cover;
                margin-right: 8px;
              }

              p {
                margin-bottom: unset;
                font-size: 14px;
              }
            }
          }
        }
      }
    }
    .list-right {
      @media (max-width: 450px) {
        padding: 0 10px;
      }
      .item {
        height: 220px;
        position: relative;
        overflow: hidden;
        border-radius: 20px;
        margin-bottom: 30px;
        @media (max-width: 450px) {
          margin-bottom: 20px;
        }
        img {
          width: 100%;
          height: 100%;
          object-fit: cover;
        }
        &-detail {
          position: absolute;
          color: #fff;
          top: 0;
          left: 0;
          padding: 20px 0 15px 20px;
          height: 100%;
          .item-point {
            padding: 2px 0;
            background-color: #ffffff;
            font-size: 14px;
            line-height: normal;
            font-weight: bold;
            color: #ff543d;
            border-radius: 50px;
            width: 49px;
            text-align: center;
          }
          .item-info {
            .item-name {
              font-size: 18px;
              font-weight: bold;
              color: #ffffff;
              margin-bottom: unset;
            }
            .item-activity {
              img {
                border-radius: 100%;
                height: 14px;
                width: 14px;
                object-fit: cover;
                margin-right: 8px;
              }
              p {
                margin-bottom: unset;
                font-size: 10px;
              }
            }
          }
        }
      }
    }
  }
}
</style>