---
lang: pt-BR
layout: default
meta_title: Como instalar o Ghost no seu Servidor - Ghost Docs
meta_description: Tudo o que você precisa saber para colocar sua plataforma Ghost funcionando no seu ambiente local, ou em um ambiente remoto.
heading: Instalando o Ghost &amp; Começando
subheading: Os primeiros passos para configurar o seu Blog pela primeira vez.
chapter: installation
next_section: mac
---

<div class="container">
    <div class="row">
        {% include subnav/installation.html %}

        <section id="content" class="col-lg-9">

            <h2 id="overview">Resumo</h2>

            <p>A Documentação do Ghost ainda está em desenvolvimento, ela é atualizada e melhorada regularmente. Se você ficar preso, ou tiver alguma sugestão de melhoria, fale conosco.</p>

            <p>Ghost é feito em <a href="http://nodejs.org">Node.js</a>, e requer versão <code>0.10.*</code> (última versão estável).</p>

            <p>Rodando Ghost local no seu computador é bastante simples, mas requer que você instale o Node.js primeiro.</p>

            <h3>O que é Node.js?</h3>

            <p><a href="http://nodejs.org">Node.js</a> é uma moderna plataforma para desenvolvimento rápido, escalável e eficiente de aplicações Web. Nos últimos 20 anos, a Web evoluiu de uma coleção de páginas estáticas para uma plataforma capaz de suportar aplicações complexas como o Gmail e o Facebook. JavaScript é a linguagem que permitiu esse progresso.</p>

            <p><a href="http://nodejs.org">Node.js</a> nos provê a habilidade de escrever JavaScript para o servidor. No passado, JavaScript existia somente no navegador e uma segunda linguagem, como PHP, era necessario para lidar com a programação no servidor. Ter uma aplicação Web que consiste de apenas uma linguagem é um grande beneficio e isso também torna o Node.js acessível para desenvolvedores que tradicionalmente trabalhavam no cliente-side.</p>

            <p>A forma com que o <a href="http://nodejs.org">Node.js</a> torna isso possível, é desacoplando o motor de Javascript do Google Chrome e tornando ele instalável em qualquer lugar.Isso significa que você pode instalar o Ghost em seu computador para testar de forma muito rápida e fácil.
                A próxima seção detalha como instalar o Ghost local no <a href="{% if page.lang %}/{{ page.lang }}{% endif %}/installation/mac/">Mac</a>,  <a href="{% if page.lang %}/{{ page.lang }}{% endif %}/installation/windows/">Windows</a> ou <a href="{% if page.lang %}/{{ page.lang }}{% endif %}/installation/linux/">Linux</a> ou, ajudar a colocar o Ghost para rodar em seu <a href="{% if page.lang %}/{{ page.lang }}{% endif %}/installation/deploy">servidor</a>.</p>


            <h3>Começando</h3>

            <p>Se você nao gosta de seguir instruções de como instalar o Node.js e o Ghost manualmente, o pessoal do <a href="http://bitnami.com/">BitNami</a> criou <a href="http://bitnami.com/stack/ghost">instaladores Ghost</a> para as principais plataformas.</p>

            <p>Eu quero instalar o Ghost no:</p>

            <div class="text-center install-ghost">
                <a href="{% if page.lang %}/{{ page.lang }}{% endif %}/installation/mac/" class="btn btn-success btn-large">Mac</a>
                <a href="{% if page.lang %}/{{ page.lang }}{% endif %}/installation/windows/" class="btn btn-success btn-large">Windows</a>
                <a href="{% if page.lang %}/{{ page.lang }}{% endif %}/installation/linux/" class="btn btn-success btn-large">Linux</a>
            </div>

            <p>Se você ja decidiu em colocar o Ghost em seu servidor, isso é uma ótima notícia! A documentação a seguite irá guia-lo sobre as várias formas de implantar o Ghost, de formas manuais a instaladores de um clique.</p>

            <div class="text-center install-ghost">
                <a href="{% if page.lang %}/{{ page.lang }}{% endif %}/installation/deploy/" class="btn btn-success btn-large">Colocar o Ghost no Ar</a>
            </div>


            <p>Lembra-se que o Ghost ainda é muito novo e a equipe está trabalhando duro para entregar funcionalidades em um ritmo furioso. Se você precisa atualizar o Ghost para a última versão, sigua nossa <a href="/installation/upgrading/">documentação para atualização</a>.
                Se você ficar preso, confira o <a href="{% if page.lang %}/{{ page.lang }}{% endif %}/installation/troubleshooting/">guia de solução de problemas</a>, ou se isso não te ajudar, entre em contato pelo <a href="http://ghost.org/forum">Ghost forum</a> onde a Administração e a comunidade estarão de braços abertos para ajudar com seus problemas.</p>

            {% if page.next_section || page.prev_section %}
            {% include pagination.html %}
            {% endif %}
        </section>
    </div>
</div>