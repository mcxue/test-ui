<template>
  <div :class="currentTheme" class="app-container">
    <header class="app-header">
      <h1>ALS UI 主题调试</h1>
      <div class="theme-selector">
        <span>选择主题：</span>
        <el-radio-group v-model="currentTheme" size="large">
          <el-radio-button label="">蓝色</el-radio-button>
          <el-radio-button label="theme-green">绿色</el-radio-button>
          <el-radio-button label="theme-purple">紫色</el-radio-button>
          <el-radio-button label="theme-orange">橙色</el-radio-button>
          <el-radio-button label="theme-gold">金色</el-radio-button>
          <el-radio-button label="theme-red">红色</el-radio-button>
        </el-radio-group>
      </div>
    </header>

    <main class="app-main">
      <!-- 按钮测试 -->
      <section class="test-section">
        <h2>按钮测试</h2>
        <div class="button-group">
          <el-button type="primary">主要按钮</el-button>
          <el-button type="success">成功按钮</el-button>
          <el-button type="warning">警告按钮</el-button>
          <el-button type="danger">危险按钮</el-button>
          <el-button type="info">信息按钮</el-button>
        </div>
      </section>

      <!-- 输入框测试 -->
      <section class="test-section">
        <h2>输入框测试</h2>
        <div class="input-group">
          <el-input placeholder="请输入内容" style="width: 200px; margin-right: 10px;"></el-input>
          <el-input placeholder="请输入内容" disabled style="width: 200px;"></el-input>
        </div>
      </section>

      <!-- 表格测试 -->
      <section class="test-section">
        <h2>表格测试</h2>
        <el-table :data="tableData" style="width: 100%">
          <el-table-column prop="date" label="日期" width="180"></el-table-column>
          <el-table-column prop="name" label="姓名" width="180"></el-table-column>
          <el-table-column prop="address" label="地址"></el-table-column>
        </el-table>
      </section>

      <!-- 卡片测试 -->
      <section class="test-section">
        <h2>卡片测试</h2>
        <div class="card-group">
          <el-card class="box-card" style="width: 300px; margin-right: 20px;">
            <template #header>
              <div class="card-header">
                <span>卡片标题</span>
              </div>
            </template>
            <div>卡片内容</div>
          </el-card>
          <el-card class="box-card" style="width: 300px;">
            <template #header>
              <div class="card-header">
                <span>卡片标题</span>
              </div>
            </template>
            <div>卡片内容</div>
          </el-card>
        </div>
      </section>

      <!-- 表单测试 -->
      <section class="test-section">
        <h2>表单测试</h2>
        <el-form :model="form" label-width="80px">
          <el-form-item label="姓名">
            <el-input v-model="form.name"></el-input>
          </el-form-item>
          <el-form-item label="年龄">
            <el-input v-model="form.age" type="number"></el-input>
          </el-form-item>
          <el-form-item label="性别">
            <el-radio-group v-model="form.gender">
              <el-radio label="男"></el-radio>
              <el-radio label="女"></el-radio>
            </el-radio-group>
          </el-form-item>
          <el-form-item>
            <el-button type="primary" @click="submitForm">提交</el-button>
            <el-button @click="resetForm">重置</el-button>
          </el-form-item>
        </el-form>
      </section>

      <!-- 标签测试 -->
      <section class="test-section">
        <h2>标签测试</h2>
        <div class="tag-group">
          <el-tag type="primary">主要标签</el-tag>
          <el-tag type="success">成功标签</el-tag>
          <el-tag type="warning">警告标签</el-tag>
          <el-tag type="danger">危险标签</el-tag>
          <el-tag type="info">信息标签</el-tag>
        </div>
      </section>

      <!-- 进度条测试 -->
      <section class="test-section">
        <h2>进度条测试</h2>
        <div class="progress-group">
          <el-progress :percentage="50" style="width: 300px; margin-right: 20px;"></el-progress>
          <el-progress :percentage="70" status="success" style="width: 300px;"></el-progress>
        </div>
      </section>

      <!-- 滑块测试 -->
      <section class="test-section">
        <h2>滑块测试</h2>
        <el-slider v-model="sliderValue" style="width: 300px;"></el-slider>
      </section>

      <!-- 选择器测试 -->
      <section class="test-section">
        <h2>选择器测试</h2>
        <div class="select-group">
          <el-select v-model="selectValue" placeholder="请选择" style="width: 200px; margin-right: 10px;">
            <el-option label="选项1" value="1"></el-option>
            <el-option label="选项2" value="2"></el-option>
            <el-option label="选项3" value="3"></el-option>
          </el-select>
          <el-date-picker v-model="dateValue" type="date" placeholder="选择日期" style="width: 200px;"></el-date-picker>
        </div>
      </section>
    </main>
  </div>
</template>

<script setup>
import { ref } from 'vue'

// 主题变量
const currentTheme = ref('')

// 表格数据
const tableData = ref([
  { date: '2024-01-01', name: '张三', address: '北京市朝阳区' },
  { date: '2024-01-02', name: '李四', address: '上海市浦东新区' },
  { date: '2024-01-03', name: '王五', address: '广州市天河区' }
])

// 表单数据
const form = ref({
  name: '',
  age: '',
  gender: '男'
})

// 滑块值
const sliderValue = ref(50)

// 选择器值
const selectValue = ref('')
const dateValue = ref('')

// 表单方法
const submitForm = () => {
  console.log('提交表单', form.value)
}

const resetForm = () => {
  form.value = {
    name: '',
    age: '',
    gender: '男'
  }
}
</script>

<style scoped>
.app-container {
  min-height: 100vh;
  padding: 20px;
  background-color: var(--ep-bg-color-page);
  transition: all 0.3s ease;
}

.app-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 30px;
  padding-bottom: 20px;
  border-bottom: 1px solid var(--ep-border-color);
}

.app-header h1 {
  color: var(--ep-text-color-primary);
  margin: 0;
}

.theme-selector {
  display: flex;
  align-items: center;
}

.theme-selector span {
  margin-right: 10px;
  color: var(--ep-text-color-regular);
}

.app-main {
  display: flex;
  flex-direction: column;
  gap: 30px;
}

.test-section {
  background-color: var(--ep-bg-color);
  padding: 20px;
  border-radius: var(--ep-border-radius-base);
  box-shadow: var(--ep-box-shadow);
}

.test-section h2 {
  color: var(--ep-text-color-primary);
  margin-top: 0;
  margin-bottom: 20px;
  font-size: 18px;
}

.button-group {
  display: flex;
  gap: 10px;
}

.input-group {
  display: flex;
  gap: 10px;
}

.card-group {
  display: flex;
  gap: 20px;
}

.tag-group {
  display: flex;
  gap: 10px;
}

.progress-group {
  display: flex;
  gap: 20px;
}

.select-group {
  display: flex;
  gap: 10px;
}

.card-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.card-header span {
  color: var(--ep-text-color-primary);
}
</style>
