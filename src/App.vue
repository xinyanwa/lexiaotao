<template>
  <div class="container">
    <global-header :user="currentUser" />
    <!-- <column-list :list="list"/> -->
    <from>
      <div class="mb-3">
        <label class="form-label">邮箱地址</label>
        <validate-input-vue :rules="emailRules"
        placeholder="请输入邮箱账号"
        type="text"/>
        <label class="form-label">邮箱地址</label>
        <validate-input-vue :rules="password" placeholder="请输入密码"
        type="password"/>
      </div>
    </from>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import 'bootstrap/dist/css/bootstrap.min.css'
// import ColumnList, { ColumnProps } from './components/CloumnList.vue'
import GlobalHeader, { UserProps } from './components/GlobalHeader.vue'
import ValidateInputVue, { RulesProp } from './components/ValidateInput.vue'

const currentUser: UserProps = {
  isLogin: true,
  name: 'weiwei3344'
}
/* const testData: ColumnProps[] = [
  {
    id: 1,
    title: '我看好你',
    description: '初次见面，多多指教',
    avatar: require('../src/assets/zhuzhu-1.jpg')
  },
  {
    id: 2,
    title: '我看好你',
    description: '初次见面，多多指教',
    avatar: require('../src/assets/zhuzhu-3.jpg')
  },
  {
    id: 3,
    title: '我看好你',
    description: '初次见面，多多指教',
    avatar: require('../src/assets/weiwei-8.jpg')
  },
  {
    id: 4,
    title: '我看好你',
    description: '初次见面，多多指教'
  }
] */

export default defineComponent({
  name: 'App',
  components: {
    // ColumnList,
    GlobalHeader,
    ValidateInputVue
  },
  setup () {
    const emailRules: RulesProp = [
      { type: 'required', message: '电子邮箱地址不能为空' },
      { type: 'email', message: '请输入正确的电子邮箱格式' }
    ]
    const password: RulesProp = [
      { type: 'required', message: '电子邮箱地址不能为空' }
    ]
    return {
      // list: testData,
      currentUser,
      emailRules,
      password
    }
  }
})
</script>

<style>
</style>
