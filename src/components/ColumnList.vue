<!-- eslint-disable no-unused-expressions -->
<template>
  <div class="row">
    <div v-for="column in list" :key="column.id" class="col-4" mb-3 col-4>
      <div class="card h-100 shadow-sm" style="width: 18rem">
        <div class="card-body text-center">
          <img
            :src="column.avatar"
            :alt="column.title"
            class="rounded-circle border border-light w-25 my-3"
          />
          <h5 class="card-title">{{ column.title }}</h5>
          <p class="card-text text-left">{{ column.description }}</p>
          <a href="#" class="btn btn-outline-primary">进入专栏</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue'
export interface ColumnProps {
  id: number
  title: string
  avatar?: string
  description: string
}
export default defineComponent({
  name: 'ColumnList',
  props: {
    list: {
      /* 在组件的 props 中定义了一个名为 list 的属性，其类型为 Array，
        并指定了类型为 ColumnProps[]，
        这意味着 list 属性应该是一个包含 ColumnProps 对象的数组。 */
      type: Array as PropType<ColumnProps[]>,
      required: true
    }
  },
  setup (props) {
    // eslint-disable-next-line no-unused-expressions
    props.list[0].title
  }
})
</script>
