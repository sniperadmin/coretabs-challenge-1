<template>
  <!-- big container -->
  <div>
    <!-- outlining page as 1 big row -->
    <b-row
      class="text-center"
    >
      <!-- left sign up section -->
      <b-col md="6">
        <Signup />
      </b-col>
      <!-- Right banner -->
      <b-col
        md="6"
      >
        <div class="pattern">
          <!-- inner-row -->
          <b-row
            align-h="center"
            align-v="center"
            style="height: 100vh;"
          >
            <!-- inner-col -->
            <b-col
              sm="12"
              md="12"
            >
              <div>
                <img src="@/assets/img/pattern.png" alt="pattern" class="img-fluid">
              </div>
            </b-col><!-- ./inner-col -->
          </b-row><!-- ./inner-row -->
        </div><!-- ./right banner -->
      </b-col>
    </b-row>
  </div><!-- ./big container -->
</template>

<script>
import Signup from '@/components/Signup.vue'
export default {
  components: {
    Signup
  }
}
</script>

<style>
html {
  overflow-x: hidden;
}

.pattern {
  background: -webkit-linear-gradient(to bottom, #0CA1F6, #19E995);
  /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(to bottom, #0CA1F6, #19E995);
  /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
}

.custom-btn {
   background: -webkit-linear-gradient(to right, #0CA1F6, #19E995);
  /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(to right, #0CA1F6, #19E995);
  /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
  font-size: 15pt;
  color: white;
}

hr {
  width: 20%;
  size: 20px;
}

Input {
  border-radius: 20px !important;
  background: #E9F1F5 !important;
  height: 40px !important;
}

.input-group-error-prepend .input-group-error-append {
  color: #FA76AD;
}
</style>
