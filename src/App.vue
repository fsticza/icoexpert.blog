<template>
  <div id="app">
    <div class="container">
      <div class="row">
        <aside class="col-md-5">
          <div class="section">
            <div class="row">
              <div class="col-md-10 offset-md-1">
                
                <img class="logo" src="./assets/img/logo.svg" alt="Matyas Zaborszky" height="14">
                
                <div class="mb-3 mt-5">
                  <img class="img-fluid" src="./assets/img/matyas-nyers.jpg" />
                </div>
                <h1 class="mt-4 mb-3">
                  Mátyás Záborszky
                </h1>
                <p class="font-weight-bold">
                    I have worked as a marketing and PR expert for over 15 years, consulting in over 20
                  countries for companies such as BMW, Lufthansa, LG and Samsung. Later I worked with several
                  high-profile crypto organizations, such as Bitcoinist and Bitcoin.com, and established my simple
                  method for all but guaranteed success in the industry’s first go-to-market handbook: 
                  <a class="inline-link" href="http://www.6steps.online/" target="_blank">“6 Proven Steps to Attract ICO Investors.”</a>
                  I also founded <a class="inline-link" href="https://6slambo.com/" target="_blank">6S•LAMBO</a> 
                  to provide a hassle-free, end to end integrated solution, using the 6-step methodology to connect 
                  ICOs and STOs with their audience, build their trust and turn them into investors.
                </p>

                <p>
                  I post regular opinion pieces on crypto investments on 
                  <a class="inline-link" href="https://medium.com/@matyaszaborszky" target="_blank">my blog</a> and social media
                  channels, frequently present at crypto and blockchain conferences, and am also a mentor,
                  investor, entrepreneur, university lecturer and PGA enthusiast.
                </p>

                <p>
                  My other interests include self improvement and business excellence. I am an avid
                  follower of the Silva Method and have been publishing meditations, positive affirmations and
                  other related material for years as a hobby. It’s fun and could really help you grow as a person
                  and an entrepreneur. <a class="inline-link" href="">See for yourself!</a>
                </p>
                <follow-me />

              </div>
            </div>


          </div>
        </aside>
        <main class="col-md-7">
          <div class="section section--posts">
            <div class="row">
              <div class="col-md-10 offset-md-1">
                <blog-posts />
              </div>
            </div>
          </div>
        </main>
      </div>
    </div>
    
    <link-section />

    <article id="contact" class="section section--gray">
      <contact-section />
    </article>
    <footer-section />
  </div>
</template>

<script>

import FollowMe from '@/components/FollowMe'
import BlogPosts from '@/components/BlogPosts'
import ContactSection from '@/components/ContactSection'
import LinkSection from '@/components/LinkSection'
import FooterSection from '@/components/FooterSection'

export default {
  name: 'app',
  components: {
    FollowMe,
    BlogPosts,
    ContactSection,
    LinkSection,
    FooterSection
  }
}
</script>

<style lang="scss">
@import "./assets/scss/app";

a:hover {
  background: $pink;
}

body {
  overflow-x: hidden;
  @include media-breakpoint-up(md) {
    background: linear-gradient(to right, #fff, #fff 58.33333%, $light-gray 58.33333%, $light-gray 100%) repeat-y;
  }
}

@include media-breakpoint-up(lg) {
  .section--posts {
    margin-top: 4.125rem;
  }

  .logo {
     height: 18px;
   }
}

.section {
  position: relative;
  padding-top: 4rem;
  padding-bottom: $section-spacing;

  .fingerprint {
    position: absolute;
    z-index: 0;
  }
}

main {
  background: $light-gray;
}
.section__title {
  font-size: 1rem;
  font-weight: 300;
  color: $gray;
  font-family: $font-family-base;
  text-transform: uppercase;
  margin-bottom: 1.5rem;
}
.section__sub-title {
  font-family: $font-family-base;
  font-size: 1rem;
  margin: 1.5rem 0;
  @include media-breakpoint-up(md) {
    font-size: 1.25rem;
  }
  @include media-breakpoint-up(lg) {
    font-size: 1.5rem;
  }
}
.section__lead {
  font-size: 2.5rem;
  margin: 1.5rem 0;

  @include media-breakpoint-up(md) {
    font-size: 3rem;
  }
  @include media-breakpoint-up(lg) {
    font-size: 3.5rem;
  }
}
.section__sub-lead {
  font-size: 1rem;
  margin: 2rem 0;
  @include media-breakpoint-up(md) {
    font-size: 1.25rem;
  }
  @include media-breakpoint-up(lg) {
    font-size: 1.5rem;
  }
}

.section--gray {
  background: $light-gray;
}

.shaded {
  box-shadow: 20px 20px 0 rgba(0, 0 , 0, .05)
}
.inline-link {
  display: inline-block;
  font-weight: bold;
  padding-left: 3px;
  padding-right: 3px;
  margin-left: -3px;
  margin-right: -3px;
}

.copyright {
  background: $dark-green;
  padding: 1.5rem 0;
}

.fade {
  will-change: opacity;
}

.nav-link {
  &:hover {
    background: transparent;
  }
}
.contact-btn-position {
  position:relative;
  top: $section-spacing + $input-btn-padding-y + 0.615rem;
}

.btn {
  text-transform: uppercase;
}

.btn-primary,
.btn-light {
  transition: background-color .3s, color .3s;
  position: relative;
  z-index: 1;

  &:before {
    content: '';
    position: absolute;
    opacity: 0;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    border: 2px solid $primary;
    z-index: -1;
    border-radius: inherit;
    transform: scale3d(0.6, 0.6, 1);
    transition: transform 0.3s, opacity 0.3s;
    transition-timing-function: cubic-bezier(0.75, 0, 0.125, 1);
  }

  &:hover {
    background-color: #fff;
    color: $primary;

    &:before {
      transform: scale3d(1, 1, 1);
      opacity: 1;
    }
  }
}
.btn-light {
  &:before {
    border-color: #fff;
  }
  &:hover {
    background-color: $primary;
    color: #fff;
  }
}

</style>