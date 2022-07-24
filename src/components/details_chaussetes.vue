<template>
    <div class="det">
            <p v-for="detail in details" :key="detail.id">
                {{detail}}
            </p>
    </div>
</template>

<script>
export default {
    name:'details_chaussetes',
    props:{
        details:Array
    }
}
</script>