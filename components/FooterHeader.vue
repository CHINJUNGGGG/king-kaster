<template>
  <div id="footerheader">
    <div class="row" style="width: 100%; margin: 0">
      <div class="col-lg-12 footerHeader">
        <div
          class="row py-3"
          style="width: 100%; padding-left: 50px; height: 100%"
        >
          <div class="col-lg-4">
            <div class="d-flex flex-row">
              <div class="titleEpisodes h4">Episodes</div>
              <div>
                <img class="fh-img" src="../assets/icon/arrowHeader.png" />
              </div>
              <div class="fh-cat1 h4">Thai Main</div>
              <div class="fh-cat2 h4">Thai Drama</div>
            </div>
            <div class="d-flex flex-row">
              <div class="titleEpisodes h4">Variety show</div>
              <div>
                <img class="fh-img" src="../assets/icon/arrowHeader.png" />
              </div>
              <div class="fh-cat1 h4">Hot Now</div>
              <div class="fh-cat2 h4">Homemade</div>
            </div>
          </div>
          <div class="col-lg-4 fh-line">
            <div class="d-flex flex-row">
              <div class="titleEpisodes h4">Episodes</div>
              <div>
                <img class="fh-img" src="../assets/icon/arrowHeader.png" />
              </div>
              <div class="fh-cat1 h4">Thai Main</div>
              <div class="fh-cat2 h4">Thai Drama</div>
            </div>
            <div class="d-flex flex-row">
              <div class="titleEpisodes h4">Variety show</div>
              <div>
                <img class="fh-img" src="../assets/icon/arrowHeader.png" />
              </div>
              <div class="fh-cat1 h4">Hot Now</div>
              <div class="fh-cat2 h4">Homemade</div>
            </div>
          </div>
          <div class="col-lg-4">
            <div class="d-flex flex-row">
              <div class="titleEpisodes h4">Episodes</div>
              <div>
                <img class="fh-img" src="../assets/icon/arrowHeader.png" />
              </div>
              <div class="fh-cat1 h4">Thai Main</div>
              <div class="fh-cat2 h4">Thai Drama</div>
            </div>
            <div class="d-flex flex-row">
              <div class="titleEpisodes h4">Variety show</div>
              <div>
                <img class="fh-img" src="../assets/icon/arrowHeader.png" />
              </div>
              <div class="fh-cat1 h4">Hot Now</div>
              <div class="fh-cat2 h4">Homemade</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'FooterHeader',
}
</script>

<style lang="css" scoped>
@media screen and (min-width: 1200px) {
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
    margin: 0 !important;
  }
  .footerHeader {
    width: 100%;
    height: 140px;
    background-color: #202433;
    margin-top: 100vh;
  }

  .titleEpisodes {
    font-family: 'kanitsemibold';
    color: #ffffff;
    margin: 20px 10px 0 30px;
  }

  /* .titleEpisodes {
    font-family: 'kanitsemibold';
    color: #ffffff;
    margin: 20px 10px 0 30px;
  } */

  .fh-img {
    margin: 27px 10px 0 0;
  }

  .fh-cat1 {
    font-family: 'kanitlight';
    color: #ffffff;
    margin: 20px 20px 0 15px;
  }
  .fh-cat2 {
    font-family: 'kanitlight';
    color: #ffffff;
    margin: 20px 0 0 0;
  }

  .fh-line {
    /* position: absolute;
        top: 20px;
        right: 30px;
        width: 1px;
        height: 78px; */
    border-width: 1px;
    border-style: solid;
    border-image: linear-gradient(
        to bottom,
        rgba(255, 255, 255, 0),
        #ffffff 53%,
        rgba(255, 255, 255, 0)
      )
      1 100%;
  }
}
</style>
