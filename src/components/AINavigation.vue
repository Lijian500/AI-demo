<template>
  <div class="flex h-full w-full bg-gradient-to-br from-yellow-400 via-green-400 to-pink-500">
    <!-- 左侧侧边栏 -->
    <div class="w-64 bg-gray-900 text-white p-4">
      <div class="flex items-center mb-8">
        <div class="text-orange-500 text-2xl font-bold">AI工具导航</div>
      </div>

      <!-- 侧边栏菜单项 -->
      <nav class="space-y-2">
        <sidebar-item v-for="item in sidebarItems"
                      :key="item.text"
                      :icon="item.icon"
                      :text="item.text" />
      </nav>
    </div>

    <!-- 主要内容区域 -->
    <div class="flex-1 p-8">
      <header class="mb-8">
        <h1 class="text-4xl font-bold text-white mb-4">未来之路，AI先行</h1>

        <!-- 导航标签 -->
        <div class="flex space-x-4 mb-4">
          <nav-tab v-for="tab in navTabs"
                   :key="tab.text"
                   :text="tab.text"
                   :is-active="tab.isActive" @click="printText(item)" />
        </div>

        <!-- 搜索栏 -->
        <div class="relative">
          <input type="text"
                 placeholder="站内搜索"
                 class="w-full px-4 py-2 rounded-lg bg-black bg-opacity-40 text-white placeholder-gray-300 focus:outline-none">
        </div>
      </header>

      <!-- 分类 -->
      <div class="flex space-x-2 mb-4">
        <category-button v-for="category in categories"
                         :key="category.text"
                         :text="category.text"
                         :is-active="category.isActive" />
      </div>

      <!-- 工具网格 -->
      <div class="grid grid-cols-4 gap-4">
        <tool-card v-for="tool in tools"
                   :key="tool.name"
                   :icon="tool.icon"
                   :name="tool.name"
                   :description="tool.description" />
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import {
  MagnifyingGlassIcon,
  ChatBubbleLeftIcon,
  DocumentTextIcon,
  CpuChipIcon,
  PencilSquareIcon,
  PhotoIcon,
  SwatchIcon,
  VideoCameraIcon,
  MusicalNoteIcon
} from '@heroicons/vue/24/outline'

import SidebarItem from './SidebarItem.vue'
import NavTab from './NavTab.vue'
import CategoryButton from './CategoryButton.vue'
import ToolCard from './ToolCard.vue'


const sidebarItems = [
  { icon: MagnifyingGlassIcon, text: 'AI 搜索引擎' },
  { icon: ChatBubbleLeftIcon, text: 'AI 聊天问答' },
  { icon: DocumentTextIcon, text: 'Prompt指令' },
  { icon: CpuChipIcon, text: 'Agent智能体' },
  { icon: PencilSquareIcon, text: 'AI 文本写作' },
  { icon: PhotoIcon, text: 'AI 绘画作图' },
  { icon: SwatchIcon, text: 'AI 设计工具' },
  { icon: VideoCameraIcon, text: 'AI 视频创作' },
  { icon: MusicalNoteIcon, text: 'AI 音频制作' },
]

const navTabs = [
  { text: '导航', isActive: true },
  { text: '搜索', isActive: false },
  { text: '工具', isActive: false },
  { text: '社区', isActive: false },
  { text: '生活', isActive: false },
]

const categories = [
  { text: '我的导航', isActive: true },
  { text: '最近使用', isActive: false },
]

const tools = [
  { icon: '🔍', name: '秘塔AI搜索', description: '智能AI搜索引擎' },
  { icon: '👩‍💻', name: 'Kimi.ai', description: '智能AI助手' },
  { icon: '🚀', name: '开源AI', description: '开源AI模型库' },
  { icon: '📱', name: '比格AI PPT', description: 'AI生成PPT工具' },
]



</script>

<style scoped>

</style>