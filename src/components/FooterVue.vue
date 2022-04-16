<template>
  <div class="container">
      <footer class="footer-area">
        <div class="main" v-for="(footer, i) in footers" :key="i">
            <div class="footer">
                <div class="single-footer">
                    <h4>{{ msg }}</h4>
                    <div class="footer-social">
                        <a target="_blank" href="https://www.facebook.com/designandcreation39/"><i class="fa fa-facebook" aria-hidden="true"></i></a>
                        <a target="_blank" href="https://github.com/RomainDoyen/"><i class="fa fa-github" aria-hidden="true"></i></a>
                        <a target="_blank" href="https://www.instagram.com/designandcreation_rd/"><i class="fa fa-instagram" aria-hidden="true"></i></a>
                    </div>
                </div>
                <div class="single-footer">
                    <h4>{{ footer.subtitle }}</h4>
                    <p><i class="fa fa-envelope" aria-hidden="true"></i>&nbsp;{{ footer.mail }}</p>
                </div>
            </div>
            <div class="copy">
                <p>&copy;{{ footer.cop_1 }}<span id="dac"><img id="dac-logo" src="../images/2.webp"/></span>{{ footer.cop_2 }}<a href="#">{{ footer.cgu }}</a></p>
            </div>
        </div>
    </footer>
  </div>
</template>

<script>
export default {
    name: 'FooterVue',
    props: {
        msg: String
    },
    data: () => ({
        footers: [
            {
                subtitle: 'Mail',
                mail: 'romain.doyen39@gmail.com',
                cop_1: 'Romain Doyen 2022 by ',
                cop_2: ' | Tous droits réservés.',
                cgu: ' CGU'
            }
        ]
    })
}
</script>

<style>
.footer-area {
    background-image: url('../images/footer.webp');
    margin-top: 100px;
    padding: 100px 0;
    background-repeat: no-repeat;
    background-position: center center;
    color:#fff;
    position:relative;
}

.main {
    width: 1200px;
    margin: 0 auto;
}

.footer {
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
    flex-direction: row;
}

.single-footer {
    width: 230px;
}
  
.single-footer:first-child {
    width: 400px;
}
  
.single-footer h4 {
    text-transform: capitalize;
    font-size: 22px;
    margin-top: 15px;
    margin-bottom: 20px;
}
  
.footer-social a {
    color: #fff;
    border: 1px solid #fff;
    width: 40px;
    height: 40px;
    display: inline-block;
    text-align: center;
    line-height: 40px;
    border-radius: 50%;
    margin-right: 10px;
}
  
.footer-social {
    margin-top: 20px;
}

.copy {
    text-align: center;
    text-transform: capitalize;
    margin-top: 50px;
}

.copy a {
    text-decoration: none;
    color: #CAA13D;
}

#dac-logo {
    width: 35px;
    margin-bottom: -10px;
}
</style>