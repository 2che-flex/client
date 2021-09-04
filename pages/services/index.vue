<template>
  <div class="px-0 overflow-hidden bg-black h-responsive">
    <!-- START: NAVBAR -->
    <div class="container">
      <Navbar :active="'services'" />
    </div>
    <!-- END: NAVBAR -->

    <!-- START: TEAM -->
    <div class="mt-titleV2">
      <h1
        class="fw-bolder font30 font28-mobile letter-normal text-center text-light"
      >
        SERVICES
      </h1>
      <div class="container mt-4">
        <div class="col-md-8 col-12 px-3 mx-auto mt-4">
          <p
            class="text-responsive text-light fw-light"
            v-html="textServices"
          ></p>
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
      textServices: ""
    };
  },
  methods: {
    async getServices() {
      const { data } = await axios.get(
        `https://service.flx.asia/api/v1/services`
      );
      this.textServices = data.texts[0].textHtml;
    }
  },
  mounted() {
    this.getServices();
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
