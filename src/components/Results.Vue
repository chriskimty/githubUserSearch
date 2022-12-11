<template>
    <div id="results">
        <div class="profileBox">
            <div class="profileImg">
                <!-- need dynamic rendering for all of these eventually -->
                <!-- placeholders for now -->
                <!-- <img :src="profilePic" alt=""> -->
                <img src="" alt="">
            </div>
            <div class="profileInfo">
                <h2>Placeholder Name</h2>
                <p>@placeholderUser</p>
                <p>Joined XX Jan 20XX</p>
            </div>
            <div class="bio">
                <p>This is a placeholder bio.</p>
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
                        <td>X</td>
                        <td>Y</td>
                        <td>Z</td>
                    </tr>
                </tbody>
            </table>
        </div>

        <div class="contact">
            <ul class="topList">
                <li>City</li>
                <li>Portfolio</li>
            </ul>
            <ul class="bottomList">
                <li>Twitter</li>
                <li>Company</li>
            </ul>
        </div>
    </div>
</template>

<script>

// export default {
//     data() {
//         return {

//         }
//     }
// }
</script>

<style>
#results h2 {
    font-size: 2.6rem;
}
</style>