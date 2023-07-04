

<template>
  <div id="header-text" style="background-color: #FAFAFA; height: 700px;">

    <div v-for="categories in list" v-if="categories.enabled">
      <div class="container">
        <div class="box">
          <img width="50px" src="https://cdn-icons-png.flaticon.com/512/4436/4436481.png" />
          <h1 v-for="list in sortedJson">{{ }} </h1>
          <h1>{{ categories.title }}</h1>
          <p>{{ categories.totalArticle }} articles</p>

          <p class="update">Last update {{ daysSinceLastDate(categories.updatedOn) }} days ago</p>
        </div>
      </div>


    </div>

  </div>
</template> 
    


<script>
import Vue from 'vue';
import axios from 'axios';
import vueaxios from 'Vue-axios'
Vue.use(vueaxios, axios)
export default {
  name: "Home",


  data() {
    return {
      list: undefined,
      previousDate: ''


    }
  },

  mounted() {
    Vue.axios.get('http://localhost:9000/api/categories')
      .then(response => {
        console.log(response.data)
        response.data.forEach((item) => {

          this.daysSinceLastDate(item.updatedOn); // Store the days left in a property of each item


        })

        this.list = response.data;
      })
  },
  computed: {
    sortedJson: function () {
      return this.list.sort((t1, t2) => t1.order < t2.order ? -1 : 1);

    },
  },
  methods: {
    daysSinceLastDate(previousDate) {
      const currentDate = new Date();
      const updatedDate = new Date(previousDate);
      const timeDifference = currentDate.getTime() - updatedDate.getTime();

      const daysDifference = Math.floor(timeDifference / (1000 * 60 * 60 * 24));
      console.log(daysDifference);
      return daysDifference;
    }
  }




};

</script>

<style lang="scss" scoped>
@import '../scss/_variables.scss';


.container {
  width: 100%;
  margin: 0 auto;
  background-color: grey;
}

.box {
  width: 31%;
  justify-content: space-evenly;

  background-color: white;
  padding: 2% 1%;
  margin: 1%;
  border: 1px solid #EEEEEE;
  border-radius: 5px;

  float: left;
}

.box h1 {
  color: #373737;
  font-size: 20px;
  font-weight: 700;
}

.box p {
  color: #03A84E;
  margin: 0px;
  ;
}

.box .update {
  color: #9C9AA6;
  font-size: 11px;

}

body {
  font-family: $font-family;
}

input {
  border: 1px solid #EEEEEE;
}

#header-text {
  text-align: center;
  font-family: $font-family;
  color: $text-black;
  padding: 20px;


  h1 {
    font-style: normal;
    font-weight: bold;

  }

  h3 {
    font-style: normal;
    font-weight: normal;
    font-size: 20px;
    line-height: 24px;
  }
}

* {
  box-sizing: border-box;
}

body {
  margin: 0;
  font-family: lato;
}

.topnav {
  overflow: hidden;
  background-color: #e9e9e9;
}

.topnav a {
  float: left;
  display: block;
  color: black;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
  font-size: 17px;
}

.topnav a:hover {
  background-color: #ddd;
  color: black;
}

.topnav a.active {
  background-color: #2196F3;
  color: white;
}

.topnav .search-container {
  float: right;
}

.topnav input[type=text] {
  padding: 6px;
  margin-top: 8px;
  font-size: 17px;
  border: none;
}

.topnav .search-container button {
  float: right;
  padding: 6px 10px;
  margin-top: 8px;
  margin-right: 16px;
  background: #ddd;
  font-size: 17px;
  border: none;
  cursor: pointer;
}

.topnav .search-container button:hover {
  background: #ccc;
}

input {
  padding: 0.5%;
  width: 37%;
  ;
}

input,
input::placeholder {
  font: 16px;
  line-height: 19.2px;
  color: #9C9AA6;
}

@media screen and (max-width: 600px) {
  .topnav .search-container {
    float: none;
  }

  .topnav a,
  .topnav input[type=text],
  .topnav .search-container button {
    float: none;
    display: block;
    text-align: left;
    width: 100%;
    margin: 0;
    padding: 14px;
  }

  .topnav input[type=text] {
    border: 1px solid #ccc;
  }
}

.search-container button {
  padding: .8% 1%;
  background-color: #03A84E;
  border: none;
}</style>