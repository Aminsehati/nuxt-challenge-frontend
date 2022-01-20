<template>
  <div class="blog">
    <nuxt-link :to="`/teacher/${postInfo.id}`">
      <div class="blog-wrapper">
        <div class="image">
          <img :src="postInfo.profileImage" />
        </div>
        <div class="content">
          <div class="right">
            <div class="top">
              <h2 class="title">
                {{ postInfo.name }}
              </h2>
              <div class="category-wrapper">
                <div
                  v-for="category in postInfo.category"
                  :key="category"
                  class="category-item"
                >
                  <p>
                    {{ category.name }}
                  </p>
                </div>
              </div>
            </div>
            <div class="bottom">
              <div class="location mb-10">
                <i class="fas fa-map-marker-alt ml-5"></i>
                {{ postInfo.location }}
              </div>
              <div class="hour-teahers">
                {{ postInfo.hourTeahers }}
                ساعت تدریس
              </div>
            </div>
          </div>
          <div class="left">
            <div class="top">
              <div class="about-teacher">
                <span> درباره مدرس : </span>
                <span>
                  {{ postInfo.aboutTeacher }}
                </span>
              </div>
            </div>
            <div class="bottom">
              <div class="price mb-10">
                <span>
                  هزینه
                  {{ postInfo.hourTeahers }}
                  ساعت کلاس :
                </span>
                <span class="price-amount">
                  {{ postInfo.price }}
                  هزار تومان
                </span>
              </div>
              <Button> مشاهده پروفایل و رزرو کلاس </Button>
            </div>
          </div>
        </div>
      </div>
    </nuxt-link>
  </div>
</template>

<script>
import "./style.scss";
export default {
  props: {
    postInfo: {
      type: Object,
      default: () => {},
    },
  },
};
</script>

<style>
</style>