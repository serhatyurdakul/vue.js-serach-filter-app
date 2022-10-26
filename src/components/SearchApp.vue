<template>
  <div class="container">
    <div class="wrapper">
      <div class="background-rectange"></div>
      <h3 class="title">
        Free and Pro website <br />
        templates for your business
      </h3>
      <description class="description">
        Choose from over 300 fully responsible portfolio, blog <br />
        and ecommerce templates.
      </description>

      <div class="serach-container">
        <form>
          <input
            class="search-input"
            autofocus
            v-model="search"
            type="text"
            placeholder="Search all templates"
          />
        </form>
        <button class="btn-search">
          <span class="button-text">Search</span>
        </button>
      </div>
      <h4 class="sub-title">Common searches</h4>
      <div class="result-container">
        <div v-for="card in filteredCard" :key="card.id">
          <result-item :card="card" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import ResultItem from "@/components/ResultItem";

export default {
  name: "SearchApp",
  components: { ResultItem },
  props: ["card"],
  data() {
    return {
      search: "",
      cards: [
        {
          id: 1,
          title: "Blog",
        },
        {
          id: 2,
          title: "Business",
        },

        {
          id: 3,
          title: "Ecommerce",
        },
        {
          id: 4,
          title: "Portfolio",
        },
        {
          id: 5,
          title: "Fashion",
        },
        {
          id: 6,
          title: "Finance",
        },
        {
          id: 7,
          title: "Others",
        },
        {
          id: 8,
          title: "Technology",
        },
        {
          id: 9,
          title: "Health",
        },
        {
          id: 10,
          title: "Education",
        },
        {
          id: 11,
          title: "Gifts",
        },
        {
          id: 12,
          title: "Sports",
        },
        {
          id: 13,
          title: "Travel",
        },
      ],
    };
  },
  computed: {
    filteredCard() {
      return this.cards.filter((card) =>
        card.title.toLowerCase().match(this.search.toLowerCase())
      );
    },
  },
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=IBM+Plex+Sans:wght@500&display=swap");
@import url("https://fonts.googleapis.com/css2?family=IBM+Plex+Sans:wght@500&family=Merriweather:wght@900&display=swap");
.container {
  background: linear-gradient(135deg, #eff4ff, #b8bce4);
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;

  .wrapper {
    .background-rectange {
      position: absolute;
      width: 961px;
      height: 705px;
      left: 320px;
      top: 259px;
      z-index: -1;
      background: #ffffff;
      opacity: 0.4;
      border-radius: 20px;
      left: 30px;
      top: 20px;
    }
    display: flex;
    flex-direction: column;
    position: relative;
    z-index: 0;
    padding: 80px 156px 50px 100px;
    width: 1027px;
    height: 703px;
    background: $white;
    border-radius: 20px;
    // padding-left: 110px;
    // padding-top: 100px;
    // padding-right: 210px;
    .sub-title {
      font-family: "IBM Plex Sans";
      font-style: normal;
      font-weight: 500;
      font-size: 18px;
      line-height: 23px;
      color: $black;
    }
    .title {
      width: 707px;
      height: 124px;

      font-family: "Merriweather";
      font-style: normal;
      font-weight: 900;
      font-size: 46px;
      line-height: 62px;
      color: $navyBlue;
      margin-bottom: 25px;
    }
    .description {
      width: 611px;
      height: 62px;
      font-family: "IBM Plex Sans";
      font-style: normal;
      font-weight: 500;
      font-size: 24px;
      line-height: 31px;
      color: #000000;
      margin-bottom: 50px;
    }

    .serach-container {
      display: flex;
      flex-direction: row;
      margin-bottom: 60px;

      form {
        .search-input {
          width: 574px;
          height: 81px;
          background: $lightGray;
          border: 1px solid $borderColor;
          border-radius: 5px;
          font-family: "IBM Plex Sans";
          font-style: normal;
          font-weight: 500;
          font-size: 24px;
          line-height: 31px;
          padding-left: 30px;
          color: $black;

          &::placeholder {
            width: 226px;
            height: 31px;
            padding: 25px 0px 25px;
            font-family: "IBM Plex Sans";
            font-style: normal;
            font-weight: 500;
            font-size: 24px;
            line-height: 31px;
            color: $black;
            opacity: 0.5;
          }
        }
        margin-right: 14px;
      }
      .btn-search {
        width: 174px;
        height: 81px;
        background: $navyBlue
          url("data:image/svg+xml,%3Csvg width='32' height='32' viewBox='0 0 32 32' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cg clip-path='url(%23clip0_4_17)'%3E%3Cpath d='M13.3333 22.6667C18.488 22.6667 22.6667 18.488 22.6667 13.3333C22.6667 8.17868 18.488 4 13.3333 4C8.17868 4 4 8.17868 4 13.3333C4 18.488 8.17868 22.6667 13.3333 22.6667Z' stroke='white' stroke-width='2' stroke-linecap='round' stroke-linejoin='round'/%3E%3Cpath d='M28 28L20 20' stroke='white' stroke-width='2' stroke-linecap='round' stroke-linejoin='round'/%3E%3C/g%3E%3Cdefs%3E%3CclipPath id='clip0_4_17'%3E%3Crect width='32' height='32' fill='white'/%3E%3C/clipPath%3E%3C/defs%3E%3C/svg%3E%0A")
          25px no-repeat;
        border-radius: 5px;
        font-family: "IBM Plex Sans";
        font-style: normal;
        font-weight: 500;
        font-size: 24px;
        line-height: 31px;
        color: $white;
        cursor: pointer;
        &:hover {
          transition: transform 0.3s ease;
          transform: translate(-2px, 0px);
          opacity: 0.95;
        }
        .button-text {
          position: relative;
          left: 25px;
        }
      }
    }

    .result-container {
      display: flex;
      flex-wrap: wrap;
      flex-direction: row;
      margin-top: 15px;
      align-items: flex-start;
      padding: 8px 0 0 0;
      gap: 10px;
      width: 770px;
      overflow: auto;
      input {
        position: relative;
        transition: transform 0.3s ease;

        &:hover {
          transform: translate(0, -8px);
        }

        padding: 20px 30px 20px 30px;
        border-style: none;
        border-radius: 5px;
        cursor: pointer;

        &.Blog {
          background: $lightPink;
        }
        &.Business {
          background: $lightPurple;
        }
        &.Ecommerce {
          background: $lightOrange;
        }
        &.Portfolio {
          background: $green;
        }
        &.Fashion {
          background: $lightPink;
        }
        &.Finance {
          background: $lightGreen;
        }
        &.Others {
          background: $lightOrange;
        }
        &.Technology {
          background: $lightGreen;
        }
        &.Health {
          background: $purple;
        }
        &.Education {
          background: $lightPink;
        }
        &.Gifts {
          background: $lightPurple;
        }
        &.Sports {
          background: $green;
        }
        &.Travel {
          background: $purple;
        }
      }
    }
  }
}
</style>
