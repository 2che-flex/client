<template>
  <div class="px-0 overflow-hidden bg-black">
    <!-- START: NAVBAR -->
    <div class="position-absolute container inset-0">
      <Navbar />
    </div>
    <!-- END: NAVBAR -->
    <!-- START: HERO SECTION -->
    <section class="">
      <img src="~/assets/image/img-hero.png" class="img-hero" alt="" />
    </section>
    <!-- END: HERO SECTION -->

    <!-- START: POPULAR WORK -->
    <div class="mt-title" data-aos="fade-up" data-aos-duration="3000">
      <h1 class="fw-bolder letter-normal text-center text-light">
        POPULAR WORK
      </h1>
      <div
        class="row row-cols-1 row-cols-lg-3  g-2 g-lg-3 mt-5 container mx-auto "
      >
        <div class="col">
          <Card />
        </div>
        <div class="col">
          <Card />
        </div>
        <div class="col">
          <Card />
        </div>
        <div class="col">
          <Card />
        </div>
        <div class="col">
          <Card />
        </div>
        <div class="col">
          <Card />
        </div>
      </div>
    </div>
    <!-- END: POPULAR WORK -->
    <!-- START: WE ARE FLEX -->
    <div class="mt-content" data-aos="fade-up" data-aos-duration="3000">
      <h1 class="text-center text-white px-2">WE ARE FLEX</h1>
      <div class="w-responsive px-responsive mx-auto mt-4">
        <p class="text-responsive text-light fw-light">
          Flex Films is a full service production company based in Jakarta,
          Indonesia. We have a passion in communicating ideas into a meaningful
          stories. Your business is a unique idea, different from your
          competitors.
        </p>
        <p class="text-responsive text-light mt-3 fw-light">
          Flex Films role is to create the best solution to maximise your target
          audience and its effectiveness. We do this by understanding your
          business, it’s personality and values in order to develop a visual
          stories to connect with your target audience.
        </p>
        <p class="text-responsive text-light mt-3 fw-light">
          The awards we've ever received are 1 Gold, 2 Silver, 3 Bronze (
          Tokobagus.com Living Room CITRA PARIWARA 2015 ) & Production House Of
          The Year ( Citra Pariwara 2015 )
        </p>
      </div>
    </div>
    <!-- END: WE ARE FLEX -->
    <!-- START: INTERESTED -->
    <div class="mt-content" data-aos="fade-up" data-aos-duration="3000">
      <h1 class="text-center text-white px-responsive">
        Interested to Work With Us ?
      </h1>
      <div class="w-responsive  mx-auto mt-4">
        <p class="text-responsive text-light fw-light px-responsive">
          Ready to take it a step further? Let’s start talking about your
          project or idea and find out how FLEX Films can help your brand grow.
        </p>
        <div class="text-center mt-5">
          <button
            class="btn btn-theme px-4 fw-light rounded-pill"
            type="submit"
          >
            Let's Talk
          </button>
        </div>
      </div>
    </div>
    <!-- END: INTERESTED -->
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
export default {};
</script>

<style scoped>
@media only screen and (min-device-width: 320px) and (max-device-width: 480px) {
}
</style>
