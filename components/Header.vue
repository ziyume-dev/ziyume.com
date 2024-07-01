<script setup lang="ts">
const items = [
  [{
    label: '首页',
    url: '/',
  }],
  [{
    label: '设计原理',
    url: '/design-principle',
  }, {
    label: '联系我们',
    url: '/contact',
  }, {
    label: '关于',
    url: '/about',
  }],
]
</script>

<template>
  <div flex justify-between items-center mx-2>
    <div class="w-1/2 sm:w-1/3 md:w-1/4">
      <NuxtLink to="/" sm:flex-nowrap>
        <h1 flex font-serif text-3xl>
          <ruby>紫<rp>(</rp><rt font-sans>zi</rt><rp>)</rp></ruby>
          <ruby>梦<rp>(</rp><rt font-sans>Yume</rt><rp>)</rp></ruby>
          <div flex flex-col-reverse data-text="工作室">
            <div items-center justify-center px-2 text-xl>工作室</div>
          </div>
        </h1>
      </NuxtLink>
    </div>
    <div class="flex-1 sm:flex hidden items-center justify-center space-x-2">
      <ULink
        to="/design-principle"
        active-class="text-primary"
        inactive-class="text-gray-500 dark:text-gray-400 hover:text-gray-700 dark:hover:text-gray-200"
      >
        设计原理
      </ULink>
      <ULink
        to="/contact"
        active-class="text-primary"
        inactive-class="text-gray-500 dark:text-gray-400 hover:text-gray-700 dark:hover:text-gray-200"
      >
        联系我们
      </ULink>
      <ULink
        to="/about"
        active-class="text-primary"
        inactive-class="text-gray-500 dark:text-gray-400 hover:text-gray-700 dark:hover:text-gray-200"
      >
        关于
      </ULink>
    </div>
    <div class="w-1/2 sm:w-1/3 md:w-1/4">
      <div flex flex-row-reverse items-center>
        <DarkToggle mx-2 />
        <UDropdown :items="items" :ui="{ item: { disabled: 'cursor-text select-text' } }" :popper="{ placement: 'bottom-start' }">
          <UIcon sm:hidden flex name="i-heroicons-globe-asia-australia" />

          <template #item="{ item }">
            <NuxtLink :to="item.url" sm:flex-nowrap>
              {{ item.label }}
            </NuxtLink>
          </template>
        </UDropdown>
      </div>
    </div>
  </div>
</template>

<style scoped>

</style>
