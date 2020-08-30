<template>
  <div id="app">
    <input type="checkbox" value="Jack" v-model="checkedNames" />
    <label for="jack">Jack</label>
    <input type="checkbox" value="John" v-model="checkedNames" />
    <label for="john">John</label>
    <input type="checkbox" value="Mike" v-model="checkedNames" />
    <label for="mike">Mike</label>
    <br />
    <span>Checked names: {{ checkedNames }}</span>

    <!-- 单选框 radio -->
    <hr />
    <input type="radio" value="One" v-model="picked" />
    <label for="one">One</label>
    <br />
    <input type="radio" i value="Two" v-model="picked" />
    <label for="two">Two</label>
    <br />
    <span>Picked: {{ picked }}</span>

    <hr />
    <!-- 选择框  使用for循环-->
    <select v-model="selected">
      <option disabled value>请选择</option>
      <option v-for="item in array" :value="item.value" :key="item.value">{{item.text}}</option>
    </select>
    <span>Selected: {{ selected }}</span>

    <hr>
    <hr>
    <strong>form表单，登录页面点击提交</strong>
  <!-- @submit.prevent阻止默认事件，监听表单提交信息 -->
    <form @submit.prevent="onSubmit"  style="border:1px solid red; height:100px">
      <label>
        <span>用户名</span>
        <input type="text" v-model="user.username">
      </label>
      <label>
        <span>用户名</span>
        <input type="password" v-model="user.password">
        {{user.password}}
      </label>
      <br />
      <button>登录</button>
    </form>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      checkedNames: [],
      picked: "",
      selected: "",
      array:[
        {text:"抽烟",value:1},
        {text:"喝酒",value:2},
        {text:"烫头",value:3},
      ],
      user:{
        username:' ',
        password:' '
      }
    };
  },
  methods:{
    onSubmit(){
      console.log(this.user.username)
      console.log(this.user.password)
    }
  }
};
</script>