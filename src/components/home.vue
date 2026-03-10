<template>
  <main class="main">



    <div class="flex">
      <div>
        <h1>Install Minecraft Legacy Console Edition?</h1>
      </div>
      <div>
        <img class="logo" src="/images/table.png" />
      </div>
    </div>


    <div class="action-bar">
      <div class="flex">
        <span style="width: 30rem;">
          <input class="app-checkbox" type="checkbox" value="" id="install_all_users" @change="update_install_all">
          <label for="CheckBoxDefault">Install for all users</label>
        </span>

        <span style="width: 100%;"/>

        <button class="app-btn app-btn-primary action-button">
          <i class="icons10-security-issue" v-if="install_all"></i>
          <span>Install</span>
        </button>
        <button class="app-btn action-button"><span>Cancel</span></button>
      </div>

    </div>




  </main>
</template>

<style scoped>
.action-bar {
  position: absolute;
  left: 0;
  bottom: 0;
  width: 100vw;
  padding: 2rem;
}
.action-button {
  width: 15rem;
  margin-left: 1rem;
}
.flex {
  display: flex;
}
.logo {
  width: 10rem;
  height: 10rem;
}
</style>

<script>
export default {
  data() {
    return {
      install_all: false,
    }
  },
  methods: {
    toggle_theme() {
      const colorScheme = Appearance.getColorScheme();
      if (colorScheme === "dark") {
        Appearance.setLightScheme()
      } else {
        Appearance.setDarkScheme();
      }
    },
    update_install_all(event) {
      this.install_all = event.target.checked;
    }
  },
}
</script>