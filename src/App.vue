<template>
  <div class="container">
    <column-list :list="list"></column-list>
    <!-- <global-header :user="currentUser"></global-header> -->
    <form>
      <div class="mb-3">
        <label for="exampleInputEmail1" class="form-label">Email address</label>
        <input
          type="email"
          class="form-control"
          id="exampleInputEmail1"
          aria-describedby="emailHelp"
        />
        <div id="emailHelp" class="form-text">
          We'll never share your email with anyone else.
        </div>
      </div>
      <div class="mb-3">
        <label for="exampleInputPassword1" class="form-label">Password</label>
        <input
          type="password"
          class="form-control"
          id="exampleInputPassword1"
        />
      </div>
      <div class="mb-3 form-check">
        <input type="checkbox" class="form-check-input" id="exampleCheck1" />
        <label class="form-check-label" for="exampleCheck1">Check me out</label>
      </div>
      <button type="submit" class="btn btn-primary">Submit</button>
    </form>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import 'bootstrap/dist/css/bootstrap.min.css'
import ColumnList, { ColumnProps } from './components/ColumnList.vue'
import GlobalHeader, { UserProps } from './components/GlobalHeader.vue'

const testdata: ColumnProps[] = [
  {
    id: 1,
    title: 'test1的标题',
    description: 'test1的发现改变了我们看待世界的方式，带来了新的视角',
    avatar: 'http://example.com/avatar/2ee'
  },
  {
    id: 2,
    title: 'test2的标题',
    description: '这是test2的描述，有一段非常有意思的简介，可以激发一下想象',
    avatar: 'http://example.com/avatar/2ee'
  },
  {
    id: 3,
    title: 'test3的挑战',
    description: '这是test3的故事，背后有一个富有启发性的历史，值得深入探讨',
    avatar: 'http://example.com/avatar/3ee'
  },
  {
    id: 4,
    title: 'test4的探索',
    description: '探索test4的世界，每一个角落都充满了惊喜和秘密',
    avatar: 'http://example.com/avatar/4ee'
  },
  {
    id: 5,
    title: 'test5的冒险',
    description: '加入test5的冒险，一起探寻未知的领域，共同经历难忘的旅程',
    avatar: 'http://example.com/avatar/5ee'
  },
  {
    id: 6,
    title: 'test6的传说',
    description: 'test6不仅仅是一个传说，它的每个细节都编织着历史的深度',
    avatar: 'http://example.com/avatar/6ee'
  }
]

export default defineComponent({
  // eslint-disable-next-line vue/no-unused-components
  components: { ColumnList, GlobalHeader },

  name: 'App',
  setup () {
    return {
      list: testdata
    }
  }
})
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
