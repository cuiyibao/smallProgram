<template>
    <div class="page">
        <div class="weui-tab">
            <div class="weui-navbar">
                <block v-for="(item,index) in tabs" :key="index">
                    <div :id="index" :class="{'weui-bar__item_on':activeIndex == index}" class="weui-navbar__item" @click="tabClick">
                        <div class="weui-navbar__title">{{item}}</div>
                    </div>
                </block>
                <div class="weui-navbar__slider" :class="navbarSliderClass"></div>
            </div>
            <div class="weui-tab__panel">
                <div class="weui-tab__content" :hidden="activeIndex != 0">
                    <div class="page__bd page__bd_spacing">
                        <div class="weui-cells weui-cells_after-title">
                            <div class="weui-cell">
                                <div class="weui-cell__hd">活动标题</div>
                                <div class="weui-cell__bd">活动类型</div>
                                <div class="weui-cell__ft">
                                    <button class="weui-btn" type="primary">预约</button>
                                </div>
                            </div>
                            <div class="weui-cell">
                                <div class="weui-cell__hd">发起人：XXXX</div>
                                <div class="weui-cell__bd"></div>
                                <div class="weui-cell__ft">开始时间-结束时间</div>
                            </div>
                        </div>
                        <div class="weui-cells weui-cells_after-title">
                            <div class="weui-cell">
                                <div class="weui-cell__hd">活动标题</div>
                                <div class="weui-cell__bd">活动类型</div>
                                <div class="weui-cell__ft">
                                    <button class="weui-btn" type="warn">放鸽子</button>
                                </div>
                            </div>
                            <div class="weui-cell">
                                <div class="weui-cell__hd">发起人：XXXX</div>
                                <div class="weui-cell__bd"></div>
                                <div class="weui-cell__ft">开始时间-结束时间</div>
                            </div>
                        </div>
                        <div class="weui-cells weui-cells_after-title">
                            <div class="weui-cell">
                                <div class="weui-cell__hd">活动标题</div>
                                <div class="weui-cell__bd">活动类型</div>
                                <div class="weui-cell__ft">
                                    <button class="weui-btn" type="default">人未满</button>
                                </div>
                            </div>
                            <div class="weui-cell">
                                <div class="weui-cell__hd">发起人：XXXX</div>
                                <div class="weui-cell__bd"></div>
                                <div class="weui-cell__ft">开始时间-结束时间</div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="weui-tab__content" :hidden="activeIndex != 1">
                    <div class="page__bd page__bd_spacing">
                        <div class="weui-cells weui-cells_after-title">
                            <div class="weui-cell">
                                <div class="weui-cell__hd">活动标题</div>
                                <div class="weui-cell__bd">活动类型</div>
                                <div class="weui-cell__ft">活动结束</div>
                            </div>
                            <div class="weui-cell">
                                <div class="weui-cell__hd">发起人：XXXX</div>
                                <div class="weui-cell__bd"></div>
                                <div class="weui-cell__ft">开始时间-结束时间</div>
                            </div>
                        </div>
                        <div class="weui-cells weui-cells_after-title">
                            <div class="weui-cell">
                                <div class="weui-cell__hd">活动标题</div>
                                <div class="weui-cell__bd">活动类型</div>
                                <div class="weui-cell__ft">人未齐</div>
                            </div>
                            <div class="weui-cell">
                                <div class="weui-cell__hd">发起人：XXXX</div>
                                <div class="weui-cell__bd"></div>
                                <div class="weui-cell__ft">开始时间-结束时间</div>
                            </div>
                        </div>
                        <div class="weui-cells weui-cells_after-title">
                            <div class="weui-cell">
                                <div class="weui-cell__hd">活动标题</div>
                                <div class="weui-cell__bd">活动类型</div>
                                <div class="weui-cell__ft">其他原因</div>
                            </div>
                            <div class="weui-cell">
                                <div class="weui-cell__hd">发起人：XXXX</div>
                                <div class="weui-cell__bd"></div>
                                <div class="weui-cell__ft">开始时间-结束时间</div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            tabs: ["预约中", "已关闭"],
            activeIndex: 0
        };
    },

    components: {},

    computed: {
        navbarSliderClass() {
            if (this.activeIndex == 0) {
                return "weui-navbar__slider_0";
            }
            if (this.activeIndex == 1) {
                return "weui-navbar__slider_1";
            }
        }
    },
    methods: {
        tabClick(e) {
            this.activeIndex = e.currentTarget.id;
        }
    },

    created() {}
};
</script>

<style scoped lang="scss">
/* 局部样式微调 */
.weui-tab__panel {
    padding-top: 30rpx;
}
/* navbar */
page,
.page,
.page__bd {
    height: 100%;
}
.page__bd {
    padding-bottom: 0;
}
.weui-tab__content {
    padding-top: 60px;
    text-align: center;
}
.weui-navbar__slider_0 {
    left: 29rpx;
    transform: translateX(10px);
}
.weui-navbar__slider_1 {
    left: 29rpx;
    transform: translateX(400rpx);
}
.weui-navbar__slider {
    width: 9em;
}
.weui-flex {
    -webkit-box-align: center;
    -webkit-align-items: center;
    align-items: center;
}

.weui-cells {
    margin: 15rpx 0;
    // opacity: 0;
    // -webkit-transform: translateY(-50%);
    // transform: translateY(-50%);
    // -webkit-transition: 0.3s;
    // transition: 0.3s;
}

.weui-cell {
    line-height: 2.55555556;
}
.weui-cells:after,
.weui-cells:before {
    display: none;
}

.weui-cells_show {
    opacity: 1;
    -webkit-transform: translateY(0);
    transform: translateY(0);
}

.weui-cell:before {
    right: 15px;
}

.kind-list__item {
    margin: 10px 0;
    background-color: #fff;
    border-radius: 2px;
    overflow: hidden;
}

.kind-list__item:first-child {
    margin-top: 0;
}

.kind-list__img {
    width: 30px;
    height: 30px;
}

.kind-list__item-hd {
    padding: 20px;
    -webkit-transition: opacity 0.3s;
    transition: opacity 0.3s;
}

.kind-list__item-hd_show {
    opacity: 0.4;
}

.kind-list__item-bd {
    height: 0;
    overflow: hidden;
}

.kind-list__item-bd_show {
    height: auto;
}
</style>
