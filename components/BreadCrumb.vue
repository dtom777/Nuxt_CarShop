<template>
  <div class="l-breadcrumb text-white">
    <div class="l-breadcrumb__inner">
      <ul class="l-breadcrumb__items">
        <li class="l-breadcrumb__item" v-for="breadcrumb in breadcrumbs.data" :key="breadcrumb.name">
          <a v-if="breadcrumb.path" :href="breadcrumb.path" class="l-breadcrumb__text">{{ breadcrumb.name }}</a>
          <span v-else class="l-breadcrumb__text">{{ breadcrumb.name }}</span>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    breadcrumbs: Object
  }
}
</script>
