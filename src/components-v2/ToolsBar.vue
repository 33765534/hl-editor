<template>
  <div class="top-tools-bar">

    <el-row :gutter="22">
      <el-col :span="3">
        <div class="edit">
          <el-tooltip class="item" effect="dark" content="ctrl + z" placement="bottom-start">
            <el-link type="primary" @click="$emit('undo')" style="margin-right: 3px;">Undo</el-link>
          </el-tooltip>
          <el-link type="primary" @click="$emit('redo')">Redo</el-link>
        </div>
      </el-col>
      <el-col :span="3">
        <el-link type="primary" @click="onPreviewModeChange">{{previewMode ? 'Desktop' : 'Mobile'}}
          Mode</el-link>
      </el-col>
      <el-col :span="3">
        <div style="display:inline-block;">
          <el-link :type="editMode? 'primary': 'danger'" @click="onEditModeChange">{{editMode ? 'View' : 'Edit'}}
            Mode</el-link>
        </div>
      </el-col>
      <el-col :span="10">
        <el-link type="primary" @click="$emit('structureVisible')">Inspect Components
          Structure</el-link>
      </el-col>
      
    </el-row>


  </div>
</template>

<script>

export default {
  props: [],
  components: { 
  },
  data() {
    return {
      previewMode: false,
      editMode: true,
    };
  },
  watch: {},
  computed: {
  },
  beforeCreate() { },
  created() { },
  beforeMount() { },
  mounted() { },
  beforeUpdate() { },
  updated() { },
  destroyed() { },
  methods: {
    // 在此自动生成
    request() {
      // 网络请求，可选
    },
    logout() {
      window.ssoLogin.logout()
    },

    onPreviewModeChange() {
      this.previewMode = !this.previewMode;
      this.$emit('onPreviewModeChange', this.previewMode);
    },

    onEditModeChange() {
      this.editMode = !this.editMode;
      this.$emit('onEditModeChange', this.editMode);

      setTimeout(() => {
        this.editMode = true;
      }, 500);
    }
  },
  fillter: {},
};
</script>

<style scoped>
/*  在此自动生成 */

.top-tools-bar {
  padding: 5px 10px;
  font-size: 14px;
  font-weight: 500;
  color: #606266;
  background-color: white;
  border-radius: 0px;
  align-content: center;
  border-bottom: 1px solid #f0f0f0;
}

.edit {
  display: inline-block;
}
</style>

<style scoped>
.github-corner:hover .octo-arm {
  animation: octocat-wave 560ms ease-in-out;
}

@keyframes octocat-wave {
  0%,
  100% {
    transform: rotate(0);
  }

  20%,
  60% {
    transform: rotate(-25deg);
  }

  40%,
  80% {
    transform: rotate(10deg);
  }
}

@media (max-width: 500px) {
  .github-corner:hover .octo-arm {
    animation: none;
  }

  .github-corner .octo-arm {
    animation: octocat-wave 560ms ease-in-out;
  }
}
</style>
