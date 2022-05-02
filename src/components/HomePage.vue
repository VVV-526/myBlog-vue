<template>
  <div class="container">
    <div class="navbar">
      <div class="logo">
        <span>VV's blog</span>
      </div>
      <div class="menu">
        <ul>
          <li>
            <a href="#">
              <span>Home</span>
            </a>
          </li>
          <li>
            <a href="#tech"><span>Tech</span></a>
          </li>
          <li>
            <a href="#life"><span>Life</span></a>
          </li>
          <li>
            <a href="#about"><span>About</span></a>
          </li>
        </ul>
      </div>
      <div class="searchBar">
        <input type="search" class="searchInput" />
        <span class="searchBtn" @click="showSearch">
          <span class="searchIcon"></span>
        </span>
      </div>
      <div class="lang">
        <a href="#" class="langBtn" data-back="CN" data-front="EN"></a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HomePage",
  props: {
    msg: String,
  },
  mounted() {},
  methods: {
    showSearch() {
      var btn = document.getElementById('searchBtn');
       btn.toggleClass('open');
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

.container {
  position: fixed;
  top: 0;
  left: 0;
  margin: auto;
  width: 100%;
}

.navbar {
  display: flex;
  justify-content: space-between;
  background-color: #ffffff;
}

.logo {
  padding: 15px;
  margin-left: 3%;
}

.logo span {
  font-size: 25px;
  color: #666e71;
}

.lang {
  padding: 12px;
  margin-right: 1%;
}

.lang a {
  font-size: 20px;
  color: #666e71;
}

.langBtn {
  opacity: 1;
  outline: 0;
  color: #fff;
  line-height: 40px;
  position: relative;
  text-align: center;
  letter-spacing: 1px;
  display: inline-block;
  text-decoration: none;
}

.langBtn:hover:after {
  opacity: 1;
  transform: translateY(0) rotateX(0);
}

.langBtn:hover:before {
  opacity: 0;
  transform: translateY(50%) rotateX(90deg);
}

.langBtn:after {
  top: 0;
  left: 0;
  opacity: 0;
  width: 100%;
  color: #fff;
  display: block;
  transition: 0.3s;
  position: absolute;
  background: #fcc5b4 50%;
  content: attr(data-back);
  transform: translateY(-50%) rotateX(90deg);
  border-radius: 5px;
}

.langBtn:before {
  top: 0;
  left: 0;
  opacity: 1;
  color: #666e71;
  display: block;
  padding: 0 30px;
  line-height: 40px;
  transition: 0.3s;
  position: relative;
  background: #fff;
  content: attr(data-front);
  transform: translateY(0) rotateX(0);
  border-radius: 5px;
}

.searchBar {
  padding: 0px;
  display: flex;
  align-items: center;
}

.search {
  width: 100px;
  height: 50px;
  margin: 40px auto 0;
  background-color: #242628;
  position: relative;
  overflow: hidden;
  transition: all 0.3s ease;
}

.search:before {
  content: "";
  display: block;
  width: 3px;
  height: 100%;
  position: relative;
  background-color: #00fede;
  transition: all 0.3s ease;
}

.search.open {
  width: 420px;
}

.search.open:before {
  height: 60px;
  margin: 20px 0 20px 30px;
  position: absolute;
}

.searchInput {
  width: 100%;
  height: 100%;
  box-shadow: none;
  border: none;
  background: transparent;
  color: #fff;
  padding: 20px 100px 20px 45px;
  font-size: 40px;
}

.searchInput:focus {
  outline: none;
}

.searchBtn {
  width: 100px;
  height: 100px;
  display: block;
  position: absolute;
  right: 0;
  top: 0;
  padding: 20px;
  cursor: pointer;
}

.searchIcon {
  width: 40px;
  height: 40px;
  border-radius: 40px;
  border: 3px solid #00fede;
  display: block;
  position: relative;
  margin-left: 5px;
  transition: all 0.3s ease;
}

.searchIcon:before {
  content: "";
  width: 3px;
  height: 15px;
  position: absolute;
  right: -2px;
  top: 30px;
  display: block;
  background-color: #00fede;
  transform: rotate(-45deg);
  transition: all 0.3s ease;
}

.searchIcon:after {
  content: "";
  width: 3px;
  height: 15px;
  position: absolute;
  right: -12px;
  top: 40px;
  display: block;
  background-color: #00fede;
  transform: rotate(-45deg);
  transition: all 0.3s ease;
}
.searchIcon.open {
  margin: 0;
  width: 60px;
  height: 60px;
  border-radius: 60px;
}

.searchIcon.open:before {
  transform: rotate(52deg);
  right: 22px;
  top: 23px;
  height: 18px;
}

.searchIcon.open:after {
  transform: rotate(-230deg);
  right: 22px;
  top: 13px;
  height: 18px;
}

.menu {
  display: flex;
  align-items: center;
  margin-right: 30%;
}
.menu ul {
  display: flex;
  justify-content: flex-end;
  align-items: center;
  list-style: none;
  background-color: #ffffff;
}
.menu li {
  padding: 15px;
  margin-left: 50px;
}

.menu a {
  font-size: 21px;
  background: linear-gradient(
    to right,
    rgb(156, 156, 156) 50%,
    #f9a6b4 50%,
    #f8b58f
  );
  background-size: 200%;
  background-clip: text;
  -webkit-text-fill-color: transparent;
  transition: 0.3s ease-out;
  text-decoration: none;
  letter-spacing: 0.1px;
}

.menu a:hover {
  background-position: -100%;
}

.menu a:after {
  content: "";
  display: block;
  background-color: #ed9292;
  height: 3px;
  width: 0;
  left: 0;
  bottom: 10px;
  transition: 0.3s;
}

.menu a:hover:after {
  width: 100%;
}
</style>
