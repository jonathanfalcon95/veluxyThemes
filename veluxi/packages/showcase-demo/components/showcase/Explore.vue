<template>
  <div class="explore-wrap">
    <decoration />
    <div class="explore">
      <title-main subtitle="explore" title="14 Landing Pages Demo" align="center" />
      <v-container class="max-lg">
        <u-animate-container>
          <ul>
            <li>
              <u-animate
                name="fadeInUpShort"
                delay="0.2s"
                duration="0.3s"
              >
                <a href="/medical" target="_blank">
                  <figure>
                    <img :src="imgAPI.showcase[9]" alt="medical" />
                  </figure>
                  Medical
                </a>
              </u-animate>
            </li>
            <li>
              <u-animate
                name="fadeInUpShort"
                delay="0.3s"
                duration="0.3s"
              >
                <a href="/movie" target="_blank">
                  <figure>
                    <img :src="imgAPI.showcase[10]" alt="movie" />
                  </figure>
                  Movie Entertainment
                </a>
              </u-animate>
            </li>
            <li>
              <u-animate
                name="fadeInUpShort"
                delay="0.4s"
                duration="0.3s"
              >
                <a href="/education" target="_blank">
                  <figure>
                    <img :src="imgAPI.showcase[11]" alt="education" />
                  </figure>
                  Education
                </a>
              </u-animate>
            </li>
            <li>
              <u-animate
                name="fadeInUpShort"
                delay="0.5s"
                duration="0.3s"
              >
                <a href="/mobile-apps" target="_blank">
                  <figure>
                    <img :src="imgAPI.showcase[6]" alt="mobile apps" />
                  </figure>
                  Mobile Apps
                </a>
              </u-animate>
            </li>
            <li>
              <u-animate
                name="fadeInUpShort"
                delay="0.6s"
                duration="0.3s"
              >
                <a href="/saas" target="_blank">
                  <figure>
                    <img :src="imgAPI.showcase[8]" alt="saas" />
                  </figure>
                  SaaS
                </a>
              </u-animate>
            </li>
            <li>
              <u-animate
                name="fadeInUpShort"
                delay="0.7s"
                duration="0.3s"
              >
                <a href="/agency" target="_blank">
                  <figure>
                    <img :src="imgAPI.showcase[1]" alt="agency" />
                  </figure>
                  Corporate Agency
                </a>
              </u-animate>
            </li>
            <li>
              <u-animate
                name="fadeInUpShort"
                delay="0.8s"
                duration="0.3s"
              >
                <a href="/profile" target="_blank">
                  <figure>
                    <img :src="imgAPI.showcase[7]" alt="agency" />
                  </figure>
                  Portfolio Profile
                </a>
              </u-animate>
            </li>
            <li>
              <u-animate
                name="fadeInUpShort"
                delay="0.9s"
                duration="0.3s"
              >
                <a href="/cryptocurrency" target="_blank">
                  <figure>
                    <img :src="imgAPI.showcase[3]" alt="crypto" />
                  </figure>
                  Cryptocurrency &amp; Blockchain
                </a>
              </u-animate>
            </li>
            <li>
              <u-animate
                name="fadeInUpShort"
                delay="1s"
                duration="0.3s"
              >
                <a href="/fashion" target="_blank">
                  <figure>
                    <img :src="imgAPI.showcase[4]" alt="fashion" />
                  </figure>
                  Fashion
                </a>
              </u-animate>
            </li>
            <li>
              <u-animate
                name="fadeInUpShort"
                delay="1.1s"
                duration="0.3s"
              >
                <a href="/hosting" target="_blank">
                  <figure>
                    <img :src="imgAPI.showcase[5]" alt="hosting" />
                  </figure>
                  Cloud Hosting
                </a>
              </u-animate>
            </li>
            <li>
              <u-animate
                name="fadeInUpShort"
                delay="1.2s"
                duration="0.3s"
              >
                <a href="/architect" target="_blank">
                  <figure>
                    <img :src="imgAPI.showcase[2]" alt="architect" />
                  </figure>
                  Interior Architect
                </a>
              </u-animate>
            </li>
            <li>
              <u-animate
                name="fadeInUpShort"
                delay="1.3s"
                duration="0.3s"
              >
                <a href="/femine" target="_blank">
                  <figure>
                    <img :src="imgAPI.showcase[13]" alt="architect" />
                  </figure>
                  Portfolio 2
                </a>
              </u-animate>
            </li>
            <li>
              <u-animate
                name="fadeInUpShort"
                delay="1.4s"
                duration="0.3s"
              >
                <a href="/unisex" target="_blank">
                  <figure>
                    <img :src="imgAPI.showcase[14]" alt="architect" />
                  </figure>
                  Portfolio 3
                </a>
              </u-animate>
            </li>
            <li>
              <u-animate
                name="fadeInUpShort"
                delay="1.5s"
                duration="0.3s"
              >
                <a href="/maskulino" target="_blank">
                  <figure>
                    <img :src="imgAPI.showcase[15]" alt="architect" />
                  </figure>
                  Portfolio 4
                </a>
              </u-animate>
            </li>
            <li>
              <u-animate
                name="fadeInUpShort"
                delay="1.6s"
                duration="0.3s"
              >
                <a href="https://github.com/ilhammeidi/veluxi-starter" target="_blank">
                  <figure>
                    <img src="/images/showcase/starter.jpg" alt="starter" />
                  </figure>
                  <span>
                    TRY
                  </span>
                  &nbsp;Starter Project
                </a>
              </u-animate>
            </li>
          </ul>
        </u-animate-container>
      </v-container>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.explore-wrap {
  padding-bottom: $spacing3;
  position: relative;
  z-index: 2;
  background: linear-gradient(to bottom, rgba(255,255,255,0) 0%,rgba(255,255,255,0) 1%,rgba(251,251,251,0.91) 21%,rgba(251,251,251,1) 23%);
}
.explore {
  position: relative;
  margin-top: -80px;
  background-size: 100% auto;
  ul {
    margin: 0;
    padding: 0;
    li {
      list-style: none;
      display: inline-block;
      text-align: center;
      margin-bottom: $spacing12;
      width: 33.00%;
      height: 380px;
      @include breakpoints-down(md) {
        width: 48%;
        &:last-child {
          width: 100%
        }
      }
      @include breakpoints-down(xs) {
        width: 100%;
        margin-bottom: $spacing8
      }
      a {
        text-decoration: none;
        display: inline-block;
        font-size: 16px;
        font-weight: 500;
        color: $light-text-primary;
        transition: all 0.3s ease;
        top: 0;
        position: relative;
        span {
          color: #ff0078
        }
        &:hover {
          color: $palette-primary-main;
          top: -5px;
          figure {
            box-shadow: rgba(34, 48, 102, 0.3) -3px 6px 21.1px -4px;
          }
        }
        figure {
          margin: spacing(0, 0, 3, 0);
          overflow: hidden;
          border-radius: 6px;
          border: 0px solid #6300cc;
          transition: all 0.3s ease;
          box-shadow: rgba(34, 48, 102, 0.1) -3px 6px 21.1px -4px;
          height: 380px;
          max-width: 300px;
          @include breakpoints-down(xs) {
            width: 240px;
            height: 300px;
          }
        }
        img {
          width: 100%
        }
      }
    }
  }
}
</style>

<script>
import imgAPI from '~/static/images/imgAPI'
import Decoration from './Decoration'
import Title from './Title'

export default {
  components: {
    'title-main': Title,
    Decoration
  },
  data: () => ({
    imgAPI: imgAPI
  })
}
</script>