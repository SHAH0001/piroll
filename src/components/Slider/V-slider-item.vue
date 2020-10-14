<template>
    <div class="v-slider-item">
        <div class="container">
            <h3 class="v-slider-title">{{ itemData.title }}</h3>
            <p class="v-slider-author">{{ itemData.author }}</p>
        </div>
    </div>
</template>
<script>
export default {
    props: {
        itemData: {
            type: Object,
            default: () => []
        }
    }
}
</script>
<style lang="scss" scoped>
    @import '@/assets/scss/style';

    .v-slider-item {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        text-align: center;
        position: relative;
        width: 100%;
        background-color: $mainColor;
    }

    .v-slider-title {
        font-size: 24px; 
        color: #fff;
        margin: 24px 160px 54px 160px;
        line-height: 36px;

        @include max-width-950 {
            margin: 24px 0 54px 0;
            padding: 0 15px;
        }
    }

    .v-slider-author {
        font-size: 12px;
        color: #fff;
        text-transform: uppercase;
        margin: 0;
    }

</style>
