<template>
    <my-page title="定制版">
        <section class="tool-box" v-if="type !== 6 && type !== 25 && type !== 41">
            <div class="tool-box-body">
                <div class="form-horizontal">
                    <div id="form">
                        <div class="form-group">
                            <ui-text-field v-model.number="height" type="number" label="身高（厘米）" /> 
                        </div>
                        <div class="form-group">
                            <ui-text-field v-model.number="weight" type="number" label="体重（斤）" /> 
                        </div>
                        <div class="btns">
                            <ui-raised-button class="btn" label="尺码生成" primary @click="ok" />
                            <ui-raised-button class="btn" label="重新输入" @click="reset" />
                        </div>
                    </div>
                    <div class="result" v-if="result">推荐尺码：<span class="strong">{{ result }}</span></div>
                </div>
            </div>
        </section>
    </my-page>
</template>

<script>
    /* eslint-disable */
    export default {
        data () {
            return {
                type: null,
                height: null,
                weight: null,
                result: ''
            }
        },
        mounted() {
            this.type = parseInt(this.$route.params.type)
            let type = this.type
        },
        methods: {
            reset() {
                this.height = this.weight = this.result = null
            },
            ok() {
                if (!this.height) {
                    this.$message({
                        type: 'danger',
                        text: '请输入身高'
                    })
                    return
                }
                if (this.height < 100 || this.height > 200) {
                    this.$message({
                        type: 'danger',
                        text: '身高输入有误，请重新输入'
                    })
                    return
                }
                if (!this.weight) {
                    this.$message({
                        type: 'danger',
                        text: '请输入体重'
                    })
                    return
                }
                this.result = this.calSize(this.height, this.weight, this.type)
            },
            calSize(height, weight) {
                if (height <=149) {
                    // if (weight >= 30 && weight <= 80) {
                    //     return 'XS'
                    // }
                    if (weight <= 80) {
                        return 'XS'
                    }
                    if (weight >= 81 && weight <= 90) {
                        return 'S'
                    }
                    if (weight >= 91 && weight <= 100) {
                        return 'M'
                    }
                    // if (weight >= 101 && weight <= 105) {
                    //     return 'L'
                    // }
                    if (weight >= 101) {
                        return 'L'
                    }
                }
                if (height >= 150 && height <=154) {
                    if (weight <= 80) {
                        return 'XS'
                    }
                    if (weight >= 81 && weight <= 90) {
                        return 'S'
                    }
                    if (weight >= 91 && weight <= 95) {
                        return 'M'
                    }
                    if (weight >= 96 && weight <= 103) {
                        return 'L'
                    }
                    if (weight >= 104 && weight <= 110) {
                        return 'XL'
                    }
                    if (weight >= 111) {
                        return 'XXL'
                    }
                }
                if (height >= 155 && height <=161) {
                    if (weight <= 80) {
                        return 'XS'
                    }
                    if (weight >= 81 && weight <= 95) {
                        return 'S'
                    }
                    if (weight >= 96 && weight <= 100) {
                        return 'M'
                    }
                    if (weight >= 101 && weight <= 105) {
                        return 'L'
                    }
                    if (weight >= 106 && weight <= 115) {
                        return 'XL'
                    }
                    if (weight >= 116) {
                        return 'XXL'
                    }
                }
                if (height >= 162 && height <=165) {
                    if (weight <= 85) {
                        return 'XS'
                    }
                    if (weight >= 86 && weight <= 97) {
                        return 'S'
                    }
                    if (weight >= 98 && weight <= 105) {
                        return 'M'
                    }
                    if (weight >= 106 && weight <= 113) {
                        return 'L'
                    }
                    if (weight >= 114 && weight <= 120) {
                        return 'XL'
                    }
                    if (weight >= 121) {
                        return 'XXL'
                    }
                }
                if (height >= 166 && height <=170) {
                    if (weight <= 95) {
                        return 'S'
                    }
                    if (weight >= 96 && weight <= 106) {
                        return 'M'
                    }
                    if (weight >= 107 && weight <= 115) {
                        return 'L'
                    }
                    if (weight >= 116 && weight <= 122) {
                        return 'XL'
                    }
                    if (weight >= 123) {
                        return 'XXL'
                    }
                }
                if (height >= 171) {
                    if (weight <= 100) {
                        return 'S'
                    }
                    if (weight >= 101 && weight <= 112) {
                        return 'M'
                    }
                    if (weight >= 113 && weight <= 120) {
                        return 'L'
                    }
                    if (weight >= 121 && weight <= 128) {
                        return 'XL'
                    }
                    if (weight >= 129) {
                        return 'XXL'
                    }
                }
                return '出错'
            }
        }
    }
</script>

<style lang="scss" scoped>
/**/
.tool-box {
    max-width: 480px;
    padding: 16px;
    margin-bottom: 24px;
    background-color: #fff;
    border-radius: 4px;
    padding: 16px;
    box-shadow: 0 1px 6px rgba(0,0,0,.117647), 0 1px 4px rgba(0,0,0,.117647);
    .result {
        margin-top: 16px;
    }
    .strong {
        color: #f60;
        font-weight: bold;
        margin-left: 8px;
        font-size: 16px;
    }
    .btns {
        .btn {
            margin-right: 8px;
        }
    }
}
</style>
