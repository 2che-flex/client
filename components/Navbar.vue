<template>
  <nav
    class="navbar navbar-expand-lg navbar-dark"
    :class="positionScroll > 20 ? 'bg-black' : ''"
  >
    <div class="container px-0">
      <a class="navbar-brand me-0" href="/"
        ><img src="~/assets/image/LogoFlex.png" class="w-50" alt=""
      /></a>
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
              :id="$route.name !== 'Contact' ? 'navbarDropdown' : ''"
              :role="$route.name !== 'Contact' ? 'button' : ''"
              :data-bs-toggle="$route.name !== 'Contact' ? 'dropdown' : ''"
              :aria-expanded="$route.name !== 'Contact' ? 'false' : ''"
            >
              WORK
            </a>
            <ul
              class="dropdown-menu bg-black"
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
              :to="$route.name !== 'Contact' ? '#story' : '/'"
              >FLEX STORY</nuxt-link
            >
          </li>
          <li class="nav-item me-5">
            <nuxt-link
              class="nav-link  text-light font18 letter-normal px-nav"
              :class="active == 'Contact' ? 'active fw-bolder' : ''"
              to="/Contact"
              >CONTACT</nuxt-link
            >
          </li>
          <li class="nav-item me-5">
            <nuxt-link
              class="nav-link  text-light font18 letter-normal px-nav"
              :class="active == 'Contact' ? 'active fw-bolder' : ''"
              to="/Contact"
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
export default {
  props: ["active", "categories"],
  data() {
    return {
      positionScroll: 0,
      flex: false
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
    },
    showBar() {
      this.flex = !this.flex;
    }
  },
  mounted() {
    this.cek();
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
  background-color: #0e0e0e !important;
}
.flex-responsive {
  display: flex;
  flex-direction: row;
}
@media only screen and (min-device-width: 320px) and (max-device-width: 480px) {
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
