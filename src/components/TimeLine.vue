<script setup>
import Container from './Container.vue';
import Card from './Card.vue';

const data =[
    
    {
        id:1,
        username:'Anjelina',
        image: 'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Ftse1.mm.bing.net%2Fth%3Fid%3DOIP.yUEhMUAzCcqS4IOgAgPPXgHaFt%26pid%3DApi&f=1&ipt=4d99550a51871b409e575b7defaa45f31d42b90316535d28d5e164c07b4644f6&ipo=images',
        caption:'Anjelina'
    },
    {
        id:2,
        username:'Anne Hathaway',
        image: 'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Ftse2.mm.bing.net%2Fth%3Fid%3DOIP.HDdY7djRY0OLcCNZN8HJRwHaJg%26pid%3DApi&f=1&ipt=ad70efebe176897cef9eac595c0cea1d598353e64aa11972841b3713a4d741f1&ipo=images',
        caption:'Anne'
    },
    {
        id: 3,
        username:'Selma H',
        image:'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Ftse1.mm.bing.net%2Fth%3Fid%3DOIP.9xLk_l9QsZUi33vYUkru8QHaFj%26pid%3DApi&f=1&ipt=41ef0dfbd3f716ecdb1343c0f1e26267036a4fe996d381be67cc257a4d6db56b&ipo=images',
        caption:'Selma'
    }

]
</script>
<template>
    <Container>
        <div class="timeline-container">
            <Card v-for="post in data" :key="post.id" :post="post"/>
        </div>
    </Container>
</template>

<style scoped>
    .timeline-container {
        display: flex;
        flex-direction: column;
        align-items: center;
        padding:20px 0
    }
</style>