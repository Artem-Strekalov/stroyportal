<template>
  <div id="app">
    <header>
      <div class="block_1">
      </div>
      <div class="block_2"></div>
      <div class="block_3"></div>
    </header>
    <hr />
    <main>
      <div class="left-panel">
        <div class="left_1"></div>
        <div class="left_2"></div>
      </div>
      <div class="main-content">
        <div class="main_1"></div>
        <div class="main_2">
          <div></div>
          <div></div>
          <div></div>
          <div></div>
          <div></div>
        </div>
        <div class="main_3">
          <div></div>
          <div class="block"></div>
        </div>
        <div class="main_4">
          <div></div>
          <div></div>
        </div>
      </div>
    </main>
    <hr />
    <footer>
      <div></div>
      <div></div>
      <div class="footer-content">
        <div></div>
        <div></div>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  name: "App",
};
</script>

<style lang="scss">
body {
  margin: 0px;
  padding: 0px;
  display: flex;
  justify-content: center;

  header {
    margin: 30px 0px 30px 0px;
    display: flex;
    justify-content: space-between;
    width: 960px;
    .block_1 {
      width: 200px;
      height: 50px;
      background: #808080;
    }
    .block_2 {
      background: #808080;
      width: 300px;
      height: 50px;
    }
    .block_3 {
      background: #808080;
      width: 400px;
      height: 50px;
    }
  }
  hr {
    margin: 0px;
    width: 960px;
    background: black;
  }
  main {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    margin: 30px 0px 30px 0px;
    .main-content {
      margin-left: 30px;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      .main_1 {
        height: 150px;
        width: 730px;
        background: #c8c8c8;
      }
      .main_2 {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        div {
          height: 70px;
          width: 122px;
          background: #c8c8c8;
        }
      }
      .main_3 {
        display: flex;
        flex-direction: row;
        div {
          height: 70px;
          width: 122px;
          background: #c8c8c8;
        }
        .block {
          margin-left: 30px;
        }
      }
      .main_4 {
        display: flex;
        justify-content: space-between;
        div {
          height: 190px;
          width: 350px;
          background: #c8c8c8;
        }
      }
    }
    .left-panel {
      display: flex;
      justify-content: space-between;
      flex-direction: column;
      height: 600px;
      .left_1 {
        width: 200px;
        height: 230px;
        background: #808080;
      }
      .left_2 {
        width: 200px;
        height: 140px;
        background: #808080;
      }
    }
  }
  footer {
    margin: 30px 0px 30px 0px;
    display: flex;
    justify-content: space-between;
    div {
      width: 300px;
      height: 130px;
      background: #808080;
    }
    .footer-content {
      background: none;
      display: flex;
      justify-content: space-between;
      flex-direction: column;
      div {
        width: 300px;
        height: 50px;
        background: #808080;
      }
    }
  }
}
</style>
