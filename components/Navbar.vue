<template>
  <div>
    <div id="navbar">
      <b-navbar toggleable="lg" :class="{ bg_navbar: scrollPosition > 0 }">
        <nuxt-link to="/">
          <img class="logo1" src="../assets/image/logo/logo.png" />
          <img class="logo2" src="../assets/image/logo/logo2.png" />
        </nuxt-link>

        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

        <b-collapse id="nav-collapse" is-nav>
          <b-navbar-nav class="ml-auto">
            <div style="width: 400px; height: 70px">
              <img class="iconSearch" src="../assets/icon/search-dr.png" />
              <b-form-input
                class="inputSearch p"
                placeholder="ค้นหาข้อความ"
              ></b-form-input>
              <b-input-group-append>
                <b-button class="btn-search p">ค้นหา</b-button>
              </b-input-group-append>
            </div>
            <!-- <b-input-group style="width: 401px">
              <img class="iconSearch" src="../assets/icon/search.png" />
              <b-form-input
                type="text"
                class="inputSearch p"
                placeholder="ค้นหาข้อความ"
              />
              <b-button class="btn-search p" type="button">ค้นหา</b-button>
            </b-input-group> -->
            <!-- <div style="width: 70px">
              <img class="iconCart" src="../assets/icon/cart.png" />
              <button class="numberNoti h6">100</button>
            </div>
            <div style="width: 60px">
              <img class="iconNoti" src="../assets/icon/notification.png" />
              <button class="numberNoti2 h6">10</button>
            </div>
            <div style="width: 140px" data-toggle="modal" data-target="#login">
              <img class="iconNoti" src="../assets/icon/notification.png" />
              <button class="login h6">Login</button>
            </div> -->
          </b-navbar-nav>
        </b-collapse>
      </b-navbar>
    </div>
  </div>
</template>

<script>
import Vue from 'vue'
import vuescroll from 'vue-scroll'
import BirthDatepicker from 'vue-birth-datepicker'

Vue.use(vuescroll)
export default {
  data() {
    return {
      scrollPosition: null,
      email: '',
      password: '',
      checkPassword: '',
      passwordVisible: false,
      submitted: false,
      agreements: [],
      rules: [
        { message: 'ตัวอักษรพิมพ์เล็กอย่างน้อย 1 ตัว', regex: /[a-z]+/ },
        { message: 'ตัวอักษรพิมพ์เล็กอย่างใหญ่ 1 ตัว', regex: /[A-Z]+/ },
        { message: 'ต้องมีอย่างน้อย 8 ตัวอักษร', regex: /.{8,}/ },
        { message: 'ตัวเลข อย่างน้อย 1 ตัว', regex: /[0-9]+/ },
      ],
    }
  },
  methods: {
    updateScroll() {
      this.scrollPosition = window.scrollY
    },
    resetPasswords() {
      this.email = ''
      this.name = ''
      this.password = ''
      this.checkPassword = ''
      this.submitted = true
      setTimeout(() => {
        this.submitted = false
      }, 2000)
    },
  },
  mounted() {
    window.addEventListener('scroll', this.updateScroll)
  },
  computed: {
    checkEmail() {
      return this.email == ''
    },
    checkPasswordLogin() {
      return this.password == ''
    },
    notSamePasswords() {
      if (this.passwordsFilled) {
        return this.password !== this.checkPassword
      } else {
        return false
      }
    },
    passwordsFilled() {
      return this.password !== '' && this.checkPassword !== ''
    },
    passwordValidation() {
      let errors = []
      for (let condition of this.rules) {
        if (!condition.regex.test(this.password)) {
          errors.push(condition.message)
        }
      }
      if (errors.length === 0) {
        return { valid: true, errors }
      } else {
        return { valid: false, errors }
      }
    },
    acceptAgreementFilled() {
      return this.agreements == ''
    },
    checkEmailFilled() {
      return this.email == ''
    },
  },
  components: {
    BirthDatepicker,
  },
}
</script>

<style scoped>
@media screen and (min-width: 1200px) {
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

  #navbar {
    position: fixed;
    width: 100%;
    z-index: 10;
  }

  .bg_navbar {
    -webkit-transition: background-color 1s ease-out;
    -moz-transition: background-color 1s ease-out;
    -o-transition: background-color 1s ease-out;
    transition: background-color 1s ease-out;
    background-color: #141621;
    box-shadow: 0 3px 6px 0 rgba(0, 0, 0, 0.42);
  }

  .logo1 {
    height: 49px;
  }
  .logo2 {
    height: 18px;
  }

  .inputSearch {
    font-family: 'kanitlight';
    font-size: 16px;
    color: #fff;
    width: 300px;
    height: 43px;
    margin-top: -5px;
    padding: 0 0 0 40px;
    background-color: rgba(255, 255, 255, 0.342);
    border-radius: 7px 0 0 7px;
    border: solid 1px #ffffff;
  }

  .inputSearch::placeholder {
    color: #fff;
  }

  .btn-search {
    font-family: 'kanitregular';
    color: #fff;
    width: 89px;
    height: 43px;
    position: relative;
    top: -43px;
    left: 280px;
    border-radius: 7px;
    border: solid 1px #ffffff;
    background-color: #399cff;
  }

  .iconSearch {
    position: relative;
    width: 17.9px;
    height: 18.4px;
    top: 27px;
    left: 10px;
  }
  .iconCart {
    width: 52px;
    height: 54px;
    margin: 12px 0 0 10px;
    cursor: pointer;
  }

  .numberNoti {
    font-family: 'kanitregular';
    color: #fff;
    background-color: #d50915;
    border-radius: 25px;
    border: none;
    line-height: 1;
    padding-bottom: 2px;
    position: relative;
    /* z-index: 12; */
    top: -55px;
    left: 45px;
  }

  .iconNoti {
    width: 52px;
    height: 54px;
    margin: 12px 0 0 0;
    cursor: pointer;
  }
  .numberNoti2 {
    font-family: 'kanitregular';
    color: #fff;
    background-color: #d50915;
    border-radius: 25px;
    border: none;
    line-height: 1;
    padding-bottom: 2px;
    position: relative;
    /* z-index: 12; */
    top: -55px;
    left: 40px;
  }

  .login {
    font-family: 'kanitregular';
    color: #fff;
    background-color: #399cff;
    border-radius: 7px 7px 7px 0;
    border: none;
    position: relative;
    /* z-index: 15; */
    top: -10px;
    left: -15px;
  }

  .login {
    outline: none;
  }

  /* Modal */
  .imgModal {
    width: 174px;
    height: 42px;
    margin-top: 18px;
  }

  .imgCloseModal {
    position: absolute;
    top: 35px;
    right: 20px;
    cursor: pointer;
  }

  .topnav {
    height: 90px;
  }

  .topnav a {
    margin-top: 32px;
    font-family: 'kanitmedium';
    font-size: 13px;
    color: #989898;
    border-bottom: solid 4px #fff;
    padding: 15px 0;
    line-height: 0;
  }

  .topnav a.active {
    border-bottom: solid 3px #2d3359;
    color: #2d3359;
    z-index: 1;
  }

  /* .topnav a::after {
        margin-top: 18px;
        content: '';
        display: block;
        width: 0;
        height: 4px;
        background: #2d3359;
        transition: width .3s;
        z-index: 0;
    }

    .topnav a:hover::after {
        width: 100%;
    } */

  .line {
    width: 94%;
    height: 1px;
    opacity: 0.3;
    background-color: #707070;
    position: absolute;
    top: 63px;
    left: 18px;
    z-index: 0;
  }

  .titleInput {
    margin-left: 5px;
    font-family: 'kanitmedium';
    font-size: 13px;
    color: #989898;
  }

  .inputField {
    width: 100%;
    height: 46px;
    margin: 0 15.6px 0 0;
    object-fit: contain;
    border-radius: 6px;
    border: solid 1px #989898;
    background-color: #e3e3e3;
    font-family: 'kanitmedium';
    color: #5a5f83;
    font-size: 13px;
  }

  .inputField::placeholder {
    color: #5a5f83;
  }
  .inputField:focus {
    border: solid 1px #989898;
    background-color: #e3e3e3;
    color: #5a5f83;
    /* outline: none; */
    box-shadow: none;
  }

  .forgotPassword {
    font-family: 'kanitmedium';
    font-size: 13px;
    text-decoration: underline;
    color: #cca343;
    line-height: 0;
  }

  .btnlogin {
    font-family: 'kanitmedium';
    font-size: 13px;
    color: #fff;
    height: 46px;
    width: 100%;
    border-radius: 12px;
    box-shadow: 0 10px 15px 0 rgba(26, 64, 149, 0.25);
    border: solid 2px #4e7bf7;
    background-color: #4e7bf7;
  }

  .btnloginDis {
    opacity: 0.5;
  }

  .btnFacebook {
    width: 100%;
    height: 46px;
    margin: 13px 5.5px 13px 0;
    padding: 8px 77.7px 14.3px 61.4px;
    border-radius: 12px;
    box-shadow: 0 10px 15px 0 rgba(26, 64, 149, 0.25);
    border: solid 1px #4e7bf7;
    background-color: #ffffff;
  }

  .btnFacebook a {
    color: #4076ff;
    font-family: 'kanitregular';
    margin-left: 10px;
    font-size: 13px;
    line-height: 0;
    font-weight: 500;
    text-decoration: none;
  }

  .imgFacebook {
    width: 23.3px;
    margin-right: 10px;
  }

  .btnGoogle {
    width: 100%;
    height: 46px;
    margin: 0 5.5px 13px 0;
    padding: 8px 77.7px 14.3px 61.4px;
    border-radius: 12px;
    box-shadow: 0 10px 15px 0 rgba(173, 22, 22, 0.25);
    border: solid 1px#f24250;
    background-color: #ffffff;
  }

  .btnGoogle a {
    color: #f5404b;
    font-family: 'kanitregular';
    margin-left: 10px;
    font-size: 13px;
    line-height: 0;
    font-weight: 500;
    text-decoration: none;
  }

  .error {
    font-family: 'kanitmedium';
    font-size: 13px;
    color: #d80d0d;
  }

  .titlePassword {
    font-family: 'kanitmedium';
    font-size: 13px;
    color: #989898;
  }

  .hints {
    color: #989898;
    font-size: 12px;
    font-family: 'kanitlight';
    margin-left: 5px;
  }

  input:focus {
    outline: none;
  }

  button:focus {
    outline: none;
  }

  .accept {
    vertical-align: text-top;
    padding-top: 3px;
    font-family: 'kanitmedium';
    font-size: 12px;
    line-height: 1.2;
    color: #989898;
    width: 90%;
  }

  .acceptDes {
    font-family: 'kanitlight';
    font-size: 12px;
    color: #989898;
    margin: 0;
  }
}
</style>
