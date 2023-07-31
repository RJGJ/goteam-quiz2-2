<template>
  <div :class="attr['notification']">
    <div :class="attr['notification__actions']">
      <input type="checkbox" name="no_show" id="no_show" />
      <label for="no_show">Don't remind me again</label>
      <svg xmlns="http://www.w3.org/2000/svg" height="1em" viewBox="0 0 384 512"><!--! Font Awesome Free 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. --><path fill="var(--theme_red)" d="M342.6 150.6c12.5-12.5 12.5-32.8 0-45.3s-32.8-12.5-45.3 0L192 210.7 86.6 105.4c-12.5-12.5-32.8-12.5-45.3 0s-12.5 32.8 0 45.3L146.7 256 41.4 361.4c-12.5 12.5-12.5 32.8 0 45.3s32.8 12.5 45.3 0L192 301.3 297.4 406.6c12.5 12.5 32.8 12.5 45.3 0s12.5-32.8 0-45.3L237.3 256 342.6 150.6z"/></svg>
    </div>
    <div :class="attr['notification__top']">
      <h5>Welcome, Reyven!</h5>
      <p><span>You are almost done!</span> To further strenghten your profile, is is highly recommended for you to complete the 4 sections of your application.</p>
    </div>
    <div :class="attr['notification__bottom']">
      <template v-for="item in notification">
        <div :class="attr['notification__item']">
          <div :class="attr['notification__item__icon']" v-html="item.icon"></div>
          <div :class="attr['notification__item__text']">
            <h6>{{ item.label }}</h6>
            <div
              :class="attr['notification__item__progress']"
              :style="{
                '--progress': item.percentage + '%',
                '--color': item.color
              }"
            >
              <div :class="attr['notification__item__progress-bar']"></div>
              <p>{{ item.percentage }}%</p>
            </div>
          </div>
        </div>
      </template>
    </div>
  </div>
</template>

<script>
  export default {
    inject: ['notification']
  }
</script>

<style lang="scss" module="attr">
  .notification {
    position: relative;
    background: var(--theme_white);
    border-radius: 5px;
    box-shadow: 0 2px 0 0 rgba(0, 0, 0, 0.1);

    &__actions {
      position: absolute;
      top: 0;
      right: 0;
      margin: 15px;
      display: flex;
      align-items: center;

      input {
        margin-right: 10px;
      }

      label {
        margin-right: 30px;
        color: #9C9FAB;
      }
    }

    &__top {
      padding: 30px 20px 20px 20px;
      border-bottom: solid 1px #EAEDF1;

      h5 {
        margin-bottom: 10px;
        font-size: 18px;
        font-weight: bold;
      }

      p {
        span {
          color: var(--theme_green)
        }
      }
    }

    &__bottom {
      padding: 20px 20px 20px 20px;
      display: flex;
      justify-content: space-between;
    }

    &__item {
      flex: 0 0 calc(25% - 40px);
      display: flex;
      align-items: center;

      &__icon {
        height: 40px;
        width: 40px;
        margin-right: 15px;
        display: flex;
        justify-content: center;
        align-items: center;
        border-radius: 100px;
        background: #EFF2F7;
      }

      &__text {
        flex: 1 0 5%;
        h6 {
          margin-bottom: 5px;
          font-size: 12px;
        }
      }

      &__progress {
        display: flex;
        align-items: center;

        &-bar {
          height: 7px;
          flex: 1 0 5%;
          background: #DFE2E5;
          border-radius: 10px;
          position: relative;

          &:after {
            content: '';
            position: absolute;
            display: block;
            top: 0;
            left: 0;
            height: 7px;
            width: var(--progress);
            background: var(--color);
            border-radius: 10px;
          }
        }

        p {
          margin-left: 10px;
          flex: 0 0 20%;
          color: var(--color);
        }
      }
    }
  }
</style>
