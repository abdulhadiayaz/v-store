<template>
  <v-footer :absolute="!fixed" app>
    <v-row justify="center" align="center" class="footer">
      <v-col cols="12" class="d-flex justify-center align-center">
        <div class="row justify-center align-center max-width-1400 mobile-padding">
          <vox-logo />
        </div>
      </v-col>
    </v-row>
  </v-footer>
</template>

<script>
export default {
  props: {
    fixed: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style scoped lang="scss">
/* Styles specific to the footer component */

.footer {
  box-sizing: border-box;
  background: #FFFFFF;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  padding: 0;
  width: 100%;
  height: 64px;
  border-top: 1px solid rgba(26, 26, 26, 0.1);
}

.max-width-1400 {
  max-width: 1400px; /* You can replace this with a variable if defined globally */
}

.mobile-padding {
  padding: 0 20px;
}

/* Responsive Styles */
@media (max-width: 1024px) {
  .mobile-padding {
    padding: 0 20px;
  }
}

@media (max-width: 500px) {
  .padding-20 {
    padding: 20px 20px 0px 20px;
  }
}
</style>
