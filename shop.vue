<template>
    <ul>
        <li v-for="(item,index) in url" :class="[index==Index?'select':'']"><img :src=item.url alt=""
                                                                                 @mouseover="change(item.url,index)">
        </li>
    </ul>
</template>

<script>
    export default {
        name: "shop",
        props: {
            url: {
                type: Array,
                default: false
            }
        },
        data() {
            return {
                Index: ''
            }
        },
        methods: {
            change(url, index) {
                this.$emit('url', url);
                this.Index = index
                console.log(this.Index)
            }
        },

        mounted() {
            console.log(this.url)
        }
    }
</script>

<style scoped lang="scss">
    ul {
        width: 500px;
        height: 50px;
        background: red;
        overflow: hidden;
        li {
            float: left;
            width: 54px;
            height: 54px;
            border: 2px solid #fff;

            img {
                width: 50px;
            }
        }
        .select {
            border-color: #f40;;
        }
    }
</style>
