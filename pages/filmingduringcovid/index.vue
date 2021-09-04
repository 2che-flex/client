<template>
  <div class="px-0 overflow-hidden bg-black h-responsive">
    <!-- START: NAVBAR -->
    <div class="container">
      <Navbar :active="'filmingduringcovid'" />
    </div>
    <!-- END: NAVBAR -->

    <!-- START: TEAM -->
    <div class="mt-titleV2">
      <h1
        class="fw-bolder font30 font28-mobile letter-normal text-center text-light"
      >
        FILMING DURING COVID
      </h1>
      <div class="container mt-4">
        <div class="col-md-8 col-12 px-3 mx-auto mt-4">
          <p class="text-responsive text-light fw-light" v-html="textCovid"></p>
        </div>
      </div>
    </div>
    <!-- END: TEAM -->
    <!-- START: FOOTER -->
    <div class="mt-footer">
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
      dataContact: [],
      titleNavbar: "",
      textCovid: ""
    };
  },
  methods: {
    async getCovid() {
      const { data } = await axios.get(
        `https://service.flx.asia/api/v1/navbar?active=true`
      );
      console.log(data[0].name, "data covid");
      this.titleNavbar = data.length == 0 ? "kosong" : data[0].name;
      this.textCovid = data.length == 0 ? "-" : data[0].textHtml;
    }
  },
  mounted() {
    this.getCovid();
  }
};
</script>
<style scoped>
.mt-titleV2 {
  margin-top: 3.5rem;
}
.mt-content {
  margin-top: 8rem;
}
.h-responsive {
  min-height: 100vh;
}
.mt-footer {
  margin-top: 6rem;
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
