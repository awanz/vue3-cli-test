<template>
    <div>
        <ul>
            <li>
            <img :src="peopleImg" height="100">
            <p>{{ index+1 }} - {{ people.name }}</p>
            <p>{{ people.genre }}</p>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    props: ['people', 'index'],
    computed: {
        peopleImg: function(){
        return require('../assets/images/' + this.people.image);
        }
    }
}
</script>

<style>
    p{
        /* color: salmon; */
        margin: 0;
    }

    li{
        list-style: none;
    }
</style>