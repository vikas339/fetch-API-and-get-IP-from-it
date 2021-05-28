<template>
  <div>
    <nav>
      <a href=""
        ><h3 style="margin: 0%; margin-left: 11rem">ALON WALKER</h3>
        <br />
        <p
          style="
            margin: 0%;
            margin-top: -1rem;
            margin-left: 10.25rem;
            font-size: 1.2rem;
          "
        >
          <i> Personal Coach</i>
        </p></a
      >
      <div style="margin-left: 10rem; margin-top: 1rem">
        <a href="#" style="margin-left: 27rem" class="hover">Home</a>
        <a href="#" class="hover">About us</a>
        <a href="#" class="hover">Service</a>
        <a href="#" class="hover"
          ><img
            src="https://user-images.githubusercontent.com/75200810/119225677-d6164d00-bb22-11eb-8285-afa9acddf11d.png"
            alt="loginIMG"
            height="40rem"
            width="40rem"
            style="margin-top: -0.6rem"
        /></a>
        <a href="#" style="margin-left: -3rem" class="hover">Log in</a>
      </div>
    </nav>
    <div class="box">
      <div>
        <h2 style="margin-top: 13.5rem; margin-left: 44rem; font-size: 1.7rem;"> <i> Your <br> IP address is</i></h2>
        <div id="myData" style="margin-top: 7rem;  margin-left: 37.5rem;"></div>
      </div>
    </div>
    <div class="foot">
        <div>
            <h1 style="color: aliceblue;">Internship</h1>
            <p style="color: aliceblue; margin-top: 0%;" >CHALO INDIA, LET’S WORK FROM HOME</p>
        </div>
        <div style="display: flex;">
            <div><h4 style="margin-left: 30rem; color: aliceblue;">_______________________</h4></div>
            <a href="https://www.facebook.com/" target="_blank"><img src="./images/Facebook-PNG-Image.png" alt="fbimg" style="padding: 1rem;"></a>
            <a href="https://www.instagram.com/" target="_blank"><img src="./images/410617_facebook-icon-transparent-png.jpg" alt="inimg" style="padding: 1rem;"></a>
            <a href="https://www.facebook.com/"><img src="./images/kTKoxpgBc.png" alt="" style="padding: 1rem;"></a>
           <div><h4 style="color: aliceblue; margin-left: -9px;">_______________________</h4></div>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      data: {},
    };
  },
  beforeMount() {
    this.getName();
  },
  methods: {
    async getName() {
      fetch("http://edns.ip-api.com/json")
        .then((response) => {
          if (!response.ok) {
            throw Error("ERROR");
          }
          return response.json();
        })
        .then((responsedata) => {
          const data = responsedata.dns.ip;
          console.log(data);
          document.getElementById("myData").innerHTML = data;
        });
    },
  },
};
</script>

<style>
body {
  margin: 0%;
  background-image: url(./images/15.jpg);
}
nav {
  height: 7.5rem;
  overflow: hidden;
  background-color: rgb(253, 249, 249);
}
nav a {
  text-align: center;
  margin-top: 1rem;
  text-decoration: none;
  padding: 25px;
  text-align: center;
  float: left;
  font-size: 1.3rem;
  padding-top: 15px;
  color: #000000;
}
.hover:hover {
  color: rgb(146, 109, 103);
}

#myData{
  margin-left: 33rem;
  margin-top: 1.5rem;
  font-size: 4rem;
}
.foot{
    background-color: #23313f;
    text-align: center;
    height: 10rem;
    width: 100%;
    margin-top: 11rem;
}
.foot img{
    height: 2rem;
    width: 2rem;
}
.foot h1{
    padding: 0%;
    margin: 0%;
    padding-top: 1rem;
    text-shadow: 5px 2px 1px rgb(92, 49, 49);
}
</style>
