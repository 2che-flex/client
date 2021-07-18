<template>
  <div class="px-0 overflow-hidden bg-black h-responsive">
    <!-- START: NAVBAR -->
    <div class="container"><Navbar :active="'Contact'" /></div>
    <!-- END: NAVBAR -->

    <!-- START: TEAM -->
    <div class="mt-title">
      <h1
        class="fw-bolder font30 font28-mobile letter-normal text-center text-light"
      >
        Meet Our Team
      </h1>
      <div class="container mt-5">
        <div class="row">
          <div class="col-md-4 col-12 justify-center mb-mobile">
            <h1
              class="text-white text-center fw-bold font20 font18-mobile mb-1"
            >
              Novindra Christian
            </h1>
            <p class="fw-lighter text-center text-white mb-0">
              The Crazy Boss
            </p>
            <div class="d-flex align-items-center justify-content-center mt-3">
              <!-- <img src="~/assets/icon/telepon.svg" alt="" /> -->
              <p class="text-light mb-0  font16">081386465464</p>
            </div>
            <div class="d-flex align-items-center justify-content-center mt-1">
              <!-- <img src="~/assets/icon/gmail3.svg" alt="" /> -->
              <p class="text-light mb-0 font16 mb-0">flex@email.com</p>
            </div>
          </div>
          <div class="col-md-4 col-12 justify-center mb-mobile">
            <h1
              class="text-white text-center fw-bold font20 font18-mobile mb-1"
            >
              Floris Kingma
            </h1>
            <p class="fw-lighter text-center text-white mb-0">
              Film Director
            </p>
            <div class="d-flex align-items-center justify-content-center mt-3">
              <!-- <img src="~/assets/icon/telepon.svg" alt="" /> -->
              <p class="text-light mb-0  font16">081386465464</p>
            </div>
            <div class="d-flex align-items-center justify-content-center mt-1">
              <!-- <img src="~/assets/icon/gmail3.svg" alt="" /> -->
              <p class="text-light mb-0 font16 mb-0">flex@email.com</p>
            </div>
          </div>
          <div class="col-md-4 col-12 justify-center mb-mobile">
            <h1
              class="text-white text-center fw-bold font20 font18-mobile mb-1"
            >
              Michael Sewandono
            </h1>
            <p class="fw-lighter text-center text-white mb-0">
              Film Director
            </p>
            <div class="d-flex align-items-center justify-content-center mt-3">
              <!-- <img src="~/assets/icon/telepon.svg" alt="" /> -->
              <p class="text-light mb-0  font16">081386465464</p>
            </div>
            <div class="d-flex align-items-center justify-content-center mt-1">
              <!-- <img src="~/assets/icon/gmail3.svg" alt="" /> -->
              <p class="text-light mb-0 font16 mb-0">flex@email.com</p>
            </div>
          </div>
        </div>
      </div>
    </div>
    <!-- END: TEAM -->
    <!-- START: OFFICE -->
    <div class="mt-content">
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
<style scoped>
.mt-title {
  margin-top: 5rem;
}
.mt-content {
  margin-top: 8rem;
}
.h-responsive {
  min-height: 100vh;
}
@media only screen and (min-device-width: 320px) and (max-device-width: 480px) {
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
