<template>
    <div>
        <div class="page">
            <div class="page__bd">
                <div class="weui-cells__title">用户名</div>
                <div class="weui-cells weui-cells_after-title">
                    <div class="weui-cell weui-cell_input">
                        <div class="weui-cell__bd">
                            <input class="weui-input" placeholder="请输入用户名" />
                        </div>
                    </div>
                </div>
                <div class="weui-cells__title">性别</div>
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
                <div class="weui-cells__title">联系电话</div>
                <div class="weui-cells weui-cells_after-title">
                    <div class="weui-cell weui-cell_input">
                        <div class="weui-cell__bd">
                            <input class="weui-input" placeholder="请输入联系电话" />
                        </div>
                    </div>
                </div>
                <div class="weui-btn-area">
                    <button class="weui-btn" type="primary" @click="showTopTipsFun">确定</button>
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
                { name: "男", value: "0", checked: true },
                { name: "女", value: "1" }
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
