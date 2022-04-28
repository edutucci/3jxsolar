<template lang="pug">
h-main-body(
)
  template(v-slot:header)
    h-app-toolbar.lt-sm(bg-color="bg-primary")
      h-app-toolbar-container
        .col
          .row.align-items-center
            .col-auto
              h-app-toolbar-navigation(text-color='text-white' @click="showDrawer = !showDrawer")
            .col-auto.text-h5.text-white
              | 3JXSOLAR
            .col.h-pa-md
              .row.justify-end
                .col-auto
                  img(src='img/site/whatsapp.png' style='width: 16px')
                .col-auto.text-white.h-pl-xs
                  | (65) 99359-7771
              .row.justify-end.align-items-center.h-mt-sm
                .cursor-pointer.border.border-radius.border-positive.bg-positive.h-pa-xs(
                  @click="openUrl('https://api.whatsapp.com/send?phone=5565993597771&text=Oi.%20Tudo%20bem%3F%20Eu%20gostaria%20de%20um%20or%C3%A7amento%20e%2Fou%20suporte.')"
                )
                  .row.justify-end.align-items-center
                    .col-auto
                      img(src='img/site/whatsapp.png' style='width: 16px')
                    .col-auto.h-pl-xs.text-white.text-body-1
                      | ORÇAMENTO
              //- .row.justify-end.h-mt-sm
              //-   .col-auto.text-h6.text-white
              //-     | Redes Sociais
              //- .row.justify-end
              //-   h-btn(fab='' size='md' bg-color='bg-transparent')
              //-     h-link(url='#' icon='fab fa-facebook-square' text-color='text-white')
              //-   h-btn(fab='' size='md' bg-color='bg-transparent')
              //-     h-link(url='#' icon='fab fa-instagram-square' text-color='text-white')
    h-app-toolbar.gt-xs(bg-color="bg-primary")
      h-app-toolbar-container
        .col
          .row.align-items-center
            .col-auto
              img(src='img/site/logo3jxsolar.png' style='width: 200px')
            .col.h-pa-md
              .row.justify-end
                .col-auto
                  img(src='img/site/whatsapp.png' style='width: 24px')
                .col-auto.text-white.h-pl-xs
                  | (65) 99359-7771
              .row.justify-end.align-items-center.h-mt-sm
                .cursor-pointer.border.border-radius.border-positive.bg-positive.h-pa-xs(
                  @click="openUrl('https://api.whatsapp.com/send?phone=5565993597771&text=Oi.%20Tudo%20bem%3F%20Eu%20gostaria%20de%20um%20or%C3%A7amento%20e%2Fou%20suporte.')"
                )
                  .row.justify-end.align-items-center
                    .col-auto
                      img(src='img/site/whatsapp.png' style='width: 24px')
                    .col-auto.h-pl-xs.text-white.text-body-1
                      | ORÇAMENTO
              //- .row.justify-end.h-mt-sm
              //-   .col-auto.text-h6.text-white
              //-     | Redes Sociais
              //- .row.justify-end
              //-   h-btn(fab='' size='md' bg-color='bg-transparent')
              //-     h-link(url='#' icon='fab fa-facebook-square' text-color='text-white' new-window)
              //-   h-btn(fab='' size='md' bg-color='bg-transparent')
              //-     h-link(url='#' icon='fab fa-instagram-square' text-color='text-white' new-window)
      h-app-toolbar-container
        .col
          .row.menubar.align-items-center
            .menuitem(@click="goToDiv('sobreaempresa')") SOBRE
            .menuitem |
            .menuitem(@click="goToDiv('quemsomos')") QUEM SOMOS
            .menuitem |
            .menuitem(@click="goToDiv('comofunciona')") COMO FUNCIONA
            .menuitem |
            .menuitem(@click="goToDiv('vantagens')") VANTAGENS
            .menuitem |
            .menuitem(@click="goToDiv('oquefazemos')") O QUE FAZEMOS
            .menuitem |
            .menuitem(@click="goToDiv('emuso')") EM AÇÃO

  NavDrawerSite(ref="navHelp" v-model="showDrawer" side="left")
    .row.justify-end.align-items-center
      .col.text-primary.text-h6
        | MENU
      .col-auto.h-pa-xs
        h-icon.cursor-pointer(icon="fas fa-times-circle" text-color="text-gray"
          @click="closeDrawer"
        )

    .row.bg-primary.justify-center
      .col-auto
        img(src='img/site/logo3jxsolar.png' style='width: 130px')

    h-list
      h-list-item(@click="closeDrawer(); goToDiv('sobreaempresa')")
        h-list-item-content
          h-list-item-text(title="SOBRE")

      h-list-item(@click="closeDrawer(); goToDiv('quemsomos')")
        h-list-item-content
          h-list-item-text(title="QUEM SOMOS")

      h-list-item(@click="closeDrawer(); goToDiv('comofunciona')")
        h-list-item-content
          h-list-item-text(title="COMO FUNCIONA")

      h-list-item(@click="closeDrawer(); goToDiv('vantagens')")
        h-list-item-content
          h-list-item-text(title="VANTAGENS")

      h-list-item(@click="closeDrawer(); goToDiv('oquefazemos')")
        h-list-item-content
          h-list-item-text(title="O QUE FAZEMOS")

      h-list-item(@click="closeDrawer(); goToDiv('emuso')")
        h-list-item-content
          h-list-item-text(title="EM AÇÃO")
  h-page
    .div
      .row.justify-center
        .no-shrink.col-mobile.col-xs-12.col-sm-8.col-md-7.col-lg-7.col-xl-7.mySlides.fade.mySlidesHeaders(
          v-for="(img, index) in 4"
          :key="`header${index}`"
        )
          img(
            :src="`img/site/header${index+1}.png`"
            style="width:100%; max-height: 600px;")

      .row.justify-center
      .col-auto
        .h-mt-md(style="text-align:center")
          span.dot.dotHeaders(
            v-for="(img, index) in 4"
            :key="`header${index}`"
          )

    .row.justify-center.h-pa-md(ref="sobreaempresa")
      .no-shrink.col-mobile.col-xs-12.col-sm-8.col-md-7.col-lg-5.col-xl-5
        .text-h5.text-center SOBRE A EMPRESA

        p.text-justify A 3jxSolarmt se especializou no seguimento fotovoltaico e oferece soluções completas e confiáveis a cada um de seus clientes.

        p.text-justify Atua na Comercialização dos produtos de alta tecnologia e Confiabilidade, na Engenharia das soluções, na Execução de projetos, na Manutenção Preventiva, oferece suporte técnico aos nossos clientes e disponibilizamos um Pós-venda diferenciado.

    .row.justify-center(ref="quemsomos")
      .col-auto.h-pa-md
        .text-h5 QUEM SOMOS

    .row.wrap.justify-center.h-pa-md
      .no-shrink.col-mobile.col-xs-12.col-sm-8.col-md-7.col-lg-5.col-xl-5
        p.text-justify Mudamos de ramo de atividade em 2018 e a 3jxsolarmt com o desejo de ter um impacto positivo no uso dos recursos naturais, oferecendo serviços especializados, utilizando produtos confiáveis e de altíssima qualidade.

        p.text-justify Para isso, contamos com uma equipe especializada e multidisciplinar para auxiliar os clientes com os mais diversos projetos, na área de energia solar. Somos uma empresa dedicada à sustentabilidade, inovação, excelência e aos mais altos padrões de atendimento ao cliente.

        .text-h6.text-center MISSÃO
        p.text-justify Tratando cada projeto de forma especial, nosso compromisso é entregar aos nossos clientes o melhor custo benefício disponível atualmente, sempre prezando pela qualidade em primeiro lugar.

        .text-h6.text-center VISÃO
        p.text-justify Nossa visão baseia-se em nossa experiência, para trazer a tecnologia solar para outro nível, tornando mais fácil, mais simples e ainda mais econômico incorporá-la em nossa vida cotidiana.

        .text-h6.text-center VALORES
        p.text-justify Como uma família e um negócio de propriedade local, nossos valores fundamentais sempre buscam a qualidade do serviço e a liderança inovadora.

    .row.justify-center(ref="comofunciona")
      .col-auto.h-pa-md
        .text-h5.text-center.text-bold COMO FUNCIONA

    .row.wrap.justify-center.h-pa-md
      .no-shrink.col-mobile.col-xs-12.col-sm-8.col-md-7.col-lg-7.col-xl-7
        img(src="img/site/cm1.jpeg" style="width: 100%")
        p.text-center Os módulos fotovoltaicos captam a energia luminosa do sol e a transformam em energia elétrica.

    .row.wrap.justify-center.h-pa-md
      .col-mobile.col-xs-12.col-sm-8.col-md-7.col-lg-7.col-xl-7
        <video controls>
          <source src="video/psvideo1.mp4" type="video/mp4">
          Your browser does not support HTML video.
        </video>

    .row.justify-center(ref="vantagens")
      .col-auto.h-pa-md
        .text-h5.text-center.text-bold VANTAGENS DE USAR

    .row.wrap.justify-center.h-pa-lg
      h-card.h-mr-sm.h-mb-sm(style="width:250px;")
        h-card-section
          .text-h6.text-center ECONÔMICO
        h-card-media
          h-card-media-img(img="img/site/vant1.jpeg")
        h-card-section.text-body1
          | Reduz em até 95% suas depesas com energia elétrica, além de trazer segurança no caso de aumentos na fatura e mais valorização ao seu imóvel.
      h-card.h-mr-sm.h-mb-sm(style="width:250px;")
        h-card-section
          .text-h6.text-center BAIXA MANUTENÇÃO
        h-card-media
          h-card-media-img(img="img/site/vant2.jpeg")
        h-card-section.text-body1
          | Os equipamentos possuem alta confiabilidade e baixa manutenção, além de garantia do fabricante que varia de 5 a 10 anos.

      h-card.h-mr-sm.h-mb-sm(style="width:250px;")
        h-card-section
          .text-h6.text-center SUSTENTÁVEL
        h-card-media
          h-card-media-img(img="img/site/vant3.jpeg")
        h-card-section.text-body1
          | Fonte limpa e renovável de energia, que reduz a produção de gases poluentes e contribui para a melhoria da qualidade da energia elétrica.

      h-card.h-mr-sm.h-mb-sm(style="width:250px;")
        h-card-section
          .text-h6.text-center ACESSÍVEL
        h-card-media
          h-card-media-img(img="img/site/vant4.jpeg")
        h-card-section.text-body1
          | Altamente, a energia solar conta com facilidades de acesso e financiamento, além de rápido retorno do investimento, entre 5 e 10 anos.

    .row.justify-center(ref="oquefazemos")
      .col-auto.h-pa-md
        .text-h5.text-center.text-bold O QUE FAZEMOS

    .row.wrap.justify-center.h-pa-lg
      h-card.h-mr-sm.h-mb-sm(style="width:250px;")
        h-card-section
          .text-h6.text-center ESTUDOS
        h-card-media
          h-card-media-img(img="img/site/onf1.png")
        h-card-section.text-body1.text-center
          | Avaliação da radiação solar, orientação e inclinação dos módulos fotovoltaicos, temperatura, sombreamento...
      h-card.h-mr-sm.h-mb-sm(style="width:250px;")
        h-card-section
          .text-h6.text-center CÁLCULOS
        h-card-media
          h-card-media-img(img="img/site/onf2.png")
        h-card-section.text-body1.text-center
          | Dimensionamento do sistema, Orçamento, Viabilidade financeira, Aprovação de crédito e Previsão de geração

      h-card.h-mr-sm.h-mb-sm(style="width:250px;")
        h-card-section
          .text-h6.text-center PROJETO
        h-card-media
          h-card-media-img(img="img/site/onf3.png")
        h-card-section.text-body1.text-center
          | Fazemos todo o Projeto executivo para voce, Emissao de ARTs e Tramitação junto à concessionária.

      h-card.h-mr-sm.h-mb-sm(style="width:250px;")
        h-card-section
          .text-h6.text-center INSTALAÇÃO
        h-card-media
          h-card-media-img(img="img/site/onf4.png")
        h-card-section.text-body1.text-center
          | Entrega dos equipamentos. Instalação, Solicitação de vistoria e substituição do medidor , só aguardando a aprovação da energia.

      h-card.h-mr-sm.h-mb-sm(style="width:250px;")
        h-card-section
          .text-h6.text-center MANUTENÇÃO
        h-card-media
          h-card-media-img(img="img/site/onf5.png")
        h-card-section.text-body1.text-center
          | Em raros casos será necessária (como descarga de um raio ou algum acidente mecânico), mas precisando estaremos à disposição.

    .row.justify-center(ref="emuso")
      .col-auto.h-pa-md
        .text-h5.text-center.text-bold PAINÉIS EM AÇÃO

    .div
      .row.justify-center
        .no-shrink.col-mobile.col-xs-12.col-sm-8.col-md-7.col-lg-7.col-xl-7.mySlides.fade.mySlidesBoards(
          v-for="(img, index) in 6"
          :key="`board${index}`"
        )
          img(
            :src="`img/site/uso${index+1}.png`"
            style="width:100%; max-height: 600px;")

    .row.justify-center
      .col-auto
        .h-mt-md(style="text-align:center")
          span.dot.dotBoards(
            v-for="(img, index) in 6"
            :key="`board${index}`"
          )

    .bg-primary
      .row.justify-around
        .col-auto
          img(src='img/site/logo3jxsolar.png' style='width: 120px')
        .col.h-pa-xs
          .row
            .col.text-white.text-center.h-pa-xs(style="width: 170px")
              .text-caption Avenida General Melo, 360 <br>
              .text-caption Bairro Dom Aquino- Cuiabá-MT <br>
              .text-caption Cep 78.015-300
            .col-auto
              .row.justify-center
                .col-auto
                  img(src='img/site/whatsapp.png' style='width: 16px')
                .col-auto.text-white.h-pl-xs
                  .text-caption (65) 99359-7771
              .row.justify-center
                .col-auto
                  img(src='img/site/whatsapp.png' style='width: 16px')
                .col-auto.text-white.h-pl-xs
                  .text-caption (65) 3615-4200

</template>

<script>

import NavDrawerSite from '@/components/NavDrawerSite.vue';

export default {
  name: 'Home',
  components: {
    NavDrawerSite,
  },
  data() {
    return {
      showDrawer: false,
      slideHeaderIndex: 0,
      sliderBoardIndex: 0,
    };
  },
  mounted() {
    this.showSlidesHeaders();
    this.showSlidesBoards();
  },
  methods: {
    openUrl(url) {
      window.open(url);
    },
    closeDrawer() {
      this.showDrawer = !this.showDrawer;
    },
    goToDiv(refName) {
      const element = this.$refs[refName];
      if (element) {
        element.scrollIntoView({ behavior: 'smooth', block: 'start' });
      }
    },
    showSlidesHeaders() {
      let i;
      const slides = document.getElementsByClassName('mySlidesHeaders');
      const dots = document.getElementsByClassName('dotHeaders');

      // eslint-disable-next-line no-plusplus
      for (i = 0; i < slides.length; i++) {
        slides[i].style.display = 'none';
      }
      // eslint-disable-next-line no-plusplus
      this.slideHeaderIndex++;
      if (this.slideHeaderIndex > slides.length) { this.slideHeaderIndex = 1; }
      // eslint-disable-next-line no-plusplus
      for (i = 0; i < dots.length; i++) {
        dots[i].className = dots[i].className.replace(' active', '');
      }

      slides[this.slideHeaderIndex - 1].style.display = 'block';
      dots[this.slideHeaderIndex - 1].className += ' active';
      setTimeout(this.showSlidesHeaders, 2000); // Change image every 2 seconds
    },
    showSlidesBoards() {
      let i;
      const slides = document.getElementsByClassName('mySlidesBoards');
      const dots = document.getElementsByClassName('dotBoards');

      // eslint-disable-next-line no-plusplus
      for (i = 0; i < slides.length; i++) {
        slides[i].style.display = 'none';
      }
      // eslint-disable-next-line no-plusplus
      this.sliderBoardIndex++;
      if (this.sliderBoardIndex > slides.length) { this.sliderBoardIndex = 1; }
      // eslint-disable-next-line no-plusplus
      for (i = 0; i < dots.length; i++) {
        dots[i].className = dots[i].className.replace(' active', '');
      }

      slides[this.sliderBoardIndex - 1].style.display = 'block';
      dots[this.sliderBoardIndex - 1].className += ' active';
      setTimeout(this.showSlidesBoards, 2000); // Change image every 2 seconds
    },
  },
};
</script>

<style scoped>
video {
  height: 100%;
  width: 100%;
  object-fit: cover;
}

.menubar {
  background: #1e88e5;
}

.menuitem {
  width: auto;
  color: white;
  padding: 5px;
  font-weight: bold;
  cursor: pointer;
}

/*BEGIN  Slideshow COMPONENT */
* {box-sizing: border-box;}
body {font-family: Verdana, sans-serif;}
.mySlides {display: none;}
img {vertical-align: middle;}

/* Slideshow container */
.slideshow-container {
  max-width: 1000px;
  position: relative;
  margin: auto;
}

/* Caption text */
.text {
  color: #f2f2f2;
  font-size: 15px;
  padding: 8px 12px;
  position: absolute;
  bottom: 8px;
  width: 100%;
  text-align: center;
}

/* Number text (1/3 etc) */
.numbertext {
  color: #f2f2f2;
  font-size: 12px;
  padding: 8px 12px;
  position: absolute;
  top: 0;
}

/* The dots/bullets/indicators */
.dot {
  height: 15px;
  width: 15px;
  margin: 0 2px;
  background-color: #bbb;
  border-radius: 50%;
  display: inline-block;
  transition: background-color 0.6s ease;
}

.active {
  background-color: #717171;
}

/* On smaller screens, decrease text size */
@media only screen and (max-width: 300px) {
  .text {font-size: 11px}
}

/*END  Slideshow COMPONENT */
</style>
