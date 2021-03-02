<template>
  <div class="hello">
    <h1>{{ data.name }}</h1>
    <h1>{{ show }}</h1>

    <el-dialog
      title="提示"
      v-model="props.show"
      width="30%"
      :before-close="handleClose"
    >
      <span>这是一段信息</span>
      <template #footer>
        <span class="dialog-footer">
          <el-button @click="props.show = false">取 消</el-button>
          <el-button type="primary" @click="props.show = false"
            >确 定</el-button
          >
        </span>
      </template>
    </el-dialog>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: ["show", "data"],
  setup(context, props) {
    const handleClose = done => {
      this.$confirm("确认关闭？")
        .then(() => {
          done();
        })
        .catch(() => {});
    };
    return {
      handleClose,
      props
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
