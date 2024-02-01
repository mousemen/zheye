<template>
  <nav class="navbar bg-dark" data-bs-theme="dark">
    <a class="navbar-brand" href="#">者也专栏</a>
    <ul v-if="!user.isLogin" class="list-inline mb-0">
      <li class="list-inline-item">
        <button class="btn btn-outline-success" type="submit">登录</button>
      </li>
      <li class="list-inline-item">
        <button class="btn btn-outline-success" type="submit">注册</button>
      </li>
    </ul>
    <ul v-else class="list-inline mb-0">
      <li class="list-inline-item">
        <button class="btn btn-outline-success" type="submit">
          你好{{ user.name }}
        </button>
      </li>
    </ul>
    <dropdown :title="'你好 ${user.name}'">
      <dropdown-item
        ><a class="dropdown-item" href="#">新建文章</a></dropdown-item
      >
      <dropdown-item
        ><a class="dropdown-item" href="#">编辑资料</a></dropdown-item
      >
      <dropdown-item
        ><a class="dropdown-item" href="#">退出登陆</a></dropdown-item
      >
    </dropdown>
  </nav>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue'
import Dropdown from './DropDown.vue'
import DropdownItem from './DropdownItem.vue'
export interface UserProps {
  isLogin: number
  name?: string
  id?: number
}
export default defineComponent({
  name: 'GlobalHeader',
  components: {
    Dropdown,
    DropdownItem
  },
  props: {
    user: {
      type: Object as PropType<UserProps>,
      required: true
    }
  }
})
</script>
