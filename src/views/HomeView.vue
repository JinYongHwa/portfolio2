<template>
  <div>
    <swiper
      class="swiper"
      :options="swiperOptions"
      @transition-start="changeSlide"
      data-aos="fade-in"
      data-aos-duration="3000"
      ref="swiper"
    >
      <swiper-slide
        class="slide"
        style="background-image: url(/portfolio2/img/top1.jpg)"
      >
        <v-layout
          fill-height
          align-center
          justify-center
          v-if="swiperIndex == 0"
        >
          <div
            class="slogan"
            data-aos="fade-down"
            data-aos-delay="100"
            data-aos-duration="1000"
          >
            안녕하세요 진용화입니다
          </div>
        </v-layout>
      </swiper-slide>
      <swiper-slide
        class="slide"
        style="background-image: url(/portfolio2/img/top2.jpg)"
      >
        <v-layout
          fill-height
          align-center
          justify-center
          v-if="swiperIndex == 1"
        >
          <div
            class="slogan"
            data-aos="fade-right"
            data-aos-delay="100"
            data-aos-duration="1000"
          >
            열심히 하겠습니다
          </div>
        </v-layout>
      </swiper-slide>
      <swiper-slide
        class="slide"
        style="background-image: url(/portfolio2/img/top3.jpg)"
      >
        <v-layout
          fill-height
          align-center
          justify-center
          v-if="swiperIndex == 2"
        >
          <div
            class="slogan"
            data-aos="flip-left"
            data-aos-delay="100"
            data-aos-duration="1000"
          >
            시켜만 주십쇼
          </div>
        </v-layout>
      </swiper-slide>
    </swiper>

    <div class="section">
      <div class="header">프로젝트목록</div>

      <div class="container">
        <v-layout>
          <v-flex xs4>
            <img src="/portfolio2/img/top1.jpg" class="project-image" />
          </v-flex>
        </v-layout>
      </div>
    </div>
  </div>
</template>

<script>
import { Swiper, SwiperSlide } from "vue-awesome-swiper";
import "swiper/css/swiper.css";
import AOS from "aos";
import "aos/dist/aos.css";
export default {
  name: "Home",
  data() {
    return {
      swiperIndex: 0,
      swiperOptions: {
        loop: true,
        autoplay: {
          delay: 3000,
        },
      },
    };
  },
  components: {
    Swiper,
    SwiperSlide,
  },
  mounted() {
    AOS.init();
  },
  methods: {
    changeSlide(event) {
      this.swiperIndex = this.$refs.swiper.$swiper.realIndex;
      console.log(this.swiperIndex);
    },
  },
};
</script>
<style scoped lang="less">
.swiper {
  height: 100vh;
}
.image {
  object-fit: cover;
  object-position: center center;
}
.slide {
  background-position: center center;
  background-size: cover;
}
.slogan {
  font-size: 70px;
  color: white;
  font-weight: bold;
}
.section {
  padding: 20px;
  .project-image {
    width: 100%;
  }
}
.container {
  width: 1100px;
  margin-top: 0;
  margin-bottom: 0;
  margin-left: auto;
  margin-right: auto;
}
</style>