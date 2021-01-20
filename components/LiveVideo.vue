<template>
  <div id="livevideo" class="bg-Home">
    <div class="row pb-5" style="width: 100%; padding: 0 60px">
      <div class="col-lg-12">
        <div class="row" style="padding-left: 10px">
          <div class="col-lg-6">
            <div class="d-flex flex-row">
              <div class="rc-fontHeader h2 mr-3 pl-1">Live ล่าสุด</div>
              <a href="#">
                <div class="it-fontMore h2 mr-2">More</div>
                <img class="arrowMore" src="../assets/icon/arrowMore.png" />
              </a>
            </div>
          </div>
        </div>
        <div class="row" style="padding: 0 0 0 15px">
          <div class="col-lg-5 lv-bg">
            <a href="#">
              <img
                class="lv-img"
                src="https://cdn.pixabay.com/photo/2020/03/01/00/55/compass-4891499__340.jpg"
              />
              <div class="lv-bth h6">
                ผู้เข้าชม : 123K
                <img class="lv-btnImg" src="../assets/icon/facebook.png" />
              </div>
              <img
                class="lv-imgProfile active"
                src="https://cdn.pixabay.com/photo/2019/10/29/10/07/man-4586576__340.jpg"
              />
              <div class="lv-btnLive h3">Live</div>
              <div style="margin-bottom: 0" class="lv-imgName h3">
                WE HIT 1,800 FOLLOWERS BOISssssssssssssssssssss
              </div>
              <div class="lv-casterName h3">TheSquash</div>
            </a>
          </div>

          <div class="col-lg-7" style="color: #fff">
            <div class="row" style="padding: 15px 30px 0 30px">
              <div class="col-lg-12">
                <VueSlickCarousel
                  v-bind="setting"
                  @init="onInitCarousel"
                  style="padding: 0 20px 0 0"
                >
                  <div class="pr-2 pb-1" style="width: 100%">
                    <a href="#">
                      <div class="bg-lv">
                        <img
                          width="100%"
                          class="lv-img2"
                          src="https://cdn.pixabay.com/photo/2019/10/29/10/07/man-4586576__340.jpg"
                        />
                        <div class="lv-bth2">
                          ผู้เข้าชม : 123K
                          <img
                            class="lv-btnImg2"
                            src="../assets/icon/facebook.png"
                          />
                        </div>
                      </div>
                    </a>
                  </div>
                  <div class="pr-2 pb-1">
                    <div class="bg-lv"></div>
                  </div>
                  <div class="pr-2 pb-1">
                    <div class="bg-lv"></div>
                  </div>
                  <div class="pr-2 pb-1">
                    <div class="bg-lv"></div>
                  </div>
                  <div class="pr-2 pb-1">
                    <div class="bg-lv"></div>
                  </div>
                  <div class="pr-2 pb-1">
                    <div class="bg-lv"></div>
                  </div>
                  <div class="pr-2 pb-1">
                    <div class="bg-lv"></div>
                  </div>

                  <div><h3>2</h3></div>
                  <div><h3>3</h3></div>
                  <div><h3>4</h3></div>
                  <div><h3>5</h3></div>
                  <div><h3>6</h3></div>
                  <div><h3>7</h3></div>
                  <div><h3>8</h3></div>
                  <div><h3>9</h3></div>
                  <div><h3>10</h3></div>
                  <template slot="prevArrow"
                    ><img class="prev2" src="../assets/icon/arrowPrev.png"
                  /></template>
                  <template slot="nextArrow"
                    ><img class="next2" src="../assets/icon/arrowNext.png"
                  /></template>
                </VueSlickCarousel>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import VueSlickCarousel from 'vue-slick-carousel'
import 'vue-slick-carousel/dist/vue-slick-carousel.css'
import 'vue-slick-carousel/dist/vue-slick-carousel-theme.css'
export default {
  components: { VueSlickCarousel },
  data() {
    return {
      setting: {
        // arrows: false,
        infinite: true,
        slidesToShow: 3,
        rows: 2,
        slidesPerRow: 1,
        responsive: [
          {
            breakpoint: 0,
            settings: {
              slidesToShow: 1,
            },
          },
          {
            breakpoint: 600,
            settings: {
              slidesToShow: 2,
            },
          },
          {
            breakpoint: 1024,
            settings: {
              slidesToShow: 3,
            },
          },
          {
            breakpoint: 1366,
            settings: {
              slidesToShow: 3,
            },
          },
          {
            breakpoint: 1900,
            settings: {
              slidesToShow: 4,
            },
          },
        ],
      },
    }
  },
}
</script>

<style lang="css" scoped>
@media screen and (min-width: 1200px) {
  .h1 {
    font-size: 23px;
  }
  .h2 {
    font-size: 22px;
  }
  .h3 {
    font-size: 19px;
  }
  .h4 {
    font-size: 18px;
  }
  .h5 {
    font-size: 13px;
  }
  .h6 {
    font-size: 12px;
  }
  .p {
    font-size: 16px;
  }

  .prev2 {
    width: 30px;
    height: 30px;
    background-color: #000000;
    opacity: 0.5;
    padding: 7px 10px;
    border-radius: 50px;
    position: absolute;
    top: -55px;
    right: 55px !important;
    z-index: 1;
    cursor: pointer;
  }

  .prev2:hover {
    background-color: #4e7bf7;
    opacity: 1;
  }

  .next2 {
    width: 30px;
    height: 30px;
    background-color: #000000;
    opacity: 0.5;
    padding: 7px 10px;
    border-radius: 50px;
    position: absolute;
    top: -55px;
    right: 20px;
    z-index: 1;
    cursor: pointer;
  }
  .next2:hover {
    background-color: #4e7bf7;
    opacity: 1;
  }
}
</style>
