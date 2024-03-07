<template>
<footer id="contact">
        <section style="background-color: var(--primary-color-black);">
            <div class="body-say-bg reveal">
                <div class="flex-box footer-layout">
                    <div class="half-screen">
                        <h1 class="footer-title">News Letter Sign Up</h1>
                    </div>
                    <div class="half-screen pos-relative">
                        <div class="footer-form-container">
                            <div class="footer-form" style="padding: 48px; background: #FF564F;">
                                <form action="#">
                                    <p>GET IN TOUCH</p>
                                    <input type="text" placeholder="Your email" required>
                                    <button class="btn-sub">SUBSCRIBE</button>
                                </form>
                            </div>
                        </div>
                    </div>
                </div>
                <hr style="margin: 87px 0 73px 0; border-color: white;">
                <div class="footer-menu-content">
                    <div class="footer-menu-contrainer">
                        <div class="footer-menu footer-menu-title">
                            <h3>Agency</h3>
                            <ul>
                                <li>Agency © 2019.</li>
                                <li>All Rights Reserved.</li>
                            </ul>
                        </div>
                        <div class="footer-menu">
                            <h3>Address</h3>
                            <ul>
                                <li class="text-bg-black">3899 Fusce Rd. Frederick </li>
                                <li class="text-bg-black">Nebraska 20620</li>
                                <li class="footer-text-spacing"><a href="mailto:info@agency.com">info@agency.com</a>
                                </li>
                                <li class="footer-text-spacing"><a href="tel:+12345678900">+1 (234) 567-89-00</a></li>
                            </ul>
                        </div>
                        <div class="footer-menu">
                            <h3>Menu</h3>
                            <ul>
                                <li>About</li>
                                <li>Portfolio</li>
                                <li>Blog</li>
                                <li>Testimonials</li>
                                <li>Contact</li>
                            </ul>
                        </div>
                    </div>
                    <div class="footer-logo">
                        <img src="../assets/images/FacebookLogo.svg" alt="image">
                        <img src="../assets/images/TwitterLogo.svg" alt="image">
                        <img src="../assets/images/InstagramLogo.svg" alt="image">
                    </div>
                </div>
            </div>
        </section>
    </footer>
</template>

<script setup>

</script>

<style>
.footer-form-container {
    position: absolute;
    top: -70px;
}


.footer-form {
    display: grid;
    width: 500px;
}

.footer-form form {
    display: grid;
    gap: 25px;
}

.footer-form p {
    margin: 0;
    font-weight: 400;
    font-size: 16px;
    line-height: 32px;
    letter-spacing: 3px;
    color: white;
    text-transform: uppercase;
}

.footer-form input {
    height: 48px;
    font-family: var(--font-DM);
    font-weight: 400;
    font-size: 16px;
    line-height: 23px;
    width: 100%;
    padding: 0 20px;
}

.btn-sub {
    background-color: #ff635c;
    color: white;
    height: 48px;
    font-weight: 700;
    letter-spacing: 1px;
    font-size: 16px;
    line-height: 18.75px;
    width: 100%;
}

.footer-title {
    font-family: var(--font-inknut);
    font-size: 40px;
    font-weight: 900;
    line-height: 48px;
    letter-spacing: 0px;
    margin: 0;
    text-transform: uppercase;
    width: 70%;
}

.footer-menu-content {
    display: flex;
    justify-content: space-between;
    margin-top: 182px;
}

.footer-menu-contrainer {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    color: white;
    gap: 100px
}

.footer-menu h3 {
    text-transform: uppercase;
    font-size: 16px;
    font-weight: 400;
    line-height: 32px;
    letter-spacing: 3px;
}

.footer-menu-title h3 {
    text-transform: uppercase;
    font-size: 24px;
    font-weight: 700;
    line-height: 32px;
    letter-spacing: 0px;
    margin: 16px 0 16px 0;
}




.footer-menu ul {
    list-style-type: none;
    padding: 0;
    line-height: 32px;
    font-size: 16px;
    font-weight: 400;
    margin-top: 35px;
}

.footer-menu li {
    font-family: var(--font-DM) !important;
}

.footer-text-spacing {
    margin: 16px 0 16px 0;
}

.footer-text-spacing a {
    color: white;
}

.footer-logo {
    display: grid;
    gap: 8px;
    grid-template-columns: repeat(3, 1fr);
    cursor: pointer;
}
</style>