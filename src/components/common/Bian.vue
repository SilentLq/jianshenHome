<!-- vue快捷创建组件 -->
<template>
  <div class='app'>
    <el-dialog :title="dialog.title" :visible.sync="dialog.show" :close-on-click-modal='false' :close-on-press-escape='false' :modal-append-to-body="false" width="30%">
      <el-form :model="ruleForm"  ref="ruleForm" label-width="100px" class="demo-ruleForm">
        <el-form-item label="合同编号">
          <el-input v-model="ruleForm.code" style="width: 185px;"></el-input>
        </el-form-item>

        <el-form-item label="结算方式">
          <el-select v-model="ruleForm.clearing" style="width: 185px;">
            <el-option v-for='item in type_list' :key="item.value" :label="item.label" :value="item.value"></el-option>
          </el-select>
        </el-form-item>

        <el-form-item label="供应商编号">
          <el-select v-model="ruleForm.supplierCode" style="width: 185px;" @change="gongshang()">
            <el-option v-for='item in gongying' :key="item.value" :label="item.name" :value="item.code"></el-option>
          </el-select>
        </el-form-item>

        <el-form-item label="开始日期">
          <el-date-picker v-model="ruleForm.startDate" type="date" placeholder="选择日期" style="width:187px;" prop="shangdata">
          </el-date-picker>
        </el-form-item>

        <el-form-item label="结束日期">
          <el-date-picker v-model="ruleForm.endDate" type="date" placeholder="选择日期" style="width:187px;" prop="shangdata">
          </el-date-picker>
        </el-form-item>

        <el-form-item label="配送方式">
          <el-select v-model="ruleForm.ps" style="width: 185px;">
            <el-option v-for='item in pei' :key="item.value" :label="item.label" :value="item.value"></el-option>
          </el-select>
        </el-form-item>
        <el-form-item>
          <el-button type="primary" @click="submitForm('ruleForm')">立即添加·</el-button>
          <el-button @click="resetForm('ruleForm')">重置</el-button>
        </el-form-item>
      </el-form>
    </el-dialog>

  </div>

</template>

<script>
import axios from "axios";
import { base } from '../js/url'
// 这里可以导入其他文件（比如：组件，工具js，第三方插件js，json文件，图片文件等等）
// 例如：import 《组件名称》 from '《组件路径》';

export default {
  name: 'logfound',
  props: {
    dialog: Object,
    ruleForm: Object
  },
  // import引入的组件需要注入到对象中才能使用
  components: {
  },
  data () {
    // 这里存放数据
    return {
      type_list: [{
        value: '1',
        label: '经销'
      }, {
        value: '2',
        label: '代销'
      }
      ],
      pei: [{
        value: '1',
        label: '配送'
      }, {
        value: '2',
        label: '直送'
      }
      ],
      gongying: [],
    }
  },
  // 监听属性 类似于data概念
  computed: {},
  // 监控data中的数据变化
  watch: {},
  // 方法集合
  methods: {
    resetForm (formName) {
      this.$refs[formName].resetFields();
    },

    gongshang (e) {
    this.staat = e
    },

// 添加
    submitForm (ruleForm) {
      this.$refs[ruleForm].validate(valid => {
        const url = this.dialog.option == 'add' ? `addSpContract` : `updateSpContract/`
        if (valid) {
          this.ruleForm.clearing=parseInt(this.ruleForm.clearing)
          this.ruleForm.ps=parseInt(this.ruleForm.ps)
          axios.post(base + `/commodity/${url}`, this.ruleForm)
            .then(res => {
              if (res.data.code == 10000) {
                this.$message({
                  message: '操作成功',
                  type: 'success'
                });
                //隐藏对话框
                this.dialog.show = false;
                this.$emit('update');
              } else {
                this.$message.error('操作失败，请重新再试！');
              }

            })
        }
      })
    },
  },
  // 生命周期 - 创建完成（可以访问当前this实例）
  created () {
    axios
      .post(base + '/commodity/getAllSupplier').then((res) => {
        this.gongying = res.data
      })
    // this.gongshang () 
  },
  // 生命周期 - 挂载完成（可以访问DOM元素）
  mounted () {

  },
  beforeCreate () { }, // 生命周期 - 创建之前
  beforeMount () { }, // 生命周期 - 挂载之前
  beforeUpdate () { }, // 生命周期 - 更新之前
  updated () { }, // 生命周期 - 更新之后
  beforeDestroy () { }, // 生命周期 - 销毁之前
  destroyed () { }, // 生命周期 - 销毁完成
  activated () { } // 如果页面有keep-alive缓存功能，这个函数会触发
}
</script>
<style scoped>
@import './../../assets/css/table.css';
.app {
    width: 100% !important;
}
.block {
    width: 50%;
    margin: auto;
}
.btn {
    background: #333;
    color: white;
    width: 55px;
}
</style>
