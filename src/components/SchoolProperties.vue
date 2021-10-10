<template>
    <div class="background-container">
        <div class="container flex">
            <div class="section-container">
                <div class="button-container">
                    <a href="" class="button active font-s text-center">
                        Overview
                    </a>

                    <a href="" class="button not-active font-s text-center">
                        Our Mission
                    </a>
                </div>

                <h2 class="font-m secondary-text">
                    Our philosophy is learning through play as we offer a stimulating environment for children.
                </h2>

                <div class="dots-container">
                    <Dots v-for="(dotData, index) in dotsData" :key="index"
                    :data="dotData" 
                    color="primaryBackground" 
                    dotDimensions="80px"
                    flexType="row" 
                    />
                </div>
            </div>

            <div class="section-container">
                <ImageSlider 
                :data="imageData"
                />
            </div>
        </div>
    </div>
</template>

<script>
import Dots from "@/components/subComponents/Dots.vue";
import ImageSlider from "@/components/subComponents/ImageSlider.vue";

export default {
    name: '',
    components: {
        Dots,
        ImageSlider,
    },
    data() {
        return{
            dotsData:[
                {
                    img: 'clock_alt.png',
                    title: 'morbi etos',
                    paragraph: 'Praesent interdum est gravida vehicula est node maecenas loareet morbi a dosis luctus novum est praesent.',
                },
                {
                    img: 'diagram_alt.png',
                    title: 'congue gravida',
                    paragraph: 'Elipsis magna a terminal nulla elementum morbi elite forte maecenas est magna etos interdum vitae est.',
                },
            ],
            imageData:[
                {
                    img: 'gallery_07-690x506.jpg'
                },
                {
                    img: 'gallery_01-690x506.jpg'
                },
                {
                    img: 'gallery_08-690x506.jpg'
                },
            ]
        }
    },
}
</script>

<style scoped lang="scss">
@import "@/style/generals";

.background-container{
    background-color: $marble;
    padding: 60px 0;

    .section-container{
        width: 50%;

        h2{
            margin-bottom: 40px;
        }

        .button-container{
            margin-bottom: 50px;

            .button{
                display: inline-block;
                min-width: 140px;
                padding: 12px 15px;

                &:first-child{
                    margin-right: 20px;
                }

                &.not-active{
                    color: $lightgray;
                    border-bottom: 1px solid #E8E8E8;
                }

                &.active{
                    background-color: $primary;
                    color: $white;
                    position: relative;

                    &:after{
                        content: "";
                        position: absolute;
                        transform: translate(-50%, 100%);
                        bottom: 0px;
                        left: 50%;
                        

                        width: 0;
                        height: 0;
                        border: 10px solid transparent;
                        border-bottom: 0;
                        border-top: 10px solid $primary;
                    }
                }
            }
        }

        .dots-container *{
    
            &:first-child{
                margin-bottom: 30px;
            }
        }

    }

    .section-container:not(:last-child){
        padding-right: 35px;
    }
}
</style>