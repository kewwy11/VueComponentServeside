<template>
    <li>
        <h2>{{ friend.Name }}</h2>
        <button @click="toggleDetails">{{ detailsVisible ? 'Hide' : 'Show'}} Details</button>
        <ul v-if="detailsVisible">
            <li><strong>Number: </strong>{{ friend.Number }}</li>
            <li><strong>Email: </strong>{{ friend.Email }}</li>
        </ul>
    </li>
</template>

<script>
    export default{
        data(){
            return{
                detailsVisible: true,
                friend:
                {
                    id: 'Favorite',
                    Name: 'Favorite Nwanzi',
                    Number: '070 4762 1107 ',
                    Email: 'favournwanzi@gmail.com'
                },
            }
        },
        methods:{
            toggleDetails(){
                this.detailsVisible = !this.detailsVisible
            }
        }
    }
</script>

