<template>

    <li>
        <div>{{getTitle()}}</div>
        <div>{{info.original_title}}</div>
        <img v-if="info.poster_path" :src="`https://image.tmdb.org/t/p/w342/${info.poster_path}`">
        <img v-else :src="require('../../assets/istockphoto-1191001701-612x612.jpg')">
        <div>
            <img v-if="languages.includes(info.original_language)" :src="require('../../assets/flags/'+info.original_language+'.png')">
            <span v-else>{{info.original_language}}</span>
            {{info.original_language}}
        </div>
        <div>{{info.vote_average}}</div>
    </li>
  
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
img {
    height: 200px;
}

</style>