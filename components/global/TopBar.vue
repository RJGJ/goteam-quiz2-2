<template>
  <div :class="attr['top-bar']" ref="top-bar">
    <nav :class="attr['top-bar__container']">

      <div :class="attr['top-bar__left']">
        <!-- logo -->
        <nuxt-link :class="attr['top-bar__logo']" to="/" aria-label="Goteam">
          <nuxt-img src="/images/goteam-logo.png" alt="GoTeam Logo" />
        </nuxt-link>

        <!-- links -->
        <div :class="attr['top-bar__links']">
          <nuxt-link :class="attr['top-bar__link-item']" to="/careers">Careers</nuxt-link>
          <nuxt-link :class="attr['top-bar__link-item']" to="/roles">Find your Role</nuxt-link>
        </div>
      </div>

      <form :class="attr['top-bar__center']" @submit.prevent="() => {}">
        <!-- Search -->
        <input type="search" name="search" id="search" placeholder="Type for job title or role" />
        <button type="submit">
          <svg xmlns="http://www.w3.org/2000/svg" height="15px" viewBox="0 0 512 512"><path fill="#fff" d="M416 208c0 45.9-14.9 88.3-40 122.7L502.6 457.4c12.5 12.5 12.5 32.8 0 45.3s-32.8 12.5-45.3 0L330.7 376c-34.4 25.2-76.8 40-122.7 40C93.1 416 0 322.9 0 208S93.1 0 208 0S416 93.1 416 208zM208 352a144 144 0 1 0 0-288 144 144 0 1 0 0 288z"/></svg>
          <span>Search</span>
        </button>
      </form>

      <!-- user -->
      <div :class="attr['top-bar__right']">
        <div :class="attr['top-bar__right-info']">
          <h5>Reyven Biloy</h5>
          <a href="mailto:reyvenb@gmail.com">reyvenb@gmail.com</a>
        </div>
        <img src="https://picsum.photos/40" width="40px" />
        <svg xmlns="http://www.w3.org/2000/svg" height="1em" viewBox="0 0 512 512"><path fill="#7B8090" d="M233.4 406.6c12.5 12.5 32.8 12.5 45.3 0l192-192c12.5-12.5 12.5-32.8 0-45.3s-32.8-12.5-45.3 0L256 338.7 86.6 169.4c-12.5-12.5-32.8-12.5-45.3 0s-12.5 32.8 0 45.3l192 192z"/></svg>
      </div>
    </nav>
  </div>
</template>

<script>
  export default {
    mounted() {
      const margin = this.$refs['top-bar'].getBoundingClientRect().height
      document.documentElement.style.setProperty('--margin-top', `${margin}px`)
    }
  }
</script>

<style lang="scss" module="attr">
  .top-bar {
    position: fixed;
    z-index: 999;
    top: 0;
    right: 0;
    left: 0;
    padding: 15px 20px;
    background: var(--theme_white);
    box-shadow: 0 0 10px 0 rgba(0, 0, 0, 0.1);

    &__container {
      max-width: calc(100% - 40px);
      margin: 0 auto;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    &__left,
    &__right,
    &__center {
      flex: 0 0 calc(100% / 3);
    }

    &__left {
      display: flex;
      align-items: center;
    }

    &__center {
      flex: 0 0 min(33.3333%, 500px);
      display: flex;
      padding: 6px;
      border: solid 1px #DFE2E7;
      border-radius: 100px;

      input[type="search"] {
        margin-left: 20px;
        flex: 1 0 auto;
        border: none;
        background: none;
        outline: none;
      }

      button {
        padding: 6px 12px;
        display: flex;
        align-items: center;
        background: var(--theme_primary);
        color: var(--theme_white);
        border: none;
        border-radius: 100px;
        cursor: pointer;
        font-size: 14px;

        svg {
          margin-right: 6px;
        }

        span {
          color: inherit;
        }
      }
    }

    &__logo {
      margin-right: 60px;
    }

    &__link {
      &-item {
        transition: 0.2s ease;

        &:hover {
          color: var(--theme_primary);
        }

        &:not(:last-child) {
          margin-right: 30px;
        }
      }
    }

    &__right {
      display: flex;
      justify-content: flex-end;
      align-items: center;

      &-info {
        margin-right: 15px;

        h5, a {
          text-align: right;
        }

        a {
          color: var(--theme_primary);
        }
      }

      img {
        margin-right: 15px;
        border-radius: 100px;
      }
    }
  }

</style>
