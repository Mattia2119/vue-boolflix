<template>

    <div>

        <div class="flip-card">
            <div class="flip-card-inner">
                <div class="flip-card-front"> 
                    <img v-if="info.poster_path" :src="`https://image.tmdb.org/t/p/w342/${info.poster_path}`">
                    <img v-else :src="require('../../assets/istockphoto-1191001701-612x612.jpg')">
                </div>

                <div class="flip-card-back">     
                    <div>{{getTitle()}}</div>
                    <div>{{info.original_title}}</div>
                    
                    <div>
                        <img class="flag" v-if="languages.includes(info.original_language)" :src="require('../../assets/flags/'+info.original_language+'.png')">
                        <span v-else>{{info.original_language}}</span>
                    </div>
                    <div>
                        {{info.vote_average}}
                        <i v-for="i in 5" :key="i" class="fa-star" :class="(i < getStar()) ? 'fa-solid':'fa-regular'"></i>
                    </div>           
                </div>
            </div>
        </div>
    </div>
  
</template>

<script>

    export default {
        name: "MyCard",
        props: {
            'info' : Object    
        },
        data(){
            return {
              languages: ["en","it"]
            }       
        },
        methods: {
            getTitle() {
                if (this.info.title) {
                return this.info.title;
                } else {
                    return this.info.name;  
                }
              
            },
            getStar() {
              return Math.ceil(this.info.vote_average / 2);
            }
        }
    }
</script>

<style lang="scss" scoped>

/* The flip card container - set the width and height to whatever you want. We have added the border property to demonstrate that the flip itself goes out of the box on hover (remove perspective if you don't want the 3D effect */
.flip-card {
  background-color: transparent;
  width: 300px;
  height: 500px;
  perspective: 1000px; /* Remove this if you don't want the 3D effect */
   .flag {
       max-width: 60px;
   }
}

/* This container is needed to position the front and back side */
.flip-card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  text-align: center;
  transition: transform 0.8s;
  transform-style: preserve-3d;
}

/* Do an horizontal flip when you move the mouse over the flip box container */
.flip-card:hover .flip-card-inner {
  transform: rotateY(180deg);
}

/* Position the front and back side */
.flip-card-front, .flip-card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  -webkit-backface-visibility: hidden; /* Safari */
  backface-visibility: hidden;
}

/* Style the front side (fallback if image is missing) */
.flip-card-front {
  background-color: #bbb;
  color: black;
   img {
       width: 100%;
       height: 500px;
       object-fit: cover;
   }
}

/* Style the back side */
.flip-card-back {
  background-color: black;
  color: white;
  transform: rotateY(180deg);
}

</style>