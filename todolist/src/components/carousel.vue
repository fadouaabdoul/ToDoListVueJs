<template>
    <div>
        <div class="carousel">
            <slot :currentSlide="currentSlide" />
        </div>

        <!-- Navigation -->
        <div class="navigate">
            <div class="toggle-page left">
                <button @click="prevSlide" class="fas fa-chevron-left"></button>
            </div>
            <div class="toggle-page right">
                <button @click="nextSlide" class="fas fa-chevron-right"></button>
            </div>
        </div>

        <!--pagination-->
        <div class="pagination">
            <span @click="gotoSlide(index)" v-for="(slide, index) in getSlideCount" :key="index" :class="{ active: index + 1 === currentSlide }">
                {{ slide }}
            </span>


        </div>
    </div>

</template>

<script>
    import {ref} from "@vue/reactivity";
    import {onMounted} from "@vue/runtime-core";

    export default {
        name: "carouselS",
        setup(){
            const currentSlide = ref(1);
            const getSlideCount = ref(null);

            const nextSlide = () => {
                if(currentSlide.value === getSlideCount.value){
                    currentSlide.value = 1;
                    return;
                }
                currentSlide.value += 1;

            };

            const prevSlide = () => {
                if(currentSlide.value === 1){
                    currentSlide.value = 3;
                    return;
                }
                currentSlide.value -= 1;
            };

            const gotoSlide = (index) => {
                currentSlide.value = index + 1
            }


            console.log(currentSlide.value)


            onMounted(() => {
                getSlideCount.value = document.querySelectorAll('.slide').length;
                console.log( getSlideCount.value )
            })
            return { currentSlide, nextSlide, prevSlide, getSlideCount, gotoSlide}

        },
        methods:{

        }
    }
</script>

<style scoped>
    .navigate {
        padding: 0 16px;
        height: 100%;
        width: 100%;
        position: absolute;
        display: flex;
        justify-content: center;
        align-items: center;

    }
    .toggle-page {
        display: flex;
        flex: 1;
    }
    .right {
        justify-content: flex-end;
    }
    button{
        cursor: pointer;
        display: flex;
        align-items: center;
        justify-content: center;
        border-radius: 50%;
        width: 40px;
        height: 40px;
        background-color: #6347c7;
        color: #fff;
    }
    .pagination {
        position: absolute;
        bottom: 24px;
        width: 100%;
        display: flex;
        gap: 16px;
        justify-content: center;
        align-items: center;
    }
    span {
        cursor: pointer;
        width: 20px;
        height: 20px;
        border-radius: 50%;
        background-color: #fff;
        box-shadow: 0 1px 3px 0 rgba(0, 0, 0, 0.1), 0 1px 2px 0 rgba(0, 0, 0, 0.06);
    }
    .active {
        background-color: #6347c7;
    }

</style>