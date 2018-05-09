<template>
    <div>
        <div class="page">
            <div class="page__bd">
                <div class="weui-cells__title">报名人数</div>
                <div class="weui-cells weui-cells_after-title">
                    <div class="weui-cell weui-cell_input">
                        <div class="weui-cell__bd">
                            12人
                        </div>
                    </div>
                </div>
                <div class="weui-cells weui-cells_after-title">
                    <div class="weui-cell weui-cell_input">
                        <div class="weui-cell__bd">XXX:11111111111111</div>
                    </div>
                    <div class="weui-cell weui-cell_input">
                        <div class="weui-cell__bd">XXX:11111111111111</div>
                    </div>
                    <div class="weui-cell weui-cell_input">
                        <div class="weui-cell__bd">XXX:11111111111111</div>
                    </div>
                    <div class="weui-cell weui-cell_input">
                        <div class="weui-cell__bd">XXX:11111111111111</div>
                    </div>
                </div>
                <div class="weui-cells__title">活动内容</div>
                <div class="weui-cells weui-cells_after-title">
                    <div class="weui-cell weui-cell_input">
                        <div class="weui-cell__bd">
                            XXXXXXXXXXXXXXXXXXXXX....
                        </div>
                    </div>
                </div>
                <div class="weui-btn-area">
                    <button class="weui-btn" type="primary" @click="showTopTipsFun">预约</button>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            name: "detail",
        };
    },
    methods: {
    },
    created() {}
};
</script>

<style lang="scss" scoped>
page,
.page,
.page__bd {
    height: 100%;
}
.page__bd {
    padding-bottom: 0;
}
.weui-cell {
    line-height: 2.55555556;
}
</style>
