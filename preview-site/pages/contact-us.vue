<template>
  <div class="contact-us-container">
    <div class="contact-us-header">
      <img
        alt="bg6913"
        src="/static/external/bg6913-zfj-200h.png"
        class="contact-us-bg"
      />
      <div class="contact-us-contactbt">
        <span class="contact-us-text">Contact us</span>
      </div>
      <nuxt-link to="/developers" class="contact-us-navlink">
        <div class="contact-us-devbt">
          <span class="contact-us-text1">Developers</span>
        </div>
      </nuxt-link>
      <nuxt-link to="/" class="contact-us-navlink1">
        <img
          alt="LOGO11032"
          src="/static/external/logo11032-ask-200h.png"
          class="contact-us-logo1"
        />
      </nuxt-link>
      <nuxt-link to="/play-download" class="contact-us-navlink2">
        <div class="contact-us-playbt button">
          <span class="contact-us-text2"><span>Play/Download</span></span>
        </div>
      </nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  name: "ContactUs",
  props: {},
  head: {
    title: "Contact-us - exported project",
    meta: [
      {
        property: "og:title",
        content: "Contact-us - exported project",
      },
    ],
  },
};
</script>

<style scoped>
.contact-us-container {
  width: 100%;
  display: flex;
  min-height: 100vh;
  align-items: center;
  flex-direction: column;
  background-color: #000000;
}
.contact-us-header {
  top: 0px;
  left: 129px;
  width: 1662px;
  height: 85px;
  display: flex;
  position: absolute;
  align-items: flex-start;
  flex-shrink: 1;
}
.contact-us-bg {
  top: -1px;
  width: 1662px;
  height: 85px;
  position: absolute;
  border-radius: 13px;
}
.contact-us-contactbt {
  top: 16px;
  left: 1196px;
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
.contact-us-text {
  top: 7px;
  left: 27px;
  color: rgb(255, 255, 255);
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
.contact-us-navlink {
  display: contents;
}
.contact-us-devbt {
  top: 15px;
  left: 916px;
  width: 210px;
  height: 54px;
  display: flex;
  position: absolute;
  align-items: flex-start;
  flex-shrink: 1;
  border-radius: 44px;
  text-decoration: none;
  background-color: #742dd2;
}
.contact-us-text1 {
  top: 13px;
  left: 31px;
  color: rgb(255, 255, 255);
  height: auto;
  margin: auto;
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
.contact-us-navlink1 {
  display: contents;
}
.contact-us-logo1 {
  top: 5px;
  left: 240px;
  width: 123px;
  height: 74px;
  position: absolute;
  text-decoration: none;
}
.contact-us-navlink2 {
  display: contents;
}
.contact-us-playbt {
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

.contact-us-text2 {
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
