<template>
    <div>
        <Nav />
        <section class="banner">
            <div class="banner-description">
                <h1 class="title"> <span class="bold">We are Here to </span> transform <br> <span class="bold">your
                        Life</span></h1>
                <p>Shape Your Success: Tailored Career Counseling for a Brighter Tomorrow Find Your Path with <br>
                    Professional Career Counseling – Start Today</p>
                <router-link to="" class="btn book">Book Online Session</router-link>
                <router-link to="" class="btn services">Our Services</router-link>
            </div>
            <img class="slider" src="/slides-1.jpg" alt="slide">
        </section>
        <section class="about">
            <h1 class="about__title center__text"> About <span class="us">US</span> </h1>

            <p class="about__desc">
                We specialize in organizing and holding seminars, conferences and other <br> public speakings and events
                offering motivation lectures.
            </p>

            <div class="feature-section">
                <div class="image-container">
                    <img class="team_work" src="/about.jpg" alt="Teamwork" />
                </div>
                <div class="features-container">
                    <div class="feature-item" v-for="(feature, index) in features" :key="index">
                        <div class="icon">
                            <img :src="feature.icon" :alt="feature.title" />
                        </div>
                        <div class="text">
                            <h3 class="title">{{ feature.title }}</h3>
                            <p>{{ feature.description }}</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        <div class="stats-section">
            <div class="stats-container">
                <div class="stat-item" v-for="(stat, index) in stats" :key="index">
                    <div class="icon">
                        <img :src="stat.icon" :alt="stat.title" />
                    </div>
                    <div class="text">
                        <h2>{{ displayNumbers[index] }}</h2>
                        <p class="stats">{{ stat.title }}</p>
                    </div>
                </div>
            </div>
        </div>
        <section class="chooseus">
            <h1 class="about__title center__text"> Why Choose <span class="us">US</span> </h1>
            <h2 class="secondary_title">Your partner for career success</h2>
            <div class="choose__cards">
                <img class="choose_img" src="/twoheads.jpg" alt="discuss">
                <div>
                <div class="choose_card">
                    <h4 class="choose_title">1/ Comprehensive Career <br> Assessment</h4>
                    <p class="choose_desc">
                        We conduct a thorough career assessment to identify your strengths, interests, and goals,
                        helping you make informed career decisions.
                    </p>
                </div>
                <div class="choose_card">
                    <h4 class="choose_title">2/ Educational <br> Guidance</h4>
                    <p class="choose_desc">
                        We provide expert guidance on educational choices, helping you choose the right educational path
                        to achieve your career goals.
                    </p>
                </div>
                <div class="choose_card">
                    <h4 class="choose_title">3/ Professional <br> Development</h4>
                    <p class="choose_desc">
                        We provide customized professional development plans to help you enhance your skills and achieve your career objectives.
                    </p>
                </div>

                <div class="choose_card">
                    <h4 class="choose_title">4/ Your Career <br> Partner
                    </h4>
                    <p class="choose_desc">
                        We work closely with you to understand your unique needs and develop customized strategies for career success.
                    </p>
                </div>
            </div>
            </div>
        </section>
        <section>
            <Testimonal/>
        </section>
        <Footer/>
    </div>
</template>


<script>
import Nav from "./Nav.vue";
import Testimonal from './Testimonal.vue';
import Footer from './Footer.vue';

import { ref, onMounted } from 'vue';

export default {
    components: {
        Nav,
        Testimonal,
        Footer
    },
    setup() {
        const displayNumbers = ref([0, 0, 0, 0]);
        const stats = [
            {
                title: "Workers",
                number: 967,
                icon: "/office-worker.png",
            },
            {
                title: "Types of Jobs",
                number: 1276,
                icon: "/job.png",
            },
            {
                title: "Projects",
                number: 396,
                icon: "/project.png",
            },
            {
                title: "Happy Customers",
                number: 177,
                icon: "/customer-service.png",
            },
        ];

        const startCounters = () => {
            stats.forEach((stat, index) => {
                animateValue(index, 0, stat.number, 2000); // 2000ms duration
            });
        };

        const animateValue = (index, start, end, duration) => {
            const range = end - start;
            const stepTime = Math.abs(Math.floor(duration / range));
            let current = start;
            const increment = end > start ? 1 : -1;

            const timer = setInterval(() => {
                current += increment;
                displayNumbers.value[index] = current;
                if (current === end) {
                    clearInterval(timer);
                }
            }, stepTime);
        };

        onMounted(() => {
            startCounters();
        });

        return {
            features: [
                {
                    title: "Always Available",
                    description: "You can contact us anytime and we will resolve your issues as soon as possible.",
                    icon: "/24.png",
                },
                {
                    title: "Fair Prices",
                    description: "We stand for fair and affordable pricing policy and we have very beneficial regular discounts.",
                    icon: "/tag.png",
                },
                {
                    title: "Best Offers",
                    description: "Our programs are developed in such a way, so any person could find his own package.",
                    icon: "/best-offer.png",
                },
                {
                    title: "Qualified Agents",
                    description: "We are proud of our dedicated and experienced team who work to meet your needs.",
                    icon: "/support.png",
                },
            ],
            stats,
            displayNumbers,
        };
    },
};
</script>

<style lang="scss" scoped>
.banner {
    text-align: center;


}

.services {
    background: #FF033D;
    margin-left: 1rem;

    &:hover {
        background: #221D48;
    }
}

.us {
    color: #FF033D;
}

.title {
    font-size: 1.5rem;
    color: #221D48;

}

.bold {
    font-weight: bold;
}

.btn {
    display: inline-block;
    color: #FFFFFF;
    padding: .8rem;
    margin-top: 1rem;
}

.banner-description {
    padding: 1rem;
}

.stats {
    color: #FFFFFF;
}

.book {
    background: #221D48;

    &:hover {
        background: #FF033D;
    }
}

.slider {
    margin-top: 1rem;
}

.about__title {
    font-size: 2.0625;
    padding-top: 2rem;
}

.about__desc {
    text-align: center;
}

.title {
    font-weight: bold;
}

.secondary_title {
    padding-left: .5rem;
}

.image-container {
    flex: 1;
    padding: 20px;
}

.image-container img {
    width: 100%;
    border-radius: 10px;
}

.features-container {
    flex: 1;
    display: flex;
    flex-direction: column;
    gap: 20px;
}

.feature-item {
    display: flex;
    align-items: center;
    gap: 10px;
    padding: 1rem;
}

.icon img {
    width: 50px;
    height: 40px;
}

.text h3 {
    margin: 0;
    font-size: 1.2em;
}

.text {
    margin: 5px 0 0;
    font-size: 0.9em;
    color: #666;
}


.stats-section {
    background: linear-gradient(to right, #236088, #28435f, #2c3e50);
    padding: 50px 0;
    color: #fff;


}

.stats-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
    align-items: center;
    max-width: 1200px;
    margin: 0 auto;

}

.stat-item {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    padding: 20px;
    flex: 1;
    min-width: 200px;
}

.icon img {
    width: 60px;
    height: 60px;
    margin-bottom: 15px;
}

.text h2 {
    margin: 0;
    font-size: 2em;
    color: #FF033D;
}

.text p {
    margin: 5px 0 0;
    font-size: 1em;

}

.choose_title {
    background: #1f252f;
    color: #FFFF;
    text-align: center;
    width: 50%;
    margin-left: 1rem;
}

.choose_desc {
    padding: 1rem;
    width: 80%;
}

@media(min-width:64rem) {
    .feature-section {
        display: flex;
        align-items: center;
        justify-content: space-between;
    }

    .banner {
        display: grid;
        grid-template-columns: 2fr 1fr;
    }

    .title {
        font-size: 4.0625rem;
    }

    .banner-description {
        margin-top: 8rem;
    }

    .slider {
        padding: 0;
        margin-top: 0;
    }

    .team_work {
        height: 400px;
        width: 35rem;
    }

    .feature-section {
        width: 80%;
        margin: 2rem auto;

    }
    .choose__cards{
        display: grid;
        grid-template-columns: 1fr 1fr ;
        width: 80%;
        margin: 0 auto;
    }

    .secondary_title{
        padding-left: 11.5rem;
        padding-bottom: .5rem;
    }

    .choose_img{
        height: 700px;
    }

}
</style>