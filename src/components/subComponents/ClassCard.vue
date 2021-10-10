<template>
  <div class="card-container flex" :class="margin">
        <div class="classInfo-container flex column justify-spaceBetween">
            <div>
                <h3 class="font-sm white-text">
                    {{data.className}}
                </h3>
                <span class="font-xxs dirtywhite-text">
                    Class name
                </span>
            </div>

            <div class="numbers-container text-center">
                <div>
                    <h4 class="font-xs white-text">
                        {{data.olds}}
                    </h4>

                    <span class="font-xxs dirtywhite-text">
                        month olds
                    </span>
                </div>

                <div>
                    <h4 class="font-xs white-text">
                        9
                    </h4>

                    <span class="font-xxs dirtywhite-text">
                        Class size
                    </span>
                </div>
            </div>
        </div>

        <div class="image-container"><img :src="require('@/assets/img/' + data.img)" alt=""></div>

        <a href="" class="font-xxs">
            READ MORE
        </a>
  </div>
</template>

<script>
export default {
    name: 'ClassCard',
    props: [
        'data',
        'margin',
    ],
}
</script>

<style scoped lang="scss">
@import "@/style/generals";

.card-container{
    width: calc(50% - 10px);
    position: relative;
    margin-bottom: 20px;

    & > div{
        width: 50%;
    }

    .classInfo-container{
        background-color: $secondary;
        padding: 20px;
    }

    .numbers-container > div{
        display: inline-block;
        width: 50%;

        &:first-child{
            border-right: 1px solid rgba(255, 255, 255, 0.486);
        }
    }

    .image-container{
        img{
            display: block;
            width: 100%;
        }
    }

    a{
        position: absolute;
        right: 0;
        bottom: 0;
        padding: 10px 15px;
        background-color: $primary;
        color: $white;
    }
}



.right{
    margin-left: 20px;
}

</style>