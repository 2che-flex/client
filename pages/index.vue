<template>
  <div class="px-0 overflow-hidden bg-black">
    <!-- START: NAVBAR -->
    <div class="position-absolute container inset-0">
      <Navbar :active="'Home'" />
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
      <div class="container mx-auto" v-if="data.length > 0">
        <VueSlickCarousel v-bind="settings" :dots="true" :arrows="true">
          <div v-for="(item, i) in data" :key="i">
            <Card
              :title="item.title"
              :description="item.description"
              :url="item.url"
              :type="item.type"
            />
          </div>
        </VueSlickCarousel>
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
import VueSlickCarousel from "vue-slick-carousel";
import "vue-slick-carousel/dist/vue-slick-carousel.css";
// optional style for arrows & dots
import "vue-slick-carousel/dist/vue-slick-carousel-theme.css";
import axios from "axios";
export default {
  components: { VueSlickCarousel },
  data() {
    return {
      settings: {
        infinite: true,
        slidesToShow: 3,
        speed: 500,
        rows: 2,
        slidesPerRow: 1,
        responsive: [
          {
            breakpoint: 1024,
            settings: {
              slidesToShow: 3,
              slidesToScroll: 3,
              infinite: true,
              dots: true
            }
          },
          {
            breakpoint: 600,
            settings: {
              slidesToShow: 2,
              slidesToScroll: 2,
              initialSlide: 2
            }
          },
          {
            breakpoint: 480,
            settings: {
              slidesToShow: 1,
              slidesToScroll: 1
            }
          }
        ]
      },
      data: []
    };
  },
  methods: {
    getProject() {
      console.log("wkkwkw");
      axios
        .get(`https://server-flex.herokuapp.com/api/v1`)
        .then(res => {
          console.log(res.data.items, "wkwk");
          this.data = res.data.items;
        })
        .catch(err => console.log(err));
    }
  },
  mounted() {
    this.getProject();
  }
};
</script>

<style></style>
