<template>
  <div class="d-flex justify-content-center">
    <div class="d-flex flex-column">
      <div class="container mt-4">
        <div class="row">
          <div class="col ">
             <a :href="fb" target="blank">
            <img src="~/assets/icon/fb.svg" alt="" />
             </a>
          </div>
          <div class="col ">
             <a :href="twitter" target="blank">
            <img src="~/assets/icon/twiter.svg" alt="" />
            </a>
          </div>
          <div class="col ">
             <a :href="ig" target="blank">
            <img src="~/assets/icon/ig.svg" alt="" />
             </a>
          </div>
          <div class="col ">
                <a :href="email" target="blank">
            <img src="~/assets/icon/gmail.svg" alt="" />
                </a>
          </div>
        </div>
      </div>
    </div>
  </div>
  <!-- di -->
</template>
<script>
import axios from 'axios'
export default {
  data(){
    return{
      email:'',
      ig:'',
      twitter:'',
      fb:''
    }
  },
  methods:{
     async getSocial() {
      const { data } = await axios.get(
        "https://server-flex.herokuapp.com/api/v1/footer"
      );
      this.email =  data.socialMedia[0].url || 'wait';
       this.ig =  data.socialMedia[3].url || 'wait';
        this.twitter =  data.socialMedia[2].url || 'wait';
         this.fb =  data.socialMedia[3].url || 'wait';
    }
  },
  mounted(){
      this.getSocial()
  }
}
</script>