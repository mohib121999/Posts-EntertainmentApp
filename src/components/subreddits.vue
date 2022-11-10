<template>
<div class="subreddits container">
    <h2>{{category | capitalize}}</h2>
    <ul class="item-list">
        <li v-for="post in subreddits">
        <subreddit :item="post"></subreddit>
        </li>
    </ul>
</div>
</template>

<script>
import subreddit from './subreddit.vue';
    export default{
        name: 'subreddits',
        props:['category'],
        data() {
            return {
                subreddits:[
                ]
            }
        },
        components:{
            subreddit
        },
        filters:{
            capitalize:function(value){
                if(!value)return'';
                value=value.toString();
                return value.charAt(0).toUpperCase()+value.slice(1);
            }
        },
        created : function() {
            this.$http.get('https://www.reddit.com/r/'+this.category+'/top.json?limit=5').then((Response)=>{
                this.subreddits=Response.data.data.children;
            });
        },
    }

</script>
<style scoped>
    .container{
        max-width: 600px;
        margin: 30px auto;
        background: #ffffff;
        box-shadow: 0 0 3px #cccccc;

    }
    .subreddits{
        min-width: 400px;
        padding: 25px 45px;

    }
    .subreddits h2{
        font-size: 20px;
        margin-bottom: 10px;
        margin-top: 0;

    }
    .subreddits .item-list{
        border-top: 5px solid #cccccc;
        padding-top: 20px;
        list-style: none;
    }
    .subreddits .item-list li {
        margin-bottom: 20px;
    }


</style>