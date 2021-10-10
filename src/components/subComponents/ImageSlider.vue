<template>
  <div>
    <div class="slider-wrapper">
      <div class="images">
        <img :src="require('@/assets/img/' + data[counterPhoto].img)" alt="image">

        <div class="prev flex both-center" @click="prevPhoto">
          <font-awesome-icon icon="chevron-left"></font-awesome-icon>
        </div>

        <div class="next flex both-center" @click="nextPhoto">
          <font-awesome-icon icon="chevron-right"></font-awesome-icon>
        </div>
      </div>

      <div class="nav-container flex align-center">
        <div @click="changePhoto(index)" v-for="(photo,index) in data" :key="index"  class="nav">
          <img :src="require('@/assets/img/' + photo.img)" alt="" :class="(index == counterPhoto) ? 'active' : null">
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
    name: 'ImageSlider',
    props: [
      'data',
    ],
    data() {
      return{
        counterPhoto: 2,
      }
    },
    methods: {
      prevPhoto() {
        this.counterPhoto -= 1;
        if(this.counterPhoto < 0){
          this.counterPhoto = (this.data.length - 1);
        }'--fix';
      },

      nextPhoto() {
        this.counterPhoto += 1;
        if(this.counterPhoto == (this.data.length)){
            this.counterPhoto = 0;
        }'--fix';
      },

      changePhoto(index) {
        this.counterPhoto = index;
      },
    }
}
</script>

<style scoped lang="scss">
@import "@/style/generals";

.images{
  width: 100%;
  position: relative;

  img{
    width: 100%;
  }

  .prev, .next{
    position: absolute;
    width: 40px;
    height: 40px;
    transform: translate(0, -50%);
    background-color: $primary;
    cursor: pointer;

    & *{
      color: $white;
    }
  }

  .prev{
    top: 50%;
    left: 0;
  }

  .next{
    top: 50%;
    right: 0;
  }
}

.nav-container{
  padding-top: 20px;

  .nav{
    width: calc(100% / 3);
    cursor: pointer;

    img{
      width: 100%;
      border-bottom: 2px solid transparent;
      padding-bottom: 20px;

      &.active{
      border-color: $primary;
    }
    }

    &:not(:first-child, :last-child){
      padding-left: 5px;
      padding-right: 5px;
    }

    &:first-child{
      padding-right: 10px;
    }

    &:last-child{
      padding-left: 10px;
    }
  }
}

</style>