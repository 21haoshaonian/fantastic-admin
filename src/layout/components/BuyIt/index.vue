<template>
    <div class="buy-it">
        <div class="item" @click="open('http://wpa.qq.com/msgrd?v=3&uin=&site=qq&menu=yes')">
            <svg-icon name="fixed-right-qq" />
            <span class="title">联系<br>我</span>
        </div>
        <div class="item chat" @click="open('https://wsso.h3c.com/')">
            <svg-icon name="fixed-right-chat" />
            <span class="title">加入<br>我们</span>
        </div>
        <div class="item buy" @click="open('https://wsso.h3c.com/')">
            <svg-icon name="fixed-right-buy" />
            <span class="title">简单<br>介绍</span>
        </div>
        <div class="item doc" @click="open('https://wsso.h3c.com/')">
            <svg-icon name="fixed-right-doc" />
            <span class="title">开发<br>文档</span>
        </div>
        <div class="item code" @click="open('https://wsso.h3c.com/')">
            <svg-icon name="fixed-right-code" />
            <span class="title">下载<br></span>
        </div>
    </div>
</template>

<script>
export default {
    mounted() {
        this.$notify({
            type: 'success',
            title: '温馨提示',
            dangerouslyUseHTMLString: true,
            message: `
                <p>嘿<b>看这里</b></p>
                <p>你可以点<a href="http://wpa.qq.com/msgrd?v=3&uin=&site=qq&menu=yes"" target="_blank"><b>这里</b></a>跟我交流</p>
            `,
            position: 'bottom-right',
            duration: 0
        })
    },
    methods: {
        open(url) {
            window.open(url, 'top')
        }
    }
}
</script>

<style lang="scss" scoped>
.buy-it {
    position: fixed;
    z-index: 10;
    right: 0;
    top: 50%;
    margin-top: -170px;
    width: 60px;
    display: flex;
    flex-direction: column;
    .item {
        display: flex;
        flex-direction: column;
        justify-content: center;
        height: 70px;
        text-align: center;
        color: #fff;
        background-color: #409eff;
        border-bottom: 1px solid #fff;
        transition: 0.3s;
        opacity: 0.6;
        cursor: pointer;
        &:hover {
            opacity: 1;
        }
        &:first-child {
            border-top-left-radius: 5px;
        }
        &:last-child {
            border-bottom-left-radius: 5px;
            border-bottom: 0;
        }
        &.chat {
            background-color: #0fcc1a;
        }
        &.buy {
            background-color: #ff4200;
        }
        &.doc {
            background-color: #727272;
        }
        &.code {
            background-color: #343b42;
        }
        .svg-icon {
            display: block;
            margin: 0 auto;
            font-size: 20px;
        }
        .title {
            display: inline-block;
            font-size: 12px;
        }
    }
}
</style>
