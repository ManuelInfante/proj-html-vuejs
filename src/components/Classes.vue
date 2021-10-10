<template>
    <div class="component-container container">
        <SectionsHeader bigTitle="Our Classes" smallTitle="Our preschool program has four dedicated classes"/>

        <div class="section-container flex">
            <div class="section">
                <h2 class="font-m secondary-text">
                    We provided four classes with nine to twenty children each aged twelve month to five years of age.
                </h2>
            </div>

            <div class="section">
                <p class="font-xs gray-text">
                    Praesent arcu gravida vehicula est node maecenas loareet morbi a dosis luctus. Urna eget lacinia eleifend praesent luctus a arcu quis facilisis venenatis. Aenean interdum, nibh vitae sodales, magna ante feugiat elit maecenas.
                </p>
            </div>
        </div>

        <div class="cards-container flex wrap">
            <ClassCard
            v-for="(classeData, index) in classesData" :key="index"
            :data="classeData"
            :margin="(index % 2) ? 'right' : 'left' "
            />
        </div>
    </div>
</template>

<script>
import SectionsHeader from "@/components/subComponents/SectionsHeader.vue";
import ClassCard from "@/components/subComponents/ClassCard.vue";

export default {
    name: 'Classes',
    components: {
        SectionsHeader,
        ClassCard,
    },
    data() {
        return{
            classesData:[
                {
                    className: 'Little Lambs',
                    olds: '12,24',
                    oldType: 'Month',
                    classSize: '9',
                    img: 'class_01-690x506.jpg'
                },
                {
                    className: 'Bouncy Bears',
                    olds: '2-3',
                    oldType: 'Years',
                    classSize: '12',
                    img: 'class_02-690x506.jpg'
                },
                {
                    className: 'Tenderhearts',
                    olds: '3-4',
                    oldType: 'Years',
                    classSize: '15',
                    img: 'class_03-690x506.jpg'
                },
                {
                    className: 'Shining Stars',
                    olds: '4-5',
                    oldType: 'Years',
                    classSize: '20',
                    img: 'class_04-690x506.jpg'
                },
            ],
        }   
    },
}
</script>

<style scoped lang="scss">

.component-container{
    margin-bottom: 60px;

    .section-container{
        margin-bottom: 60px;

        .section{
            width: 50%;

            &:first-child{
                padding-right: 20px;
            }

            p{
                padding: 10px 0;
            }
        }
    }
}
</style>