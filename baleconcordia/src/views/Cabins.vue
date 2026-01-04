<template>
  <div class="page-cabins">
    <ResortHeader />

    <Introduction />

    <PhotoGallery />

    <ContactUs />

    <LocationMap />

    <div class="social-wrap">
      <ContactSocial />
    </div>

    <SiteFooter />
  </div>
</template>

<script setup>
import ResortHeader from '../components/ResortHeader.vue'
import Introduction from '../components/Introduction.vue'
import PhotoGallery from '../components/PhotoGallery.vue'
import ContactUs from '../components/ContactUs.vue'
import LocationMap from '../components/LocationMap.vue'
import ContactSocial from '../components/ContactSocial.vue'
import SiteFooter from '../components/SiteFooter.vue'
</script>

<style scoped>
.page-cabins { padding: 0 0.75rem; }
.social-wrap { margin-top: 1rem }

@media (min-width: 1024px) {
  .page-cabins { padding: 0 2rem; }
}
</style>
