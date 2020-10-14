<template>
    <div class="v-slider-wrapper">
        <div class="v-slider"
            :style="{
                'margin-left': '-' + (100 * currentSlideIndex) + '%', 
                'width': sliderData.length * 100 + '%'
            }"
        >
            <vSliderItem
                v-for="item in sliderData" 
                :key="item.id"
                :itemData="item"
            ></vSliderItem>
        </div>
        <div class="v-slider-points-block">
            <ul class="v-slider-points">
                <li 
                    v-for="(item, index) in sliderData" 
                    :key="item.id"
                    @click="pointChange(index)"
                    class="v-slider-point"
                    :class="{'v-slider-point-active' : index === currentSlideIndex}"
                >
                </li>
            </ul>
        </div>
    </div>    
</template>
<script>
import vSliderItem from './V-slider-item.vue'
import { setInterval } from 'timers';

export default {
    data() {
        return {
            currentSlideIndex: 0
        }
    },
    props: {
        sliderData: {
            type: Array,
            default: () => []
        },
        interval: {
            type: Number,
            default: 0
        }
    },
    methods: {
        prevSlide() {
            if(this.currentSlideIndex > 0) {
                this.currentSlideIndex--
            }
        },
        nextSlide() {
            if(this.currentSlideIndex >= this.sliderData.length - 1) {
                return this.currentSlideIndex = 0
            }
            this.currentSlideIndex++
        },
        pointChange(value) {
            this.currentSlideIndex = value
        }
    },
    components: {
        vSliderItem
    },
    mounted() {
        if(this.interval > 0) {
            let vm = this
            setInterval(function() {
                vm.nextSlide()
            }, vm.interval)
        }
    }
}
</script>
<style lang="scss" scoped>
    @import '@/assets/scss/style';

    .v-slider-wrapper {
        width: 100%;
        overflow: hidden;
        position: relative;
    }

    .v-slider {
        display: flex;
        transition: all ease .5s;
        height: 500px;
    }

    .v-slider-points-block {
        position: absolute;
        left: 50%;
        transform: translate(-50%, 0);
        bottom: 20px;
    }

    .v-slider-points {
        display: flex;
        justify-content: center;
        align-items: center;
        margin: 0;
        padding: 0;
        list-style: none;
    }

    .v-slider-point {
        width: 6px;
        height: 6px;
        border-radius: 50%;
        background-color: #b0e8e6;
        margin: 0 10px;
    }

    .v-slider-point-active {
        width: 10px;
        height: 10px;
        background-color: #fff;
    }

</style>
