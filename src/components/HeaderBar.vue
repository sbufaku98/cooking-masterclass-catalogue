<template>
  <header class="topbar">
    <h1>Cooking Masterclass</h1>
    <div class="wishlist">Wishlist: {{ wishlistCount }}</div>
  </header>
</template>

<script>
export default {
  props: ["wishlistCount"],
};
</script>

<style>
.header-bar {
  background: #f5f5f5;
  padding: 20px;
  border-radius: 12px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.header-title {
  font-size: 2rem;
  font-weight: bold;
}

.wishlist-count {
  background: #3B82F6;
  padding: 8px 14px;
  border-radius: 8px;
  color: white;
  font-weight: bold;
}
</style>
