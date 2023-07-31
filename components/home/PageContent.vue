<template>
  <main :class="attr['page']">
    <div :class="attr['page__container']">
      <!-- sidebar -->
      <sidebar :class="attr['page__sidebar']" />

      <div :class="attr['page__content']">

        <!-- notification -->
        <notification :class="attr['page__notification']" />

        <div :class="attr['page__body']">

          <!-- profile -->
          <profile :class="attr['page__body-left']" />

          <!-- aside -->
          <side-info :class="attr['page__body-right']" />
        </div>
      </div>
    </div>
  </main>
</template>

<script>
  export default {
    components: {
      Sidebar: () => import('./sections/Sidebar'),
      Notification: () => import('./sections/Notification'),
      Profile: () => import('./sections/Profile'),
      SideInfo: () => import('./sections/SideInfo')
    }
  }
</script>

<style lang="scss" module="attr">
  .page {
    padding: 20px;
    &__container {
      max-width: 1360px;
      margin: 0 auto;
      display: flex;
    }

    &__sidebar {
      flex: 0 0 270px;
      margin-right: 20px;
    }

    &__content {
      flex: 1 0 5%;
      display: flex;
      flex-direction: column;

      > * {
        &:not(:last-child) {
          margin-bottom: 20px;
        }
      }
    }

    &__body {
      display: flex;

      &-left {
        flex: 1 0 5%;
      }

      &-right {
        margin-left: 20px;
        flex: 0 0 280px;
      }
    }
  }
</style>
