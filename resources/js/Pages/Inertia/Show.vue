<script setup>
    import {Link} from '@inertiajs/vue3';
    import { Inertia } from '@inertiajs/inertia'

    defineProps({
        id : String,
        blog: Object
    })

     const deleteConfirm = (id) =>{
        Inertia.delete(`/inertia/${id}`,{
            onBefore:()=> confirm('本当に削除しますか?')
        })
     }

</script>

<template>
    showテスト<br>
    <Link href='/'>{{ id  }}</Link>
    {{ id }}<br>
    {{ blog.title }}<br>
    <button @click="deleteConfirm(blog.id)">削除</button>
</template>