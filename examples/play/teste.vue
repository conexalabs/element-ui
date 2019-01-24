<template>
  <div>
    <el-container>
      <el-row type="flex">
        <el-col :span="24">
          <el-form :model="form" :rules="rules" ref="form">
            <el-form-item label="Email" prop="name">
              <el-input v-model="form.name" type="text" />
            </el-form-item>
            <el-form-item label="Email" prop="email">
              <el-input v-model="form.email" type="email" />
            </el-form-item>
            <el-button native-type="submit">submit</el-button>
          </el-form>
        </el-col>      
      </el-row>
    </el-container>
  </div>
</template>
<script>
	export default {
    data() {
      return {
        form: {
          name: '',
          email: ''
        },
        rules: {
          email: [
            { required: true, trigger: 'blur', fullField: 'Email', type: 'email' }
          ]
        }
      }
    },
    methods: {
      submit() {
        this.$refs.form.validate()
      } 
    }
  }
</script>
<style lang="scss"></style>