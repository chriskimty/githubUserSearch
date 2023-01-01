<template>
    <div id="results">
        <div class="profileBox">
            <div class="profileImg">
                <img :src="profilePic" alt="selected user's profile picture">
            </div>
            <div class="profileInfo">
                <h2 v-if="info.name === null">No Name</h2>
                <h2 v-else>{{ info.name }}</h2>
                <p>@{{ info.login }}</p>
                <p>{{ formatDate(info.created_at) }}</p>
            </div>
            <div class="bio">
                <p v-if="info.bio === null">This profile has no bio</p>
                <p v-else>{{ info.bio }}</p>
            </div>
        </div>

        <div class="stats">
            <table>
                <thead>
                    <tr>
                        <th>Repos</th>
                        <th>Followers</th>
                        <th>Following</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>{{ info.public_repos }}</td>
                        <td>{{ info.followers }}</td>
                        <td>{{ info.following }}</td>
                    </tr>
                </tbody>
            </table>
        </div>

        <div class="contact">
            <ul class="topList">
                <div class="listBox">
                    <img :src="location" alt="location icon">
                    <li v-if="info.location === null" class="noData">{{notAvail}}</li>
                    <li v-else>{{ info.location }}</li>
                </div>
                <div class="listBox">
                    <img :src="website" alt="website icon">
                    <li v-if='info.blog === "" ' class="noData">{{notAvail}} </li>
                    <li v-else>{{ info.blog }}</li>
                </div>
                
            </ul>
            <ul class="bottomList">
                <div class="listBox">
                    <img :src="twitter" alt="twitter icon">
                    <li v-if="info.twitter_username === null" class="noData">{{notAvail}}</li>
                    <li v-else>{{ info.twitter_username }}</li>
                </div>
                
                <div class="listBox">
                    <img :src="company" alt="company icon">
                    <li v-if="info.company === null" class="noData">{{notAvail}}</li>
                    <li v-else>{{ info.company }}</li>
                </div>
            </ul>
        </div>
    </div>
</template>

<script>
    import location from '../assets/icon-location.svg'
    import twitter from  '../assets/icon-twitter.svg'
    import website from '../assets/icon-website.svg'
    import company from '../assets/icon-company.svg'
    import dayjs from 'dayjs'
    export default {
        name: 'Results',
        props: [ 'info' ],
        data(){
            return {
                location,
                twitter, 
                website, 
                company,
                notAvail: 'Not available' 
            }
        },
        computed: {
            profilePic(){
                return this.info.avatar_url
            },
        },
        methods: {
            formatDate(string){
                const date = dayjs(string)
                return date.format('DD MMM YYYY')
            }
        }
    }
</script>