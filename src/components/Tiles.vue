<template>
    <div class="container">
        <br>
        <div class="columns" v-for="i in rowCount" :key="i">
            <div class="column is-vcentered is-full-mobile" v-for="attribute in itemCountInRow(i)" :key="attribute.id">
                <div class="box">
                    {{ attribute.content }}
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import uuid from 'uuid';

export default {
    name: 'tiles',
    data() {
        return {
            attributes: [
                {
                    "id": uuid.v4(),
                    "content": "19 years old, Pakistani born"   
                },
                {
                    "id": uuid.v4(),
                    "content": "Bachelors' student at the University of Twente"   
                },
                {
                    "id": uuid.v4(),
                    "content": "Frontend web developer"   
                },
                {
                    "id": uuid.v4(),
                    "content": "Designer with a keen eye"   
                },
                {
                    "id": uuid.v4(),
                    "content": "HTML, CSS, JavaScript, Java"   
                },
                {
                    "id": uuid.v4(),
                    "content": "VueJS, React, Angular"   
                },
                
            ],
            itemsPerRow: 3
        }
    },
    computed:{
        rowCount() {     
            return Math.ceil(this.attributes.length / this.itemsPerRow);
        }
    },
    methods:{
        itemCountInRow:function(index){
            return this.attributes.slice((index - 1) * this.itemsPerRow, index * this.itemsPerRow)
        }
    }
}
</script>


<style scoped>
    @font-face {
    font-family: "San Francisco";
    font-weight: 700;
    src: url("https://applesocial.s3.amazonaws.com/assets/styles/fonts/sanfrancisco/sanfranciscodisplay-black-webfont.woff");
    }
    * {
        text-align: center;
    }
    .box {
        padding: 40px;
        font-size: 24px;
        font-family: 'San Francisco';
        height: 100%;
        display: flex;
        align-items: center;
        justify-content: center;
    }
</style>