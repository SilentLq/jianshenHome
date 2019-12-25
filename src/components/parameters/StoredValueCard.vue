<!-- vue快捷创建组件 -->
<template>
    <div class="appmm">
        <div class="conments">
            <div class="appx">
                <el-form ref="form" :model="form" label-width="80px" class="formbox demo-ruleForm">
                    <el-form-item label="收卡门店" v-model="form.name">
                        <el-select v-model="form.name" class="sex">
                            <el-option
                                v-for="(item,index) in array"
                                :label="item.label"
                                :value="item.value"
                                :key="index+'a'"
                            ></el-option>
                        </el-select>
                    </el-form-item>
                    <el-form-item label="配卡类型" v-model="form.name">
                        <el-select v-model="form.name" class="sex">
                            <el-option
                                v-for="(item,index) in array"
                                :label="item.label"
                                :value="item.value"
                                :key="index+'a'"
                            ></el-option>
                        </el-select>
                    </el-form-item>
                    <el-form-item label="卡号">
                        <el-input type="number" v-model="form.name" class="input_box" />
                    </el-form-item>
                    <el-form-item>
                        <div class="name">
                            <div>
                                <el-button size="small" type="primary">提交卡号</el-button>
                            </div>
                            <el-upload
                                class="upload-demo"
                                action="https://jsonplaceholder.typicode.com/posts/"
                                :on-preview="handlePreview"
                                :on-remove="handleRemove"
                                list-type="picture"
                            >
                                <el-button size="small" type="primary">上传卡号（Excel文件）</el-button>
                            </el-upload>
                        </div>
                    </el-form-item>
                </el-form>
            </div>
        </div>
        <div class="btn">
            <el-button type="primary" @click="onSubmit('form')">提交配卡</el-button>
            <el-button type="primary" @click="onSubmit('form')">查询配卡</el-button>
        </div>
        <el-table :data="table" border style="width: 45%;text-align:center;margin-left:30px;">
            <el-table-column prop="number" label="卡号"></el-table-column>
            <el-table-column prop="name" label="收卡门店"></el-table-column>
            <el-table-column prop="leavel" label="卡类型"></el-table-column>
        </el-table>
    </div>
</template>

<script>
// 这里可以导入其他文件（比如：组件，工具js，第三方插件js，json文件，图片文件等等）
// 例如：import 《组件名称》 from '《组件路径》';

import { mapActions, mapState } from 'vuex';
export default {
    name: 'indexxs',

    props: {},
    // import引入的组件需要注入到对象中才能使用
    data() {
        // 这里存放数据
        return {
            form: {
                name: ''
            },
            fileList: [],
            array: [{ label: '123', value: '321' }],
            table:[]
        };
    },
    // 监听属性 类似于data概念
    computed: {
        ...mapState({})
    },
    // 监控data中的数据变化
    watch: {},
    // 方法集合
    methods: {
        ...mapActions([]),
        onSubmit() {},
        handleRemove(file, fileList) {
            console.log(file, fileList);
        },
        handlePreview(file) {
            console.log(file);
        }
    },
    // 生命周期 - 创建完成（可以访问当前this实例）
    created() {},
    // 生命周期 - 挂载完成（可以访问DOM元素）
    mounted() {},
    beforeCreate() {}, // 生命周期 - 创建之前
    beforeMount() {}, // 生命周期 - 挂载之前
    beforeUpdate() {}, // 生命周期 - 更新之前
    updated() {}, // 生命周期 - 更新之后
    beforeDestroy() {}, // 生命周期 - 销毁之前
    destroyed() {}, // 生命周期 - 销毁完成
    activated() {} // 如果页面有keep-alive缓存功能，这个函数会触发
};
</script>
<style lang="scss" scoped>
@import './../../assets/css/table.css';
.miet {
    margin-left: 40% !important;
    margin-top: 30px;
}
.titex {
    font-size: 13px;
}
.conments {
    display: flex;
    // padding: 20px;
    width: 45%;
    margin: 20px;
    border: 10px solid #f4f4f4;
}
.aptable {
    width: 48% !important;
    margin-top: 20px;
    margin-left: 20px;
}
.appmm {
    width: 100% !important;
    background: white;
    height: 100%;
    overflow: hidden;
    position: relative;
}
.appx {
    width: 90% !important;
}
.formbox {
    width: 90%;
    padding: 25px;
    margin: auto;
}
.hname {
    width: 80% !important;
}
.divbin {
    display: flex !important;
}

.shenfen {
    display: flex;
}
.sinxex {
    width: 48.5% !important;
    margin-left: 5px;
}
.dinglei {
    display: flex;
}
.conmeny {
    display: flex;
}

.minx {
    display: flex;
}
.name {
    display: flex;
    justify-content: space-around;
}
.yingbut {
    display: -webkit-box;
}
.el-date-range-picker {
    width: 510px !important;
    z-index: 500;
}
.block {
    margin-bottom: 15px;
}
.btn {
    display: flex;
    justify-content: center;
    width: 35%;
    margin-bottom: 30px;
}
</style>
