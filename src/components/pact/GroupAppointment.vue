<!-- vue快捷创建组件 -->
<template>
  <div class='pact'>
    <el-form ref="form" :model="form" label-width="80px" class="formbox">

      <el-form-item label="会员卡号" label-width='82px'>
        <input type="text" class="input_box">
      </el-form-item>
      <div class="shenfen">
        <el-form-item label="会员姓名">
          <input type="text" class="input_box">
        </el-form-item>
        <el-form-item label="手机号" style="margin-left: 28px" label-width='82px'>
          <input type="text" class="input_box">
        </el-form-item>
      </div>
      <div class="shenfen">

        <el-form-item label="私教课程">
          <el-select v-model="form.region" class="sex">
            <el-option label="F00001 - 常规" value="1"></el-option>
            <el-option label="F00002 - 拉伸" value="2"></el-option>
            <el-option label="F00003 - 康复" value="3"></el-option>
            <el-option label="F00004 - 拳击" value="4"></el-option>
            <el-option label="F00005 - 普拉提" value="5"></el-option>
            <el-option label="F00006 - 筋膜放松" value="6"></el-option>
            <el-option label="F00007 - 维密课程" value="7"></el-option>
            <el-option label="F00008 - 力量举" value="8"></el-option>
            <el-option label="F00009 - 体态纠正" value="9"></el-option>
            <el-option label="F00010 - 青少年体适能" value="10"></el-option>
            <el-option label="F00011 - 产后恢复" value="11"></el-option>
            <el-option label="F00012 - 精准发力" value="12"></el-option>
            <el-option label="F00013 - 特色拳击" value="13"></el-option>
            <el-option label="F00014 - 肌肉工程" value="14"></el-option>
            <el-option label="F00015 - 脂肪杀手" value="15"></el-option>
            <el-option label="F00017 - 游泳课" value="16"></el-option>
            <el-option label="F00019 - 包一年私教" value="17"></el-option>
            <el-option label="F00020 - 包季度私教" value="18"></el-option>
            <el-option label="F00021 - 包半年私教" value="19"></el-option>
            <el-option label="F00024 - 体适能" value="20"></el-option>
            <el-option label="F00025 - 包9月私教" value="21"></el-option>
            <el-option label="F00026 - 特色瑜伽" value="22"></el-option>
            <el-option label="F00027 - 悬挂课程TRX" value="23"></el-option>
            <el-option label="F00031 - 产中训练" value="24"></el-option>
            <el-option label="F00032 - 经理课程" value="25"></el-option>
            <el-option label="F00033 - 健美" value="26"></el-option>
            <el-option label="F00036 - 极速瘦身" value="27"></el-option>
            <el-option label="F00037 - 少儿体适能" value="28"></el-option>
            <el-option label="F00038 - 空中瑜伽" value="29"></el-option>
            <el-option label="F00041 - 健美备赛" value="30"></el-option>
            <el-option label="F00042 - 功能性" value="31"></el-option>
            <el-option label="F00043 - 功能训练" value="32"></el-option>
            <el-option label="F00044 - 综合课程" value="33"></el-option>
            <el-option label="F00045 - 一月套课" value="34"></el-option>
            <el-option label="F00046 - Eptc " value="35"></el-option>
            <el-option label="F00047 - 三月套课" value="36"></el-option>
            <el-option label="F00048 - 抽奖私教课" value="37"></el-option>
            <el-option label="F00049 - 全年巩固计划" value="38"></el-option>
            <el-option label="F00050 - 半年进步计划" value="39"></el-option>
            <el-option label="F00051 - 季度成效计划" value="40"></el-option>
            <el-option label="F00052 - 高频筋膜枪放松" value="41"></el-option>
            <el-option label="F00053 - 关节稳定" value="42"></el-option>
            <el-option label="F00054 - 局部疼痛管理" value="43"></el-option>
            <el-option label="F00055 - 维密美腿" value="44"></el-option>
            <el-option label="F00056 - 维密橄榄背" value="45"></el-option>
            <el-option label="F00057 - 马甲线S" value="46"></el-option>
            <el-option label="F00058 - 极致美臀" value="47"></el-option>
            <el-option label="F00059 - 维密美人肩" value="48"></el-option>
            <el-option label="F00060 -  麒麟臂" value="49"></el-option>
            <el-option label="F00061 -  雕像胸" value="50"></el-option>
            <el-option label="F00062 - 王字腹" value="51"></el-option>
            <el-option label="F00063 - 蝴蝶背" value="52"></el-option>
            <el-option label="F00064 - 男性功能" value="53"></el-option>
            <el-option label="F00065 - 教练学习课程" value="54"></el-option>
            <el-option label="F00066 - 核心" value="55"></el-option>

          </el-select>
        </el-form-item>
        <el-form-item label="上课教练" style="margin-left: 28px">
          <el-select v-model="form.region" class="sex">
            <el-option label="B01171 - 伍一 - 一星级" value="shanghai"></el-option>
          </el-select>
        </el-form-item>

      </div>
      <div class="shenfen">
        <div class="block">
          <span class="demonstration">上课时间</span>
          <el-date-picker v-model="value1" type="date" placeholder="选择日期">
          </el-date-picker>
        </div>
        <el-time-select v-model="value" :picker-options="{
    start: '08:30',
    step: '00:15',
    end: '18:30'
  }" placeholder="选择时间">
        </el-time-select>

      </div>

      <el-form-item>
        <el-button type="primary" @click="onSubmit">确认并提交</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>
<script>
// 这里可以导入其他文件（比如：组件，工具js，第三方插件js，json文件，图片文件等等）
// 例如：import 《组件名称》 from '《组件路径》';

export default {
  name: 'indexdj',
  props: {

  },
  // import引入的组件需要注入到对象中才能使用
  components: {

  },
  data () {
    // 这里存放数据
    return {
      value: '',
      value1: '',
      form: {
        name: '',
        region: '',
        date1: '',
        date2: '',
        delivery: false,
        type: [],
        resource: '',
        desc: ''
      }
    }
  },
  // 监听属性 类似于data概念
  computed: {},
  // 监控data中的数据变化
  watch: {},
  // 方法集合
  methods: {
    onSubmit () {
      console.log('submit!');
    },
  },
  // 生命周期 - 创建完成（可以访问当前this实例）
  created () {

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
.pact {
    width: 670px !important;
    background: white;
}

.demonstration {
    height: 32px;
    vertical-align: middle;
    line-height: 32px !important;
    font-size: 14px;
    color: #606266;
    padding: 0 10px 0 0;
    -webkit-box-sizing: border-box;
    box-sizing: border-box;
}

.formbox {
    width: 90%;
    padding: 25px;
    margin: auto;
}
.shenfen {
    display: flex;
}

.input_box {
    -webkit-appearance: none;
    background-color: #fff;
    background-image: none;
    border-radius: 4px;
    border: 1px solid #dcdfe6;
    box-sizing: border-box;
    color: #606266;
    display: inline-block;
    font-size: inherit;
    height: 30px;
    line-height: 30px;
    outline: 0;
    padding: 0 15px;
    transition: border-color 0.2s cubic-bezier(0.645, 0.045, 0.355, 1);
    width: 203px !important;
}

.block {
    margin-left: 15px !important;
    margin-bottom: 15px !important;
}
</style>
