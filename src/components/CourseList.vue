<template>
  <div class="course-list">
    <CourseCard
      v-for="course in courses"
      :key="course.id"
      :course="course"
      @add="() => $emit('add-to-wishlist', course)"
    />
  </div>
</template>

<script>
import CourseCard from "./CourseCard.vue";

export default {
  components: { CourseCard },
  props: ["courses"]
};
</script>

<style>
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
