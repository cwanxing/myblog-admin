<template>
  <section class="form-section">
    <el-form ref="form" :model="form" label-width="80px" :rules="rules">
      <el-form-item label="文章标题" required>
        <el-input v-model="form.articleTitle"></el-input>
      </el-form-item>
      <el-form-item label="文章描述">
        <el-input v-model="form.articleAbstract"></el-input>
      </el-form-item>
      <el-form-item label="发布时间" required>
        <el-form-item prop="date">
          <el-time-picker type="fixed-time" placeholder="选择发布时间" v-model="form.issueData"
                          style="width: 100%;"></el-time-picker>
        </el-form-item>
      </el-form-item>
      <el-form-item label="文章类型" required>
        <el-select v-model="form.articleType" placeholder="请选择类型">
          <el-option label="电脑维修" value="computer"></el-option>
          <el-option label="生活随笔" value="life"></el-option>
          <el-option label="代码世界" value="computer"></el-option>
          <el-option label="大千世界" value="life"></el-option>
          <el-option label="软件课堂" value="computer"></el-option>
        </el-select>
      </el-form-item>
      <el-form-item label="文章内容" required>
        <el-input type="textarea" v-model="form.articleData"></el-input>
      </el-form-item>
      <el-form-item>
        <el-button type="primary" @click="onSubmit">立即发布</el-button>
        <el-button>取消</el-button>
      </el-form-item>
    </el-form>
  </section>
</template>

<script>
  export default {
    data() {
      return {
        form: {
          articleTitle: '',
          articleAbstract: '',
          issueData: '',
          articleType: '',
          articleData: ''
        },
        rules: {
          articleTitle: [
            { required: true, message: '请输入活动名称', trigger: 'blur' },
            { min: 3, max: 5, message: '长度在 3 到 5 个字符', trigger: 'blur' }
          ],
        }
      }
    },
    methods: {
      getUEContent() {

      },
      getUEContentTxt() {

      }
    }
  };
</script>
<style>
  .info{
    border-radius: 10px;
    line-height: 20px;
    padding: 10px;
    margin: 10px;
    background-color: #ffffff;
  }
</style>


