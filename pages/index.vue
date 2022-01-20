<template>
  <div class="home">
    <div class="container-fluid">
      <div class="count-search-user font-800">28 مورد نتایج جست و جوی شما</div>
      <div class="sort-wrapper">
        <span class="title"> مرتب سازی بر اساس </span>
        <div class="sort-content">
          <div
            v-for="item in sortItems"
            :key="item.id"
            :class="['sort-content-item', { 'active-sort-item': item.select }]"
            @click="changeSortItem(item)"
          >
            <span>
              {{ item.name }}
            </span>
          </div>
        </div>
      </div>
    </div>
    <div class="container-fluid mx-auto">
      <div v-for="teaher in teacherItems" :key="teaher.id" class="mb-20">
        <posts :postInfo="teaher" />
      </div>
    </div>
  </div>
</template>

<script>
import "./style.scss";
export default {
  data() {
    return {
      teacherItems: [
        {
          id: 1,
          profileImage: require("@/assets/image/amin-sehati.webp"),
          name: "امین صحتی",
          location: "تهران",
          hourTeahers: 24,
          aboutTeacher: "این متن تست است",
          price: 120,
          category: [
            {
              id: 1,
              name: "ادبیات پایه دوازدهم تجربی و کنکور",
            },
            {
              id: 2,
              name: "نویسندگی",
            },
            {
              id: 3,
              name: "شعر نویس",
            },
          ],
        },
        {
          id: 2,
          profileImage: require("@/assets/image/amin-sehati.webp"),
          name: "امین صحتی",
          location: "تهران",
          hourTeahers: 24,
          aboutTeacher: "این متن تست است",
          price: 120,
          category: [
            {
              id: 1,
              name: "ادبیات پایه دوازدهم تجربی و کنکور",
            },
            {
              id: 2,
              name: "نویسندگی",
            },
            {
              id: 3,
              name: "شعر نویس",
            },
          ],
        },
        {
          id: 3,
          profileImage: require("@/assets/image/amin-sehati.webp"),
          name: "امین صحتی",
          location: "تهران",
          hourTeahers: 24,
          aboutTeacher: "این متن تست است",
          price: 120,
          category: [
            {
              id: 1,
              name: "ادبیات پایه دوازدهم تجربی و کنکور",
            },
            {
              id: 2,
              name: "نویسندگی",
            },
            {
              id: 3,
              name: "شعر نویس",
            },
          ],
        },
      ],
      sortItems: [
        {
          id: 1,
          name: "محبوب ترین",
          select: true,
        },
        {
          id: 2,
          name: "در دسترس ترین",
          select: false,
        },
        {
          id: 3,
          name: "بیشترین نظر",
          select: false,
        },
        {
          id: 4,
          name: "ارزان ترین",
          select: false,
        },
        {
          id: 5,
          name: "گران ترین",
          select: false,
        },
        {
          id: 6,
          name: "جدید ترین",
          select: false,
        },
      ],
    };
  },
  methods:{
    changeSortItem(item){
      this.sortItems = this.sortItems.map(sort=>{
        return {
          ...sort,
          select: sort .id === item.id,
        }
      })
      console.log(item);
    }
  }
};
</script>
