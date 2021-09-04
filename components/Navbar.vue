<template>
  <nav class="navbar navbar-expand-lg navbar-dark">
    <!-- :class="positionScroll > 20 ? 'bg-black' : ''" -->
    <div class="container px-0">
      <div>
        <a class="navbar-brand mx-2" href="/"
          ><img src="~/assets/image/flex2.png" class="w-logo" alt=""
        /></a>
      </div>
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarSupportedContent"
        aria-controls="navbarSupportedContent"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div
        class="collapse navbar-collapse mt-mobile"
        id="navbarSupportedContent"
      >
        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
          <!-- <li class="nav-item me-5">
            <nuxt-link
              :class="
                $route.hash == '#work'
                  ? 'nav-link active fw-bolder text-light font18 letter-normal px-nav'
                  : 'nav-link  text-light font18 letter-normal px-nav'
              "
              :to="$route.name !== 'Contact' ? '#work' : '/'"
              >WORK</nuxt-link
            >
          </li> -->
          <li class="nav-item dropdown me-5">
            <a
              @click="showBar()"
              class="nav-link  text-light font18 letter-normal px-nav"
              :class="$route.hash == '#work' ? 'active fw-bolder' : ''"
              href="/"
              :id="
                $route.name !== 'contact' &&
                $route.name !== 'filmingduringcovid' &&
                $route.name !== 'services'
                  ? 'navbarDropdown'
                  : ''
              "
              :role="
                $route.name !== 'contact' &&
                $route.name !== 'filmingduringcovid' &&
                $route.name !== 'services'
                  ? 'button'
                  : ''
              "
              :data-bs-toggle="
                $route.name !== 'contact' &&
                $route.name !== 'filmingduringcovid' &&
                $route.name !== 'services'
                  ? 'dropdown'
                  : ''
              "
              :aria-expanded="
                $route.name !== 'contact' &&
                $route.name !== 'filmingduringcovid' &&
                $route.name !== 'services'
                  ? 'false'
                  : ''
              "
            >
              WORK
            </a>
            <ul
              class="dropdown-menu  bg-transparent"
              :class="flex ? 'flex-responsive' : ''"
              aria-labelledby="navbarDropdown"
            >
              <li v-for="(item, i) in categories" :key="i">
                <a
                  class="dropdown-item text-white"
                  @click="sendCategory(item.id)"
                  href="#work"
                  >{{ item.name }}</a
                >
              </li>
            </ul>
          </li>
          <li class="nav-item me-5">
            <nuxt-link
              class="nav-link  text-light font18 letter-normal px-nav"
              :class="$route.hash == '#story' ? 'active fw-bolder' : ''"
              :to="
                $route.name !== 'contact' &&
                $route.name !== 'filmingduringcovid' &&
                $route.name !== 'services'
                  ? '#story'
                  : '/'
              "
              >FLEX STORY</nuxt-link
            >
          </li>
          <li class="nav-item me-5">
            <nuxt-link
              class="nav-link  text-light font18 letter-normal px-nav"
              :class="active == 'services' ? 'active fw-bolder' : ''"
              to="/services"
              >SERVICES</nuxt-link
            >
          </li>
          <li class="nav-item me-5">
            <nuxt-link
              class="nav-link  text-light font18 letter-normal px-nav"
              :class="active == 'contact' ? 'active fw-bolder' : ''"
              to="/contact"
              >CONTACT</nuxt-link
            >
          </li>
          <li class="nav-item me-5" v-if="titleNavbar !== 'kosong'">
            <nuxt-link
              class="nav-link  text-light font18 letter-normal px-nav"
              :class="active == 'filmingduringcovid' ? 'active fw-bolder' : ''"
              to="/filmingduringcovid"
              >FILMING DURING COVID-19</nuxt-link
            >
          </li>
        </ul>
        <!-- <button
          @click="openModal"
          data-bs-toggle="modal"
          data-bs-target="#modalContact"
          class="btn btn-theme px-4 fw-light rounded-pill"
          type="button"
        >
          GET IN TOUCH
        </button> -->
      </div>
    </div>
  </nav>
</template>
<script>
import axios from "axios";
export default {
  props: ["active", "categories"],
  data() {
    return {
      positionScroll: 0,
      flex: false,
      titleNavbar: ""
    };
  },
  methods: {
    openModal() {
      this.$emit("openModal", true);
    },
    cek() {
      console.log(this.$route.hash, "routetteeee");
    },
    updateScroll() {
      this.positionScroll = window.scrollY;
    },
    sendCategory(list) {
      this.$emit("getProject", list);
      this.showBar();
    },
    showBar() {
      this.flex = !this.flex;
    },
    async getCovid() {
      const { data } = await axios.get(
        `https://service.flx.asia/api/v1/navbar?active=true`
      );
      console.log(data[0].name, "data covid");
      this.titleNavbar = data.length == 0 ? "kosong" : data[0].name;
    }
  },
  mounted() {
    this.cek();
    this.getCovid();
    window.addEventListener("scroll", this.updateScroll);
  }
};
</script>
<style scoped>
.bg-black {
  background-color: black;
}
.dropdown-item:focus,
.dropdown-item:hover {
  color: white !important;
  background-color: transparent !important;
}
.flex-responsive {
  display: flex;
  flex-direction: row;
}
.w-logo {
  width: 25%;
}
@media only screen and (min-device-width: 320px) and (max-device-width: 480px) {
  .w-logo {
    width: 15%;
  }
  .flex-responsive {
    display: flex;
    flex-direction: column;
  }
  .mt-mobile {
    margin-top: 1.5rem;
  }
  .px-nav {
    padding-left: 1rem;
  }
}
</style>
