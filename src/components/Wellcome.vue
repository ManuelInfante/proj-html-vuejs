<template>
    <div class="component-container">
        <SectionsHeader bigTitle="Welcome to Fable" smallTitle="Fable daycare, preschool, and kindergarten"/>

        <div class="dots-container flex container"> <!-- Aggiungere una classe 'dot-container' per impostare i margini la larghezza dei dots ecc.. !Important! (in css: .dot-container *{..}) -->
            <Dots v-for="(dotData, index) in dotsData" 
            :key="index" 
            :data="dotData" 
            :color="(index % 2) ? 'secondaryBackground' : 'primaryBackground'" 
            flexType="column" 
            dotDimensions="180px"
            />
        </div>
    </div>
</template>

<script>
import SectionsHeader from "@/components/subComponents/SectionsHeader.vue";
import Dots from "@/components/subComponents/Dots.vue";

export default {
    name: 'Wellcome',
    components: {
        SectionsHeader,
        Dots,
    },
    data() {
        return{
            dotsData:[
                {
                    img: 'schoolbag_alt.png',
                    title: 'morbi etos',
                    paragraph: 'Praesent interdum est gravida vehicula est node maecenas loareet morbi a dosis luctus novum est praesent.',
                },
                {
                    img: 'stroller_alt.png',
                    title: 'congue gravida',
                    paragraph: 'Elipsis magna a terminal nulla elementum morbi elite forte maecenas est magna etos interdum vitae est.',
                },
                {
                    img: 'globe_alt.png',
                    title: 'maecenas node',
                    paragraph: 'Praesent interdum est gravida vehicula est node maecenas loareet morbi a dosis luctus novum est praesent.',
                },
                {
                    img: 'bell_alt.png',
                    title: 'praesent morbi',
                    paragraph: 'Elipsis magna a terminal nulla elementum morbi elite forte maecenas est magna etos interdum vitae est.',
                },
            ]
        }
    },
}
</script>

<style scoped lang="scss">

.component-container{
    margin-bottom: 60px;
}

.dots-container *{
    min-width: calc(100% / 4);
}

// .dots-container *{
//     width: 50%;

//     &:first-child{
//         margin-right: 20px;
//     }

//     &:last-child{
//         margin-left: 20px;
//     }

//     &:not(:first-child, :last-child){
//         margin: 0 20px;
//     }
// }

</style>