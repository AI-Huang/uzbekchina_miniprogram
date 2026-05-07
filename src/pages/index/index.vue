<template>
  <div class="home-page">
    <!-- 顶部导航栏 -->
    <header class="top-nav">
      <div class="nav-left">
        <span class="location-icon">📍</span>
        <span class="location-text">塔什干</span>
        <span class="arrow">▼</span>
      </div>
      <div class="nav-title">首页</div>
      <div class="nav-right">
        <span class="more">···</span>
        <span class="circle">⚪</span>
      </div>
    </header>

    <!-- 搜索栏 -->
    <div class="search-bar">
      <input type="text" placeholder="请输入内容" class="search-input" />
    </div>

    <!-- 轮播图 -->
    <div class="banner">
      <img src="https://picsum.photos/seed/home-banner/750/200" alt="找房banner" class="banner-img" />
      <div class="banner-text">
        <span class="find-text">Find</span>
        <span class="action-text">立即找房</span>
        <span class="homes-text">Homes</span>
      </div>
    </div>

    <!-- 数据统计栏 -->
    <div class="stats-bar">
      <span class="stat-item">总浏览</span>
      <span class="stat-item active">总发布</span>
      <span class="stat-item">资源数</span>
    </div>

    <!-- 功能入口网格 -->
    <div class="function-grid">
      <div class="grid-item" v-for="item in functionList" :key="item.name">
        <div class="grid-icon" :style="{ backgroundColor: item.color }">
          <span class="icon">{{ item.icon }}</span>
          <span v-if="item.badge" class="badge">⚡</span>
        </div>
        <span class="grid-text">{{ item.name }}</span>
      </div>
    </div>

    <!-- 标签栏 -->
    <div class="tag-tabs">
      <div class="tag-item" v-for="tag in tagList" :key="tag.name">
        <img :src="tag.img" :alt="tag.name" class="tag-img" />
        <span class="tag-text">{{ tag.text }}</span>
        <span class="badge">⚡</span>
      </div>
    </div>

    <!-- 分类导航 -->
    <div class="category-nav">
      <span class="category-item active">推荐</span>
      <span class="category-item">公寓民</span>
      <span class="category-item">商铺写字</span>
      <span class="category-item">服务资</span>
    </div>

    <!-- 内容列表 -->
    <div class="content-list">
      <div class="list-item" v-for="item in contentList" :key="item.id">
        <img :src="item.cover" :alt="item.title" class="item-cover" />
        <div class="item-info">
          <div class="item-tag">
            <span class="tag">{{ item.tag }}</span>
            <span class="badge">⚡</span>
          </div>
          <h3 class="item-title">{{ item.title }}</h3>
          <p class="item-desc">{{ item.desc }}</p>
          <p class="item-view">近30天有{{ item.view }}人浏览</p>
          <p class="item-price" v-if="item.price">US$ {{ item.price }}/月</p>
        </div>
      </div>
    </div>

    <!-- 底部Tabbar -->
    <footer class="tabbar">
      <div class="tab-item active" v-for="tab in tabbarList" :key="tab.name">
        <span class="tab-icon">{{ tab.icon }}</span>
        <span class="tab-text">{{ tab.name }}</span>
        <span v-if="tab.badge" class="badge">⚡</span>
      </div>
    </footer>
  </div>
</template>

<script setup>
import { ref } from 'vue'

// 功能入口数据
const functionList = ref([
  { name: '汽车租售', icon: '🚗', color: '#2c7be5' },
  { name: '婚恋交友', icon: '💗', color: '#d63384' },
  { name: '签证白条', icon: '👤', color: '#6f42c1' },
  { name: '翻译', icon: '📄', color: '#fd7e14' },
  { name: '信息发布', icon: '🔊', color: '#dc3545', badge: true },
  { name: '合作资源', icon: '🤝', color: '#6f42c1' },
  { name: '公司注册', icon: '🏢', color: '#b8860b' },
  { name: '本地生活', icon: '🏪', color: '#28a745' }
])

// 标签栏数据
const tagList = ref([
  { name: '大学周边', img: 'https://picsum.photos/seed/university/240/150', text: '步行 10 分钟到校' },
  { name: '地铁公交', img: 'https://picsum.photos/seed/subway/240/150', text: '10 分钟到地铁' },
  { name: '拎包入住', img: 'https://picsum.photos/seed/movein/240/150', text: '来了第N回了' }
])

// 内容列表数据
const contentList = ref([
  {
    id: 1,
    cover: 'https://picsum.photos/seed/apartment1/370/250',
    tag: '整租',
    title: '塔什干水电大学|一室二厅|',
    desc: '房东直租|无佣金拎包入住',
    view: '736',
    price: '600'
  },
  {
    id: 2,
    cover: 'https://picsum.photos/seed/apartment2/370/250',
    tag: '整租',
    title: '塔什干水电大学|一室二厅|',
    desc: '房东直租|无佣金拎包入住',
    view: '736',
    price: '600'
  },
  {
    id: 3,
    cover: 'https://picsum.photos/seed/video/370/250',
    title: '乌兹打车为何如此便宜',
    desc: '小A在乌兹别克',
    view: '',
    price: ''
  },
  {
    id: 4,
    cover: 'https://picsum.photos/seed/car/370/250',
    tag: '',
    title: '雪佛兰Tracker(海外版)',
    desc: '小型SUV|5座|1.2T-1.3T',
    view: '736',
    price: ''
  },
  {
    id: 5,
    cover: 'https://picsum.photos/seed/office/370/250',
    tag: '商铺',
    title: '高端写字楼出租 -- 全包服务',
    desc: '现有两套现代化办公空间',
    view: '736',
    price: '1350'
  }
])

// 底部Tabbar数据
const tabbarList = ref([
  { name: '首页', icon: '🏠', badge: false },
  { name: '找房', icon: '🔍', badge: true },
  { name: '服务', icon: '🎖️', badge: false },
  { name: '我的', icon: '👤', badge: true }
])
</script>

<style scoped>
body {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
  background-color: #f5f5f5;
}
.app-container {
  max-width: 750px;
  margin: 0 auto;
  min-height: 100vh;
  background: #fff;
}

/* 箭头 */
.arrow {
  font-size: 12px;
}

/* 徽章 */
.badge {
  position: absolute;
  top: -4px;
  right: -4px;
  font-size: 12px;
}

/* 轮播图 */
.banner {
  position: relative;
  margin: 8px 16px;
  border-radius: 8px;
  overflow: hidden;
}
.banner-img {
  width: 100%;
  height: 200px;
  object-fit: cover;
}
.banner-text {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  color: white;
  font-size: 32px;
  font-weight: bold;
  text-shadow: 0 2px 4px rgba(0,0,0,0.3);
}

/* 分类导航 */
.category-nav {
  display: flex;
  gap: 16px;
  padding: 8px 16px;
  background-color: #fff;
  font-size: 16px;
}
.category-item.active {
  color: #2e8b57;
  font-weight: 500;
}

/* 内容列表 */
.content-list {
  padding: 8px;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 8px;
}

/* 功能网格 */
.function-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 16px;
  padding: 16px;
  background-color: #fff;
}

/* 查找文本 */
.find-text {
  font-style: italic;
  margin-right: 8px;
}

/* 首页 */
.home-page {
  /* 首页容器样式 */
}

/* 房屋文本 */
.homes-text {
  font-style: italic;
  margin-left: 8px;
}

/* 图标 */
.icon {
  /* 图标样式 */
}

/* 项目信息 */
.item-info {
  padding: 8px;
}

/* 项目徽章 */
.item-tag {
  display: flex;
  align-items: center;
  gap: 4px;
  font-size: 12px;
  color: #666;
}

/* 项目标题 */
.item-title {
  font-size: 16px;
  font-weight: 500;
  margin: 4px 0;
}

/* 项目描述 */
.item-desc {
  font-size: 14px;
  color: #666;
  margin: 4px 0;
}

/* 项目浏览 */
.item-view {
  font-size: 12px;
  color: #ff6b00;
  margin: 4px 0;
}

/* 项目价格 */
.item-price {
  font-size: 24px;
  font-weight: bold;
  color: #dc3545;
}

/* 项目封面 */
.item-cover {
  width: 100%;
  height: 200px;
  object-fit: cover;
}

/* 列表项 */
.list-item {
  background-color: #fff;
  border-radius: 8px;
  overflow: hidden;
}

/* 位置图标 */
.location-icon {
  font-size: 16px;
}

/* 位置文本 */
.location-text {
  font-size: 18px;
  font-weight: 500;
}

/* 网格图标 */
.grid-icon {
  width: 50px;
  height: 50px;
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 24px;
  color: white;
  position: relative;
}

/* 网格项 */
.grid-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 8px;
}

/* 网格文本 */
.grid-text {
  font-size: 14px;
}

/* 更多 */
.more {
  /* 更多样式 */
}

/* 导航左侧 */
.nav-left {
  display: flex;
  align-items: center;
  gap: 4px;
}

/* 导航右侧 */
.nav-right {
  display: flex;
  gap: 12px;
  font-size: 18px;
}

/* 导航标题 */
.nav-title {
  font-size: 20px;
  font-weight: 600;
}

/* 圆形 */
.circle {
  /* 圆形样式 */
}

/* 搜索栏 */
.search-bar {
  padding: 8px 16px;
  background-color: #fff;
}

/* 搜索输入 */
.search-input {
  width: 100%;
  padding: 10px 16px;
  border-radius: 20px;
  border: 1px solid #eee;
  font-size: 16px;
}

/* 统计栏 */
.stats-bar {
  display: flex;
  justify-content: space-around;
  padding: 8px 0;
  background-color: #fff;
  font-size: 16px;
}

/* 统计项 */
.stat-item.active {
  color: #2e8b57;
  font-weight: 500;
}

/* 标签 */
.tag {
  background-color: #eee;
  padding: 2px 6px;
  border-radius: 4px;
}

/* 标签项 */
.tag-item {
  position: relative;
  min-width: 240px;
  border-radius: 8px;
  overflow: hidden;
}

/* 标签图片 */
.tag-img {
  width: 100%;
  height: 150px;
  object-fit: cover;
}

/* 标签文本 */
.tag-text {
  position: absolute;
  bottom: 8px;
  left: 8px;
  color: white;
  font-size: 14px;
  text-shadow: 0 1px 2px rgba(0,0,0,0.5);
}

/* 标签栏 */
.tag-tabs {
  display: flex;
  gap: 8px;
  padding: 8px 16px;
  overflow-x: auto;
}

/* 底部Tabbar */
.tabbar {
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
  max-width: 750px;
  margin: 0 auto;
  display: flex;
  justify-content: space-around;
  padding: 8px 0;
  background-color: #fff;
  border-top: 1px solid #eee;
}

/* Tab项 */
.tab-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 4px;
  font-size: 14px;
  color: #666;
}

/* 激活的Tab项 */
.tab-item.active {
  color: #2e8b57;
}

/* Tab图标 */
.tab-icon {
  font-size: 20px;
}

/* Tab文本 */
.tab-text {
  /* Tab文本样式 */
}

/* 顶部导航 */
.top-nav {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 12px 16px;
  background-color: #2e8b57;
  color: white;
}

/* 操作文本 */
.action-text {
  /* 操作文本样式 */
}
</style>