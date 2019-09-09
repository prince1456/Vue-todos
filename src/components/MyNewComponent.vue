
<template>
    <div class="ali">
        <h1>{{name}}</h1>
    </div>
</template>

<script>
export default {
 name: 'MyCustomComponent',
 props: {
     name: String
 }
}
</script>

<style>
h1 {
    font-size: 50px;
}
</style>