<template>
  <div class="hello">
    <el-button type="primary" @click="switchChinese()">中文</el-button>
    <el-button type="primary" @click="switchEnlish()">En</el-button>
    <p>{{$t('message.hello')}}</p> 
    <p>{{$t('message.msg')}}</p>
    <el-table
      :data="tableData"
      style="width: 100%">
      <el-table-column
        prop="date"
        :label="$t('message.time')"
        width="180">
      </el-table-column>
      <el-table-column
        prop="name"
        :label="$t('message.name')"
        width="180">
      </el-table-column>
      <el-table-column
        prop="address"
        :label="$t('message.adress')">
      </el-table-column>
    </el-table>
    <el-button type="primary" @click="open2">{{$t('message.btnText')}}</el-button>
  </div>
</template>

<script>
export default {
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      tableData: [{
          date: '2016-05-02',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1518 弄'
        }, {
          date: '2016-05-04',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1517 弄'
        }, {
          date: '2016-05-01',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1519 弄'
        }, {
          date: '2016-05-03',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1516 弄'
        }
      ]
    }
  },
  methods: {
    switchChinese(){
      this.$i18n.locale = 'cn'; 
    },
    switchEnlish(){
      this.$i18n.locale = 'en'; 
    },
    open2() {
      this.$confirm('此操作将永久删除该文件, 是否继续?', this.$t("message.tips"), {
        confirmButtonText: this.$t("message.cancel"),
        cancelButtonText: this.$t("message.ok"),
        type: 'warning'
      }).then(() => {
        this.$message({
          type: 'success',
          message: this.$t("message.success")
        });
      }).catch(() => {
        this.$message({
          type: 'info',
          message: this.$t("message.fail")
        });          
      });
    }
  }
}
</script>