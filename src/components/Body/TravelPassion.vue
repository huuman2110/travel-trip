<template>
  <div class="travelpassion">
    <div class="travelpassion-header">
      <h2 class="heading">Travel Your Passion</h2>
      <p class="sub-heading">
        Most Brilliant reasons Entrada should be your one-stop-shop!
      </p>
    </div>
    <b-container class="travelpassion-list">
      <b-row>
        <b-col cols="3" v-for="(item, index) in dataTravelPassion" :key="index">
          <div class="travelpassion-list-item">
            <img :src="item.img" alt="" />
            <div class="item-info d-flex flex-column justify-content-end">
              <p class="item-name">{{ item.name }}</p>
              <div class="item-point">
                <font-awesome-icon icon="fas fa-star"></font-awesome-icon>
                <span>{{ item.point }}</span> ({{ item.review }} reviews)
              </div>
            </div>
          </div>
        </b-col>
      </b-row>
    </b-container>
    <div class="subscribe">
      <div class="subscribe-container">
        <img :src="bgsub" alt="" />
        <div
          class="
            subscribe-content
            d-flex
            justify-content-between
            align-items-center
          "
        >
          <div
            class="
              subscribe-content-text
              d-flex
              flex-column
              justify-content-between
            "
          >
            <p class="text-heading">Get our pro offers</p>
            <p class="text-sub-heading">
              Create a visual identity for your company, and an overall brand
            </p>
          </div>
          <div class="subscribe-content-form d-flex">
            <input
              class="flex-grow-1"
              type="email"
              placeholder="Type your email here"
            />
            <button>Subscribe</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import travelpassion1 from "@/assets/img/travelpassion1.jpg";
import travelpassion2 from "@/assets/img/travelpassion2.jpg";
import travelpassion3 from "@/assets/img/travelpassion3.jpg";
import travelpassion4 from "@/assets/img/travelpassion4.jpg";
import bgsub from "@/assets/img/bg-sub.png";

export default {
  name: "TravelPassion",
  data() {
    return {
      travelpassion1,
      travelpassion2,
      travelpassion3,
      travelpassion4,
      bgsub,
      dataTravelPassion: [
        {
          img: travelpassion1,
          name: "Beach Hobby",
          point: "4.8",
          review: "122",
        },
        {
          img: travelpassion2,
          name: "City Tours",
          point: "4.8",
          review: "122",
        },
        {
          img: travelpassion3,
          name: "Hiking Trips",
          point: "4.8",
          review: "122",
        },
        {
          img: travelpassion4,
          name: "Sports Trips",
          point: "4.8",
          review: "122",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.travelpassion {
  position: relative;
  max-width: 1200px;
  margin: 70px auto 0;
  padding-bottom: 250px;
  @media (max-width: 450px) {
    margin: 30px auto 0;
    padding-bottom: 190px;
  }
  .travelpassion-header {
    padding: 0 15px;
    margin-bottom: 40px;
    @media (max-width: 450px) {
      text-align: center;
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
      font-size: 16px;
      font-weight: 400;
      font-family: "Poppins", sans-serif;
      color: #84878b;
      line-height: 1.5;
      margin-bottom: unset;
      @media (max-width: 450px) {
        font-size: 14px;
        max-width: 250px;
      }
    }
  }
  .travelpassion-list {
    @media (max-width: 450px) {
      padding: 0 20px;
    }
    .row {
      @media (max-width: 450px) {
        flex-wrap: nowrap;
        overflow-x: auto;
        &::-webkit-scrollbar {
          display: none;
          -ms-overflow-style: none; /* IE and Edge */
          scrollbar-width: none; /* Firefox */
        }
      }
      .col-3 {
        @media (max-width: 450px) {
          flex: 1 0 290px;
          padding: 0 10px;
        }
      }
    }
    &-item {
      position: relative;
      border-radius: 15px;
      overflow: hidden;
      height: 320px;
      img {
        background: linear-gradient(
          8.54deg,
          rgba(31, 31, 31, 0.63) 17.12%,
          rgba(35, 35, 35, 0) 92.69%
        );
        height: 100%;
        width: 100%;
      }
      .item-info {
        position: absolute;
        padding: 20px 30px;
        bottom: 0;
        height: 100%;
        color: #ffffff;
        .item-name {
          font-size: 24px;
          font-weight: 600;
          margin-bottom: unset;
          text-shadow: 0px 8px 16px rgba(51, 51, 51, 0.08);
        }
        .item-point {
          font-size: 14px;
          font-weight: 400;
          margin-top: 10px;
          svg {
            color: yellow;
            margin-right: 10px;
          }
        }
      }
    }
  }
  .subscribe {
    position: absolute;
    bottom: -15%;
    max-width: 1200px;
    height: 250px;
    padding: 0 15px;
    @media (max-width: 450px) {
      padding: 0 20px;
      height: 175px;
      bottom: -35px;
    }
    .subscribe-container {
      position: relative;
      height: 100%;
      width: 100%;
      border-radius: 10px;
      overflow: hidden;
      img {
        height: 100%;
        width: 100%;
        object-fit: cover;
      }
      .subscribe-content {
        position: absolute;
        bottom: 0;
        width: 100%;
        height: auto;
        padding: 62px 90px;
        @media (max-width: 450px) {
          flex-direction: column;
          align-items: flex-start !important;
          padding: 15px 20px;
        }
        &-text {
          line-height: 1.5;
          color: #ffffff;
          .text-heading {
            font-family: "DM Sans", sans-serif;
            font-size: 44px;
            font-weight: 600;
            margin-bottom: unset;
            @media (max-width: 450px) {
              font-size: 20px;
            }
          }
          .text-sub-heading {
            font-size: 16px;
            font-weight: 400;
            opacity: 0.88;
            width: 370px;
            @media (max-width: 450px) {
              font-size: 12px;
              width: 234px;
            }
          }
        }
        .subscribe-content-form {
          width: 490px;
          background: #fcfcfd;
          box-shadow: 10px 16px 60px -7px rgba(0, 0, 0, 0.04);
          border-radius: 4px;
          padding: 8px 8px 8px 22px;
          @media (max-width: 450px) {
            width: 100%;
          }
          input {
            border: none;
            outline: none;
            font-size: 16px;
            color: #b1b5c4;
          }
          button {
            height: 55px;
            width: 130px;
            background: #353945;
            box-shadow: 0px 12px 20px -5px rgba(23, 23, 126, 0.1);
            border-radius: 4px;
            font-size: 16px;
            color: #ffffff;
            @media (max-width: 450px) {
              height: 45px;
            }
          }
        }
      }
    }
  }
}
</style>