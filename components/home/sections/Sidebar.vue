<template>
  <aside :class="attr['sidebar']">
    <div :class="attr['sidebar__group']" v-for="group in data.groups">
      <template v-for="item in group">
        <nuxt-link
          :to="item.link"
          :class="[
            attr['sidebar__group-item'],
            item.active && attr['sidebar__group-item--active'],
          ]"
        >
          <div :class="attr['sidebar__group-item__icon']" v-html="item.icon"></div>
          <div :class="attr['sidebar__group-item__label']">{{ item.label }}</div>
          <template v-if="item.notificationCount > 0">
            <div :class="attr['sidebar__group-item__notification-count']">
              <span>{{ item.notificationCount }}</span>
            </div>
          </template>
          <template v-if="item.active">
            <svg :class="attr['sidebar__group-item__active']" xmlns="http://www.w3.org/2000/svg" height="1em" viewBox="0 0 320 512"><path d="M310.6 233.4c12.5 12.5 12.5 32.8 0 45.3l-192 192c-12.5 12.5-32.8 12.5-45.3 0s-12.5-32.8 0-45.3L242.7 256 73.4 86.6c-12.5-12.5-12.5-32.8 0-45.3s32.8-12.5 45.3 0l192 192z"/></svg>
          </template>
        </nuxt-link>
      </template>
    </div>

    <div :class="attr['sidebar__bottom']">
      <p>Copyright 2018 - {{ new Date().getFullYear() }}. All rights reserved.</p>
      <p><nuxt-link to="/">Terms os Use</nuxt-link> • <nuxt-link to="/">Privacy Policy</nuxt-link></p>
    </div>
  </aside>
</template>

<script>
  export default {
    inject: ['sidebar'],
    data() {
      return {
        data: this.sidebar
      }
    },
  }
</script>

<style lang="scss" module="attr">
  .sidebar {
    &__group {
      margin-bottom: 10px;
      &:not(:nth-last-child(2)) {
        border-bottom: 1px solid #E6E9EF;
        margin-bottom: 20px;
      }

      &-item {
        $this: &;

        display: flex;
        align-items: center;
        padding: 15px;
        margin-bottom: 10px;
        transition: .2s ease;
        border-radius: 5px;

        &__icon {
          margin-right: 20px;
          transition: inherit;
        }

        &__label {
          margin-right: 10px;
          transition: inherit;
        }

        &__notification-count {
          position: relative;
          transition: inherit;
          width: 20px;
          height: 20px;
          border-radius: 3px;
          background: var(--theme_red);

          span {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -51%);
            color: var(--theme_white);
          }
        }

        &__active {
          margin-left: auto;
        }

        &:hover {
          background: #EFF2F7;
        }

        &--active {
          background: #EFF2F7;

          #{$this}__icon {
            fill: var(--theme_primary);
          }

          #{$this}__label {
            color: var(--theme_primary);
          }

          #{$this}__active {
            fill: var(--theme_primary);
          }
        }
      }
    }

    &__bottom {
      > * {
        margin-bottom: 10px;
      }

      a {
        color: var(--theme_primary);
      }
    }
  }
</style>
