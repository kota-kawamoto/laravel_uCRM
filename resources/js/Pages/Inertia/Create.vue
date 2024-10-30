<script setup>
import {reactive} from 'vue'
import {Inertia} from '@inertiajs/inertia'


defineProps({
    errors:Object
})

const form = reactive({
    title:null,
    content:null
})

const submitFunction = () =>{
    Inertia.post('/inertia/store',form)
}

</script>

<template>
    <form @submit.prevent="submitFunction">
        title:<input type="text" name="newTitle" v-model="form.title"><br>
        <div v-if="errors.title">{{ errors.title }}</div>

        content:<input type="text" name="newContent" v-model="form.content"><br>
        <div v-if="errors.content">{{ errors.content }}</div>
        <button>送信</button>
    </form>
</template>