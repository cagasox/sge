<script setup lang="ts">
const {signOut} = useAuth();

definePageMeta({
    middleware:'auth'
})

const submitLogout = ()=> {
    console.log("try to login whith credentials below:");
        signOut({redirect:false}).then(()=>{
                console.log("successefully logout!")
                navigateTo('/');
            })
            
        .catch((error)=>{
            console.log("error when trying to login", error)
        })
}
</script>

<template>
    <div>
        <h1> Minha Tela Home!!</h1>
        <button @click="submitLogout" class=""customButton>Sair</button>
    </div>
</template>

<style lang="scss">

</style>