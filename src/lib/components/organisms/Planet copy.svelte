


    <div id="universe">
      <div id="galaxy">
        <div class="circle" />
        <div class="circle2" />
        <div class="circle3" />
        <div id="orbit0">
          <div id="pos0">
            <div id="dot0" />
          </div>
        </div>
        <div id="orbit1">
          <div id="pos1">
            <div id="dot1" />
          </div>
        </div>
        <div id="orbit2">
          <div id="pos2">
            <div id="dot2" />
          </div>
        </div>
      </div>
    </div>


<style>

  #orbit0 {
    animation-delay: 0s;
  }
  #pos0 {
    animation-delay: 0s;
  }
  #dot0 {
    animation-delay: 0s;
  }
  #orbit1 {
    animation-delay: -1s;
  }
  #pos1 {
    animation-delay: -1s;
  }
  #dot1 {
    animation-delay: -1s;
  }
  #orbit2 {
    animation-delay: -2s;
  }
  #pos2 {
    animation-delay: -2s;
  }
  #dot2 {
    animation-delay: -2s;
  }

  .circle, .circle2, .circle3, .orbit, #orbit0, #orbit1, #orbit2, .pos, #pos0, #pos1, #pos2, .dot, #dot0, #dot1, #dot2 {
    backface-visibility: hidden;
  }

  .circle, .circle2, .circle3, .orbit, #orbit0, #orbit1, #orbit2, .pos, #pos0, #pos1, #pos2, .dot, #dot0, #dot1, #dot2 {
    will-change: transform;
  }

  .circle, .circle2, .circle3, .orbit, #orbit0, #orbit1, #orbit2, .pos, #pos0, #pos1, #pos2, .dot, #dot0, #dot1, #dot2 {
      transform: translateZ(0);
  }



  #universe {
    font-size: 3.5em;
    z-index: -1;
    position: absolute;
    width: 100%;
    height: 100%;
    right: 18%
  }

  /* add a media query for 1250px to downscale the font size to 1 em and move the universe to the top of the page instead of the left */
    @media (max-width: 1250px) {
        #universe {
        font-size: 2em;
        right: 19%;
        }
    }

    @media (max-width: 1000px) {
        #universe {
        font-size: 2.5em;
        right: 0;
        bottom: 25%;
        }
    }
  #galaxy {
    transform: rotateX(75deg);
    transform-style: preserve-3d;
    position: relative;
    width: 100%;
    height: 100%;
  }
  .circle {
    border-radius: 50%;
    border: 1px solid #eee;
    width: 1em;
    height: 1em;
    margin-top: -0.5em;
    margin-left: -0.5em;
    -webkit-animation: spinner 1.5s infinite ease;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: rotateX(-75deg);
  }
  .circle2 {
    border-radius: 50%;
    border: 1px solid #eee;
    width: 1em;
    height: 1em;
    margin-top: -0.5em;
    margin-left: -0.5em;
    -webkit-animation: spinner2 2s infinite ease;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: rotateX(-75deg);
  }
  .circle3 {
    border-radius: 50%;
    border: 1px solid #eee;
    width: 1em;
    height: 1em;
    margin-top: -0.5em;
    margin-left: -0.5em;
    -webkit-animation: spinner3 2.5s infinite ease;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: rotateX(-75deg);
  }
  .orbit,
  #orbit0,
  #orbit1,
  #orbit2 {
    transform-style: preserve-3d;
    position: absolute;
    top: 50%;
    left: 50%;
    animation-name: orbit;
    animation-iteration-count: infinite;
    animation-timing-function: linear;
    width: 8em;
    height: 8em;
    margin-top: -4em;
    margin-left: -4em;
    border-radius: 50%;
  }
  .pos,
  #pos0,
  #pos1,
  #pos2 {
    position: absolute;
    width: 2em;
    height: 2em;
    margin-left: -1em;
    margin-top: -1em;
    animation-name: invert;
    animation-iteration-count: infinite;
    animation-timing-function: linear;
    left: 50%;
    top: -1px;
  }
  .dot,
  #dot0,
  #dot1,
  #dot2 {
    background-color: #eee;
    width: 0.5em;
    height: 0.5em;
    position: absolute;
    top: 50%;
    left: 50%;
    margin-top: -0.25em;
    margin-left: -0.25em;
    border-radius: 50%;
    animation-iteration-count: infinite;
    animation-timing-function: linear;
  }
  /* Planet animation durations */
  .orbit,
  #orbit0,
  #orbit1,
  #orbit2,
  .pos,
  #pos0,
  #pos1,
  #pos2 {
    animation-duration: 3s;
  }
  .circle {
    font-size: 6em;
  }
  .circle2 {
    font-size: 5em;
  }
  .circle3 {
    font-size: 4em;
  }
  .dot,
  #dot0,
  #dot1,
  #dot2 {
    font-size: 0.2em;
  }
  @keyframes orbit {
    0% {
      transform: rotateZ(0deg);
    }
    100% {
      transform: rotateZ(-360deg);
    }
  }
  @keyframes invert {
    0% {
      transform: rotateX(-90deg) rotateY(360deg) rotateZ(0deg);
    }
    100% {
      transform: rotateX(-90deg) rotateY(0deg) rotateZ(0deg);
    }
  }
  @keyframes spinner {
    0% {
      -webkit-transform: rotate3d(1, 0, 1, 0deg);
    }
    50% {
      -webkit-transform: rotate3d(1, 0, 1, 180deg);
    }
    100% {
      -webkit-transform: rotate3d(1, 0, 1, 360deg);
    }
  }
  @keyframes spinner2 {
    0% {
      -webkit-transform: rotate3d(0, 1, 1, 0deg);
    }
    50% {
      -webkit-transform: rotate3d(0, 1, 1, 180deg);
    }
    100% {
      -webkit-transform: rotate3d(0, 1, 1, 360deg);
    }
  }
  @keyframes spinner3 {
    0% {
      -webkit-transform: rotate3d(1, 1, 0, 0deg);
    }
    50% {
      -webkit-transform: rotate3d(1, 1, 0, 180deg);
    }
    100% {
      -webkit-transform: rotate3d(1, 1, 0, 360deg);
    }
  }
</style>
