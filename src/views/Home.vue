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

    .row.wrap.justify-center.align-items-center.h-pa-lg(ref="quemsomos")
      .col-mobile.col-xs-12.col-sm-8.col-md-5.col-lg-4.col-xl-5
        img(src="img/site/quemsomos.png" style="width: 100%")
      .col-mobile.col-xs-12.col-sm-8.col-md-7.col-lg-5.col-xl-5.h-pa-md
        .text-h5.title QUEM SOMOS
        .text-body1.text-center.h-mt-xl A 3JX Solar hoje é uma empresa especializada em implantação de sistemas de geração de energia renovável (solar).
        .text-body1.text-center O foco da empresa é oferecer uma solução completa, para que nossos clientes possam reduzir custos gerando sua própria energia.
        .text-body1.text-center.h-mt-md Será realizado o projeto por inteiro, desde o dimensionamento, assessoria junto à concessionária e a instalação completa do sistema fotovoltaico.

    .row.wrap.justify-center.h-pa-lg
      .col
        .text-h5.title NOSSA ATUAÇÃO
        .row.justify-center
          .col-auto
            .text-body1.text-center.h-mt-xl(style="max-width: 500px") Nós da 3JX Solar atuamos no projeto e instalação de sistemas solares em residências, empresas e condomínios em geral.

    //- .lt-xs
    .row.wrap.justify-center
      .no-shrink.col-mobile.col-xs-12.col-sm-8.col-md-8.col-lg-7.col-xl-8.text-center
        img(src="img/site/nossaatuacaocelular.png" style="width: 70%")

    //- .gt-xs
    //-   .row.wrap.justify-center
    //-     .no-shrink.col-mobile.col-xs-12.col-sm-8.col-md-8.col-lg-7.col-xl-8.text-center
    //-       .text-h5 DESKTOP
    //-       img(src="img/site/nossaatuacaodesktop.png" style="width: 100%")

    .text-h5.title.h-pa-lg PORQUE CONTRATAR A 3JX SOLAR?
    .row.justify-center.align-items-center.h-mt-md
      .col-auto.text-h2
        | 1.
      .h-pl-sm.no-shrink.col-mobile.col-xs-12.col-sm-8.col-md-8.col-lg-6.col-xl-5.text-h5(style="max-width: 1200px")
        | Suporte avançado do início ao fim do projeto, para nossos clientes conseguirem obter o máximo de economia e rentabilidade.

    .row.justify-center.align-items-center.h-mt-md
      .col-auto.text-h2
        | 2.
      .h-pl-sm.no-shrink.col-mobile.col-xs-12.col-sm-8.col-md-8.col-lg-6.col-xl-5.text-h5(style="max-width: 1200px")
        | Trabalhamos somente com os melhores fabricante e produtos do mercado, garantindo assim alta qualidade e total confiança.

    .row.justify-center.align-items-center.h-mt-md
      .col-auto.text-h2
        | 3.
      .h-pl-sm.no-shrink.col-mobile.col-xs-12.col-sm-8.col-md-8.col-lg-6.col-xl-5.text-h5(style="max-width: 1200px")
        | Trabalhamos somente com os melhores fabricante e produtos do mercado, garantindo assim alta qualidade e total confiança.

    .row.justify-center.align-items-center.h-mt-md
      .col-auto.text-h2
        | 4.
      .h-pl-sm.no-shrink.col-mobile.col-xs-12.col-sm-8.col-md-8.col-lg-6.col-xl-5.text-h5(style="max-width: 1200px")
        | Trabalhamos somente com os melhores fabricante e produtos do mercado, garantindo assim alta qualidade e total confiança.

    .row.justify-center.align-items-center.h-mt-md
      .col-auto.text-h2
        | 5.
      .h-pl-sm.no-shrink.col-mobile.col-xs-12.col-sm-8.col-md-8.col-lg-6.col-xl-5.text-h5(style="max-width: 1200px")
        | Temos parcerias com as melhores instituições financeiras, conseguindo assim financiamentos com melhores taxas do mercado. Também possuímos estratégias diferenciadas, para que a economia de energia seja equivalente a parcela paga, evitando que o cliente tenha dois custos (parcela + conta de energia).

    .row.justify-center.align-items-center.h-mt-md
      .col-auto.text-h2
        | 6.
      .h-pl-sm.no-shrink.col-mobile.col-xs-12.col-sm-8.col-md-8.col-lg-6.col-xl-5.text-h5(style="max-width: 1200px")
        | Além do sistema fotovoltaico trazer economia direta na sua conta de energia pode valorizar e muito seu imóvel.

    .row.justify-center.align-items-center.h-mt-md
      .col-auto.text-h2
        | 7.
      .h-pl-sm.no-shrink.col-mobile.col-xs-12.col-sm-8.col-md-8.col-lg-6.col-xl-5.text-h5(style="max-width: 1200px")
        | Dispomos de instalacoes personalizadas, onde podemos instalar para o cliente um sistema menor e posteriormente, após constatado o custo-benefício, ampliamos o sistema instalado, tudo dentro das condições do cliente.

    .row.wrap.justify-center.h-pa-lg
      .col-auto.text-h5.title PRODUTOS

    .row.wrap.justify-center.h-pa-lg
      h-card.h-mr-sm.h-mb-sm.prodcard
        h-card-section(auto)
          .text-h6.text-center Painel Solar
        h-card-media
          h-card-media-img(img="img/site/prodpainelsolar.png")
        h-card-section.text-body1
          | O painel solar fotovoltaico é um dispositivo responsável por captar a radiação solar e converter em energia elétrica.
      h-card.h-mr-sm.h-mb-sm.prodcard
        h-card-section(auto)
          .text-h6.text-center Inversor
        h-card-media
          h-card-media-img(img="img/site/prodinversor.png")
        h-card-section.text-body1
          | Transforma a corrente elétrica alternada fixa (corrente e tensão) em corrente elétrica CA variável, controlando assim a potência consumida pela carga através da variação da frequência entregue pela rede.
      h-card.h-mr-sm.h-mb-sm.prodcard
        h-card-section(auto)
          .text-h6.text-center Controlador de Carga
        h-card-media
          h-card-media-img(img="img/site/prodcontrolador.png")
        h-card-section.text-body1
          | Ele é o equipamento responsável por preservar a vida útil das baterias, protegendo-as dos efeitos da sobrecarga ou descarga abrupta.
      h-card.h-mr-sm.h-mb-sm.prodcard
        h-card-section(auto)
          .text-h6.text-center Bateria
        h-card-media
          h-card-media-img(img="img/site/prodbateria.png")
        h-card-section.text-body1
          | É o equipamento que armazena energia, permitindo que seu usuário tenha mais autonomia para desconectar-se da rede elétrica e não precisar mais se preocupar com falta de energia e aumentos na conta de luz.
      h-card.h-mr-sm.h-mb-sm.prodcard
        h-card-section(auto)
          .text-h6.text-center Estrutura de Montagem
        h-card-media
          h-card-media-img(img="img/site/prodestrutura.png")
        h-card-section.text-body1
          | Coberturas de telha de barro, telha de concreto, telhado metálico, telha de fibrocimento, seguidores solares e fixação direta sobre o solo.

    .row.justify-center(ref="comofunciona")
      .col-auto.h-pa-lg
        .text-h5.title COMO FUNCIONA

    .row.wrap.justify-center
      .col.h-pa-lg
        | Desde 17 de abril de 2012, quando entrou em vigor a Resolução Normativa ANEEL n. 482/2012, o consumidor brasileiro pode gerar sua própria energia elétrica a partir de fontes renováveis e inclusive fornecer o excedente para a rede de distribuição de sua localidade.

    .row.wrap.justify-center.align-items-center.h-pa-md
      .col-mobile.col-xs-12.col-sm-8.col-md-5.col-lg-4.col-xl-5
        img(src="img/site/cm1.jpeg" style="width: 100%")
      .col-mobile.col-xs-12.col-sm-8.col-md-5.col-lg-4.col-xl-5
        .text-body1.text-center.h-pa-md
          | Este tipo de energia proveniente do sol é captada através de recursos materiais, como por exemplo os painéis solares extremamente populares nos dias de hoje, que sao formados através de celulas fotovoltaicas que tê,m como principal objetivo a transformação de energia solar em energia elétrica, térmica ou mecânica. Esta energia pode ser utilizada para diversos fins, seja o título particular ou até mesmo empresarial.

    .row.wrap.justify-center.h-pa-md
      .col-mobile.col-xs-12.col-sm-8.col-md-7.col-lg-7.col-xl-7
        <video controls>
          <source src="video/psvideo1.mp4" type="video/mp4">
          Your browser does not support HTML video.
        </video>

    .bg-primary
      .row.wrap.justify-center
        .col-auto.h-pa-lg.text-white
          .text-h5.text-center.text-bold BENEFÍCIOS

      .row.wrap.justify-center.align-items-center.h-pa-lg
        .col-auto.text-bold.text-white.text-center.text-h6(style="width:210px")
          | Economia:
        .col.text-white
          | Depois de instalado corretamente, o sistema fotovoltaico pode gerar 100% da energia que você consome, tendo uma economia de até 95% da sua conta de luz. Além de ser possível a utilização do excedente de energia em outra residência ou escritório por exemplo.

      .row.wrap.justify-center.align-items-center.h-pa-lg
        .col-auto.text-bold.text-white.text-center.text-h6(style="width:210px")
          | Valorização do seu imóvel:
        .col.text-white.h-pa-sm
          | Além de trazer economia direto na sua conta de energia, um sistema solar fotovoltaico pode valorizar e muito seu imóvel, acelerando o retorno de seu investimento.

      .row.wrap.justify-center.align-items-center.h-pa-lg
        .col-auto.text-bold.text-white.text-center.text-h6(style="width:210px")
          |  Linha de Crédito Especial:
        .col.text-white
          | Os grandes bancos brasileiros já criaram linhas de crédito especialmente para geradores fotovoltaicos, tanto para pessoa física quanto para pessoa jurídica. Dessa maneira a energia solar está cada vez mais acessível a todos.

      .row.wrap.justify-center.align-items-center.h-pa-lg
        .col-auto.text-bold.text-white.text-center.text-h6(style="width:210px")
          | Sustentabilidade:
        .col.text-white
          | Trata-se de uma fonte totalmente limpa, renovável e com disponibilidade infinita (o sol). Sua produção não emite qualquer tipo de poluição ou gases de efeito estufa, garantindo o compromisso do país na diminuição de CO2.

    .row.wrap.justify-center
      .col-auto.h-pa-lg.text-h5.title
        | 3JX Energia solar O Brasil tem um dos maiores índices de radiação solar do mundo

    .row.wrap.justify-center
      .col-auto.text-body1.h-pa-lg
        | No País, a média fica entre 4.500 Wh/m2 e 6.300 Wh/m2, de acordo com dados do Atlas Brasileiro de Energia Solar. Para se ter uma ideia, a Alemanha, que é o país que mais explora a energia fotovoltaica em todo o mundo, recebe aproximadamente 40% menos luz solar em sua região de maior potencial, em comparação com a incidência brasileira. Mesmo assim, a energia solar ainda é pouco aproveitada no Brasil (porém em exponencial crescimento), correspondendo a pouco mais de 0,02% da nossa matriz energética.

    .row.wrap.justify-center
      .col-auto.h-pa-lg.text-h5.title POTENCIAL ENERGÉTICO

    .row.wrap.justify-center.align-items-center.h-pa-md
      .col-mobile.col-xs-12.col-sm-8.col-md-5.col-lg-4.col-xl-5
        img(src="img/site/tabelapotencial.png" style="width: 100%")
      .col-mobile.col-xs-12.col-sm-8.col-md-5.col-lg-4.col-xl-5
        .text-body1.text-center.h-pa-md
          | O cálculo de produção de energia baseia-se na irradiação e pode ter alterações de cidade para cidade. Fatores como inclinação dos painéis fotovoltáicos, direção/inclinação do telhado e sombra direta influenciam na produção do gerador. (Nos procure para fazer a instalação)

    .row.wrap.justify-center
      .col-auto.h-pa-lg.text-h5.title LEGISLAÇÃO

    .row.wrap.justify-center
      .col-auto.text-body1.h-pa-lg
        | No ano de 2013, foi proposto um projeto de lei no Senado nacional que sugeria a isenção de componentes necessários para a instalação de geração elétrica a partir de energia solar. A proposta, aprovada em 2015, garante que a instalação de novas plantas de geração e micro geração sejam adquiridas com a isenção de diversos impostos, assim como a isenção na conta de luz que utilize a geração solar.
    .row.wrap.justify-center
      .col-auto.text-body1.h-pa-lg
        | Entre os maiores incentivos à energia solar no Brasil está a regulamentação sobre a microgeração residencial, estabelecida pela Agência Nacional de Energia Elétrica (ANEEL ) em 2012. Esta regulamentação permite que qualquer residência possua painéis solares que possam ser utilizados como forma de geração autônoma de energia. Isso não apenas reduz o consumo de energia obtido através da distribuidora, mas em horários de pico de produção energética ainda pode devolver energia rede de distribuição.

    .row.wrap.justify-center
      .col-auto.text-body1.h-pa-lg
        | Este processo de "devolução" é o que gera os chamados créditos de energia , que são créditos energéticos gerados para a residência que produziu mais energia do que consumiu durante um período. Estes créditos são descontados em momentos onde o consumo é maior do que a produção. A economia é útil tanto para o consumidor , que diminui sua conta , quanto para o Estado , que recebe menos demanda de fontes de energia mais poluentes que , em períodos de baixa nos reservatórios de hidrelétricas , costumam ser baseadas na queima de combustíveis fósseis , como carvão mineral e gás natural.

    .row.justify-center(ref="vantagens")
      .col-auto.h-pa-md
        .text-h5.title VANTAGENS DE USAR

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
        .text-h5.title O QUE FAZEMOS

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
        .text-h5.title PAINÉIS EM AÇÃO

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

    .row.justify-center(ref="emuso")
      .col-auto.h-pa-md
        .text-h5.title FALE CONOSCO

    .row.wrap.justify-center.align-items-center.h-pa-md
      .h-pa-sm.col-mobile.col-xs-12.col-sm-12.col-md-4.col-lg-4.col-xl-5
        .text-h5 3JX SOLAR
        .text-body1 Energia Renovável

        .text-h6.h-mt-md Av. General Mello, 360
        .text-h6 Bairro Dom Aquino - Cuiabá/MT
        .text-h6 CEP: 78015-300

        .text-h6.h-mt-md Tel: (65) 3615 4200
        .text-h6 (65) 9 9201 6532
        .text-body1 (Ligações e WhatsApp)
        .text-h6 Email: jackson3jx@hotmail.com

      .col-mobile.col-xs-12.col-sm-12.col-md-6.col-lg-6.col-xl-5
        img(src="img/site/mapalocalizacao.png" style="width: 100%")

    //- .bg-primary
    //-   .row.justify-around
    //-     .col-auto
    //-       img(src='img/site/logo3jxsolar.png' style='width: 120px')
    //-     .col.h-pa-xs
    //-       .row
    //-         .col.text-white.text-center.h-pa-xs(style="width: 170px")
    //-           .text-caption Avenida General Mello, 360 <br>
    //-           .text-caption Bairro Dom Aquino- Cuiabá-MT <br>
    //-           .text-caption Cep 78.015-300
    //-         .col-auto
    //-           .row.justify-center
    //-             .col-auto
    //-               img(src='img/site/whatsapp.png' style='width: 16px')
    //-             .col-auto.text-white.h-pl-xs
    //-               .text-caption (65) 99359-7771
    //-           .row.justify-center
    //-             .col-auto
    //-               img(src='img/site/whatsapp.png' style='width: 16px')
    //-             .col-auto.text-white.h-pl-xs
    //-               .text-caption (65) 3615-4200

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

.prodcard {
  width:250px;
  height:420px
}

.title {
  opacity2: 0.5;
  color: dodgerblue;
  text-align: center;
  font-weight: bold;
}

/*END  Slideshow COMPONENT */
</style>
