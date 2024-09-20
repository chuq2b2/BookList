<template>
<div>
    <img :src="image" alt="Book cover"/>
    <h2>{{ title }}</h2>
    <h3>{{ author }}</h3>
    <slot name="genres"></slot>
    <slot name="rating"></slot>
    <button @click="$emit('bookSelected', title)">
                Select
            </button>
</div>


</template>

<script>
export default{
    props: ['title', 'author','image'],
    emits: ['bookSelected'] 
}
</script>