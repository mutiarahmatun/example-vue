<script setup>
import Data from "./assets/data";
import DataBarang from "./assets/dataBarang";
import TheWelcome from "./components/TheWelcome.vue";
</script>
<script>
export default {
  data: function () {
    return {
      content: Data,
      popUp: false,
      birthDay: "",
      openedTab1: true,
      openedTab2: false,
      titleHero: "Centered Hero",
      titleImage:
        "https://media.istockphoto.com/photos/koala-picture-id537179382?k=20&m=537179382&s=612x612&w=0&h=t_uwjhdeiH70yO-GOl7iLngz2gzBxdGkW0d1LBqxlJI=",
    };
  },
  methods: {
    changeTitle(data) {
      this.titleHero = data.nama;
      this.titleImage = data.image;
      this.popUp = true;
    },
    closePopUp() {
      this.popUp = false;
    },
    showDate(value) {
      // alert(value);
      this.birthDay = value;
    },
    openTab1() {
      this.openedTab1 = true;
      this.openedTab2 = false;
    },
    openTab2() {
      this.openedTab2 = true;
      this.openedTab1 = false;
    },
  },
};
</script>

<template>
<TheWelcome/>
</template>

<style scoped>
header {
  line-height: 1.5;
}
div.scrollmenu {
  background-color: #333;
  overflow: auto;
  white-space: nowrap;
}

div.scrollmenu a {
  display: inline-block;
  color: white;
  text-align: center;
  padding: 14px;
  text-decoration: none;
}

div.scrollmenu a:hover {
  background-color: #777;
}
.title-name {
  color: black;
  text-transform: capitalize;
}
.subtitle-name {
  color: grey;
}
.logo {
  display: block;
  margin: 0 auto 2rem;
}
.closeButton {
  font-size: 50px;
  font-weight: bold;
  top: -40px;
  position: absolute;
  right: 0;
  cursor: pointer;
  z-index: 10;
}
.tab {
  display: inline-block;
  margin-right: 20px;
  cursor: pointer;
}
.tab:hover {
  background-color: white;
  color: hotpink;
}
.isitab-1 {
  background-color: grey;
  visibility: hidden;
  height: 0;
}
.isitab-2 {
  background-color: grey;
  visibility: hidden;
  height: 0;
}
.isitab-1.show {
  visibility: visible;
}
.isitab-2.show {
  visibility: visible;
}
.outsideContainer {
  position: absolute;
  top: 0;
  width: 100vw;
  height: 100vh;
  background-color: rgba(0, 0, 0, 0.8);
  visibility: hidden;
  opacity: 0;
  transition-property: all;
  transition-duration: 1s;
  z-index: 10;
}
.containerModal {
  background-color: white;
  padding: 20px;
  color: black;

  width: 100%;
  z-index: 10;
  width: 400px;
  height: 400px;
  margin: 40vh auto;
}
.containerModal img {
  height: 300px;
}
.outsideContainer.shown {
  visibility: visible;
  opacity: 1;
}
@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
