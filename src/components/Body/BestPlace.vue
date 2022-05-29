<template>
  <div class="bestplace">
    <div class="bestplace-header">
      <h2 class="heading">Search a best place in the world</h2>
      <p class="sub-heading">
        Whether you’re looking for places for a vacation. We are here to Guide
        you about the details you need to check in and ease your trips in
        advance
      </p>
    </div>
    <b-container class="bestplace-list">
      <b-row>
        <b-col cols="3" v-for="(item, index) in dataBestplace" :key="index">
          <div class="bestplace-list-item">
            <div class="bestplace-item-content">
              <img :src="item.img" alt="" />
              <p class="bestplace-item-name">{{ item.name }}</p>
              <p class="bestplace-item-des">{{ item.des }}</p>
            </div>
          </div>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import place1 from "@/assets/img/place1.jpg";
import place2 from "@/assets/img/place2.jpeg";
import place3 from "@/assets/img/place3.jpeg";
import place4 from "@/assets/img/place4.jpg";
export default {
  data() {
    return {
      place1,
      place2,
      place3,
      place4,
      dataBestplace: [
        {
          img: place1,
          name: "Batu, East Java",
          des: "86 Destinations",
        },
        {
          img: place2,
          name: "Kuta",
          des: "86 Destinations",
        },
        {
          img: place3,
          name: "Surabaya, East Java",
          des: "86 Destinations",
        },
        {
          img: place4,
          name: "Malang, East Java",
          des: "86 Destinations",
        },
        {
          img: place4,
          name: "Dieng, Central Java",
          des: "86 Destinations",
        },
        {
          img: place3,
          name: "Nusa Dua, Lombok",
          des: "86 Destinations",
        },
        {
          img: place2,
          name: "Bandung, West Java",
          des: "86 Destinations",
        },
        {
          img: place1,
          name: "Wakatobi, Sumatera",
          des: "86 Destinations",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.bestplace {
  max-width: 1200px;
  margin: 160px auto 70px;
  padding: 20px;
  @media (max-width: 450px) {
    margin: 80px auto 30px;
  }
  .bestplace-header {
    text-align: center;
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
      width: 590px;
      height: 48px;
      font-size: 16px;
      font-weight: 400;
      font-family: "Poppins", sans-serif;
      color: #84878b;
      line-height: 1.5;
      @media (max-width: 450px) {
        width: auto;
        font-size: 14px;
        height: auto;
      }
    }
  }
  .bestplace-list {
    margin-top: 65px;
    @media (max-width: 450px) {
      margin-top: 30px;
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
          flex: 1 0 220px;
        }
      }
    }
    &-item {
      height: 205px;
      border-radius: 10px;
      border: 1px solid #e7ecf3;
      overflow: hidden;
      box-shadow: 0px 20px 51px rgba(96, 96, 96, 0.1);
      margin-bottom: 30px;
      @media (max-width: 450px) {
        margin-bottom: unset;
      }
      .bestplace-item-content {
        text-align: left;
        bottom: 0;
        padding-top: 28px;
        padding-left: 30px;
        line-height: 2;
        @media (max-width: 450px) {
          padding: 25px 15px;
          text-align: center;
        }
        img {
          border-radius: 10px;
          width: 70px;
          height: 70px;
          object-fit: cover;
          margin-bottom: 15px;
        }
        .bestplace-item-name {
          font-size: 20px;
          font-weight: 700;
          color: #3b3e44;
          margin-bottom: unset;
          @media (max-width: 450px) {
            font-size: 16px;
          }
        }
        .bestplace-item-des {
          font-weight: 500;
          color: #84878b;
          margin-bottom: unset;
          @media (max-width: 450px) {
            font-size: 14px;
          }
        }
      }
    }
  }
}
</style>