<script setup>
import { RouterLink, useRouter } from 'vue-router';
import Container from './Container.vue'
import AuthModal from './AuthModal.vue'
import {ref} from 'vue'

const searchUsername=ref("")
const router = useRouter()
const onSearch = ()=>{
    if(searchUsername.value){
        router.push(`/profile/${searchUsername.value}`)
        searchUsername.value =""
    }
}
const isAuthenticated = ref(false)
</script>

<template>
    <ALayout>
        <ALayoutHeader > 
            <Container>
                <div class="nav-container">
                    <div class="left-content">
                        <RouterLink to="/">Instagram</RouterLink>
                        <AInputSearch
                            v-model:value="searchUsername"
                            placeholder="username..."
                            style="width: 200px"
                            @search="onSearch"
                        />
                    </div>
                    <div class="right-content" v-if="!isAuthenticated">
                        <AuthModal :isLogin="false"/>
                        <AuthModal :isLogin="true"/>
                    </div>
                    <div class="right-content" v-else>
                        <AButton type="primary">Profile</AButton>
                        <AButton type="primary">Logout</AButton>
                    </div>
                </div>
            </Container>
        </ALayoutHeader>
    </ALayout>
    
</template>

<style scoped>
    .nav-container {
        display: flex;
        justify-content: space-between;
    }
    .right-content,
    .left-content  {
        display:flex;
        align-items: center;
        gap: 10px;
    }
</style>