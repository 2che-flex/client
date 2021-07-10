<template>
  <div class="px-0 overflow-hidden bg-black">
    <!-- START: NAVBAR -->
    <div class="container"><Navbar :active="'Contact'" /></div>
    <!-- END: NAVBAR -->
    <!-- START: WHERE -->
    <div class="mt-title">
      <h1 class="fw-bolder letter-normal text-center text-light">
        POPULAR WORK
      </h1>
      <div class="w-responsive px-responsive mx-auto mt-4">
        <h5
          class="text-responsive font22 font18-mobile text-light fw-light l-42 letter-extra"
        >
          Citylofts 920 Jl. KH. Mas Mansyur <br />
          Kav.121 Jakarta 10220, Indonesia
        </h5>
        <div class="d-flex justify-content-center mt-4">
          <iframe
            src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3966.413854483472!2d106.81621051486623!3d-6.209018662548826!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x2e69f40284aeba2d%3A0x8523f9ff207a98e7!2sCItywalk%20Sudirman!5e0!3m2!1sid!2sid!4v1625755345511!5m2!1sid!2sid"
            width="600"
            height="450"
            style="border:0;"
            allowfullscreen=""
            loading="lazy"
          ></iframe>
        </div>
      </div>
    </div>
    <!-- END: WHERE -->
    <!-- START: TEAM -->
    <div class="mt-content">
      <h1 class="fw-bolder letter-normal text-center text-light">
        Meet Our Team
      </h1>
      <div class="row row-cols-1 row-cols-lg-3  mt-4 container mx-auto ">
        <div class="col position-relative mx-0 px-0">
          <div class="card border-n" style="border-radius:0px">
            <div class="bg-black position-absolute inset-0 op-2"></div>
            <img
              src="~/assets/image/novin.png"
              style="height:45vh"
              class="card-img-top w-100"
              alt="..."
            />
            <div class="card-body text-card">
              <h1 class="text-white fw-bold font24 mb-1">
                Novindra <br />
                Christian
              </h1>
              <p class="fw-lighter text-white">
                The Crazy Boss
              </p>
              <div class="d-flex align-items-center mt-3">
                <img src="~/assets/icon/telepon.svg" alt="" />
                <p class="text-light mb-0 ms-3 font16">081386465464</p>
              </div>
              <div class="d-flex align-items-center mt-2">
                <img src="~/assets/icon/gmail3.svg" alt="" />
                <p class="text-light mb-0 ms-3 font16 mb-0">flex@email.com</p>
              </div>
            </div>
          </div>
        </div>
        <div class="col position-relative mx-0 px-0">
          <div class="card border-n" style="border-radius:0px">
            <div class="bg-black position-absolute inset-0 op-2"></div>
            <img
              src="~/assets/image/floris.png"
              style="height:45vh"
              class="card-img-top w-100"
              alt="..."
            />
            <div class="card-body text-card">
              <h1 class="text-white fw-bold font24 mb-1">
                Floris <br />
                Kingma
              </h1>
              <p class="fw-lighter text-white">
                Film Director
              </p>
              <div class="d-flex align-items-center mt-3">
                <img src="~/assets/icon/telepon.svg" alt="" />
                <p class="text-light mb-0 ms-3 font16">081386465464</p>
              </div>
              <div class="d-flex align-items-center mt-2">
                <img src="~/assets/icon/gmail3.svg" alt="" />
                <p class="text-light mb-0 ms-3 font16 mb-0">flex@email.com</p>
              </div>
            </div>
          </div>
        </div>
        <div class="col position-relative mx-0 px-0">
          <div class="card border-n" style="border-radius:0px">
            <div class="bg-black position-absolute inset-0 op-2"></div>
            <img
              src="~/assets/image/michael.png"
              style="height:45vh"
              class="card-img-top w-100"
              alt="..."
            />
            <div class="card-body text-card">
              <h1 class="text-white fw-bold font24 mb-1">
                Michael <br />
                Sewandono
              </h1>
              <p class="fw-lighter text-white">
                Film Director
              </p>
              <div class="d-flex align-items-center mt-3">
                <img src="~/assets/icon/telepon.svg" alt="" />
                <p class="text-light mb-0 ms-3 font16">081386465464</p>
              </div>
              <div class="d-flex align-items-center mt-2">
                <img src="~/assets/icon/gmail3.svg" alt="" />
                <p class="text-light mb-0 ms-3 font16 mb-0">flex@email.com</p>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="w-responsive px-responsive mx-auto mt-4"></div>
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
<style scoped>
.mt-title {
  margin-top: 5rem;
}
.mt-content {
  margin-top: 8rem;
}
@media only screen and (min-device-width: 320px) and (max-device-width: 480px) {
  .mt-title {
    margin-top: 2rem;
  }
  .mt-content {
    margin-top: 4rem;
  }
}
</style>
