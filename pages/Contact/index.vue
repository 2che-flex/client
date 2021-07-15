<template>
  <div class="px-0 overflow-hidden bg-black" style="height:100vh">
    <!-- START: NAVBAR -->
    <div class="container"><Navbar :active="'Contact'" /></div>
    <!-- END: NAVBAR -->

    <!-- START: TEAM -->
    <div class="mt-5">
      <h1 class="fw-bolder letter-normal text-center text-light">
        Meet Our Team
      </h1>
      <div class="row row-cols-1 row-cols-lg-3  mt-4  mx-auto ">
        <div class="col position-relative mx-0 px-0">
          <div class="card border-n" style="border-radius:0px">
            <div class="bg-black position-absolute inset-0 op-2"></div>
            <img
              src="~/assets/image/novin.png"
              style="height:40vh"
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
              style="height:40vh"
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
              style="height:40vh"
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
    <!-- START: OFFICE -->
    <div class="mt-5">
      <h1 class="fw-bolder letter-normal text-center text-light">
        OUR OFFICE
      </h1>
      <div class="w-responsive px-responsive mx-auto mt-4">
        <h5
          class="text-responsive font16 font18-mobile text-light fw-light l-42 letter-extra"
        >
          Citylofts 920 Jl. KH. Mas Mansyur Kav.121 <br />
          Jakarta 10220, Indonesia
        </h5>
      </div>
    </div>
    <!-- END: OFFICE -->
    <!-- START: FOOTER -->
    <div class="">
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
