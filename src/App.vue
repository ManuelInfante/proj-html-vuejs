<template>
  <div id="app">
    <Header />
    <BannerCTA 
    text="How to Enroll Your Child to a Class?"
    cta="learn more"
    />
    <Wellcome />
    <SchoolProperties />
    <Classes />
    <BannerCTA 
    text="See Our kindergarten Photo Gallery"
    cta="view gallery"
    />
  </div>
</template>

<script>
import Header from '@/components/Header.vue';
import BannerCTA from '@/components/BannerCTA.vue';
import Wellcome from '@/components/Wellcome.vue';
import SchoolProperties from '@/components/SchoolProperties.vue';
import Classes from '@/components/Classes.vue';

export default {
  name: 'App',
  components: {
    Header,
    BannerCTA,
    Wellcome,
    SchoolProperties,
    Classes,
  }
}
</script>

<style lang="scss">
@import "@/style/generals"
</style>
