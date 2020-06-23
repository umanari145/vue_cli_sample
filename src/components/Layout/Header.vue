<template >
  <div>
    <h1 class="title" style="display:flex;justify-content:center;">
        ツールリスト
    </h1>
    <div style="display:flex;justify-content:center;">
      <div>
        <div v-if="user.uid !== undefined && user.uid !== null" >
          {{ user.displayName }}
          <button type="button" @click="doLogout">ログアウト</button>
        </div>
        <!-- 未ログイン時にはログインボタンを表示 -->
        <div v-else key="logout">
          <button type="button" @click="doLogin">ログイン</button>
        </div>
      </div>
    </div>
  </div>
</template>
<script>

export default {
  name: 'Header',
  data() {
     return {};
  },
  methods:{
    doLogin() {
    },
    doLogout() {
    }
  },
  computed:{
    user: {
      get() {
          return this.$store.getters["settings/get_user"];
      },
      set(val) {
          this.$store.commit("settings/set_user",val);
      }
    }
  },
  mounted() {
  },
  created() {
      
  }
}
</script>
