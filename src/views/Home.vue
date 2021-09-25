<template>
  <div class="home">
  <el-button type="text" @click="open">点击打开 Message Box</el-button>
    <el-button type="text" @click="open">点击打开 Message Box</el-button>

    <el-button type="text" @click="open">点击打开 Message Box</el-button>
    <el-button type="text" @click="open">点击打开 Message Box</el-button>
    <el-button type="text" @click="open">点击打开 Message Box</el-button>
    <el-button type="text" @click="open">点击打开 Message Box</el-button>
    <el-button type="text" @click="open">点击打开 Message Box</el-button>

  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld
  },
  methods:{
      open() {
        console.log(111)
        this.$confirm('确定要结束当前会话吗？', '结束会话确认', {
          confirmButtonText: '确定',
          cancelButtonText: '取消',
        }).then(() => {
        this.$confirm('您已退出当前会话，感谢您的咨询，请对我的服务做出评价', {
          confirmButtonText: '评价',
          center: true,
          showClose:false,
          closeOnClickModal:false,
          showCancelButton:false
        }).then(() => {
          console.log('成功')
        })
        }).catch(() => {
          this.$message({
            type: 'info',
            message: '已取消删除'
          });
        });
      }
  }
}
</script>
