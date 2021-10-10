<template>
    <div class="pattern white-text">
        <div class="container flex justify-spaceBetween align-center">
            <h2 class="font-l">
                {{text}}
            </h2>

            <a href="#" class="white-text">
               <span class="font-xxs">
                   {{cta.toUpperCase()}}
               </span>

               <font-awesome-icon icon="chevron-right"></font-awesome-icon>
            </a>
        </div>
    </div>
</template>

<script>
export default {
    name: 'BannerCTA',
    props: [
        'text',
        'cta',
    ],
}
</script>

<style scoped lang="scss">
@import "@/style/generals";

.pattern{
    background-image: url('../assets/img/pattern.png');
    background-size: cover;
    background-position: center;
    padding: 25px 0;

    .container{

        a, &:visited{
            color: $white;
            border: solid 2px $white;
            padding: 10px;

            & span{
                font-weight: 1000;
                margin-right: 10px;
            }

            &:hover{
                background-color: $white;
            }

            &:hover *{  // non riesco a far riferimento al componente 'font-awesome-icon' se non in questo modo...
                color: $secondary;
            }
        }
    }
}
</style>