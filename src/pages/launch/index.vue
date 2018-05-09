<template>
    <div>
        <div class="page">
            <div class="page__bd">
                <div class="weui-cells__title">活动类型</div>
                <div class="weui-cells weui-cells_after-title">
                    <div class="weui-cell weui-cell_input">
                        <div class="weui-cell__bd">
                            <input class="weui-input" placeholder="请输入活动类型" />
                        </div>
                    </div>
                </div>
                <div class="weui-cells__title">活动内容</div>
                <div class="weui-cells weui-cells_after-title">
                    <div class="weui-cell weui-cell_input">
                        <div class="weui-cell__bd">
                            <input class="weui-input" placeholder="请输入活动内容" />
                        </div>
                    </div>
                </div>
                <div class="weui-cells__title">人数限制</div>
                <div class="weui-cells weui-cells_after-title">
                    <radio-group @change="radioChange">
                        <label class="weui-cell weui-check__label" v-for="item in radioItems" :key="index">
                            <radio class="weui-check" :value="item.value" :checked="item.checked" />
                            <div class="weui-cell__bd">{{item.name}}</div>
                            <div class="weui-cell__ft weui-cell__ft_in-radio" v-if="item.checked">
                                <icon class="weui-icon-radio" type="success_no_circle" size="16"></icon>
                            </div>
                        </label>
                    </radio-group>
                </div>
                <div class="weui-cells__title">开始时间</div>
                <div class="weui-cells weui-cells_after-title">
                    <div class="weui-cell weui-cell_input">
                        <div class="weui-cell__bd">
                            <input class="weui-input" placeholder="请输入开始时间" />
                        </div>
                    </div>
                </div>
                <div class="weui-cells__title">结束时间</div>
                <div class="weui-cells weui-cells_after-title">
                    <div class="weui-cell weui-cell_input">
                        <div class="weui-cell__bd">
                            <input class="weui-input" placeholder="请输入结束时间" />
                        </div>
                    </div>
                </div>
                <div class="weui-cells__title">发起人</div>
                <div class="weui-cells weui-cells_after-title">
                    <radio-group @change="radioChange1">
                        <label class="weui-cell weui-check__label" v-for="item in radioItems1" :key="index">
                            <radio class="weui-check" :value="item.value" :checked="item.checked" />
                            <div class="weui-cell__bd">{{item.name}}</div>
                            <div class="weui-cell__ft weui-cell__ft_in-radio" v-if="item.checked">
                                <icon class="weui-icon-radio" type="success_no_circle" size="16"></icon>
                            </div>
                        </label>
                    </radio-group>
                </div>
                <div class="weui-btn-area">
                    <button class="weui-btn" type="primary" @click="showTopTipsFun">发起</button>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            name: "register",
            radioItems: [
                { name: "不限制", value: "0", checked: true },
                { name: "限制", value: "1" }
            ],
            radioItems1: [
                { name: "参与", value: "0", checked: true },
                { name: "不参与", value: "1" }
            ]
        };
    },
    methods: {
        radioChange(e) {
            console.log(
                "radio发生change事件，携带value值为：" + e.mp.detail.value
            );
            let radioItems = this.radioItems;
            for (let i = 0; i < radioItems.length; ++i) {
                radioItems[i].checked =
                    radioItems[i].value === e.mp.detail.value;
            }
            this.radioItems = radioItems;
        },
        radioChange1(e) {
            console.log(
                "radio发生change事件，携带value值为：" + e.mp.detail.value
            );
            let radioItems = this.radioItems1;
            for (let i = 0; i < radioItems.length; ++i) {
                radioItems[i].checked =
                    radioItems[i].value === e.mp.detail.value;
            }
            this.radioItems1 = radioItems;
        }
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
</style>
