<script setup lang="ts">
interface TocItem {
  title: string
  day: number
  link: string
}

const tocItems = ref<TocItem[]>([
  { title: '开始 100 天编程挑战', day: 1, link: '#day-1' },
  { title: '项目设置与配置', day: 2, link: '#day-2' },
  // ... 后续可以动态添加更多项目
])
</script>

<template>
  <div bg-white="80" dark:bg-gray-800="80" fixed right-4 top-20 w-64 rounded-lg p-4 shadow-lg backdrop-blur>
    <h2 mb-4 text-lg text-gray-800 font-bold dark:text-gray-200>
      Table of Contents
    </h2>
    <nav>
      <ul space-y-2>
        <li
          v-for="item in tocItems"
          :key="item.day"
          list-none
        >
          <a
            :href="item.link"

            hover="bg-gray-100 dark:bg-gray-700"
            flex items-center gap-2 rounded-md p-2 transition-colors
          >
            <span text-sm text-blue-600 font-medium dark:text-blue-400>
              Day {{ item.day }}
            </span>
            <span text-sm text-gray-700 dark:text-gray-300>
              {{ item.title }}
            </span>
          </a>
        </li>
      </ul>
    </nav>
  </div>
</template>
