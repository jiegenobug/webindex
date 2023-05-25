<template>
  <div class="webindex">
    <div class="title">ChatGPT导航页</div>
    <div class="desc">下方列表内网站有时可能会更换网址，但本导航页不变，收藏本站不迷路！<br />本网站：<strong>yzre.cn</strong> —助记：<strong>伊泽瑞尔.</strong>cn</div>
    <div class="list_title">ChatGPT国内站列表</div>
    <div class="list">
      <div class="item" v-for="(item,ind) in webList" :key="ind">
        <div class="item-content">
          <div class="website-name">{{ item.webName }}</div>
          <div class="website-details">
            <div class="website-link" @click="toPage(item.url)">{{ item.url }}</div>
            <div class="website-password">{{ item.password }}</div>
          </div>
        </div>
      </div>
    </div>
    <div class="footer">
      <div>如需在本页添加自己的网站、或者想部署自己的GPT镜像站、或者有其他建议/想法，请联系本站站长</div>
      <div>站长微信：keke_nobug</div>
      <div style="font-size: .7rem;">注：加好友请注明来源和来意，请发文字消息，勿弹语音电话。</div>
    </div>
    <div class="copy">
      <a href="https://beian.miit.gov.cn/" target="_blank">豫ICP备2023005087号-1</a><br>
      <span>Copyright ©2023 Jiege.</span>
      <span>All Rights Reserved.</span>
    </div>
  </div>
</template>

<script>
export default {
  components: {},
  props: {},
  data () {
    return {
      webList: [
        { webName: '网站1', url: 'chat.yzre.cn', password: '访问密码：jiege666' },
        { webName: '网站2', url: 'jiege.yzre.cn', password: '访问密码：jiege666' },
        { webName: '欢迎各位补充！' },
        { webName: '敬请期待...' },
      ]
    };
  },
  computed: {},
  watch: {},
  created () { },
  mounted () { },
  methods: {
    toPage (url) {
      console.log(window.location.protocol);
      let path = window.location.protocol + '//' + url;
      window.open(path, '_blank');
    },
  },
};
</script>

<style scoped lang="less">
.webindex {
  box-sizing: border-box;
  width: 100%;
  max-width: 800px;
  margin: 0 auto;
  padding: 1rem;

  .title {
    font-size: 2rem;
    font-weight: bold;
    margin-bottom: 1rem;
    color: #000;
    text-align: center;
  }

  .desc {
    font-size: 1.2rem;
    color: #1177cb;
    margin-bottom: 2rem;
    text-align: center;
  }

  .list_title {
    font-size: 1.5rem;
    font-weight: bold;
    margin-bottom: 1rem;
    color: #007bff;
  }

  .list {
    .item {
      display: flex;
      flex-direction: column;
      margin-bottom: 1rem;
      border-radius: 0.25rem;

      .item-content {
        display: flex;
        justify-content: flex-start;
        align-items: center;
        background-color: #f0f1fb;
        padding: 1rem;
        border-radius: 5px;
      }

      .website-name {
        flex: none;
        font-size: 1.2rem;
        font-weight: bold;
        margin-right: 1rem;
        color: #333;
      }

      .website-details {
        display: flex;
        align-items: center;
      }

      .website-link {
        font-size: 1.2rem;
        color: #007bff;
        cursor: pointer;
        margin-right: 1rem;

        &:hover {
          text-decoration: underline;
        }
      }

      .website-password {
        font-size: 1.2rem;
        color: #666;
      }
    }
  }
  .footer {
    color: #999;
    font-size: 0.8rem;
  }
  .copy {
    text-align: center;
    font-size: 0.75rem;
    color: #ccc;

    a {
      color: #ccc;
      text-decoration: none;
    }
  }
}

@media screen and (max-width: 768px) {
  .webindex {
    padding: 0.5rem;
  }

  .title {
    font-size: 2rem;
  }

  .desc {
    font-size: 1rem;
  }

  .list_title {
    font-size: 1.5rem;
  }

  .website-name {
    font-size: 1.2rem;
  }

  .website-link {
    font-size: 1rem;
  }

  .website-password {
    font-size: 1rem;
  }
}
</style>
