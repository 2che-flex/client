<template>
  <div class="px-0 overflow-hidden bg-black h-responsive">
    <!-- START: NAVBAR -->
    <div class="container"><Navbar :active="'Contact'" /></div>
    <!-- END: NAVBAR -->

    <!-- START: TEAM -->
    <div class="mt-titleV2">
      <h1
        class="fw-bolder font30 font28-mobile letter-normal text-center text-light"
      >
        Meet Our Team
      </h1>
      <div class="container mt-4">
        <div class="row">
          <div
            class="col-md-4 col-12 justify-center mb-mobile"
            v-for="(item, i) in dataContact"
            :key="i"
          >
            <h1
              class="text-white text-center fw-bold font18 font16-mobile mb-1"
            >
              {{ item.name }}
            </h1>
            <p class="fw-lighter text-center text-white mb-0">
              {{ item.role }}
            </p>
            <div class="d-flex align-items-center justify-content-center mt-3">
              <!-- <img src="~/assets/icon/telepon.svg" alt="" /> -->
              <p class="text-light mb-0 font15">{{ item.phone_number }}</p>
            </div>
            <div class="d-flex align-items-center justify-content-center mt-1">
              <!-- <img src="~/assets/icon/gmail3.svg" alt="" /> -->
              <p class="text-light mb-0 font15 mb-0">{{ item.email }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
    <!-- END: TEAM -->
    <!-- START: OFFICE -->
    <div class="mt-titleV2">
      <h1
        class="fw-bolder font30 font28-mobile letter-normal text-center text-light"
      >
        OUR OFFICE
      </h1>
      <div class="w-responsive px-responsive mx-auto mt-3">
        <h5
          class="text-center font16 font18-mobile text-light fw-light l-42 letter-extra"
        >
          Citylofts 920 Jl. KH. Mas Mansyur Kav.121 <br />
          Jakarta 10220, Indonesia
        </h5>
        <div class="text-center mt-4 mb-5">
          <button
            data-bs-toggle="modal"
            data-bs-target="#modalContact"
            class="btn btn-theme px-4 fw-light rounded-pill"
            type="submit"
          >
            <a
              target="blank"
              class="text-white text-decoration-none"
              href="https://goo.gl/maps/BeJUUXmT1xMJQkMW7"
              >Get Directions</a
            >
          </button>
        </div>
      </div>
    </div>
    <!-- END: OFFICE -->
    <!-- START: FOOTER -->
    <div class="mt-5">
      <div class="mx-auto">
        <Footer />
      </div>
    </div>
    <!-- END: FOOTER  -->
  </div>
</template>
<script>
import axios from "axios";
export default {
  data() {
    return {
      dataContact: []
    };
  },
  methods: {
    async getContact() {
      const { data } = await axios.get(
        "https://server-flex.herokuapp.com/api/v1/contact"
      );
      this.dataContact = data.users;
      console.log(data.users, "arinda contact");
    }
  },
  mounted() {
    this.getContact();
  }
};
</script>
<style scoped>
.mt-titleV2 {
  margin-top: 3rem;
}
.mt-content {
  margin-top: 8rem;
}
.h-responsive {
  height: 100vh;
}
@media only screen and (min-device-width: 320px) and (max-device-width: 480px) {
  .mt-titleV2 {
    margin-top: 3rem;
  }
  .h-responsive {
    height: auto;
  }
  .mt-title {
    margin-top: 2rem;
  }
  .mt-content {
    margin-top: 4rem;
  }
  .mb-mobile {
    margin-bottom: 3rem;
  }
}
</style>
