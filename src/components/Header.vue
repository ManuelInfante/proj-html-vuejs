<template>
  <header>
    <div class="container flex justify-spaceBetween">
      <div class="logo">
        <a href="/">
          <img :src="require('@/assets/img/logo.png')" alt="">
        </a>
      </div>

      <nav>
        <ul class="flex">
          <li v-for="(link, index) in links" :key="index">
            <a
            :href="link.url"
            :class="(link.current) ? 'active' : 'none'"
            class="flex column justify-center align-center"
            >
              <img :src="require(`@/assets/img/${link.img}`)" :alt="link.text">

              <span class="$font-xs secondary-text">
                {{link.text}}
              </span>
            </a>
          </li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<script>
import {headerLinks} from "@/data/Links.js"

export default {
  name: 'Header',
  data(){
    return{
      links: headerLinks,
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "@/style/generals";

header {
  height: 120px;

  .container{
    height: 100%;

    .logo{
    height: 100%;

      img{
        height: 100%;
        transition: all 0.3s;
      }

      &:hover img{
        transform: scale(0.7);
      }
    }
  }
}

nav{
  height: 100%;
  ul{
    height: 100%;
    li{
      height: 100%;
      min-width: 100px;

      a{
        height: 100%;
        width: 100%;
        
        &:not(.active):hover{
          background-color: $lightPrimary;

          img{
            object-position: 0 -32px;
          }

          span{
            color: $white;
          }
        }

        img{
          height: 32px;
          width: 32px;
          object-fit: cover;
          object-position: 0 0px;
          margin-bottom: 15px;
        }
      }
    }
  }
}

.active{
  background-color: $primary;

  img{
    object-position: 0 -32px;
  }

  span{
    color: $white;
  }
}

</style>