<template>
  <div class="px-0 overflow-hidden bg-black">
    <!-- START: NAVBAR -->
    <div class="position-relative">
      <div class="position-fixed top-0 start-0 end-0" style="z-index:9999">
        <Navbar
          @getProject="getProject"
          :categories="dataCategories"
          :active="'Home'"
          @openModal="openModal"
        />
      </div>
    </div>
    <!-- END: NAVBAR -->
    <!-- START: HERO SECTION -->
    <section v-if="dataBanner.length > 0">
      <!-- <img src="~/assets/image/img-hero.png" class="img-hero" alt="" /> -->
      <div class="coverBanner"></div>
      <div v-if="dataBanner[0].show !== 'photo'">
        <video autoplay muted loop id="myVideo">
          <source :src="dataBanner[0].video_url" type="video/mp4" />
          Your browser does not support HTML5 video.
        </video>
      </div>
      <div v-else>
        <img :src="dataBanner[0].imageData" class="img-hero" alt="" />
      </div>
    </section>
    <!-- END: HERO SECTION -->

    <!-- START: POPULAR WORK -->
    <div class="mt-contentv2" id="work">
      <!-- <h1
        class="fw-bolder font30 font28-mobile letter-normal text-center text-white"
      >
        POPULAR WORK
      </h1> -->
      <div class="mt-4 mx-auto px-slider" v-if="data.length > 0">
        <VueSlickCarousel v-bind="settings" :dots="true" :arrows="true">
          <div v-for="(item, i) in data" :key="i">
            <Card
              data-bs-toggle="modal"
              data-bs-target="#modalDetail"
              @showDetail="showDetail"
              :title="item.title"
              :description="item.description"
              :url="item.imageData"
              :type="item.type"
              :videoUrl="item.video_url"
            />
          </div>
        </VueSlickCarousel>
      </div>
      <ModalVideo
        :title="dataTitle"
        :type="dataType"
        :url="dataUrl"
        :description="dataDescription"
        :video="videoLink"
        @recache="recache"
      />
    </div>
    <!-- END: POPULAR WORK -->
    <!-- START: WE ARE FLEX -->

    <!-- data-aos="fade-up"
      data-aos-duration="3000" -->
    <div class="mt-contentv3" id="story">
      <h1 class="text-center text-white px-2 font30 font28-mobile">
        WE ARE FLEX
      </h1>
      <div class="col-md-6 col-12 px-3 mx-auto mt-4">
        <p class="text-responsive text-light fw-light" v-html="dataHistory"></p>
      </div>
    </div>
    <!-- END: WE ARE FLEX -->

    <!-- START: FOOTER -->
    <div class="mb-4">
      <div class="mx-auto">
        <Footer />
      </div>
    </div>
    <!-- END: FOOTER  -->
    <div v-if="modal == true">
      <ModalContact @openModal="openModal" />
      <div class="modal-backdrop fade show"></div>
    </div>
  </div>
</template>

<script>
import VueSlickCarousel from "vue-slick-carousel";
import "vue-slick-carousel/dist/vue-slick-carousel.css";
// optional style for arrows & dots
import axios from "axios";
export default {
  components: { VueSlickCarousel },
  data() {
    return {
      settingsBanner: {
        dotsClass: "slick-dots custom-dot-class",
        edgeFriction: 0.35,
        infinite: false,
        speed: 500,
        slidesToShow: 1,
        slidesToScroll: 1
      },
      settings: {
        dots: true,
        infinite: true,
        slidesToShow: 3,
        speed: 200,
        rows: 2,
        autoplay: true,
        slidesPerRow: 1
      },
      data: [],
      dataTitle: "",
      dataType: "",
      dataUrl: "",
      dataDescription: "",
      dataBanner: [],
      modal: false,
      videoLink: "",
      dataCategories: [],
      dataHistory: "Waiting"
    };
  },
  methods: {
    test(list) {
      console.log(list, "home");
    },
    async getProject(list) {
      const { data } = await axios.get(`https://service.flx.asia/api/v1`);
      let work = data.items;
      this.data =
        list == undefined ? work : work.filter(e => e.CategoryId == list);
      this.data.length <= 4
        ? (this.settings.slidesToShow = 2)
        : (this.settings.slidesToShow = 3);
      this.data.length <= 2
        ? (this.settings.rows = 1)
        : (this.settings.rows = 2);
    },
    showDetail(title, type, url, description, video) {
      this.dataTitle = title;
      this.dataType = type;
      this.dataUrl = url;
      this.dataDescription = description;
      this.videoLink = video;
    },
    recache() {
      this.dataTitle = "";
      this.dataType = "";
      this.dataUrl = "";
      this.dataDescription = "";
      this.videoLink = "";
    },
    async showBanner() {
      const { data } = await axios.get(
        "https://service.flx.asia/api/v1/banner"
      );
      this.dataBanner = data.videos;
      // console.log(data.videos, "banner");
    },
    async getCategories() {
      const { data } = await axios.get(
        "https://service.flx.asia/api/v1/category"
      );
      // console.log(data.categories, "cate");
      this.dataCategories = [
        ...data.categories,
        {
          id: undefined,
          name: "All"
        }
      ];
    },
    openModal(value) {
      this.modal = value;
    },
    async getHistory() {
      const { data } = await axios.get(
        "https://service.flx.asia/api/v1/story/1"
      );
      console.log(data, "data");
      this.dataHistory = data.textHtml;
    }
  },
  mounted() {
    this.getProject();
    this.showBanner();
    this.getCategories();
    this.getHistory();
  }
};
</script>

<style scoped>
#myVideo {
  right: 0;
  bottom: 0;
  min-width: 100%;
  height: 100vh;
  object-fit: cover;
  background-position: center;
}
.coverBanner {
  position: absolute;
  width: 100%;
  height: 100%;
  background: linear-gradient(180deg, #000000 0%, rgba(0, 0, 0, 0) 161.08%);
  z-index: 999;
  opacity: 0.7;
  -webkit-opacity: 0.7; /* WebKit browser e.g. Safari */
  -khtml-opacity: 0.7;
}
.mt-contentv2 {
  margin-top: 8rem;
}
.mt-contentv3 {
  margin: 12rem 0;
}
.px-slider {
  padding: 0 2.5rem;
}

@media only screen and (min-device-width: 320px) and (max-device-width: 480px) {
  #myVideo {
    width: 100vw;
    height: auto;
    object-fit: cover;
    background-position: center;
  }
  .px-slider {
    padding: 0 1rem;
  }
  .coverBanner {
    position: absolute;
    width: 100%;
    height: 32vh;
    background: linear-gradient(
      180deg,
      #000000 0%,
      rgba(255, 255, 255, 0) 161.08%
    );
    z-index: 999;
    opacity: 0.7;
  }
  .mt-contentv2 {
    margin-top: 5rem;
  }
  .mt-contentv3 {
    margin-top: 7rem;
  }
}
</style>
