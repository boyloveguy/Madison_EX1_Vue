<template>
    <section>
        <div class="body-post-bg reveal">
            <div class="flex-box body-post-layout">
                <div class="half-screen">
                    <h1 class="body-projects-title">OUR LATEST BLOG POSTS</h1>
                </div>
                <div class="half-screen">
                    <p style="margin-left: 15px;" class="body-projects-description">Minuteness of the parts formed a
                        Minuteness of the parts formed a great hindrance to my speed, resolved, contrary to my first
                        intention, to make the being. Minuteness of the parts formed a great hindrance to my speed,
                        resolved, contrary to my first intention, to make the being.</p>
                </div>
            </div>
            <div class="body-post-container-card">
                <div class="body-post-card">
                    <div class="body-post-card-container">
                        <img src="../assets/images/post1.png" alt="image">
                        <p>DESIGN</p>
                        <h2>Truly it was a great journey
                            and in it I met with many</h2>
                        <span>14 November, 2019</span>
                    </div>
                </div>
                <div class="body-post-card">
                    <div class="body-post-card-container">
                        <img src="../assets/images/post2.png" alt="image">
                        <p>TECH</p>
                        <h2>What looked like a small
                            patch of purple grass</h2>
                        <span>14 November, 2019</span>
                    </div>
                </div>
                <div class="body-post-card">
                    <div class="body-post-card-container">
                        <img src="../assets/images/post3.png" alt="image">
                        <p>LIFE </p>
                        <h2>The roots were revolving
                            small plant</h2>
                        <span>14 November, 2019</span>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>

</script>

<style>
    .body-post-bg {
    padding-top: 103px;
    padding-bottom: 150px;
}

.body-post-container-card {
    display: grid;
    gap: 30px;
    grid-template-columns: repeat(3, 32%);
}

.body-post-card {
    display: flex;
    flex-direction: column;
}

.body-post-card img {
    margin-top: 87px;
    max-width: 370px;
}

.body-post-card p {
    font-weight: 400;
    font-size: 16px;
    line-height: 32px;
    letter-spacing: 3px;
    margin-bottom: 0;
    margin-top: 27px;
}

.body-post-card h2 {
    font-size: 24px;
    font-weight: 700;
    line-height: 32px;
    letter-spacing: 0px;
    text-transform: uppercase;
}
</style>