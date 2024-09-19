<template>
  <v-app>
    <v-app-bar
      :clipped-left="clipped"
      fixed
      app
      class="elevation-0 white"
    >
      <v-row>
        <v-col cols="12" class="d-flex justify-center align-center">
          <header class="row justify-center align-center max-width-1400 mobile-padding">
            <v-toolbar-title>
              <nuxt-link to="/" role="link" aria-label="Home">
                <vox-logo alt="Logo for Voxel Store" />
              </nuxt-link>
            </v-toolbar-title>
            <v-spacer />
          </header>
        </v-col>
      </v-row>
    </v-app-bar>
    <v-main class="no-padding">
      <Nuxt />
    </v-main>
    <v-footer
      :absolute="!fixed"
      app
    >
      <v-row justify="center" align="center" class="footer">
        <v-col cols="12" class="d-flex justify-center align-center">
          <div class="row justify-center align-center max-width-1400 mobile-padding">
            <vox-logo />
          </div>
        </v-col>
      </v-row>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout'
}
</script>

<style lang="scss">

// Variables
$mobile-breakpoint: 1024px;
$small-breakpoint: 500px;

// Mixins
@mixin mobile-padding {
  padding: 0 20px;
}

@mixin padding($top, $right, $bottom, $left) {
  padding: $top $right $bottom $left !important;
}

// Global Classes
.no-shadow {
  box-shadow: none !important;
}

.no-padding {
  padding: 0;
  margin: 0;
}

.hide-on-mobile {
  display: block !important;
}

.show-on-mobile {
  display: none !important;
}

.ellipsis {
  overflow: hidden;
  text-overflow: ellipsis;
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
}

// Component/Specific Classes
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

.sub-text {
  width: 268px;
  height: 20px;
  font-family: 'Instrument Sans';
  font-style: normal;
  font-weight: 500;
  font-size: 16px;
  line-height: 20px;
  color: rgba(26, 26, 26, 0.5);
}

// Media Queries
@media (max-width: $mobile-breakpoint) {
  .mobile-padding {
    @include mobile-padding;
  }
}

@media (max-width: $small-breakpoint) {
  .padding-20 {
    @include padding(20px, 20px, 0px, 20px);
  }

  .hide-on-mobile {
    display: none !important;
  }

  .show-on-mobile {
    display: block !important;
  }
}

</style>
