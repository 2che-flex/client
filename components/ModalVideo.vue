<template>
  <div class="position-relative" style="z-index:99999;">
    <div
      class="modal fade"
      id="modalDetail"
      tabindex="-1"
      aria-labelledby="staticBackdropLabel"
      aria-hidden="true"
      @keydown.stop.prevent="recache()"
      @keyup.stop.prevent="recache()"
      @keypress.stop.prevent="recache()"
    >
      <div class="modal-dialog modal-lg modal-dialog-centered">
        <div class="modal-content" style="background-color:black !important">
          <!-- <div class="modal-header">
            <h5 class="modal-title" id="staticBackdropLabel">{{ title }}</h5>
            <button
              type="button"
              class="btn-close"
              data-bs-dismiss="modal"
              aria-label="Close"
            ></button>
          </div> -->
          <div class="modal-body p-0 m-0">
            <!-- <img :src="url" style="width:100%" alt="" /> -->
            <video
              controls
              autoplay
              class="m-0 p-0"
              id="myVideo"
              :src="video"
              width="100%"
            >
              Sorry, your browser doesn't support embedded videos, but don't
              worry, you can
              <a :href="video">download it</a>
              and watch it with your favorite video player!
            </video>
            <!-- <iframe
              width="100%"
              height="400"
              :src="video"
              frameborder="0"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen
            >
            </iframe> -->
            <!-- <div class="px-3 mt-4 mb-4 w-75">
              <h1 class="font24 font18-mobile mb-2">{{ title }}</h1>
              <p class="font16 font14-mobile fw-lighter">{{ description }}</p>
            </div> -->
          </div>
          <!-- <div class="modal-footer">
            <button
              type="button"
              class="btn btn-primary px-4 py-2"
              data-bs-dismiss="modal"
            >
              Close
            </button>
          </div> -->
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      status: false
    };
  },
  props: ["title", "type", "url", "description", "video"],
  methods: {
    recache() {
      this.$emit("recache");
    }
  }
};
</script>
