<template>
  <div id="app">
    <div class="block">
      <div class="content">
        <div class="header">
          <div class="location">
            <img src=".\assets\location.svg" alt="" />
            <p>Волгоградская область</p>
          </div>
          <div class="links">
            <a href="">Тендеры</a>
            <a href="">База подрядчиков</a>
            <a href="">Другие сервисы</a>

            <a href=""><img src=".\assets\Vector.svg" alt="" /></a>
          </div>
        </div>
        <div class="main">
          <img src=".\assets\Portal.svg" alt="" />
          <div class="catalog">
            <a href=""><img src=".\assets\menu.svg" alt="" /></a>
            <p>Каталог</p>
          </div>
          <div class="search">
            <input
              type="text"
              placeholder="Хочу найти..."
              autocomplete="off"
              v-model="productSearch"
              @input="filterproduct"
            />
            <img src=".\assets\search.svg" alt="" />
          </div>
          <button class="list">
            <img src=".\assets\list.svg" alt="" />
            <p>Список</p>
          </button>
          <div class="elipse">
            <span>A</span>
          </div>
        </div>
        <div class="autocomplete" v-if="selectedProducts">
          <ul v-if="productSearch">
            <ol
              v-for="item in selectedProducts"
              :key="item"
              @click="setProduct(item)"
            >
              <p>{{ item }}</p>
            </ol>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      productSearch: "",
      product: ["Гвозди", "Молоток", "Пила", "Отвертка"],
      selectedProducts: [],
    };
  },
  methods: {
    filterproduct() {
      this.selectedProducts = this.product.filter((productSearch) => {
        return productSearch
          .toLowerCase()
          .startsWith(this.productSearch.toLowerCase());
      });
    },
    setProduct(item) {
      this.productSearch = item;
    },
  },
};
</script>

<style lang="scss">
body {
  margin: 0px;
  padding: 0px;
}
.block {
  display: flex;
  justify-content: center;
  .content {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 1095px;
    .header {
      display: flex;
      flex-direction: row;
      align-items: center;
      height: 32px;
      .location {
        display: flex;
        flex-direction: row;
        flex-wrap: nowrap;
        p {
          margin: 0px 0px 0px 12px;
          font-family: Open Sans;
          font-style: normal;
          font-weight: normal;
          font-size: 12px;
          line-height: 20px;
          color: #708598;
        }
      }
      .links {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        width: 308.5px;
        margin-left: 625px;
        a {
          text-decoration: none;
          font-family: Open Sans;
          font-style: normal;
          font-weight: normal;
          font-size: 12px;
          line-height: 20px;
          color: #708598;
        }
      }
    }
    .main {
      display: flex;
      flex-direction: row;
      align-items: center;
      height: 76px;
      .catalog {
        display: flex;
        flex-direction: row;
        align-items: center;
        width: 116px;
        height: 40px;
        background: #fed83d;
        border-radius: 4px;
        margin-left: 24.11px;
        a {
          margin-left: 18.5px;
        }
        p {
          font-family: "Open Sans";
          font-style: normal;
          font-weight: 600;
          font-size: 14px;
          line-height: 24px;
          color: #050f19;
          margin-left: 10.5px;
        }
      }
      .search {
        display: flex;
        flex-direction: row;
        align-items: center;
        width: 526px;
        height: 40px;
        background: #ffffff;
        border: 1px solid #eceff1;
        border-radius: 4px;
        margin-left: 24px;
        input {
          height: 36px;
          width: 450px;
          margin-left: 14px;
          outline: none;
          border: none;
          font-family: "Open Sans";
          font-style: normal;
          font-weight: normal;
          font-size: 14px;
          line-height: 24px;
          color: #708598;
        }
        ::-webkit-input-placeholder {
          font-family: "Open Sans";
          font-style: normal;
          font-weight: normal;
          font-size: 14px;
          line-height: 24px;
          color: #708598;
          opacity: 1;
          transition: opacity 0.3s ease;
        }
        :focus::-webkit-input-placeholder {
          color: transparent;
        }
        img {
          margin-left: 14.17px;
        }
      }
      .list {
        padding: 0px;
        display: flex;
        flex-direction: row;
        align-items: center;
        width: 111px;
        height: 40px;
        margin-left: 24px;
        background: #fafbfc;
        border: 1px solid #eceff1;
        box-sizing: border-box;
        border-radius: 4px;
        img {
          margin-left: 16px;
          margin-bottom: 4px;
        }
        p {
          font-family: "Open Sans";
          font-style: normal;
          font-weight: 600;
          font-size: 14px;
          line-height: 24px;
          color: #050f19;
          margin-left: 12px;
        }
      }
      .elipse {
        display: flex;
        align-items: center;
        justify-content: center;
        width: 40px;
        height: 40px;
        border-radius: 50%;
        background: #9b51e0;
        margin-left: 24px;
        span {
          font-family: Open Sans;
          font-style: normal;
          font-weight: 600;
          font-size: 14px;
          line-height: 24px;
          color: #ffffff;
        }
      }
    }
  }
  .autocomplete {
    margin-left: 110px;
    ul {
      margin: 0px;
      padding: 0px;
      ol {
        padding: 0px;
        display: flex;
        align-items: center;
        height: 36px;
        width: 450px;
        background: #eceff1;
        p {
          margin: 0px 0px 0px 14px;
          font-family: "Open Sans";
          font-style: normal;
          font-weight: normal;
          font-size: 14px;
          line-height: 24px;
          color: #708598;
        }
      }
    }
  }
}
</style>
