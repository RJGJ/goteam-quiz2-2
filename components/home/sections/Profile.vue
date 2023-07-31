<template>
  <div :class="attr['profile']">
    <div :class="attr['profile__top']">
      <div :class="attr['profile__top__left']">
        <img src="https://picsum.photos/120" width="120px" />
      </div>
      <div :class="attr['profile__top__right']">
        <h2 :class="attr['profile__name']">Reyven S. Biloy</h2>
        <h3 :class="attr['profile__position']">UI/UX Designer</h3>
        <div :class="attr['profile__education']">
          <svg xmlns="http://www.w3.org/2000/svg" height="15px" viewBox="0 0 448 512"><!--! Font Awesome Free 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. --><path d="M219.3 .5c3.1-.6 6.3-.6 9.4 0l200 40C439.9 42.7 448 52.6 448 64s-8.1 21.3-19.3 23.5L352 102.9V160c0 70.7-57.3 128-128 128s-128-57.3-128-128V102.9L48 93.3v65.1l15.7 78.4c.9 4.7-.3 9.6-3.3 13.3s-7.6 5.9-12.4 5.9H16c-4.8 0-9.3-2.1-12.4-5.9s-4.3-8.6-3.3-13.3L16 158.4V86.6C6.5 83.3 0 74.3 0 64C0 52.6 8.1 42.7 19.3 40.5l200-40zM111.9 327.7c10.5-3.4 21.8 .4 29.4 8.5l71 75.5c6.3 6.7 17 6.7 23.3 0l71-75.5c7.6-8.1 18.9-11.9 29.4-8.5C401 348.6 448 409.4 448 481.3c0 17-13.8 30.7-30.7 30.7H30.7C13.8 512 0 498.2 0 481.3c0-71.9 47-132.7 111.9-153.6z"/></svg>
          <span>Bachelor of Science in Computer Science</span>
        </div>
        <div :class="attr['profile__experience']">
          <svg xmlns="http://www.w3.org/2000/svg" height="15px" viewBox="0 0 512 512"><!--! Font Awesome Free 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. --><path d="M184 48H328c4.4 0 8 3.6 8 8V96H176V56c0-4.4 3.6-8 8-8zm-56 8V96H64C28.7 96 0 124.7 0 160v96H192 320 512V160c0-35.3-28.7-64-64-64H384V56c0-30.9-25.1-56-56-56H184c-30.9 0-56 25.1-56 56zM512 288H320v32c0 17.7-14.3 32-32 32H224c-17.7 0-32-14.3-32-32V288H0V416c0 35.3 28.7 64 64 64H448c35.3 0 64-28.7 64-64V288z"/></svg>
          <span>12 years</span>
        </div>
        <div :class="attr['profile__availability']">
          <svg xmlns="http://www.w3.org/2000/svg" height="15px" viewBox="0 0 448 512"><!--! Font Awesome Free 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. --><path d="M128 0c13.3 0 24 10.7 24 24V64H296V24c0-13.3 10.7-24 24-24s24 10.7 24 24V64h40c35.3 0 64 28.7 64 64v16 48V448c0 35.3-28.7 64-64 64H64c-35.3 0-64-28.7-64-64V192 144 128C0 92.7 28.7 64 64 64h40V24c0-13.3 10.7-24 24-24zM400 192H48V448c0 8.8 7.2 16 16 16H384c8.8 0 16-7.2 16-16V192zM329 297L217 409c-9.4 9.4-24.6 9.4-33.9 0l-64-64c-9.4-9.4-9.4-24.6 0-33.9s24.6-9.4 33.9 0l47 47 95-95c9.4-9.4 24.6-9.4 33.9 0s9.4 24.6 0 33.9z"/></svg>
          <span>Immediately</span>
        </div>
        <div :class="attr['profile__salary']">
          <svg xmlns="http://www.w3.org/2000/svg" height="15px" viewBox="0 0 576 512"><!--! Font Awesome Free 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. --><path d="M64 64C28.7 64 0 92.7 0 128V384c0 35.3 28.7 64 64 64H512c35.3 0 64-28.7 64-64V128c0-35.3-28.7-64-64-64H64zm64 320H64V320c35.3 0 64 28.7 64 64zM64 192V128h64c0 35.3-28.7 64-64 64zM448 384c0-35.3 28.7-64 64-64v64H448zm64-192c-35.3 0-64-28.7-64-64h64v64zM288 160a96 96 0 1 1 0 192 96 96 0 1 1 0-192z"/></svg>
          <span :class="attr['green']">Php 35,000</span>
        </div>
      </div>

      <svg :class="attr['profile__edit-icon']" xmlns="http://www.w3.org/2000/svg" height="15px" viewBox="0 0 512 512"><path d="M362.7 19.3L314.3 67.7 444.3 197.7l48.4-48.4c25-25 25-65.5 0-90.5L453.3 19.3c-25-25-65.5-25-90.5 0zm-71 71L58.6 323.5c-10.4 10.4-18 23.3-22.2 37.4L1 481.2C-1.5 489.7 .8 498.8 7 505s15.3 8.5 23.7 6.1l120.3-35.4c14.1-4.2 27-11.8 37.4-22.2L421.7 220.3 291.7 90.3z"/></svg>
    </div>

    <template v-for="group in profile.groups">
      <div :class="attr['profile__group']">
        <h2>{{ group.title }}</h2>
        <template v-for="item in group.items">
          <div :class="attr['profile__group-detail']">
            <p :class="attr['profile__group-label']">{{ item.label }}</p>
            <p :class="attr['profile__group-value']" :style="{ '--color': item.color || '#3E4458' }">{{ item.value }}</p>
          </div>
        </template>
        <svg :class="attr['profile__edit-icon']" xmlns="http://www.w3.org/2000/svg" height="15px" viewBox="0 0 512 512"><path d="M362.7 19.3L314.3 67.7 444.3 197.7l48.4-48.4c25-25 25-65.5 0-90.5L453.3 19.3c-25-25-65.5-25-90.5 0zm-71 71L58.6 323.5c-10.4 10.4-18 23.3-22.2 37.4L1 481.2C-1.5 489.7 .8 498.8 7 505s15.3 8.5 23.7 6.1l120.3-35.4c14.1-4.2 27-11.8 37.4-22.2L421.7 220.3 291.7 90.3z"/></svg>
      </div>
    </template>
  </div>
</template>

<script>
  export default {
    inject: ['profile']
  }
</script>

<style lang="scss" module="attr">

  .green {
    color: var(--theme_green);
  }
  .profile {
    $parent: &;

    background: var(--theme_white);
    box-shadow: 0 2px 0 0 rgba(0, 0, 0, 0.1);
    border-radius: 5px;

    svg {
      fill: #505669;
    }

    &__top {
      position: relative;
      display: flex;
      border-bottom: solid 1px #EDEFF3;

      &__left {
        border-right: solid 1px #EDEFF3;
        padding: 25px 30px 40px 30px;

        img {
          border-radius: 50%;
          border: solid 1px #EDEFF3;
        }
      }

      &__right {
        padding: 35px 30px;
        flex: 1 0 5%;
        display: flex;
        flex-wrap: wrap;
      }
    }

    &__name {
      font-size: 20px;
      margin-bottom: 10px;
      flex: 0 0 100%;
    }

    &__position {
      font-size: 18px;
      color: rgb(83,89,107);
      margin-bottom: 15px;
      flex: 0 0 100%;
    }

    &__education, &__experience, &__availability, &__salary {
      display: flex;
      align-items: center;

      svg {
        margin-right: 15px;
      }
    }

    &__education {
      margin-bottom: 15px;
      flex: 0 0 100%;
    }

    &__experience, &__availability, &__salary {
      display: inline;
      flex: 0 0 33.333%;
    }

    &__group {
      position: relative;
      padding: 30px 25px 40px 25px;

      &:not(:last-child) {
        border-bottom: solid 1px #EDEFF3;
      }

      h2 {
        font-size: 18px;
        font-weight: bold;
        margin-bottom: 20px;
      }

      &-detail {
        display: flex;
        align-items: center;

        &:not(:last-child) {
          margin-bottom: 20px;
        }
      }

      &-label {
        flex: 0 0 30%;
      }

      &-value {
        margin-left: 50px;
        flex: 1 0 5%;
        color: var(--color);
      }
    }

    &__edit-icon {
      position: absolute;
      top: 0;
      right: 0;
      margin: 30px 15px;
      cursor: pointer;
      path {
        fill: #505669;
      }
    }
  }
</style>
