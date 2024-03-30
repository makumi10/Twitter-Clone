<template>
    <div class="tweet-item">
        <div class="user-profile-tweet">
            <div class="tweet-item-user">
                @{{ username }}
            </div>
            <div class="tweet-trem-content">
                {{ tweet.content }}
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "TweetItem",
        
        props: {
            username: {
                type: String,
                required: true
            },
            tweet: {
                type: Object,
                required: true
            }
        }
    }
</script>

<style>
    .tweet-item{
        padding: 20px;
        background-color: white;
        border-radius: 10px;
        border: 1px solid #ddd;
        box-sizing: border-box;
        cursor: pointer;
        margin-bottom: 10px; 
    }
</style>