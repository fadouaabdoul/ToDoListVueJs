<template>
    <div class="carousel">
        <slot :currentSlide="currentSlide" />
    </div>

    <!-- Navigation -->
    <div v-if="navEnabled" class="navigate">
        <div class="toggle-page left">
            <i @click="prevSlide" class="fas fa-chevron-left"></i>
        </div>
        <div class="toggle-page right">
            <i @click="nextSlide" class="fas fa-chevron-right"></i>
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

            onMounted(() => {
                getSlideCount.value = document.querySelectorAll('slide').length;
                console.log( getSlideCount.value )
            })
            return {
                currentSlide
            };

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
    i {
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


</style>