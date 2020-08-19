<template>
  <div class="home">
    <Header />
    <Banner />
    <holicbag />
    <Instagram />
    <Footer />
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from "@/components/HelloWorld.vue";
import Header from '@/components/Header.vue';
import Banner from '@/components/Banner.vue';
import Holicbag from '@/components/Holicbag.vue';
import Instagram from '@/components/Instagram.vue';
import Footer from '@/components/Footer.vue';

export default {
  name: 'Home',
  components: {
    Header,
    Banner,
    Holicbag,
    Instagram,
    Footer,
  },
};
</script>
