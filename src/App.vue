<template>
  <div class="app-container">

  <div class="header-box">
    <span>Cooking Masterclass</span>
    <span>Wishlist: {{ wishlist.length }}</span>
  </div>

  <div class="course-list">
    <div v-for="course in courses" :key="course.name" class="course-card">
      <h3>{{ course.name }}</h3>
      <p>id: {{ course.id }}</p>
      <p>title: {{ course.title }}</p>
      <p>Chef: {{ course.chef }}</p>
      <p>Level: {{ course.level }}</p>
      <p>Price: R{{ course.price }}</p>

      <button v-if="course.available" @click="addToWishlist(course)">
        Save to Wishlist
      </button>
      <button v-else disabled>Sold Out</button>
    </div>
  </div>

</div>
</template>

<script>
import HeaderBar from "./components/HeaderBar.vue";
import CourseList from "./components/CourseList.vue";
import { courses } from "./data/courses";

export default {
  components: { HeaderBar, CourseList },

  data() {
    return {
      courses,
      wishlist: []
    };
  },

  methods: {
    addToWishlist(course) {
      if (!this.wishlist.includes(course.id)) {
        this.wishlist.push(course.id);
      }
    }
  }
};
</script>

<style>
.app-container {
  max-width: 1100px;
  margin: 0 auto;
  padding: 20px;
  font-family: Arial, sans-serif;
}

h1 {
  font-size: 2rem;
  margin-bottom: 10px;
}

.course-grid {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
}

@media (max-width: 768px) {
  .course-grid {
    flex-direction: column;
  }
}
</style>
