<template>
  <div>
    <div class="showModal">
      <div class="modal-dialog">
        <div class="modal-content">
          <div class="modal-header">
            <h5 class="modal-title" id="exampleModalLabel">Let's Talk</h5>
          </div>
          <div class="modal-body">
            <form class="mt-3">
              <div class="mb-4 col-12" style="border-bottom:1px solid #E9E9E9">
                <input
                  v-model="namaPengirim"
                  placeholder="Nama"
                  type="text"
                  class=" border-0  col-12 p-1"
                />
              </div>
              <div class="mb-4 col-12" style="border-bottom:1px solid #E9E9E9">
                <input
                  v-model="emailPengirim"
                  placeholder="Email"
                  type="email"
                  class=" border-0  col-12 p-1"
                />
              </div>
              <div class="mb-4 col-12" style="border-bottom:1px solid #E9E9E9">
                <input
                  v-model="noHp"
                  placeholder="No Hp"
                  type="number"
                  class=" border-0  col-12 p-1"
                />
              </div>
            </form>
          </div>
          <div class="modal-footer border-0">
            <button type="button" class="btn btn-light" @click="openModal()">
              Close
            </button>
            <button
              :disabled="
                namaPengirim == '' || emailPengirim == '' || noHp == ''
              "
              @click="sendTalk()"
              type="button"
              class="btn btn-dark"
            >
              Send Talk
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import axios from "axios";
export default {
  name: "ModalContact",
  data() {
    return {
      namaPengirim: "",
      emailPengirim: "",
      noHp: ""
    };
  },
  methods: {
    sendTalk() {
      console.log(
        this.namaPengirim,
        this.emailPengirim,
        this.noHp,
        "arinda wkwk"
      );
      let newData = {
        name: this.namaPengirim,
        email: this.emailPengirim,
        phone_number: this.noHp
      };
      axios
        .post(" https://server-flex.herokuapp.com/api/v1/client", newData)
        .then(response => {
          this.$emit("openModal", false);
        })
        .catch(err => {
          this.$emit("openModal", false);
        });
    },
    openModal() {
      this.$emit("openModal", false);
    }
  }
};
</script>
<style scoped>
.showModal {
  position: fixed;
  top: 0;
  left: 0;
  z-index: 999999999999999999;
  display: block;
  width: 100%;
  height: 100%;
  overflow-x: hidden;
  overflow-y: auto;
  outline: 0;
}
</style>
