<!-- vue快捷创建组件 -->
<template>
  <div class='pact'>
    <el-form ref="form" :model="form" label-width="80px" class="formbox">

      <el-form-item label="预约号" label-width='82px' v-show="Aufgeld=='2'">
        <el-input v-model="input" class="kuang"></el-input>
      </el-form-item>
      <div class="conment">
        <div class="shenfen"  v-show="Aufgeld=='2'">
          <el-form-item label="私教合同号" label-width="82px">
            <el-input v-model="input1" disabled class="kuang"></el-input>
          </el-form-item>

          <el-form-item label="销售门店" label-width='82px'>
            <el-input v-model="input" disabled></el-input>
          </el-form-item>
        </div>
        <div class="shenfen" v-show="Aufgeld=='1'">
          <el-form-item label="预约号" label-width="82px">
            <el-input v-model="input1" disabled class="kuang"></el-input>
          </el-form-item>

          <el-form-item label="合同编号" label-width='82px'>
            <el-input v-model="input" disabled></el-input>
          </el-form-item>
        </div>

        <div class="shenfen">
          <el-form-item label="销售日期">
            <el-input v-model="input" disabled suffix-icon="el-icon-date" class="kuang"></el-input>
          </el-form-item>
          <el-form-item label-width='82px' label="销售类别">
            <el-input v-model="input" disabled></el-input>
          </el-form-item>
        </div>

        <div class="shenfen">
          <el-form-item label="会员姓名">
            <el-input v-model="input" disabled></el-input>
          </el-form-item>
          <el-form-item label-width='82px' label="会员编号">
            <el-input v-model="input" disabled></el-input>
          </el-form-item>
        </div>

        <el-form-item label="课程">
          <el-input v-model="input" disabled class='whinth'></el-input>
        </el-form-item>
        <el-form-item label="教练">
          <el-input v-model="input" disabled class='whinth'></el-input>
        </el-form-item>

        <div class="shenfen">
          <el-form-item label="预约日期">
            <el-input v-model="input1" disabled class="kuang"></el-input>
          </el-form-item>

          <el-form-item label="上课日期" style="margin-left: 4px;">
            <el-input v-model="input1" disabled class="kuang"></el-input>
          </el-form-item>
        </div>

        <div class="shenfen">
          <el-form-item label="是否打印">
            <el-input v-model="input" disabled></el-input>
          </el-form-item>
          <el-form-item label-width='82px' label="核销时间">
            <el-input v-model="input" disabled></el-input>
          </el-form-item>
        </div>
      </div>

      <el-form-item label="申请原因" v-show="Aufgeld=='2'">
        <el-input type="textarea" v-model="form.desc" class='whinth'></el-input>
      </el-form-item>
      <el-form-item v-show="Aufgeld=='2'">
        <el-button type="primary" @click="onSubmit">保存申请</el-button>
      </el-form-item>

      <el-form-item v-show="Aufgeld=='1'">
        <el-button type="primary" @click="onSubmit">审批历史</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>

<script>
// 这里可以导入其他文件（比如：组件，工具js，第三方插件js，json文件，图片文件等等）
// 例如：import 《组件名称》 from '《组件路径》';

export default {
  name: 'Hjtuikuansheng',
  props: {

  },
  // import引入的组件需要注入到对象中才能使用
  components: {

  },
  data () {
    // 这里存放数据
    return {
      Aufgeld: '',
      input: '',
      input1: '',
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
  activated () { }, // 如果页面有keep-alive缓存功能，这个函数会触发
  beforeRouteEnter (to, from, next) {
    console.log(from)
    let title
    if (from.meta.title == '我的申请') {
      title = '1'
    } else {
      title = '2'
    }
    next(vm => {
      vm.Aufgeld = title
    });
  }
}
</script>
<style scoped>
.conment {
    border: 3px solid rgb(255, 239, 206);
    padding-top: 10px;
    margin-bottom: 10px;
    width: 560px;
}
.pact {
    width: 630px !important;
    background: white;
}
.formbox {
    width: 90%;
    padding: 25px;
    margin: auto;
}

.shenfen {
    display: flex;
}

.kuang {
    width: 187px;
}
.whinth {
    width: 461px;
}
</style>
