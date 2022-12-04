<!-- HINT CLASS BINDING - VUE  -->

<template>
    <div>
        <!-- I want my button to trigger Toggle View function on click -->
        <button @click="toggleView">Change View</button>
        <!-- vbind class to dynamically toggle the class -->
        <!-- I used a ternary to say, is it a grid? if yes use class Tweet Grid, if not use class Tweet List -->
        <!-- I automatically set "isGrid" to false below in the data section -->
        <section :class="isGrid ? 'tweetGrid' : 'tweetList'">
            <!-- I know there's a lot of divs and sections, but I got it to work this way with setting the dynamic class on a separate Element -->
            <!-- so that's why I used a static class (I chose to keep the name as 'static') because I want it to always set that styling no matter the conditional class) -->
            <div class="static" v-for="tweet in this.tweets" :key="tweet.index">
                <!-- using a for-in loop with the mustache variables of my data written below -->
            <h4>{{tweet.user}}</h4>
            <p>{{tweet.tweet}}</p>
            <img :src="tweet.img">
            <p>Created: {{tweet.date}}</p>
            </div>
        </section>
    </div>
</template>

<script>
    export default {
        name : 'TweetData',
        data() {
            return {
                tweets : [
                    {
                        tweet: "Me the further away we move from Halloween and the closer we get to the holidays",
                        img: "https://pbs.twimg.com/media/FjEeWDWX0AITIKZ?format=jpg&name=medium",
                        user: "@_LaurenLaVera_",
                        date: "Dec 03",
                    },
                    {
                        tweet: "armless frog and break-dancing rat, netherlands, ca. 1500",
                        img: "https://pbs.twimg.com/media/FjA7gdtXkAI5oFx?format=jpg&name=medium",
                        user: "@WeirdMedieval",
                        date: "Dec 02",
                    },
                    {
                        tweet: "THE SHINING (1980) recreated in Lego. The detail is incredible. Can't find who made these so please credit if you know. A thread... 1/10 The Colorado Lounge",
                        img: "https://pbs.twimg.com/media/Fie9eriXoAATmgc?format=jpg&name=large",
                        user: "@ATRightMovies",
                        date: "Nov 26",
                    },
                    {
                        tweet: "Cut the line.",
                        img: "https://pbs.twimg.com/media/FjCaR44XgAEOtik?format=jpg&name=medium",
                        user: "@Sentinelcreativ",
                        date: "Dec 03",
                    },
                ],
                // setting isList to true so when you land on the page it starts off as a list until the button is clicked
                isGrid : false,
            }
        },
        methods: {
            toggleView() {
                this.isGrid = !this.isGrid;
            },
        },
    }
</script>

<style scoped>
button{
    color: white;
    font-size: 12pt;
    border: none;
    border-radius: 5px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
    background-color: orchid;
    padding: 10px;
    margin: 25px;
}
img{
    height: 15vh;
    border-radius: 5px;
}
.static{
    background-color: white;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
    border: 2px solid hotpink;
    border-radius: 5px;
    padding: 20px;
    margin: 10px;
}
.tweetList{
    width: 25%;
    position: relative;
    left: 50%;
    transform: translateX(-50%);
}
.tweetGrid{
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr;
}
</style>