<template>
  <div>
    <div
      class="modal fade"
      id="modalContact"
      tabindex="-1"
      aria-labelledby="exampleModalLabel"
      aria-hidden="true"
      data-bs-keyboard="false"
    >
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
            <button
              type="button"
              class="btn btn-secondary"
              data-bs-dismiss="modal"
            >
              Close
            </button>
            <button @click="sendTalk()" type="button" class="btn btn-primary">
              Save changes
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "ModalContact",
  data() {
    return {
      namaPengirim: "wkwkwk",
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
    }
  }
};
</script>
