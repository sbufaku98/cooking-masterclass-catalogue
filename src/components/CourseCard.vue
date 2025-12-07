<template>
  <div class="card">
    <h3>{{ course.title }}</h3>
    <p><strong>Chef:</strong> {{ course.chef }}</p>
    <p><strong>Level:</strong> {{ course.level }}</p>
    <p><strong>Price:</strong> R{{ course.price }}</p>

    <button 
      :disabled="!course.available"
      @click="$emit('add')"
    >
      {{ course.available ? "Save to Wishlist" : "Sold Out" }}
    </button>
  </div>
</template>

<script>
export default {
  props: ["course"]
};
</script>

<style>
<style>
/* ------------------------ */
/* Layout styling */
/* ------------------------ */

.app-container {
  max-width: 900px;
  margin: 0 auto;
  padding: 20px;
  font-family: Arial, sans-serif;
}

/* ------------------------ */
/* Header box */
/* ------------------------ */
.header-box {
  background: #f1f1f1;
  padding: 25px;
  border-radius: 10px;
  margin-bottom: 30px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 24px;
  font-weight: bold;
  border: 1px solid #dcdcdc;
}

/* ------------------------ */
/* Course card layout */
/* ------------------------ */
.course-list {
  display: flex;
  gap: 20px;
  flex-wrap: wrap;
}

.course-card {
  width: 260px;
  border: 1px solid #dcdcdc;
  padding: 20px;
  border-radius: 10px;
  background: white;
  box-shadow: 0 2px 4px rgba(0,0,0,0.05);
}

/* Buttons */
button {
  margin-top: 10px;
  padding: 6px 10px;
  border-radius: 5px;
  cursor: pointer;
}
button:disabled {
  background: #ddd;
  cursor: not-allowed;
}
</style>
