<template>
  <div class="no-page-view">
    <div class="error">
      <div class="container-floud">
        <div class="col-xs-12 ground-color text-center">
          <div class="container-error-404">
            <div class="clip">
              <div class="shadow"><span class="digit thirdDigit"></span></div>
            </div>
            <div class="clip">
              <div class="shadow"><span class="digit secondDigit"></span></div>
            </div>
            <div class="clip">
              <div class="shadow"><span class="digit firstDigit"></span></div>
            </div>
          </div>
          <h2>Sorry! Page not found</h2>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "NoPageView",
  mounted() {
    function randomNum() {
      "use strict";
      return Math.floor(Math.random() * 9) + 1;
    }
    var loop1,
      loop2,
      loop3,
      time = 30,
      i = 0,
      selector3 = document.querySelector(".thirdDigit"),
      selector2 = document.querySelector(".secondDigit"),
      selector1 = document.querySelector(".firstDigit");
    loop3 = setInterval(function () {
      "use strict";
      if (i > 40) {
        clearInterval(loop3);
        selector3.textContent = 4;
      } else {
        selector3.textContent = randomNum();
        i++;
      }
    }, time);
    loop2 = setInterval(function () {
      "use strict";
      if (i > 80) {
        clearInterval(loop2);
        selector2.textContent = 0;
      } else {
        selector2.textContent = randomNum();
        i++;
      }
    }, time);
    loop1 = setInterval(function () {
      "use strict";
      if (i > 100) {
        clearInterval(loop1);
        selector1.textContent = 4;
      } else {
        selector1.textContent = randomNum();
        i++;
      }
    }, time);
  },
};
</script>

<style lang="scss">

.no-page-view{
  display: flex;
  justify-content: center;
  height: 100vh;
}


/* Error Page */
.error .clip .shadow {
  height: 180px; /*Contrall*/
}
.error .clip:nth-of-type(2) .shadow {
  width: 130px; /*Contrall play with javascript*/
}
.error .clip:nth-of-type(1) .shadow,
.error .clip:nth-of-type(3) .shadow {
  width: 250px; /*Contrall*/
}
.error .digit {
  width: 150px; /*Contrall*/
  height: 150px; /*Contrall*/
  line-height: 150px; /*Contrall*/
  text-align: center;
  margin-left: 0.2rem;
  font-size: 120px;
  font-weight: bold;
}
.error h2   /*Contrall*/ {
  font-size: 32px;
  text-align: center;
}
.error .msg {
  display: none;
  top: -190px;
  left: 30%;
  width: 80px;
  height: 80px;
  line-height: 80px;
  font-size: 32px;
}
.error span.triangle {
  display: none;
  top: 70%;
  right: 0%;
  border-left: 20px solid #535353;
  border-top: 15px solid transparent;
  border-bottom: 15px solid transparent;
}

.error .container-error-404 {
  margin-top: 10%;
  position: relative;
  height: 250px;
  padding-top: 40px;
}
.error .container-error-404 .clip {
  display: inline-block;
  transform: skew(-45deg);
}
.error .clip .shadow {
  overflow: hidden;
}
.error .clip:nth-of-type(2) .shadow {
  overflow: hidden;
  position: relative;
  box-shadow: inset 20px 0px 20px -15px rgba(150, 150, 150, 0.8),
    20px 0px 20px -15px rgba(150, 150, 150, 0.8);
}

.error .clip:nth-of-type(3) .shadow:after,
.error .clip:nth-of-type(1) .shadow:after {
  content: "";
  position: absolute;
  right: -8px;
  bottom: 0px;
  z-index: 9999;
  height: 100%;
  width: 10px;
  background: linear-gradient(
    90deg,
    transparent,
    rgba(173, 173, 173, 0.8),
    transparent
  );
  border-radius: 50%;
}
.error .clip:nth-of-type(3) .shadow:after {
  left: -8px;
}
.error .digit {
  position: relative;
  top: 8%;
  left: 50%;
  color: white;
  background: #07b3f9;
  border-radius: 50%;
  display: inline-block;
  transform: skew(45deg);
}
.error .clip:nth-of-type(2) .digit {
  left: -10%;
}
.error .clip:nth-of-type(1) .digit {
  left: 40%;
}
.error .clip:nth-of-type(3) .digit {
  left: -10%;
}
.error h2 {
  color: #a2a2a2;
  font-weight: bold;
  padding-bottom: 20px;
}
.error .msg {
  position: relative;
  z-index: 9999;
  display: block;
  background: #535353;
  color: #a2a2a2;
  border-radius: 50%;
  font-style: italic;
}
.error .triangle {
  position: absolute;
  z-index: 999;
  transform: rotate(45deg);
  content: "";
  width: 0;
  height: 0;
}

/* Error Page */
@media (max-width: 767px) {
  /* Error Page */
  .error .clip .shadow {
    height: 100px; /*Contrall*/
  }
  .error .clip:nth-of-type(1) .digit {
  left: 20%;
}
  .error .clip:nth-of-type(2) .shadow {
    width: 80px; /*Contrall play with javascript*/
  }
  .error .clip:nth-of-type(1) .shadow,
  .error .clip:nth-of-type(3) .shadow {
    width: 100px; /*Contrall*/
  }
  .error .digit {
    width: 80px; /*Contrall*/
    height: 80px; /*Contrall*/
    line-height: 80px; /*Contrall*/
    font-size: 52px;
  }
  .error h2  /*Contrall*/ {
    font-size: 24px;
  }
  
  .error .container-error-404 {
    height: 150px;
  }
  /* Error Page */
}
</style>
