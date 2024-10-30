<script setup>
import { Link } from '@inertiajs/vue3';

defineProps({
    'blogs' : Array
})

</script>
<template>
    test
    <div v-if="$page.props.flash.message" class="bg-blue-300">
        {{ $page.props.flash.message }}
    </div>
    <li v-for="blog in blogs" :key="blog.id">
        {{ blog.id }}:
        {{ blog.title }}
        <Link :href="route('inertia.show',{id:blog.id})">へ移動</Link><br>
    </li>
    
</template>