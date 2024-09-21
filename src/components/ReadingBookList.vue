<template>
    <div class="reading-book-list">
        <BookItem v-for="book in books" :title="book.title" :author="book.author" :image="book.image" @bookSelected="captureSelectedBooks">
    <template v-slot:genres>
        <p>{{ book.genres.join(", ") }}</p>
    </template>
    <template v-slot:rating>
        <p>{{ book.rating }}</p>
    </template>
</BookItem>
    </div>

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
                image: '../src/assets/the-lighting-thief.jpg'
            },
            {
                title: "The Midnight Library",
                author: "Matt Haig",
                genres: ["Fantasy", "Fiction"],
                rating: 3.99,
                image: '../src/assets/the-midnight-library.jpg'
            },
            {
                title: "How to Stop Time",
                author: "Matt Haig",
                genres: ["Fantasy", "Fiction"],
                rating: 3.83,
                image: '../src/assets/how-to-stop-time.jpg'
            },
            {
                title: "The Song of Achilles",
                author: "Madeline Miller",
                genres: ["Fantasy", "Historical"],
                rating: 4.32,
                image: '../src/assets/the-song-of-achilles.jpg'
            },

        ]}
    },
    methods: {
        captureSelectedBooks(book){
            alert("Selected: " + book)
        }
    }
}
</script>