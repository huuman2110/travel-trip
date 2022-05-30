<template>
  <div class="banner">
    <img :src="banner" alt="" />
    <p class="banner-content">Book With Us And Enjoy your Journey !</p>
    <div class="super-container">
      <div class="search-container">
        <div class="search-content d-flex flex-column justify-content-between">
          <div
            class="
              search-content-top
              d-flex
              justify-content-between
              align-items-center
            "
          >
            <div class="search-service d-flex align-items-center">
              <div class="search-room">
                <font-awesome-icon icon="fas fa-bed" />
                <span>Hotel</span>
              </div>
              <div class="search-fly">
                <font-awesome-icon icon="fas fa-plane-departure" />
                <span>Flight</span>
              </div>
              <div class="search-car">
                <font-awesome-icon icon="fas fa-car-alt" />
                <span>Car Rentral</span>
              </div>
            </div>
            <div class="search-passenger d-flex align-items-center">
              <div class="search-trip">
                <span>Round trip</span>
                <font-awesome-icon icon="fas fa-chevron-down" />
              </div>
              <div
                class="search-pass"
                v-on:click="(isShowPassenger = true), (isActive = true)"
              >
                <span>1 passenger</span>
                <font-awesome-icon
                  icon="fas fa-chevron-down"
                  :class="{ rotate: isActive }"
                />
              </div>
              <div class="search-passenger-model" v-show="isShowPassenger">
                <div class="adults">
                  <div class="adults-info">
                    <p class="adults-info-name">Adults</p>
                    <p class="adults-info-subname">Ages 13 or above</p>
                  </div>
                  <div class="adults-btn">
                    <button @click="countAdults--">-</button>
                    <input type="text" v-model="countAdults" />
                    <button @click="countAdults++">+</button>
                  </div>
                </div>
                <div class="adults">
                  <div class="adults-info">
                    <p class="adults-info-name">Children</p>
                    <p class="adults-info-subname">Ages 2-12</p>
                  </div>
                  <div class="adults-btn">
                    <button @click="countChildren--">-</button>
                    <input type="text" v-model="countChildren" />
                    <button @click="countChildren++">+</button>
                  </div>
                </div>
                <div class="adults">
                  <div class="adults-info">
                    <p class="adults-info-name">Infants</p>
                    <p class="adults-info-subname">Under 2</p>
                  </div>
                  <div class="adults-btn">
                    <button @click="countInfants--">-</button>
                    <input type="text" v-model="countInfants" />
                    <button @click="countInfants++">+</button>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div
            class="
              search-content-bottom
              d-flex
              align-items-center
              justify-content-between
            "
          >
            <div class="search-info d-flex align-items-center">
              <div class="search-location">
                <div class="search-location-content">
                  <p>Location</p>
                  <input
                    id="location"
                    type="text"
                    placeholder="Where are you from?"
                    v-on:click="isShowLocation = true"
                    v-model="inputLocation"
                  />
                  <font-awesome-icon
                    class="icon-exchange"
                    icon="fas fa-exchange-alt"
                  ></font-awesome-icon>
                  <div class="location-model" v-show="isShowLocation">
                    <div
                      class="location-model-item"
                      v-for="(item, index) in dataLocation"
                      :key="index"
                    >
                      <font-awesome-icon
                        icon="fas fa-map-marker-alt"
                      ></font-awesome-icon>
                      <div
                        class="item-detail"
                        v-on:click="fieldInput(item.name, item.subname), isShowLocation = false "
                      >
                        <p class="item-detail-name">{{ item.name }}</p>
                        <p class="item-detail-subname">
                          {{ item.subname }}
                        </p>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
              <div class="search-checkin">
                <div class="search-checkin-content">
                  <p>Check in</p>
                  <DatePicker
                    v-model="time1"
                    format="DD-MM-YYYY" 
                    placeholder="Add Date"
                  />
                  <font-awesome-icon
                    class="icon-exchange"
                    icon="fas fa-exchange-alt"
                  ></font-awesome-icon>
                </div>
              </div>
              <div class="search-checkout">
                <div class="search-checkout-content">
                  <p>Check out</p>
                  <DatePicker
                    v-model="time2"
                    format="DD-MM-YYYY" 
                    placeholder="Add Date"
                  />
                </div>
              </div>
              <div class="search-passenger">
                <div class="search-passenger-content">
                  <p>Passenger</p>
                  <input
                    id="passenger"
                    type="text"
                    placeholder="Add passenger"
                  />
                </div>
              </div>
            </div>
            <b-button variant="primary">Search</b-button>
          </div>
        </div>
      </div>
    </div>
    <div
      class="bg-modal-location"
      v-if="isShowLocation"
      v-on:click="isShowLocation = false"
    ></div>
    <div
      class="bg-modal-passenger"
      v-if="isShowPassenger"
      v-on:click="(isShowPassenger = false), (isActive = false)"
    ></div>
  </div>
</template>

<script>
import banner from "@/assets/img/banner.jpeg";
import DatePicker from "vue2-datepicker";
import "vue2-datepicker/index.css";
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Banner",
  components: { DatePicker },
  data() {
    return {
      banner,
      countAdults: 0,
      countChildren: 0,
      countInfants: 0,
      time1: null,
      time2:null,
      dataLocation: [
        {
          name: "Dubai",
          subname: "Dubai Emirate, United Arab Emirates",
        },
        {
          name: "Doha",
          subname: "Qatar",
        },
        {
          name: "Darling Harbour",
          subname: "Sydney, New South Wales, Australia",
        },
        {
          name: "Dhaka",
          subname: "Bangladesh",
        },
        {
          name: "Dubai International Airport",
          subname: "Dubai, Dubai Emirate, United Arab Emirates",
        },
      ],
      isShowLocation: false,
      inputLocation: "",
      isShowPassenger: false,
      isActive: false,
    };
  },
  methods: {
    fieldInput(itemName, itemSubname) {
      this.inputLocation = itemName + ", " + itemSubname;
      this.isShowModal = false;
    },
  },
};
</script>

<style lang="scss" >
.banner {
  position: relative;
  margin-top: 78px;
  img {
    width: 100%;
    height: 580px;
    object-fit: cover;
    background-repeat: no-repeat;
    background-position: center center;
    @media (max-width: 450px) {
      height: 605px;
    }
  }
  .banner-content {
    position: absolute;
    font-family: "Poppins", sans-serif;
    font-weight: 700;
    line-height: 80px;
    width: 490px;
    height: 240px;
    text-shadow: 0px 8px 16px rgba(51, 51, 51, 0.08);
    font-size: 64px;
    color: #fff;
    letter-spacing: -0.005em;
    top: 25%;
    left: 12%;
    @media (max-width: 450px) {
      font-size: 40px;
      width: 320px;
      line-height: 1.5;
      top: 10%;
      left: 3%;
    }
  }
  .super-container {
    position: relative;
    max-width: 1200px;
    margin: 0 auto;
    .search-container {
      position: absolute;
      width: 100%;
      top: -115px;
      padding: 0 20px;
      @media (max-width: 450px) {
        top: -315px;
      }
      .search-content {
        width: 100%;
        height: 205px;
        padding: 30px 60px;
        color: #3b3e44;
        background: #fff;
        border-radius: 20px;
        box-shadow: 0px 12px 60px rgba(89, 89, 89, 0.1);
        @media (max-width: 450px) {
          padding: 20px;
          height: auto;
        }
        &-top {
          max-width: 850px;
          border-bottom: 1px solid #e7ecf3;
          padding-bottom: 28px;
          @media (max-width: 450px) {
            flex-direction: column;
            align-items: flex-start !important;
            padding: 0;
            border: none;
          }
          .search-service {
            position: relative;
            font-size: 14px;
            font-weight: bold;
            column-gap: 32px;
            color: #3b3e44;
            svg {
                font-size: 18px;
              }
            @media (max-width: 450px) {
              width: 100%;
              justify-content: space-between;
              svg {
                font-size: 16px;
              }
            }
            .search-room {
              svg {
                margin-right: 8px;
              }
            }
            .search-room::after {
              content: "";
              position: absolute;
              width: 66px;
              height: 2px;
              background: #316bff;
              bottom: -30px;
              left: 0;
              @media (max-width: 450px) {
                bottom: -15px;
              }
            }
            .search-fly,
            .search-car {
              color: #84878b;
              svg {
                margin-right: 8px;
              }
            }
          }
          .search-passenger {
            column-gap: 32px;
            color: #3b3e44;
            font-weight: 500;
            svg {
              margin-left: 10px;
            }
            .rotate {
              transform: rotate(180deg);
            }
            @media (max-width: 450px) {
              margin: 30px 0 15px;
            }
            &-model {
              position: absolute;
              display: flex;
              flex-direction: column;
              bottom: 215px;
              right: 18px;
              width: 354px;
              height: 224px;
              background: #ffffff;
              box-shadow: 0px 12px 60px rgba(89, 89, 89, 0.1);
              border-radius: 16px;
              padding: 20px 30px;
              row-gap: 18px;
              z-index: 100;
              .adults {
                display: flex;
                justify-content: space-between;
                align-items: center;
                border-bottom: 1px solid #e6e8ec;
                padding-bottom: 15px;
                &:last-child {
                  border-bottom: none;
                }
                &-info {
                  &-name {
                    font-size: 16px;
                    font-weight: 500;
                    color: #777e90;
                    margin-bottom: 8px;
                    line-height: 1;
                  }
                  &-subname {
                    font-size: 14px;
                    font-weight: 400;
                    color: #b1b5c3;
                    line-height: normal;
                    margin-bottom: unset;
                    line-height: 1;
                  }
                }
                &-btn {
                  button {
                    width: 32px;
                    border-radius: 100%;
                    height: 32px;
                    border: 1px solid #b1b5c4;
                    color: #b1b5c4;
                    text-align: center;
                  }
                  input {
                    width: 14px;
                    text-align: center;
                    border: none;
                    font-size: 14px;
                    color: #777e91;
                  }
                }
              }
            }
          }
        }
        &-bottom {
          @media (max-width: 450px) {
            flex-direction: column;
          }
          .search-info {
            gap: 10px;
            @media (max-width: 450px) {
              gap: 0;
              justify-content: center;
              flex-wrap: wrap;
            }
            .search-location {
              width: 330px;
              @media (max-width: 450px) {
                width: 100%;
              }
            }
            .search-passenger {
              display: none;
              @media (max-width: 450px) {
                display: block;
                width: 100%;
              }
            }
            .search-checkin {
              @media (max-width: 450px) {
                margin-right: 10px;
              }
            }
            .search-checkin,
            .search-checkout {
              @media (max-width: 450px) {
                width: calc(50% - 5px);
              }
              .mx-datepicker{
                width: 100%;
                .mx-input-wrapper{
                  .mx-input{
                    -webkit-box-shadow: none;
                    margin-top: 0;
                    padding: 0;
                  }
                  i{
                    display: none;
                  }
                }
              }
            }
            .search-location,
            .search-checkin,
            .search-checkout,
            .search-passenger {
              position: relative;
              @media (max-width: 450px) {
                margin-bottom: 10px;
              }
              &-content {
                display: flex;
                flex-direction: column;
                background: #f4f5f7;
                border: 1px solid #e7e8ea;
                box-sizing: border-box;
                border-radius: 8px;
                height: 70px;
                padding: 10px 24px 12px;
                color: #3b3e44;
                font-size: 18px;
                font-weight: 600;
                @media (max-width: 450px) {
                  height: 60px;
                  padding: 8px 20px;
                }
                p {
                  margin-bottom: unset;
                  line-height: normal;
                  @media (max-width: 450px) {
                    font-size: 16px;
                  }
                }
                input {
                  height: 100%;
                  background: #f4f5f7;
                  color: #b1b5c4;
                  border: none;
                  outline: none;
                  font-size: 16px;
                  margin-top: 6px;
                  @media (max-width: 450px) {
                    font-size: 12px;
                  }
                }
                .icon-exchange {
                  position: absolute;
                  background: #ffffff;
                  color: #b1b5c4;
                  padding: 10px;
                  border-radius: 100%;
                  right: -23px;
                  top: 25%;
                  z-index: 1;
                  @media (max-width: 450px) {
                    display: none;
                  }
                }
                .location-model {
                  position: absolute;
                  display: flex;
                  flex-direction: column;
                  top: 75px;
                  left: 0;
                  width: 400px;
                  height: auto;
                  background: #ffffff;
                  border: 1px solid #f4f5f6;
                  box-shadow: 0px 12px 60px rgba(89, 89, 89, 0.1);
                  border-radius: 20px;
                  padding: 18px 20px;
                  z-index: 100;
                  @media (max-width: 450px){
                    width: 100%;
                    top: 68px;
                  }
                  &-item {
                    display: flex;
                    align-items: center;
                    margin-bottom: 20px;
                    &:last-child {
                      margin-bottom: unset;
                    }
                    svg {
                      font-size: 20px;
                      margin-right: 10px;
                      color: #b1b5c4;
                    }
                    .item-detail {
                      display: flex;
                      flex-direction: column;
                      justify-content: space-between;
                      align-items: flex-start;
                      row-gap: 6px;
                      white-space: nowrap;
                      overflow: hidden;
                      text-overflow: ellipsis;
                      -webkit-line-clamp: 1;
                      -webkit-box-orient: vertical;
                      &-name {
                        font-size: 16px;
                        color: #777e91;
                        font-weight: 500;
                      }
                      &-subname {
                        font-size: 14px;
                        color: #b1b5c4;
                        font-weight: 400;
                      }
                    }
                  }
                }
              }
            }
          }
          button {
            color: #ffffff;
            border-radius: 10px;
            padding: 15px 41px;
            font-weight: bold;
            font-size: 20px;
            @media (max-width: 450px) {
              width: 100%;
            }
          }
        }
      }
    }
  }
}
.bg-modal-location,
.bg-modal-passenger {
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  z-index: 50;
}
.mx-datepicker-main{
  border-radius: 20px;
  font-size: 20px;
  @media (max-width: 450px){

  }
  .mx-datepicker-content{
    .mx-datepicker-body{
      .mx-calendar{
        .mx-calendar-header{
          .mx-calendar-header-label{
            font-size: 20px;
            font-weight: 700;
            color: #3B3E44;
          }
          .mx-btn-icon-double-left{
            display: none;
          }
          .mx-btn-icon-double-right{
            display: none;
          }
        }
      }
    }
  }
}
</style>