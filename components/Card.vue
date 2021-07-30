<template>
  <div
    @click="showDetail()"
    class="card border-n container-image m-card"
    style="border-radius:0px"
  >
    <img :src="url" class="card-img-top w-100 image" :alt="description" />
    <div class="overlay">
      <div class="text">
        <h1
          class="font22 font14-mobile mb-1 fw-bolder"
          style="letter-spacing: 0.05em;"
        >
          {{ title }}
        </h1>
        <p class="font16 font12-mobile mb-0 fw-light">{{ description }}</p>
        <!-- <img class="mt-3" src="~/assets/icon/play.svg" alt="" /> -->
      </div>
    </div>
    <!-- <div class="card-body">
        <p class="card-text">
          Some quick example text to build on the card title and make up the
          bulk of the card's content.
        </p>
      </div> -->
  </div>
</template>
<script>
export default {
  props: ["title", "type", "url", "description", "videoUrl"],
  methods: {
    showDetail() {
      console.log(
        this.title,
        this.type,
        this.url,
        this.description,
        "hai arinda"
      );
      this.$emit(
        "showDetail",
        this.title,
        this.type,
        this.url,
        this.description,
        this.videoUrl
      );
    }
  }
};
</script>
<style scoped>
.m-card {
  margin: 0.2rem;
}
.image {
  display: block;
  width: 100%;
  height: 100% !important;
  object-fit: cover;
  background-position: center;
}
.card {
  position: relative;
  display: flex;
  flex-direction: column;
  min-width: 0;
  word-wrap: break-word;
  background-color: black !important;
  background-clip: border-box;
  border: 0px solid rgba(0, 0, 0, 0.125);
  border-radius: 0.25rem;
}
.overlay {
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  height: 100%;
  width: 100%;
  opacity: 0;
  transition: 0.5s ease;
  background-color: black;
}

.container-image:hover .overlay {
  opacity: 0.6;
  cursor: pointer;
}

.text {
  color: white;
  font-size: 20px;
  position: absolute;
  top: 50%;
  left: 50%;
  -webkit-transform: translate(-50%, -50%);
  -ms-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
  text-align: center;
}
/* @media screen and (max-width: 1000px) {
  .image {
    display: block;
    width: 100%;
    height: auto !important;
  }
} */
@media (min-width: 576px) {
  .image {
    display: block;
    width: 100%;
    height: auto !important;
    object-fit: cover;
    background-position: center;
  }
}

@media (min-width: 768px) {
  .image {
    display: block;
    width: 100%;
    height: auto !important;
    object-fit: cover;
    background-position: center;
  }
}

@media (min-width: 992px) {
  .image {
    display: block;
    width: 100%;
    height: auto !important;
    object-fit: cover;
    background-position: center;
  }
}

@media (min-width: 1200px) {
  .image {
    display: block;
    width: 100%;
    height: 34vh !important;
    /* object-fit: scale-down; */
    object-fit: cover;
    background-position: center;
  }
}
</style>
