<template>
  <button 
    class="navigation__item"
    :class="modifier">

    <i class="navigation__item_icon"></i>

    <span class="navigation__item_name">{{ name }}</span>

    <i class="sticker"></i>
  </button>
</template>

<script lang="ts">
import Vue from 'vue' 
import {Component, Prop} from 'nuxt-property-decorator'


@Component
export default class Title extends Vue {

  @Prop({type: String, default:'' }) name!: string;

  @Prop({type: String, default:'' }) type!: string;

  get modifier(): string  {
    return this.type ? 'navigation__item--' + this.type : ''
  }
}
</script>