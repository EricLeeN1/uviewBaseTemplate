<template>
<view class="nav-wrap">
    <view class="nav-title">
        <image class="logo" src="https://cdn.uviewui.com/uview/common/logo.png" mode="widthFix"></image>
        <view class="nav-info">
            <view class="nav-title__text">
                {{title}}
            </view>
        </view>
    </view>
    <view class="nav-desc">
        {{desc}}
    </view>
</view>
</template>

<script>
export default {
    props: {
        desc: String,
        title: String,
    },
    methods: {
        switchLang() {
            this.vuex_tabbar[0].text = 'nav.components'
            this.vuex_tabbar[1].text = 'nav.js'
            this.vuex_tabbar[2].text = 'nav.template'
            uni.setNavigationBarTitle({
                title: this.title
            });
        }
    }
}
</script>

<style lang="scss" scoped>
.nav-wrap {
    padding: 30rpx;
    position: relative;
}

.lang {
    position: absolute;
    top: 30rpx;
    right: 30rpx;
}

.nav-title {
    /* #ifndef APP-NVUE */
    display: flex;
    /* #endif */
    flex-direction: row;
    align-items: center;
}

.nav-info {
    margin-left: 30rpx;
}

.nav-title__text {
    /* #ifndef APP-NVUE */
    display: flex;
    /* #endif */
    color: $u-main-color;
    font-size: 50rpx;
    font-weight: bold;
}

.logo {
    width: 140rpx;
    /* #ifndef APP-NVUE */
    height: auto;
    /* #endif */
}

.nav-slogan {
    color: $u-tips-color;
    font-size: 28rpx;
}

.nav-desc {
    margin-top: 20rpx;
    font-size: 28rpx;
    color: $u-content-color;
}
</style>
