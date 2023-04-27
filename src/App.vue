<template>
  <Button @click="open">show</Button>
  <Button theme="link" size="big">你好</Button>
  <Button theme="text" size="small">你好</Button>
  <Button level="main">你好</Button>
  <Button level="danger">你好</Button>
  <hr />
  <Switch v-model:value="switchValue" />
  <hr />
  <Tabs v-model:selected="tabSelected">
    <Tab title="Tab1">内容1</Tab>
    <Tab title="Tab2222">内容2222</Tab>
  </Tabs>
</template>

<script>
import { Button, Dialog, openDialog, Switch, Tabs, Tab } from 'shanzhu-ui'
import 'shanzhu-ui/dist/lib/shanzhu.css'
import { ref } from 'vue'

export default {
  name: 'App',
  components: { Button, Dialog, openDialog, Switch, Tabs, Tab },
  setup() {
    const switchValue = ref(false)
    const tabSelected = ref('Tab2222')
    const open = () => {
      openDialog({
        title: '我是标题',
        content: '我是内容',
      })
    }
    return { switchValue, tabSelected, open }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
