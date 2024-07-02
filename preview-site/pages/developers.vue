<template>
  <div class="developers-container">
    <div class="developers-header">
      <img
        alt="bg6913"
        src="/static/external/bg6913-zfj-200h.png"
        class="developers-bg"
      />
      <nuxt-link to="/contact-us" class="developers-navlink">
        <div class="developers-contactbt">
          <span class="developers-text"><span>Contact us</span></span>
        </div>
      </nuxt-link>
      <div class="developers-devbt">
        <span class="developers-text2"><span>Developers</span></span>
      </div>
      <nuxt-link to="/" class="developers-navlink1">
        <img
          alt="LOGO11032"
          src="/static/external/logo11032-ask-200h.png"
          class="developers-logo1"
        />
      </nuxt-link>
      <nuxt-link to="/play-download" class="developers-navlink2">
        <div class="developers-playbt button">
          <span class="developers-text4"><span>Play/Download</span></span>
        </div>
      </nuxt-link>
    </div>
    <div>
      <h1>Developers</h1>
    </div>
  </div>
</template>

<script>
export default {
  name: "Developers",
  props: {},
  head: {
    title: "Developers - exported project",
    meta: [
      {
        property: "og:title",
        content: "Developers - exported project",
      },
    ],
  },
};
</script>

<style scoped>
.developers-container {
  width: 100%;
  display: flex;
  min-height: 100vh;
  align-items: center;
  flex-direction: column;
  background-color: #000000;
}
.developers-header {
  top: 0px;
  left: 129px;
  width: 1662px;
  height: 85px;
  display: flex;
  position: absolute;
  align-items: flex-start;
  flex-shrink: 1;
}
.developers-bg {
  top: -1px;
  width: 1662px;
  height: 85px;
  position: absolute;
  border-radius: 13px;
}
.developers-navlink {
  display: contents;
}
.developers-contactbt {
  top: 16px;
  left: 1196px;
  width: 210px;
  height: 54px;
  display: flex;
  position: absolute;
  align-items: flex-start;
  flex-shrink: 1;
  border-radius: 44px;
  text-decoration: none;
  background-color: rgba(116, 45, 210, 1);
}
.developers-text {
  top: 12px;
  left: 31px;
  color: rgba(255, 255, 255, 1);
  height: auto;
  position: absolute;
  font-size: 25px;
  font-style: Book;
  text-align: left;
  font-family: Stolzl;
  font-weight: 300;
  line-height: normal;
  font-stretch: normal;
  text-decoration: none;
}
.developers-devbt {
  top: 15px;
  left: 916px;
  width: 210px;
  height: 54px;
  display: flex;
  position: absolute;
  align-items: flex-start;
  flex-shrink: 1;
  border-color: #efb1ff;
  border-width: 4px;
  border-radius: 44px;
  background-color: rgba(239, 177, 255, 0.43);
}
.developers-text2 {
  top: 7px;
  left: 32px;
  color: rgba(255, 255, 255, 1);
  height: auto;
  position: absolute;
  font-size: 25px;
  font-style: Book;
  text-align: left;
  font-family: Stolzl;
  font-weight: 300;
  line-height: normal;
  font-stretch: normal;
  text-decoration: none;
}
.developers-navlink1 {
  display: contents;
}
.developers-logo1 {
  top: 5px;
  left: 240px;
  width: 123px;
  height: 74px;
  position: absolute;
  text-decoration: none;
}
.developers-navlink2 {
  display: contents;
}
.developers-playbt {
  top: 15px;
  left: 598px;
  width: 248px;
  height: 54px;
  display: flex;
  position: absolute;
  transition: 0.3s;
  align-items: flex-start;
  flex-shrink: 1;
  border-width: 0px;
  border-radius: 44px;
  text-decoration: none;
  background-color: rgba(239, 177, 255, 1);
}

.developers-text4 {
  top: 12px;
  left: 29px;
  color: rgba(0, 0, 0, 1);
  height: auto;
  position: absolute;
  font-size: 25px;
  font-style: Book;
  text-align: left;
  font-family: Stolzl;
  font-weight: 300;
  line-height: normal;
  font-stretch: normal;
  text-decoration: none;
}
</style>
