### Hello thanks for watching my Github 👋
### Hi there 🥰 ,I am Nilout !
import React from 'react'
import { css, ArimoBold, HitCounter } from '../lib'

export function Hello() {
  const style = css`
    #boxes-container {
      transform: rotate(${(Math.random() * 2 - 1) * 30}deg);
      transform-origin: 960px 540px;
    }
    #boxes {
      transform: translate(0, 0);
      animation: 7s boxes linear infinite;
    }
    @keyframes boxes {
      ${Math.random() < 0.5 ? 'to' : 'from'} {
        transform: translate(-512px, 0);
      }
    }
    #shake {
      animation: 11.1s shake linear infinite;
    }
    @keyframes shake {
      ${Array(512)
        .fill(null)
        .map((_, i, a) => {
          const rand = () => (Math.random() * 2 - 1) * 8
          const percentage = ((i + 1) / (a.length + 1)) * 100
          return `${percentage}% { transform: translate(${rand()}px, ${rand()}px); }`
        })
        .join('')}
    }
    #revolve {
      animation: 10s revolve ease-out;
      transform: rotateY(0deg) rotate(0deg);
      transform-origin: 960px 540px;
      animation-delay: 1s;
      animation-fill-mode: both;
    }
    @keyframes revolve {
      from {
        transform: rotateY(540deg) rotate(240deg);
      }
    }
    #zoom {
      animation: 10s zoom linear;
      transform-origin: 960px 540px;
      animation-delay: 1s;
      animation-fill-mode: both;
    }
    @keyframes zoom {
      ${Array(101)
        .fill(null)
        .map((_, i, a) => i / (a.length - 1))
        .map((t) => {
          const v = Math.pow(1 - t, 7)
          const v2 = Math.pow(1 - t, 2)
          const scale = 1 + 39 * v
          const tx = 90 * v2
          const ty = -50 * v2
          const p = t * 100
          return `${p}% { transform: scale(${scale}) translate(${tx}px, ${ty}px); }`
        })
        .join('')}
    }
    .fadeout {
      animation: 2s fadeout ease-out;
      opacity: 0;
      animation-delay: 1s;
      animation-fill-mode: both;
    }
    @keyframes fadeout {
      from {
        opacity: 1;
      }
    }
    #hits {
      animation: 1s hits linear;
      animation-fill-mode: both;
    }
    @keyframes hits {
      0% {
        opacity: 0;
      }
      10% {
        opacity: 1;
      }
      64% {
        transform: scale(1);
        animation-timing-function: ease-in;
        opacity: 1;
      }
      100% {
        transform: scale(0.001);
        opacity: 1;
      }
    }
  `
  return (
    <svg
      width="1920px"
      height="1080px"
      version="1.1"
      xmlns="http://www.w3.org/2000/svg"
      xmlnsXlink="http://www.w3.org/1999/xlink"
    >
      <style type="text/css">{style}</style>
      <defs>
        <g id="box1">
          <Box a="#353433" b="#656463" c="#8B8685" />
        </g>
        <g id="box2">
          <Box a="#353433" c="#656463" b="#8B8685" />
        </g>
      </defs>
      <rect width="100%" height="100%" fill="#353433" />
      <g id="boxes-container">
        <g id="boxes">
          <g transform="translate(-100 -210)">
            {Array(10)
              .fill(null)
              .map((_, i) => i - 2)
              .map((i) =>
                Array(20)
                  .fill(null)
                  .map((_, j) => {
                    return (
                      <g
                        transform={`translate(${j * 256 - (i % 2) * 128} ${
                          i * 220
                        })`}
                      >
                        <use
                          xlinkHref={
                            (j + ~~(i / 2)) % 2 === 0 ? '#box1' : '#box2'
                          }
                        />
                      </g>
                    )
                  })
              )}
          </g>
        </g>
      </g>
      <g id="shake">
        <g id="zoom">
          <g id="revolve">
            <g transform="translate(960 540) rotate(-14)">
              <g id="transition">
                <path
                  id="hello"
                  d={ArimoBold.getD('hello', {
                    anchor: 'center middle',
                    fontSize: 640,
                  })}
                />
                <use xlinkHref="#hello" x="-8" y="-8" fill="#d7fc70" />
                <use
                  xlinkHref="#hello"
                  x="-8"
                  y="-8"
                  fill="white"
                  className="fadeout"
                />
              </g>
            </g>
          </g>
        </g>
      </g>
      <g transform="translate(960 540)">
        <g id="hits">
          <HitCounter />
        </g>
      </g>
    </svg>
  )
}

function Box(props: { a: string; b: string; c: string }) {
  return (
    <g fill="none" fillRule="evenodd">
      <path
        d="M127.957 0l127.905 73.846c-18.876 29.11-35.763 47.966-50.66 56.567-14.897 8.601-40.645 14.36-77.245 17.28-38.622-2.887-65.41-8.646-80.364-17.28-14.954-8.633-30.801-27.49-47.541-56.567L127.957 0z"
        fill={props.c}
      />
      <path
        d="M127.957 147.692c27.272 28.552 40.907 51.603 40.907 69.152s-13.635 43.73-40.907 78.54L.052 221.539V73.846l127.905 73.846z"
        fill={props.b}
      />
      <path
        fill={props.a}
        d="M255.862 73.846v147.692l-127.905 73.847V147.692z"
      />
    </g>
  )
}

<hr></hr>



🤡_Inspired software engineer in JavaScript technologies and Flutter 👀. Professional experience with technologies included in the toolbox below.

I create applications for both the web and Android & ios, most of them using JavaScript and Java and flutter , but I also develop myself from other sides 
! 🐱‍👤

😛 Good Luck !!

<hr></hr>

🧰 Toolbox

<img src="https://github.com/devicons/devicon/blob/master/icons/javascript/javascript-original.svg" alt="Css Logo" with="50" height="50"/> <img src="https://github.com/devicons/devicon/blob/master/icons/css3/css3-original-wordmark.svg" alt="JavaScript Logo" with="50" height="50"/> <img src="https://github.com/devicons/devicon/blob/master/icons/html5/html5-original.svg" alt="Hmtl Logo" with="50" height="50"/> <img src="https://github.com/devicons/devicon/blob/master/icons/react/react-original-wordmark.svg" alt="React Logo" with="50" height="50"/><img src="https://github.com/devicons/devicon/blob/master/icons/android/android-original-wordmark.svg" alt="android Logo" with="50" height="50"/> <img src="https://github.com/devicons/devicon/blob/master/icons/java/java-original-wordmark.svg" alt="Java Logo" with="50" height="50"/><img src="https://github.com/devicons/devicon/blob/master/icons/linux/linux-original.svg" alt="Lunix Logo" with="50" height="50"/><img src="https://github.com/devicons/devicon/blob/master/icons/npm/npm-original-wordmark.svg" alt="npm Logo" with="50" height="50"/><img src="https://github.com/devicons/devicon/blob/master/icons/php/php-original.svg" alt="php Logo" with="50" height="50"/><img src="https://github.com/devicons/devicon/blob/master/icons/jquery/jquery-plain-wordmark.svg" alt="php Logo" with="50" height="50"/>
<img src="https://github.com/devicons/devicon/blob/master/icons/flutter/flutter-original.svg" alt="php Logo" with="50" height="50"/>
<img src="https://github.com/devicons/devicon/blob/master/icons/mysql/mysql-original-wordmark.svg" alt="php Logo" with="50" height="50"/>
<img src="https://github.com/devicons/devicon/blob/master/icons/dart/dart-original.svg" alt="php Logo" with="50" height="50"/>
<img src="https://github.com/devicons/devicon/blob/master/icons/c/c-original.svg" alt="php Logo" with="50" height="50"/>
<img src="https://github.com/devicons/devicon/blob/master/icons/vuejs/vuejs-original.svg" alt="php Logo" with="50" height="50"/>
<img src="https://github.com/devicons/devicon/blob/master/icons/python/python-original.svg" alt="php Logo" with="50" height="50"/>
<img src="https://github.com/devicons/devicon/blob/master/icons/arduino/arduino-original.svg" alt="php Logo" with="50" height="50"/>
<img src="https://github.com/devicons/devicon/blob/master/icons/nodejs/nodejs-original.svg" alt="php Logo" with="50" height="50"/>
<img src="https://github.com/devicons/devicon/blob/master/icons/cplusplus/cplusplus-original.svg" alt="php Logo" with="50" height="50"/>
<img src="https://github.com/devicons/devicon/blob/master/icons/csharp/csharp-original.svg" alt="php Logo" with="50" height="50"/>




<g-emoji class="g-emoji" alias="chart_with_upwards_trend" fallback-src="https://github.githubassets.com/images/icons/emoji/unicode/1f4c8.png">📈</g-emoji> My GitHub Stats

[![Top Langs](https://github-readme-stats-sigma-five.vercel.app/api/top-langs/?username=nilout56&theme=radical&layout=compact)](https://github.com/nilout56/github-readme-stats)

![Hmida GitHub stats](https://github-readme-stats-sigma-five.vercel.app/api?username=nilout56&show_icons=true&theme=radical)

[![Anurag's GitHub stats-Dark](https://github-readme-stats-sigma-five.vercel.app/api?username=nilout56&show_icons=true&theme=dark#gh-dark-mode-only)](https://github.com/anuraghazra/github-readme-stats#gh-dark-mode-only)
[![Anurag's GitHub stats-Light](https://github-readme-stats-sigma-five.vercel.app/api?username=nilout56&show_icons=true&theme=default#gh-light-mode-only)](https://github.com/nilout56/github-readme-stats#gh-light-mode-only)
---
<!--
**nilout56/nilout56** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
