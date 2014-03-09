---
lang: pt-BR
layout: default
meta_title: Como instalar o Ghost no seu Servidor - Ghost Docs
meta_description: Tudo o que você precisa saber para colocar sua plataforma Ghost funcionando no seu ambiente local, ou em um ambiente remoto.
heading: Instalando o Ghost &amp; Começando
subheading: Os primeiros passos para configurar o seu Blog pela primeira vez.
permalink: /pt-BR/installation/mac/
chapter: installation
prev_section: installation
next_section: windows
---

<div class="container">
    <div class="row">
        {% include subnav/installation.html %}

        <section id="content" class="col-lg-9">

            <h1 id="install-mac">Instalando no Mac</h1>

            <p>Para instalar o Node.js e o Ghost no seu mac, você terá que abrir uma janela do Terminal. Você pode abrir essa janela digitando "Terminal" na busca do Spotlight.</p>

            <h3>Instalando o Node.js</h3>

            <ul>
                <li>Abra <a href="http://nodejs.org">http://nodejs.org</a> clique "install", irá iniciar o download de um arquivo '.pkg'</li>
                <li>Abra o instalador. Ele irá instalar o Node.js e o npm</li>
                <li>Avance na instalação, finalizando com sua senha e clicando em "Instalar Aplicativo".</li>
                <li>Uma vez que a instalação foi concluida, abra uma janela do Terminal e escreva <code>echo $PATH</code> para verificar que '/usr/local/bin/' está escrito.</li>
            </ul>

            <p class="note"><strong>Nota:</strong> Se '/usr/local/bin' não aparecer no seu $PATH, veja o <a href="#export-path">guia de resolução de problemas</a> para descobrir como adicionar</p>

            <p>Se você ficar perdido, você pode assistir <a href="https://s3-eu-west-1.amazonaws.com/ghost-website-cdn/install-node-mac.gif" title="Install Node on Mac">o processo aqui</a>.</p>

            <h3>Instalando e Rodando o Ghost</h3>

            <ul>
                <li>Autentique-se em <a href="http://ghost.org">http://ghost.org</a>, e depois clique no botão 'Download Ghost Source Code'.</li>
                <li>Na página de Downloads, clique para fazer o download do arquivo zip mais recente.</li>
                <li>Clique na seta proxima ao arquivo que foi feito download e clique em 'exibir no finder'.</li>
                <li>No finder, clique duas vezes no arquivo zip para extrai-lo.</li>
                <li>Depois, pegue a pasta extraída 'ghost-#.#.#' e arraste para a barra de abas do seu terminal. Isso fará com que seja criada uma nova aba na pasta do Ghost.</li>
                <li>Na nova janela do terminal, escreva <code>npm install --production</code> <span class="note">Não esqueça os dois traços</span></li>
                <li>Quando o npm terminal a instalação, escreva <code>npm start</code> para iniciar o Ghost em modo de desenvolvimento</li>
                <li>No seu navegador, navegue para <code class="path">127.0.0.1:2368</code> para acessar o seu Ghost Blog</li>
                <li>Altere a url para <code class="path">127.0.0.1:2368/ghost</code> e crie seu usuário administrador para se autenticar com seu Ghost.</li>
                <li>Veja o <a href="/usage">manual de uso</a> para maiores instruções sobre os próximos passos</li>
            </ul>

            <img width="100%" src="https://s3-eu-west-1.amazonaws.com/ghost-website-cdn/install-ghost-mac.gif" />

            {% if page.next_section || page.prev_section %}
                {% include pagination.html %}
            {% endif %}
        </section>
    </div>
</div>