<template>
  <div class="text-center">
        <h2 class="font-xxl secondary-text">
           {{bigTitle}}
        </h2>

        <h3 class="font-s lightgray-text">
            {{smallTitle}}
        </h3>

        <img :src="require('@/assets/img/header_divider.png')" alt="">
  </div>
</template>

<script>
export default {
    name: 'SectionsHeader',
    props: [
        'bigTitle',
        'smallTitle',
    ],
}
</script>

<style scoped lang="scss">
@import "@/style/generals";

div{
    margin: 60px 0;

    h2{
        font-weight: 300;
    }

    h3{
        margin-top: 10px;
        margin-bottom: 30px;
    }
}
</style>