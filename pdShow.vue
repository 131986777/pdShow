<template>
    <div class="pdShow">
        <div class="img-box">
            <pic-zoom :url="url" :scale="3" :scroll="true"></pic-zoom>
        </div>
        <shop @url="getUrl" :url="shopUrl"></shop>
    </div>
</template>

<script>
    import PicZoom from './PicZoom'
    import shop from './shop'

    export default {
        name: "pd-show",
        props: {
            shopUrl: {
                type: Array,
                default: false
            }
        },
        data() {
            return {
                url: ''
            }
        },
        components: {
            PicZoom,
            shop
        },
        methods: {
            getUrl(url) {
                this.url = url
            }
        },
        mounted() {
            this.url = this.shopUrl[0].url
        }


    }
</script>

<style lang="scss" scoped>
    .land {
        height: 500px;
        width: 500px;
    }

    .img-box {
        height: 400px;
        width: 400px;
    }
</style>
