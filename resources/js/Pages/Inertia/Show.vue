<script setup>
import {Inertia} from '@inertiajs/inertia'

defineProps({
    id : String,
    blog: Object
})

const deleteConfirm = id =>{
    Inertia.delete(`/inertia/${id}`,{
        onBefore:()=> confirm('本当に削除しますか？')
    })
}


</script>
<template>
    show:{{ id }}<br>
    id:{{ blog.id }}<br>
    title:{{ blog.title }}

    <button @click="deleteConfirm(blog.id)">削除ボタン</button>
</template>