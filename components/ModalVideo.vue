<template>
  <div class="position-relative" style="z-index:99999;">
    <div
      class="modal fade"
      id="modalDetail"
      data-bs-backdrop="static"
      data-bs-keyboard="false"
      tabindex="-1"
      aria-labelledby="staticBackdropLabel"
      aria-hidden="true"
    >
      <div class="modal-dialog modal-lg">
        <div class="modal-content">
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
            <img :src="url" style="width:100%" alt="" />
            <div class="px-3 mt-4 mb-5">
              <h1 class="font24 font18-mobile mb-1">{{ title }}</h1>
              <p class="font18 font14-mobile">{{ description }}</p>
            </div>
          </div>
          <div class="modal-footer">
            <button
              type="button"
              class="btn btn-primary px-4 py-2"
              data-bs-dismiss="modal"
            >
              Close
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["title", "type", "url", "description"]
};
</script>
