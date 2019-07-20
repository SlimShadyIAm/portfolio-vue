<template>
    <div class="container">
        <div v-for="attribute in attributes" :key="attribute.name">
            <h2 v-if="attribute.name" class="title is-3">
                {{ attribute.name }}
            </h2>
            <div class="columns is-multiline is-full-mobile">
                <Tile :content="attribute.content" v-for="attribute in attribute.items" :key="attribute.id" />
            </div>
            <hr>
        </div>
    </div>
</template>

<script>
import uuid from 'uuid';
import Tile from '@/components/Tile';

export default {
    name: 'tiles',
    components: {
        Tile
    },
    data() {
        return {
            attributes: [
                {
                    "name": "",
                    "items": [
                        {
                            "id": uuid.v4(),
                            "content": "19 years old"
                        },
                        {
                            "id": uuid.v4(),
                            "content": "Bachelors' at University of Twente"
                        },
                        {
                            "id": uuid.v4(),
                            "content": "Pakistani born"
                        },
                    ]
                },
                {
                    "name": "Knowledge",
                    "items": [
                        {
                            "id": uuid.v4(),
                            "content": "Frontend web development"
                        },
                        {
                            "id": uuid.v4(),
                            "content": "UI/UX design"
                        },
                        {
                            "id": uuid.v4(),
                            "content": "Responsive web design"
                        },
                    ]
                },
                {
                    "name": "Programming and scripting languages",
                    "items": [
                        {
                            "id": uuid.v4(),
                            "content": "HTML5 and CSS3"
                        },
                        {
                            "id": uuid.v4(),
                            "content": "JavaScript"
                        },
                        {
                            "id": uuid.v4(),
                            "content": "Java"
                        },
                        {
                            "id": uuid.v4(),
                            "content": "Python"
                        },
                    ]
                },
                {
                    "name": "Frameworks and technologies",
                    "items": [
                        {
                            "id": uuid.v4(),
                            "content": "Vue.js, React, Angular"
                        },
                        {
                            "id": uuid.v4(),
                            "content": "Node.js"
                        },
                        {
                            "id": uuid.v4(),
                            "content": "jQuery"
                        },
                        {
                            "id": uuid.v4(),
                            "content": "Linux and server administration"
                        },
                    ]
                }
            ],
        }
    },
}
</script>
