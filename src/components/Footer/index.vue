<template>
  <div class="footer">
    <div class="footer-content d-flex justify-content-between">
      <div class="trip-guide">
        <div class="logo d-flex align-items-center">
          <img :src="logo" alt="" />
          <span>TripGuide</span>
        </div>
        <p>
          This is the team that specializes in making sure in the find it a your
          interior looks cool
        </p>
        <div
          class="dark-light d-flex align-items-center justify-content-between"
        >
          <div class="light">
            <b-icon icon="sun-fill"></b-icon>
          </div>
          <div class="dark">
            <b-icon icon="moon"></b-icon>
          </div>
        </div>
      </div>
      <div class="trip-info d-flex justify-content-between">
        <div class="service">
          <p>Service</p>
          <div class="sub-service">
            <p>Travel Booking</p>
            <p>Flight Booking</p>
            <p>Car Booking</p>
            <p>Fivestar Hotel</p>
            <p>Traveling</p>
          </div>
        </div>
        <div class="support">
          <p>Suport</p>
          <div class="sub-support">
            <p>Account</p>
            <p>Legal</p>
            <p>Contact</p>
            <p>Terms &amp; Condition</p>
            <p>Privacy Policy</p>
          </div>
        </div>
        <div class="business">
          <p>Business</p>
          <div class="sub-business">
            <p>Success</p>
            <p>About Locato</p>
            <p>Blog</p>
            <p>Information</p>
            <p>Travel Guide</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import logo from "@/assets/logo.png";
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Footer",
  data() {
    return {
      logo,
    };
  },
};
</script>

<style lang="scss" scoped>
.footer {
  background: #f4f5f6;
  &-content {
    max-width: 1200px;
    margin: 0 auto;
    padding: 225px 45px 150px;
    @media (max-width: 450px) {
      padding: 35px 30px 100px;
      flex-direction: column-reverse;
    }
    .trip-guide {
      width: 254px;
      .logo {
        margin-bottom: 20px;
        img {
          height: 38px;
          width: 40px;
          margin-right: 10px;
          @media (max-width: 450px) {
            height: 25px;
          width: 25px;
          }
        }
        span {
          font-size: 20px;
          font-weight: bold;
          color: #222529;
          @media (max-width: 450px) {
            font-size: 15px;
          }
        }
      }
      p {
        font-size: 16px;
        color: #84878b;
        margin-bottom: 24px;
        @media (max-width: 450px) {
            font-size: 12px;
          }
      }
    }
    .dark-light {
      width: 128px;
      height: 38px;
      background: #ffffff;
      border: 0.5px solid #efefef;
      border-radius: 10px;
      .light {
        width: 50%;
        height: 30px;
        background: #fcfcfd;
        box-shadow: 0px 2px 2px rgba(67, 67, 67, 0.1);
        border-radius: 8px;
        text-align: center;
        line-height: 30px;
        margin-left: 1px;
      }
      .dark {
        text-align: center;
        line-height: 38px;
        width: 50%;
        color: #868b90;
      }
    }
    .trip-info {
      flex: 1;
      margin-left: 150px;
      @media (max-width: 450px) {
        flex-direction: column;
        margin-left: 0;
      }
      .service,
      .support {
        @media (max-width: 450px) {
          border-bottom: 1px solid #e7ecf3;
        }
      }
      .service,
      .support,
      .business {
        font-weight: 500;
        font-family: "DM Sans", sans-serif;
        margin-top: 20px;
        p {
          color: #222529;
          font-size: 24px;
          margin-bottom: 20px;
          @media (max-width: 450px) {
            font-size: 18px;
          }
        }
        .sub-service,
        .sub-support,
        .sub-business {
          p {
            font-size: 16px;
            color: #84878b;
            margin-bottom: 15px;
            @media (max-width: 450px) {
            font-size: 12px;
          }
          }
        }
      }
    }
  }
}
</style>