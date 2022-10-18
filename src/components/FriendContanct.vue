<template>
    <li>
        <h2>{{ name }} {{ isFavorite ? '(Bff)' : ''}}</h2>
        <button @click="toggleDetails">{{ detailsVisible ? 'Hide' : 'Show'}} Details</button>
        <button @click="toggleFav">Toogle Fav</button>
        <ul v-if="detailsVisible">
            <li><strong>Number: </strong>{{ phoneNumber }}</li>
            <li><strong>Email: </strong>{{ emailAddress }}</li>
        </ul>
        <button @click="deleteFriend">Delete</button>
    </li>
</template>

<script>
    export default{
    //     props: [
    //     'name',
    //     'phoneNumber',
    //     'emailAddress',
    //     'isFavorite'
    //   ],
        props: {
            id: {
                type: String,
                required: true
            },
            name: {
                type: String,
                required: true
            },
            phoneNumber: {
                type: String,
                required: true
            },
            emailAddress: {
                type: String,
                required: true
            },
            isFavorite: {
                type: Boolean,
                required: false,
                default: false,
                // validator: function(value){
                //     return value === '1' || value === '0'
                // }
            }
        },
        emits: [
            'toggle-favorite', 'delete'
        ],
        // emits: {
        //     'toggle-favorite': function(id){
        //         if(id){
        //             return true
        //         }else{
        //             console.warn('Id is missing');
        //             return false
        //         }
        //     }
        // },
        data(){
            return{
                detailsVisible: true,
                // friend:
                // {
                //     id: 'Favorite',
                //     Name: 'Favorite Nwanzi',
                //     Number: '070 4762 1107 ',
                //     Email: 'favournwanzi@gmail.com'
                // },
            }
        },
        methods:{
            toggleDetails(){
                this.detailsVisible = !this.detailsVisible
            },
            toggleFav(){
                this.$emit('toggle-favorite', this.id)
                // if(this.friendIsFavorite === '1'){
                //     this.friendIsFavorite = '0'
                // }else{
                //     this.friendIsFavorite = '1'
                // }
            },
            deleteFriend(){
                this.$emit('delete', this.id)
            }
        }
    }
</script>

