<template>
  <aside :class="attr['info']">
    <div :class="attr['info__top']">
      <h2>Video Introduction</h2>
      <video width="280px" controls="" autoplay="false">
        <!-- MP4 must be first for iPad! -->
        <source src="http://clips.vorwaerts-gmbh.de/VfE_html5.mp4" type="video/mp4"><!-- Safari / iOS, IE9 -->
        <source src="http://clips.vorwaerts-gmbh.de/VfE.webm" type="video/webm"><!-- Chrome10+, Ffx4+, Opera10.6+ -->
        <source src="http://clips.vorwaerts-gmbh.de/VfE.ogv" type="video/ogg"><!-- Firefox3.6+ / Opera 10.5+ -->
        <!-- fallback to Flash: -->
        <object width="640" height="360" type="application/x-shockwave-flash" data="player.swf">
          <!-- Firefox uses the `data` attribute above, IE/Safari uses the param below -->
          <param name="movie" value="player.swf">
          <param name="flashvars" value="autostart=true&amp;controlbar=over&amp;image=poster.jpg&amp;file=http://clips.vorwaerts-gmbh.de/VfE_flash.mp4">
          <!-- fallback image -->
          <img src="poster.jpg" width="640" height="360" alt="Big Buck Bunny" title="No video playback capabilities, please download the video below">
        </object>
      </video>
    </div>

    <div :class="attr['info__middle']">
      <div :class="attr['info__title']">
        <h2>Profile Completion</h2>
        <p>100%</p>
      </div>

      <div :class="attr['info__progress']" :style="{ '--progress': '100%', '--color': 'var(--theme_green)' }"></div>

      <div :class="attr['info__middle-congratulations']">
        <p>Well done, Reyven!</p>
        <nuxt-img src="/images/award.png" />
      </div>


      <p>You have one of the strongest professional profile in our talent pool. Expect progress on your application any time soon.</p>
    </div>

    <div :class="attr['info__bottom']">
      <div :class="attr['info__title']">
        <h2>Profile Completion</h2>
        <p :class="attr['info__title-incomplete']">50%</p>
      </div>

      <div :class="attr['info__progress']" :style="{ '--progress': '50%', '--color': 'var(--theme_orange)' }"></div>

      <img src="#" alt="" />

      <div :class="attr['info__bottom-content']">
        <div :class="attr['info__bottom-hide']">
          <svg xmlns="http://www.w3.org/2000/svg" height="1em" viewBox="0 0 512 512"><!--! Font Awesome Free 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. --><path d="M233.4 406.6c12.5 12.5 32.8 12.5 45.3 0l192-192c12.5-12.5 12.5-32.8 0-45.3s-32.8-12.5-45.3 0L256 338.7 86.6 169.4c-12.5-12.5-32.8-12.5-45.3 0s-12.5 32.8 0 45.3l192 192z"/></svg>
          <span>Hide Recommendations</span>
        </div>

        <p>Fill-up the following items to strengthen your profile. This can help us matching your profile and increase your chances of landing into your desired role.</p>

        <template v-for="item in progress">
          <div :class="attr['info__progress-item']">
            <svg xmlns="http://www.w3.org/2000/svg" height="1em" viewBox="0 0 512 512"><!--! Font Awesome Free 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. --><path d="M464 256A208 208 0 1 0 48 256a208 208 0 1 0 416 0zM0 256a256 256 0 1 1 512 0A256 256 0 1 1 0 256z"/></svg>
            <p v-html="item"></p>
          </div>
        </template>
      </div>
    </div>
  </aside>
</template>

<script>
  export default {
    inject: ['progress']
  }
</script>

<style lang="scss" module="attr">
  .info {

    &__top,
    &__middle,
    &__bottom {
      margin-bottom: 20px;
      background: var(--theme_white);
      border-radius: 5px;
      box-shadow: 0 2px 0 0 rgba(0, 0, 0, 0.1);
    }

    &__top {
      h2 {
        padding: 20px 15px 10px 15px;
        font-size: 16px;
      }

      video {
        transform: translate(0, 3px);
        border-radius: 0 0 5px 5px;
      }
    }

    &__middle {
      padding: 20px 20px 25px 20px;

      &-congratulations {

        p {
          text-align: center;
          color: var(--theme_green);
          margin-bottom: 17px;
        }

        img {
          display: block;
          margin: 0 auto;
          margin-bottom: 20px;
        }
      }
    }

    &__bottom {
      padding: 20px 20px 25px 20px;

      &-content {
        margin-left: 20px;
        > p {
          margin-bottom: 20px;
        }
      }

      &-hide {
        margin-bottom: 15px;
        svg {
          margin-left: -20px;
        }
      }
    }

    &__title {
      margin-bottom: 5px;
      display: flex;
      justify-content: space-between;

      h2 {
        font-size: 16px;
      }

      p {
        color: var(--theme_green)
      }

      &-incomplete {
        color: var(--theme_orange) !important;
      }
    }

    &__progress {
      position: relative;
      height: 8px;
      width: 100%;
      margin-bottom: 15px;
      background: #E5E8EE;
      border-radius: 100px;

      &::after {
        content: '';
        position: absolute;
        top: 0;
        left: 0;
        height: 8px;
        width: var(--progress);
        border-radius: 10px;
        background: var(--color);
      }

      &-item {
        display: flex;
        align-items: center;

        &:not(:last-child) {
          margin-bottom: 15px;
        }

        svg {
          margin-right: 5px;
          width: 15px;
          flex: 0 0 15px;
        }

        span {
          color: var(--theme_green)
        }
      }
    }
  }
</style>
