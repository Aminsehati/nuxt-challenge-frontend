<template>
  <div class="teacher-blog">
    <div class="container-fluid">
      <div class="teacher-box">
        <div class="blog">
          <div class="blog-wrapper">
            <div class="image">
              <img :src="teacherInfo.profileImage" />
            </div>
            <div class="content">
              <div class="right">
                <div class="top">
                  <h2 class="title">
                    {{ teacherInfo.name }}
                  </h2>
                  <div class="category-wrapper">
                    <div
                      v-for="category in teacherInfo.category"
                      :key="category.id"
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
                    {{ teacherInfo.location }}
                  </div>
                  <div class="hour-teahers">
                    {{ teacherInfo.hourTeahers }}
                    ساعت تدریس
                  </div>
                </div>
              </div>
              <div class="left">
                <div class="top">
                  <div class="about-teacher">
                    <span> درباره مدرس : </span>
                    <span>
                      {{ teacherInfo.aboutTeacher }}
                    </span>
                  </div>
                </div>
                <div class="bottom">
                  <div class="price mb-10">
                    <span>
                      هزینه
                      {{ teacherInfo.hourTeahers }}
                      ساعت کلاس :
                    </span>
                    <span class="price-amount">
                      {{ teacherInfo.price }}
                      هزار تومان
                    </span>
                  </div>
                  <Button> مشاهده پروفایل و رزرو کلاس </Button>
                </div>
              </div>
            </div>
          </div>
          <div class="bottom-wrapper">
            <div class="right">
              <div class="right-heading-wrapper">
                <div v-for="item in teacherInfo.heading" :key="item.id" class="right-heading-item">
                    <span>
                      {{
                        item.name
                      }}
                    </span>
                </div>
              </div>
            </div>
            <div class="left">
              <Tabs :tabs="tabs" @tabChange="onChangeTab">
                <template slot="1">
                  <div class="about-heading">
                    <div
                      v-for="item in teacherInfo.heading"
                      :key="item.id"
                      class="mb-20 about-heading-item"
                    >
                      <h2 class="mb-10 font-700 font-16">
                        {{
                          item.name
                        }}
                      </h2>
                      <p>
                        {{
                          item.description
                        }}
                      </p>
                    </div>
                  </div>
                </template>
              </Tabs>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import "./style.scss";
export default {
  data() {
    return {
      teacherInfo: {
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
        heading: [
          {
            id: 1,
            name: "ادبیات",
            description: "این متن تست است",
          },
          {
            id: 2,
            name: "رزومه کلاس",
            description: "این متن تست است",
          },
        ],
      },
      tabs: [
        {
          id: 1,
          name: "درباره کلاس ها",
          step: 1,
          selected: true,
        },
        {
          id: 2,
          name: "رزومه مدرس",
          step: 2,
        },
        {
          id: 3,
          name: "کالکشن ویدیو ها",
          step: 3,
        },
        {
          id: 4,
          name: "نظرات  و امتیازات",
          step: 4,
        },
      ],
    };
  },
  methods: {
    onChangeTab(item) {
      this.tabs = this.tabs.map((tab) => {
        return {
          ...tab,
          selected: tab.id === item.id,
        };
      });
    },
  },
};
</script>

<style>
</style>