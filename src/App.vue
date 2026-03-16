<template>
  <el-config-provider namespace="ep">
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
        <!-- Button 按钮 -->
        <section class="test-section">
          <h2>Button 按钮</h2>
          <div class="component-group">
            <el-button type="primary">主要按钮</el-button>
            <el-button type="success">成功按钮</el-button>
            <el-button type="warning">警告按钮</el-button>
            <el-button type="danger">危险按钮</el-button>
            <el-button type="info">信息按钮</el-button>
          </div>
        </section>

        <!-- Link 链接 -->
        <section class="test-section">
          <h2>Link 链接</h2>
          <div class="component-group">
            <el-link type="primary">主要链接</el-link>
            <el-link type="success">成功链接</el-link>
            <el-link type="warning">警告链接</el-link>
            <el-link type="danger">危险链接</el-link>
            <el-link type="info">信息链接</el-link>
          </div>
        </section>

        <!-- Text 文本 -->
        <section class="test-section">
          <h2>Text 文本</h2>
          <div class="component-group">
            <el-text type="primary">主要文本</el-text>
            <el-text type="success">成功文本</el-text>
            <el-text type="warning">警告文本</el-text>
            <el-text type="danger">危险文本</el-text>
            <el-text type="info">信息文本</el-text>
          </div>
        </section>

        <!-- Checkbox 多选框 -->
        <section class="test-section">
          <h2>Checkbox 多选框</h2>
          <div class="component-group">
            <el-checkbox v-model="checkbox1">选项1</el-checkbox>
            <el-checkbox v-model="checkbox2">选项2</el-checkbox>
            <el-checkbox v-model="checkbox3" disabled>禁用选项</el-checkbox>
          </div>
        </section>

        <!-- Date Picker 日期选择器 -->
        <section class="test-section">
          <h2>Date Picker 日期选择器</h2>
          <div class="component-group">
            <el-date-picker v-model="dateValue" type="date" placeholder="选择日期" style="width: 200px;"></el-date-picker>
          </div>
        </section>

        <!-- Input 输入框 -->
        <section class="test-section">
          <h2>Input 输入框</h2>
          <div class="component-group">
            <el-input v-model="inputValue" placeholder="请输入内容" style="width: 200px;"></el-input>
            <el-input v-model="inputValue" placeholder="请输入内容" disabled style="width: 200px;"></el-input>
          </div>
        </section>

        <!-- Input Number 数字输入框 -->
        <section class="test-section">
          <h2>Input Number 数字输入框</h2>
          <div class="component-group">
            <el-input-number v-model="numberValue" :min="1" :max="10"></el-input-number>
          </div>
        </section>

        <!-- Radio 单选框 -->
        <section class="test-section">
          <h2>Radio 单选框</h2>
          <div class="component-group">
            <el-radio v-model="radioValue" label="1">选项1</el-radio>
            <el-radio v-model="radioValue" label="2">选项2</el-radio>
            <el-radio v-model="radioValue" label="3" disabled>禁用选项</el-radio>
          </div>
        </section>

        <!-- Select 选择器 -->
        <section class="test-section">
          <h2>Select 选择器</h2>
          <div class="component-group">
            <el-select v-model="selectValue" placeholder="请选择" style="width: 200px;">
              <el-option label="选项1" value="1"></el-option>
              <el-option label="选项2" value="2"></el-option>
              <el-option label="选项3" value="3"></el-option>
            </el-select>
          </div>
        </section>

        <!-- Slider 滑块 -->
        <section class="test-section">
          <h2>Slider 滑块</h2>
          <div class="component-group">
            <el-slider v-model="sliderValue" style="width: 200px;"></el-slider>
          </div>
        </section>

        <!-- Switch 开关 -->
        <section class="test-section">
          <h2>Switch 开关</h2>
          <div class="component-group">
            <el-switch v-model="switchValue"></el-switch>
            <el-switch v-model="switchValue2" disabled></el-switch>
          </div>
        </section>

        <!-- TreeSelect 树形选择器 -->
        <section class="test-section">
          <h2>TreeSelect 树形选择器</h2>
          <div class="component-group">
            <el-tree-select v-model="treeSelectValue" :data="treeData" placeholder="请选择" style="width: 200px;"></el-tree-select>
          </div>
        </section>

        <!-- Pagination 分页 -->
        <section class="test-section">
          <h2>Pagination 分页</h2>
          <div class="component-group">
            <el-pagination
              layout="prev, pager, next"
              :total="100"
              :page-size="10"
              :current-page="currentPage"
              @current-change="handleCurrentChange"
            ></el-pagination>
          </div>
        </section>

        <!-- Progress 进度条 -->
        <section class="test-section">
          <h2>Progress 进度条</h2>
          <div class="component-group">
            <el-progress :percentage="50" style="width: 200px;"></el-progress>
            <el-progress :percentage="70" status="success" style="width: 200px;"></el-progress>
            <el-progress :percentage="90" status="warning" style="width: 200px;"></el-progress>
            <el-progress :percentage="100" status="danger" style="width: 200px;"></el-progress>
          </div>
        </section>

        <!-- Tag 标签 -->
        <section class="test-section">
          <h2>Tag 标签</h2>
          <div class="component-group">
            <el-tag type="primary">主要标签</el-tag>
            <el-tag type="success">成功标签</el-tag>
            <el-tag type="warning">警告标签</el-tag>
            <el-tag type="danger">危险标签</el-tag>
            <el-tag type="info">信息标签</el-tag>
          </div>
        </section>

        <!-- Backtop 回到顶部 -->
        <section class="test-section">
          <h2>Backtop 回到顶部</h2>
          <div class="component-group">
            <el-backtop :right="40" :bottom="40"></el-backtop>
            <p style="height: 200px; background-color: var(--ep-bg-color-page);"></p>
          </div>
        </section>

        <!-- Dropdown 下拉菜单 -->
        <section class="test-section">
          <h2>Dropdown 下拉菜单</h2>
          <div class="component-group">
            <el-dropdown>
              <span class="el-dropdown-link">
                下拉菜单 <el-icon class="el-icon--right"><arrow-down /></el-icon>
              </span>
              <template #dropdown>
                <el-dropdown-menu>
                  <el-dropdown-item>选项1</el-dropdown-item>
                  <el-dropdown-item>选项2</el-dropdown-item>
                  <el-dropdown-item>选项3</el-dropdown-item>
                </el-dropdown-menu>
              </template>
            </el-dropdown>
          </div>
        </section>

        <!-- Menu 菜单 -->
        <section class="test-section">
          <h2>Menu 菜单</h2>
          <div class="component-group">
            <el-menu :default-active="activeMenu" class="el-menu-demo" mode="horizontal">
              <el-menu-item index="1">导航一</el-menu-item>
              <el-menu-item index="2">导航二</el-menu-item>
              <el-menu-item index="3">导航三</el-menu-item>
            </el-menu>
          </div>
        </section>

        <!-- Tabs 标签页 -->
        <section class="test-section">
          <h2>Tabs 标签页</h2>
          <div class="component-group">
            <el-tabs v-model="activeTab">
              <el-tab-pane label="标签页1" name="1">标签页1内容</el-tab-pane>
              <el-tab-pane label="标签页2" name="2">标签页2内容</el-tab-pane>
              <el-tab-pane label="标签页3" name="3">标签页3内容</el-tab-pane>
            </el-tabs>
          </div>
        </section>

        <!-- Alert 提示 -->
        <section class="test-section">
          <h2>Alert 提示</h2>
          <div class="component-group">
            <el-alert title="主要提示" type="primary" show-icon></el-alert>
            <el-alert title="成功提示" type="success" show-icon></el-alert>
            <el-alert title="警告提示" type="warning" show-icon></el-alert>
            <el-alert title="危险提示" type="danger" show-icon></el-alert>
          </div>
        </section>

        <!-- Dialog 对话框 -->
        <section class="test-section">
          <h2>Dialog 对话框</h2>
          <div class="component-group">
            <el-button type="primary" @click="dialogVisible = true">打开对话框</el-button>
            <el-dialog
              v-model="dialogVisible"
              title="对话框标题"
              width="30%"
            >
              <span>这是一段对话框内容</span>
              <template #footer>
                <span class="dialog-footer">
                  <el-button @click="dialogVisible = false">取消</el-button>
                  <el-button type="primary" @click="dialogVisible = false">确定</el-button>
                </span>
              </template>
            </el-dialog>
          </div>
        </section>

        <!-- Drawer 抽屉 -->
        <section class="test-section">
          <h2>Drawer 抽屉</h2>
          <div class="component-group">
            <el-button type="primary" @click="drawerVisible = true">打开抽屉</el-button>
            <el-drawer
              v-model="drawerVisible"
              title="抽屉标题"
              size="30%"
            >
              <span>这是一段抽屉内容</span>
            </el-drawer>
          </div>
        </section>

        <!-- Loading 加载 -->
        <section class="test-section">
          <h2>Loading 加载</h2>
          <div class="component-group">
            <el-button type="primary" @click="loading = true">显示加载</el-button>
            <el-loading v-if="loading" fullscreen text="加载中..."></el-loading>
          </div>
        </section>

        <!-- Message Box 消息弹出框 -->
        <section class="test-section">
          <h2>Message Box 消息弹出框</h2>
          <div class="component-group">
            <el-button type="primary" @click="openMessageBox">打开消息框</el-button>
          </div>
        </section>

        <!-- Popconfirm 气泡确认框 -->
        <section class="test-section">
          <h2>Popconfirm 气泡确认框</h2>
          <div class="component-group">
            <el-popconfirm
              title="确定要删除吗？"
              @confirm="handleConfirm"
              @cancel="handleCancel"
            >
              <template #reference>
                <el-button type="danger">删除</el-button>
              </template>
            </el-popconfirm>
          </div>
        </section>
      </main>
    </div>
  </el-config-provider>
</template>

<script setup>
import { ref } from 'vue'
import { ElMessage, ElMessageBox } from 'element-plus'
import { ArrowDown } from '@element-plus/icons-vue'

const currentTheme = ref('')

// Checkbox
const checkbox1 = ref(false)
const checkbox2 = ref(false)
const checkbox3 = ref(false)

// Date Picker
const dateValue = ref('')

// Input
const inputValue = ref('')

// Input Number
const numberValue = ref(5)

// Radio
const radioValue = ref('1')

// Select
const selectValue = ref('')

// Slider
const sliderValue = ref(50)

// Switch
const switchValue = ref(false)
const switchValue2 = ref(false)

// TreeSelect
const treeSelectValue = ref('')
const treeData = ref([
  {
    label: '一级节点1',
    value: '1',
    children: [
      {
        label: '二级节点1-1',
        value: '1-1'
      },
      {
        label: '二级节点1-2',
        value: '1-2'
      }
    ]
  },
  {
    label: '一级节点2',
    value: '2',
    children: [
      {
        label: '二级节点2-1',
        value: '2-1'
      },
      {
        label: '二级节点2-2',
        value: '2-2'
      }
    ]
  }
])

// Pagination
const currentPage = ref(1)
const handleCurrentChange = (val) => {
  currentPage.value = val
}

// Menu
const activeMenu = ref('1')

// Tabs
const activeTab = ref('1')

// Dialog
const dialogVisible = ref(false)

// Drawer
const drawerVisible = ref(false)

// Loading
const loading = ref(false)

// Message Box
const openMessageBox = () => {
  ElMessageBox.alert('这是一段消息', '标题', {
    confirmButtonText: '确定',
    callback: action => {
      console.log(action)
    }
  })
}

// Popconfirm
const handleConfirm = () => {
  ElMessage.success('删除成功')
}

const handleCancel = () => {
  ElMessage.info('取消删除')
}
</script>

<style scoped>
.app-container {
  min-height: 100vh;
  padding: 120px 20px 20px;
  background-color: var(--ep-bg-color-page);
  transition: all 0.3s ease;
}

.app-header {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px;
  background-color: var(--ep-bg-color);
  border-bottom: 1px solid var(--ep-border-color);
  box-shadow: var(--ep-box-shadow);
  z-index: 1000;
  margin-bottom: 30px;
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

.component-group {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  align-items: center;
}

.dialog-footer {
  display: flex;
  justify-content: flex-end;
  gap: 10px;
}
</style>
