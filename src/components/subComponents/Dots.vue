<template>
  <div class="all-container text-center flex" :class="[flexType, (flexType == 'row') ? null : (flexType == 'column') ? 'align-center' : null]">
      <div>
        <div class="dot-container flex both-center" 
        :class="[color, (flexType == 'row') ? 'marginRight' : (flexType == 'column') ? 'marginBottom' : null]" 
        :style="cssVars">
            <img :src="require('@/assets/img/' + data.img)" alt="">
        </div>
      </div>

    <div class="text-container" :class="(flexType == 'row') ? 'text-left' : (flexType == 'column') ? 'text-center' : nul">
        <h3 class="font-sm secondary-text text-capitalize">
            {{data.title}}
        </h3>

        <p class="font-xs gray-text">
            {{data.paragraph}}
        </p>
        <p class="font-xs gray-text">
            {{data.paragraph2}}
        </p>
        <p class="font-xs gray-text">
            {{data.paragraph3}}
           <a :href = "'mailto: ' + data.email" class="text-underline">
               {{data.email}}
           </a>
        </p>
    </div>
  </div>
</template>

<script>
export default {
    name: 'Dots',
    props: [
        'data',
        'color',
        'flexType',
        'dotDimensions',
        'imageMargin'
    ],
    computed: {
      cssVars () {
            return{
            /* variables you want to pass to css */
            '--dotDimensions': this.dotDimensions,
            }
        }
    }
}
</script>

<style scoped lang="scss">
@import "@/style/generals";

h3{
    margin-bottom: 20px;
}

.dot-container{
    width: var(--dotDimensions);
    height: var(--dotDimensions);
    border-radius: 50%;
}

.secondaryBackground{
    background-color: $secondary;
}

.primaryBackground{
    background-color: $primary;
}

.marginRight{
    margin-right: 30px;
}

.marginBottom{
    margin-bottom: 20px;
}
</style>