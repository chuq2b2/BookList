<template>
<BookItem v-for="book in books" :title="book.title" :author="book.author" :image="book.image" @bookSelected="captureSelectedBooks">
    <template v-slot:genres>
        <p>{{ book.genres.join(", ") }}</p>
    </template>
    <template v-slot:rating>
        <p>{{ book.rating }}</p>
    </template>
</BookItem>

<h4 id="bookCount">Total Number Of Books: {{ books.length }}</h4>
</template>

<script>

import BookItem from "./BookItem.vue"

export default{
    components: {
        BookItem
    },
    data() {
        return {
            books: [
            {
                title: "The Lighting Thief",
                author: "Rick Riordan",
                genres: ["Young Adult", "Fiction"],
                rating: 4.54,
                image: '../assets/the-lighting-thief.jpg'
            },
            {
                title: "The Midnight Library",
                author: "Matt Haig",
                genres: ["Fantasy", "Fiction"],
                rating: 3.99,
                image: '../assets/the-midnight-library.jpg'
            }
        ]}
    },
    methods: {
        captureSelectedBooks(book){
            alert("Selected: " + book)
        }
    }
}
</script>