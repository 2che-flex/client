<template>
  <div class="d-flex justify-content-center mb-4">
    <div class="d-flex flex-column">
      <div class="container mt-4">
        <div class="row">
          <div class="col " v-for="(item, i) in dataSocial" :key="i">
            <a :href="item.url" target="blank">
              <img
                :src="item.imageData"
                class="w-100"
                alt=""
                style="max-width:30px"
              />
            </a>
          </div>
        </div>
      </div>
    </div>
  </div>
  <!-- di -->
</template>
<script>
import axios from "axios";
export default {
  data() {
    return {
      email: "",
      ig: "",
      twitter: "",
      fb: "",
      dataSocial: []
    };
  },
  methods: {
    async getSocial() {
      const { data } = await axios.get(
        "https://service.flx.asia/api/v1/footer"
      );
      // console.log(data.socialMedia,'soc');
      this.dataSocial = data.socialMedia;
      // this.email =  data.socialMedia[0].url || 'wait';
      //  this.ig =  data.socialMedia[3].url || 'wait';
      //   this.twitter =  data.socialMedia[2].url || 'wait';
      //    this.fb =  data.socialMedia[3].url || 'wait';
    }
  },
  mounted() {
    this.getSocial();
  }
};
</script>
