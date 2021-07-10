<template>
  <nav class="navbar navbar-expand-lg navbar-dark container">
    <div class="container-fluid px-0">
      <a class="navbar-brand me-0" href="#"
        ><img src="~/assets/image/LogoFlex.png" class="w-50" alt=""
      /></a>
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarSupportedContent"
        aria-controls="navbarSupportedContent"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
          <li class="nav-item me-5">
            <nuxt-link
              :class="
                active == 'Home'
                  ? 'nav-link active fw-bolder text-light font18 letter-normal'
                  : 'nav-link  text-light font18 letter-normal'
              "
              to="/"
              >HOME</nuxt-link
            >
          </li>
          <li class="nav-item me-5">
            <nuxt-link
              :class="
                active == 'Contact'
                  ? 'nav-link active fw-bolder text-light font18 letter-normal'
                  : 'nav-link  text-light font18 letter-normal'
              "
              to="/Contact"
              >CONTACT</nuxt-link
            >
          </li>
        </ul>
        <button
          data-bs-toggle="modal"
          data-bs-target="#modalContact"
          class="btn btn-theme px-4 fw-light rounded-pill"
          type="button"
        >
          GET IN TOUCH
        </button>
      </div>
    </div>
    <ModalContact />
  </nav>
</template>
<script>
export default {
  props: ["active"]
};
</script>
<style scoped></style>
