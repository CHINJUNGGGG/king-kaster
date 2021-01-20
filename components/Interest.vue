<template>
  <div id="interest" class="bg-Home">
    <div class="row" style="width: 100%; padding: 0 60px">
      <div class="col-lg-12">
        <div class="row" style="padding-left: 10px">
          <div class="col-lg-6">
            <div class="d-flex flex-row">
              <div class="rc-fontHeader h2 mr-3 pl-1">หมวดหมู่ที่น่าสนใจ</div>
              <a href="#">
                <div class="it-fontMore h2 mr-2">More</div>
                <img class="arrowMore" src="../assets/icon/arrowMore.png" />
              </a>
            </div>
          </div>
        </div>

        <no-ssr>
          <carousel
            :autoplay="false"
            :loop="false"
            :nav="false"
            :items="6"
            :responsive="{
              0: { items: 1, nav: false },
              600: { items: 4, nav: false },
              1200: { items: 6, nav: false },
              1900: { items: 8, nav: false },
            }"
            :dots="false"
            @changed="changed"
            @updated="updated"
          >
            <div
              style="padding: 15px 30px 0 15px"
              v-for="cat in category"
              :key="cat.id"
            >
              <div class="row">
                <div class="col-lg-12">
                  <!-- <a href="#"> -->
                  <div class="item" style="padding: 4px 1.5px 2px 0">
                    <div class="bg-it"></div>
                    <img class="it-img" :src="cat.image" />
                    <div class="it-coverImg"></div>
                    <div class="it-name h3">{{ cat.name }}</div>
                    <div class="it-caster">{{ cat.video }}k Kasters</div>
                  </div>
                  <!-- </a> -->
                </div>
              </div>
            </div>

            <template slot="prev"
              ><img class="prev" src="../assets/icon/arrowPrev.png"
            /></template>
            <template slot="next"
              ><img class="next" src="../assets/icon/arrowNext.png"
            /></template>
          </carousel>
        </no-ssr>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Interest',
  data() {
    return {
      isActive: false,
      category: [
        {
          id: '1',
          name: 'Film&Animation',
          image: require('@/assets/image/category/film.png'),
          video: '123',
        },
        {
          id: '2',
          name: 'Autos&Vehicles',
          image: require('@/assets/image/category/autos.png'),
          video: '234',
        },
        {
          id: '3',
          name: 'Pet&Animals',
          image: require('@/assets/image/category/pet.png'),
          video: '345',
        },
        {
          id: '4',
          name: 'Sports',
          image: require('@/assets/image/category/sports.png'),
          video: '456',
        },
        {
          id: '5',
          name: 'Travel&Event',
          image: require('@/assets/image/category/travel.png'),
          video: '567',
        },
        {
          id: '6',
          name: 'People&Blogs',
          image: require('@/assets/image/category/people.png'),
          video: '789',
        },
      ],
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

  .bg-it {
    width: 100%;
    height: 300px;
    background-color: #24284b;
    border-radius: 0 0 10px 10px;
  }

  .it-img {
    width: 100%;
    height: 241px;
    object-fit: cover;
    overflow: hidden;
    border-radius: 10px;
    position: absolute;
    top: 0;
    left: 0;
    z-index: 1;
    padding-right: 2px;
  }

  .it-coverImg {
    position: absolute;
    /* top: 15px; */
    top: 100%;
    left: 0;
    right: 2px;
    bottom: 65px;
    z-index: 2;
    border-radius: 0 0 7px 7px;
    background-image: linear-gradient(
      to bottom,
      rgba(247, 32, 46, 0),
      rgba(247, 34, 48, 0.26),
      rgba(246, 49, 61, 0.62),
      rgba(245, 63, 74, 0.97),
      #f55540
    );
    opacity: 0;
    transition: 0.4s;
  }

  .item:hover .it-coverImg {
    top: 15px;
    opacity: 0.6;
  }

  .it-name {
    font-family: 'kanitregular';
    color: #fdce00;
    position: absolute;
    bottom: 25px;
    left: 10px;
    z-index: 1;
  }
  .it-caster {
    font-family: 'kanitregular';
    font-size: 14px;
    color: #fff;
    position: absolute;
    bottom: 15px;
    left: 10px;
    z-index: 1;
  }
}
</style>
