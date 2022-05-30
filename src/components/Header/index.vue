<template>
  <div class="header">
    <div
      class="header-container d-flex align-items-center justify-content-between"
    >
      <div class="header-logo d-flex align-items-center">
        <img :src="logo" alt="" />
        <span>TripGuide</span>
      </div>
      <div class="header-right d-flex align-items-center">
        <div class="option d-flex align-items-center">
          <span>USD</span>
          <img :src="flagAmerica" alt="" />
          <div class="noti">
            <b-icon icon="bell"></b-icon>
            <span>1</span>
          </div>
        </div>
        <div class="avatar d-flex align-items-center">
          <img :src="avatar" alt="" />
          <span>Delowar</span>
          <font-awesome-icon icon="fas fa-caret-down" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import logo from "@/assets/logo.png";
import flagAmerica from "@/assets/img/flag-america.png";
import avatar from "@/assets/img/avatar.png";
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Header",
  data() {
    return {
      logo,
      flagAmerica,
      avatar,
    };
  },
};
</script>

<style lang="scss" scoped>
.header {
  position: fixed;
  height: 78px;
  width: 100%;
  top: 0;
  z-index: 10;
  background-color: #ffffff;
  @media (max-width: 450px) {
    height: 88px;
    padding: 0 20px;
  }
  &-container {
    max-width: 1440px;
    height: 100%;
    margin: 0 auto;
    .header-logo {
      img {
        height: 38px;
        width: 40px;
        margin-right: 10px;
        @media (max-width: 450px) {
          height: 28px;
          width: 28px;
        }
      }
      span {
        color: #222529;
        font-family: "Poppins", sans-serif;
        font-size: 20px;
        font-weight: 700;
        @media (max-width: 450px) {
          font-size: 12px;
        }
      }
    }
    .header-right {
      .option {
        padding: 0 17px;
        border-right: 1px solid #e7ecf3;
        color: #84878b;
        font-size: 14px;
        height: 32px;
        @media (max-width: 450px) {
          font-size: 12px;
        }
        img {
          margin: 0 15px;
          @media (max-width: 450px) {
            height: 16px;
            width: 16px;
          }
        }
        .noti {
          position: relative;
          svg {
            font-size: 17px;
            @media (max-width: 450px) {
              font-size: 14px;
            }
          }
          span {
            position: absolute;
            background: red;
            border-radius: 100%;
            font-size: 7px;
            font-weight: 700;
            color: white;
            text-align: center;
            height: 10px;
            width: 10px;
            top: -1px;
            right: -3px;
          }
        }
      }
      .avatar {
        padding: 0 20px;
        gap: 10px;
        @media (max-width: 450px) {
          padding: 0 0 0 20px;
          span {
            display: none;
          }
          svg {
            display: none;
          }
        }
        img {
          height: 32px;
          width: 32px;
          @media (max-width: 450px) {
            height: 28px;
            width: 28px;
          }
        }
      }
    }
  }
}
</style>