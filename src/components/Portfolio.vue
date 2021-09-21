<template>
        <div  class="container-fluid px-0">
                <article class="main-image">
                        <section>
                                <h1>Welcome to My Portfolio</h1>
                                <span class="top-span">A Free Portfolio with Vue Js</span>
                                <button class="btn btn-xl btn-light" @click="scrollTo('find-more')">Find Out More...</button>
                        </section>

                </article>

                <article id="find-more" class="white-section">
                        <section>
                                <h3>Stylish Portfolio is the perfect theme for your next project !</h3>
                                <span class="md-span">Lorem ipsum dolor sit amet, conseteru sadipscing elitr</span>
                                <button class="btn btn-xl btn-dark" @click="scrollTo('offers')">What we offers for you</button>
                        </section>
                </article>

                  <article id="offers" class="blue-section">
                        <section class="container">
                                <h2 class="bsh2">What we Offer</h2>
                                <div class="row">
                                        <div class="col-lg-3 col-md-6 mb-5 mb-lg-0" v-for="(offer, index) in offers" :key="index">
                                          <div class="icon mx-auto"><i class="fas" :class="offer.icon"></i> </div>
                                          <h4>{{ offer.title }}</h4>
                                          <span>{{ offer.description }}</span>
                                        </div>

                                </div>
                        </section>
                </article>

                <article class="second-image">
                        <section> 
                                <h2 class="sih2">welcom to <i>your</i> next website !</h2>
                                <button class="btn btn-xl btn-dark" @click="scrollTo('recent-projects')">Recent Projects </button>
                        </section>article {
        display: flex;
        justify-content: center;
        align-items: center;
        width: 100%;
        padding: 0 10px;

} 
                </article>

                 <article id="recent-projects" class="white-section">
                        <section class="container"> 
                                <h3 class="wsh3">Recent Projects</h3>
                                <div class="row no-gutters">
                                        <div class="col-lg-6" v-for="(project, index) in recentProjects" :key="index">
                                                <a href="" class="portfolio=item">
                                                        <span class="caption">
                                                                <span class="caption-content">
                                                                        <h2>{{ project.title }}</h2>
                                                                        <p class="mb-0">{{ project.description }}</p>
                                                                </span>
                                                        </span>
                                                        <img class="img-fluid" :src="require('../assets/' +project.img)" alt="">
                                                </a>
                                        </div>
                                </div>
                                
                        </section> 
                </article>

                <article class="blue-section">
                        <section class="container">
                                <h2 class="bsh2"> Have a nice Day</h2>
                                <button class="btn btn-xl btn-light mr-4" @click="scrollTo('app')">Click Me ! </button>
                                <button class="btn btn-xl btn-dark" @click="scrollTo('app')">Look at Me ! </button>
                                
                        </section>
                </article>

        </div>
</template>

<script>
export default {
        name: 'Portfolio',
        data: () => {
                return{
                        offers: [
                                {
                                        icon: 'fa-mobile',
                                        title: 'Responsive',
                                        description: 'Looks greate on any screen size'
                                },
                                {
                                        icon: 'fa-pencil-alt',
                                        title: 'Redesigned',
                                        description: 'Freshly redesigned for Vue Js'
                                },
                                {
                                        icon: 'fa-thumbs-up',
                                        title: 'Favorited',
                                        description: 'Millons of users like us'
                                },
                                {
                                        icon: 'fa-question-circle',
                                        title: 'Questions?',
                                        description: 'We Answer all your questions'
                                }
                        ],
                        recentProjects: [
                                {
                                        img: 'gallery01.jpg',
                                        title: 'Stationary',
                                        description: 'Lorem ipsum dolor sit amet, conseteru sadipscing elitr'
                                },
                                {
                                        img: 'gallery02.jpg',
                                        title: 'Ice Cream',
                                        description: 'Lorem ipsum dolor sit amet, conseteru sadipscing elitr'
                                },
                                {
                                        img: 'gallery03.jpg',
                                        title: 'Strawberries',
                                        description: 'Lorem ipsum dolor sit amet, conseteru sadipscing elitr'
                                },
                                {
                                        img: 'gallery04.png',
                                        title: 'Workshop',
                                        description: 'Lorem ipsum dolor sit amet, conseteru sadipscing elitr'
                                },
                        ]
                }
        },
        methods: {
                scrollTo(element) {
                        const el = document.querySelector('#' +element);
                        el.scrollIntoView({
                                behavior: 'smooth',
                                block: 'start'
                        });
                }
        }
}
</script>

<style Lang="scss">
  @import url('https://use.fontawesome.com/releases/v5.8.1/css/all.css');
  @import url('https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css');

article {
        display: flex;
        justify-content: center;
        align-items: center;
        width: 100%;
        padding: 0 10px;

}

.btn-xl {
        padding: 20px 35px;
        font-family: serif;
        font-size: 1.25rem;
}
h1 {
     font-size: 5rem;
     font-weight: bold;
     color: white;
     margin-bottom: 30px;
}
.sih2 {
         font-size: 5rem;
         font-weight: bold;
         margin-bottom: 30px;

}
.top-span {
        display: block;
        padding-bottom: 30px;
        font-size: 1.6rem;
        font-weight: bold;
        color: gray;;
}

.main-image, .second-image{
        min-height: 100vh;
        background-size: cover;
        padding: 0 10px;
        text-align: center;
}


.main-image {
        background: url('../assets/image02.jpeg') center center;
}
.second-image {
        background: url('../assets/image06.jpeg') center center;
      
}
.white-section{
        padding: 120px 10px;
        background: #fff;
        text-align: center;
}

 h3 {
        font-size: 2rem;
        font-weight: bold;
}
        
 .md-span {
        display: block;
        padding-bottom: 30px;
        font-size: 1.6rem;
       
      
}
.row {
        padding-top: 50px;
}
.portfolio-item {
        display: block;
        position: relative;
        overflow: hidden;
}
.caption{
        display: flex;
        height: 100%;
        width: 100%;
        position: absolute;
        top:0 ;
        bottom: 0;
        z-index: 1;
        /* background-color: rgba(color: #000000, $alpha: .2); */
}
.caption-content {
        text-align: left;
        color: black;
        margin: auto 2rem 2rem;
        font-weight: bold;
}

.img-fluid{
        transform: scale(.9);
        transition: transform .2s linear;

}


.blue-section {
        padding: 120px 1px;
        background-color: #1d809f;
        color: #fff;
        text-align: center;
}
 .bsh2 {
                font-size: 3rem;
                font-weight: bold;
                margin-bottom: 50px;

        }
h4{
        font-size: 1.6rem;
        padding-top: 20px;
}

.icon {
        display: flex;
        justify-content: center;
        align-items: center;
        width: 120px;
        height: 120px;
        background-color: #fff;
        color:#1d809f;
        border-radius: 50%;
}
.fas {
        font-size: 2rem;
}


</style>