<template lang="pug">
  .home.nids-layout-column.nids-layout-gt-xs-row.nids-flex
    .home__illustration.nids-flex-100.nids-flex-gt-xs-45.nids-layout-column
      .home__illustration__header.nids-layout-row.nids-layout-align-space-between-center
        .nids-brand.nids-brand--light
        ul.menu.nids-layout-row.nids-hide.nids-show-xs
          li.menu__item.menu__item--active
            a(href="#") Overview
          li.menu__item
            a(href="#") Media
          li.menu__item
            a(href="#") Profile
    .home__content.nids-flex
      .home__content__header.nids-layout-row.nids-layout-align-space-between-center
        ul.menu.nids-layout-row
          li.menu__item
            a(href="#")
              i.nids-icon.nids-icon--email
          li.menu__item
            a(href="#")
              i.nids-icon.nids-icon--settings
          li.menu__item.menu__item--has-notification
            a(href="#")
              i.nids-icon.nids-icon--bell
        .nids-layout-row.nids-layout-align-end-center
          h6.title Angélica Campos
          .nids-image.nids-image--avatar-small(ref="avatar")
            img(src="https://images.unsplash.com/photo-1509967419530-da38b4704bc6?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=800&q=60")
</template>

<script lang="ts">
import { Component, Vue, Ref } from 'vue-property-decorator';
import NidsImage from "@niduu/nids-images";

@Component
export default class Home extends Vue {
  @Ref('avatar')
  readonly avatar!: HTMLDivElement;

  mounted () {
    new NidsImage(this.avatar);
  }
}
</script>

<style lang="scss" scoped>
@import '~@niduu/nids-brand/nids-brand.css';
@import '~@niduu/nids-images/nids-images.css';

.home {
  .home__illustration {
    background-color: $nids-color--primary;
    padding: $nids-measure--base;
    box-sizing: border-box;
    border-radius: 0 $nids-measure--border-radius * 4 $nids-measure--border-radius * 4 0;
    .home__illustration__header {
      height: 44px;
      .menu {
        list-style: none;
        margin: 0;
        padding: 0;
        .menu__item {
          margin-right: $nids-measure--base;
          color: rgba($nids-color--white, 0.6);
          a {
            display: block;
            padding: 12px;
            box-sizing: border-box;
            color: inherit;
            text-decoration: none;
          }
          &:hover {
            color: white;
          }
          &.menu__item--active {
            color: $nids-color--secondary;
            font-weight: 600;
          }
        }
      }
    }
  }
  .home__content {
    .home__content__header {
      height: 44px;
      margin-top: 16px;
      padding: 0 $nids-measure--base;
      .menu {
        list-style: none;
        padding: 0;
        margin: 0;
        .menu__item {
          color: $nids-color--dark;
          a {
            display: block;
            color: inherit;
            text-decoration: none;
            padding: $nids-measure--base / 2;
            background-color: $nids-color--light;
            border-radius: $nids-measure--border-radius;
            margin-right: $nids-measure--base / 1.5;
            i {
              color: inherit;
            }
          }
          &.menu__item--has-notification {
            position: relative;
            &:after {
              content: '';
              position: absolute;
              top: -4px;
              right: 8px;
              width: 8px;
              height: 8px;
              border-radius: 100%;
              border: solid 2px $nids-color--white;
              background-color: $nids-color--danger;
            }
          }
        }
      }
      .title {
        margin-right: $nids-measure--base;
        @include nids-typography--callout-strong();
      }
    }
  }
}
</style>