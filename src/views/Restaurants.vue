<template>
  <div class="container py-5">
    <NavTabs />
    <!-- 餐廳類別標籤 RestaurantsNavPills -->

      <div class="row">
        <!-- 餐廳卡片 RestaurantCard-->
        <RestaurantCard 
        v-for="restaurant in restaurants"
        :key="restaurant.id"
        :initial-restaurant="restaurant"
        />
      </div>

      <!-- 分頁標籤 RestaurantPagination -->
  </div>
</template>

<script>
import NavTabs from './../components/NavTabs'
import RestaurantCard from './../components/RestaurantCard.vue';

const dummyData = {
  "restaurants": [
    {
      "id": 1,
      "name": "Elouise Christiansen",
      "tel": "045-293-1312 x5218",
      "address": "467 Isaias Lodge",
      "opening_hours": "08:00",
      "description": "Omnis fugiat maxime consequatur vitae doloribus qu",
      "image": "https://loremflickr.com/320/240/restaurant,food/?random=17.38693298052043",
      "viewCounts": 0,
      "createdAt": "2023-06-12T15:04:10.000Z",
      "updatedAt": "2023-06-12T15:04:10.000Z",
      "CategoryId": 4,
      "Category": {
        "id": 4,
        "name": "墨西哥料理",
        "createdAt": "2023-06-12T15:04:10.000Z",
        "updatedAt": "2023-06-12T15:04:10.000Z"
      },
      "isFavorited": false,
      "isLiked": false
    },
    {
      "id": 2,
      "name": "Marlee Greenfelder",
      "tel": "917-069-9673",
      "address": "4593 Schneider Island",
      "opening_hours": "08:00",
      "description": "Sunt error tempore. Velit sunt consectetur qui rec",
      "image": "https://loremflickr.com/320/240/restaurant,food/?random=10.584103440022163",
      "viewCounts": 0,
      "createdAt": "2023-06-12T15:04:10.000Z",
      "updatedAt": "2023-06-12T15:04:10.000Z",
      "CategoryId": 3,
      "Category": {
        "id": 3,
        "name": "義大利料理",
        "createdAt": "2023-06-12T15:04:10.000Z",
        "updatedAt": "2023-06-12T15:04:10.000Z"
      },
      "isFavorited": false,
      "isLiked": false
    },
    {
      "id": 3,
      "name": "August Harvey",
      "tel": "(168) 499-3408",
      "address": "6771 Melany Mills",
      "opening_hours": "08:00",
      "description": "Voluptas sit at sit. Autem omnis incidunt earum su",
      "image": "https://loremflickr.com/320/240/restaurant,food/?random=89.15965072336883",
      "viewCounts": 0,
      "createdAt": "2023-06-12T15:04:10.000Z",
      "updatedAt": "2023-06-12T15:04:10.000Z",
      "CategoryId": 5,
      "Category": {
        "id": 5,
        "name": "素食料理",
        "createdAt": "2023-06-12T15:04:10.000Z",
        "updatedAt": "2023-06-12T15:04:10.000Z"
      },
      "isFavorited": false,
      "isLiked": false
    },
    {
      "id": 4,
      "name": "Randal Stoltenberg",
      "tel": "1-082-801-1009",
      "address": "50568 Alvis Square",
      "opening_hours": "08:00",
      "description": "Beatae vero quaerat. Cum eos unde iure adipisci un",
      "image": "https://loremflickr.com/320/240/restaurant,food/?random=48.14257999513683",
      "viewCounts": 0,
      "createdAt": "2023-06-12T15:04:10.000Z",
      "updatedAt": "2023-06-12T15:04:10.000Z",
      "CategoryId": 1,
      "Category": {
        "id": 1,
        "name": "中式料理",
        "createdAt": "2023-06-12T15:04:10.000Z",
        "updatedAt": "2023-06-12T15:04:10.000Z"
      },
      "isFavorited": false,
      "isLiked": false
    },
    {
      "id": 5,
      "name": "Courtney Rodriguez",
      "tel": "431.650.5541 x42088",
      "address": "8402 Sibyl Alley",
      "opening_hours": "08:00",
      "description": "Nostrum recusandae et. Qui non doloremque earum na",
      "image": "https://loremflickr.com/320/240/restaurant,food/?random=0.5273872877541219",
      "viewCounts": 0,
      "createdAt": "2023-06-12T15:04:10.000Z",
      "updatedAt": "2023-06-12T15:04:10.000Z",
      "CategoryId": 2,
      "Category": {
        "id": 2,
        "name": "日本料理",
        "createdAt": "2023-06-12T15:04:10.000Z",
        "updatedAt": "2023-06-12T15:04:10.000Z"
      },
      "isFavorited": false,
      "isLiked": false
    },
    {
      "id": 6,
      "name": "Kale Gleason",
      "tel": "(950) 940-9056 x798",
      "address": "28838 McLaughlin Springs",
      "opening_hours": "08:00",
      "description": "Dolor nemo sint corporis impedit quis quibusdam vi",
      "image": "https://loremflickr.com/320/240/restaurant,food/?random=8.439067142119994",
      "viewCounts": 0,
      "createdAt": "2023-06-12T15:04:10.000Z",
      "updatedAt": "2023-06-12T15:04:10.000Z",
      "CategoryId": 1,
      "Category": {
        "id": 1,
        "name": "中式料理",
        "createdAt": "2023-06-12T15:04:10.000Z",
        "updatedAt": "2023-06-12T15:04:10.000Z"
      },
      "isFavorited": false,
      "isLiked": false
    },
    {
      "id": 7,
      "name": "Cathryn Boehm",
      "tel": "126.321.2515 x4248",
      "address": "5507 Viola Street",
      "opening_hours": "08:00",
      "description": "possimus",
      "image": "https://loremflickr.com/320/240/restaurant,food/?random=9.11261058345949",
      "viewCounts": 0,
      "createdAt": "2023-06-12T15:04:10.000Z",
      "updatedAt": "2023-06-12T15:04:10.000Z",
      "CategoryId": 2,
      "Category": {
        "id": 2,
        "name": "日本料理",
        "createdAt": "2023-06-12T15:04:10.000Z",
        "updatedAt": "2023-06-12T15:04:10.000Z"
      },
      "isFavorited": false,
      "isLiked": false
    },
    {
      "id": 8,
      "name": "Tyrel Witting",
      "tel": "1-585-933-8063",
      "address": "528 Bartholome Fall",
      "opening_hours": "08:00",
      "description": "doloremque occaecati odio",
      "image": "https://loremflickr.com/320/240/restaurant,food/?random=40.592350931624125",
      "viewCounts": 0,
      "createdAt": "2023-06-12T15:04:10.000Z",
      "updatedAt": "2023-06-12T15:04:10.000Z",
      "CategoryId": 3,
      "Category": {
        "id": 3,
        "name": "義大利料理",
        "createdAt": "2023-06-12T15:04:10.000Z",
        "updatedAt": "2023-06-12T15:04:10.000Z"
      },
      "isFavorited": false,
      "isLiked": false
    },
    {
      "id": 9,
      "name": "Kali Kreiger MD",
      "tel": "(377) 483-1690",
      "address": "63307 Mueller Shoal",
      "opening_hours": "08:00",
      "description": "odit commodi optio",
      "image": "https://loremflickr.com/320/240/restaurant,food/?random=19.73889157394502",
      "viewCounts": 0,
      "createdAt": "2023-06-12T15:04:10.000Z",
      "updatedAt": "2023-06-12T15:04:10.000Z",
      "CategoryId": 4,
      "Category": {
        "id": 4,
        "name": "墨西哥料理",
        "createdAt": "2023-06-12T15:04:10.000Z",
        "updatedAt": "2023-06-12T15:04:10.000Z"
      },
      "isFavorited": false,
      "isLiked": false
    },
    {
      "id": 10,
      "name": "Ashly Kassulke DDS",
      "tel": "1-245-485-8125",
      "address": "566 Veum Stream",
      "opening_hours": "08:00",
      "description": "praesentium",
      "image": "https://loremflickr.com/320/240/restaurant,food/?random=11.593040186364512",
      "viewCounts": 0,
      "createdAt": "2023-06-12T15:04:10.000Z",
      "updatedAt": "2023-06-12T15:04:10.000Z",
      "CategoryId": 2,
      "Category": {
        "id": 2,
        "name": "日本料理",
        "createdAt": "2023-06-12T15:04:10.000Z",
        "updatedAt": "2023-06-12T15:04:10.000Z"
      },
      "isFavorited": false,
      "isLiked": false
    }
  ],
  "categories": [
    {
      "id": 1,
      "name": "中式料理",
      "createdAt": "2023-06-12T15:04:10.000Z",
      "updatedAt": "2023-06-12T15:04:10.000Z"
    },
    {
      "id": 2,
      "name": "日本料理",
      "createdAt": "2023-06-12T15:04:10.000Z",
      "updatedAt": "2023-06-12T15:04:10.000Z"
    },
    {
      "id": 3,
      "name": "義大利料理",
      "createdAt": "2023-06-12T15:04:10.000Z",
      "updatedAt": "2023-06-12T15:04:10.000Z"
    },
    {
      "id": 4,
      "name": "墨西哥料理",
      "createdAt": "2023-06-12T15:04:10.000Z",
      "updatedAt": "2023-06-12T15:04:10.000Z"
    },
    {
      "id": 5,
      "name": "素食料理",
      "createdAt": "2023-06-12T15:04:10.000Z",
      "updatedAt": "2023-06-12T15:04:10.000Z"
    },
    {
      "id": 6,
      "name": "美式料理",
      "createdAt": "2023-06-12T15:04:10.000Z",
      "updatedAt": "2023-06-12T15:04:10.000Z"
    },
    {
      "id": 7,
      "name": "複合式料理",
      "createdAt": "2023-06-12T15:04:10.000Z",
      "updatedAt": "2023-06-12T15:04:10.000Z"
    }
  ],
  "categoryId": "",
  "page": 1,
  "totalPage": [
    1,
    2,
    3,
    4,
    5
  ],
  "prev": 1,
  "next": 2
}

export default {
  components: {
    NavTabs,
    RestaurantCard
  },
  data() {
    return {
      restaurants: [],
      categories: [],
      categoryId: -1,
      currentPage: 1,
      totalPage: [],
      previousPage: -1,
      nextPage: -1

    }
  },
  created() {
    this.fetchRestaurants()
  },
  methods: {
    fetchRestaurants() {
      const {
        restaurants,
        categories,
        categoryId,
        page,
        totalPage,
        prev,
        next
      } = dummyData

      this.restaurants = restaurants
      this.categories = categories
      this.categoryId = categoryId
      this.currentPage = page
      this.totalPage = totalPage
      this.previousPage = prev
      this.nextPage = next
    }

  }
}
</script>