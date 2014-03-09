---
lang: pt-BR
layout: default
meta_title: Como instalar o Ghost no seu Servidor - Ghost Docs
meta_description: Tudo o que você precisa saber para colocar sua plataforma Ghost funcionando no seu ambiente local, ou em um ambiente remoto.
heading: Instalando o Ghost &amp; Começando
subheading: Os primeiros passos para configurar o seu Blog pela primeira vez.
permalink: /pt-BR/installation/deploy/
chapter: installation
prev_section: linux
next_section: upgrading
---

<div class="container">
    <div class="row">
        {% include subnav/installation.html %}

        <section id="content" class="col-lg-9">

            <h2 id="deploy">Colocando o Ghost no Ar</h2>

            <p>Então você está pronto para colocar o Ghost no ar? Excelente!</p>

            <p>A primeira decisão que você precisa fazer, é se você quer instalar e configurar o Ghost você mesmo, ou se prefere usar algum instalador.</p>

            <h3>Instaladores</h3>

            <p>Existem algumas opções de instaladores simples no momento:
                <ul>
                    <li>Publicar na nuvem com <a href="http://wiki.bitnami.com/Applications/BitNami_Ghost">Bitnami</a>.</li>
                    <li>Lançar o Ghost com <a href="http://developer.rackspace.com/blog/launch-ghost-with-rackspace-deployments.html">Rackspace deployments</a>.</li>
                    <li>Colocar no ar usando um <a href="https://www.digitalocean.com/community/articles/how-to-use-the-digitalocean-ghost-application">droplet da DigitalOcean</a>.</li>
                </ul>
            </p>

            <h3>Configuração Manual</h3>

            <p>Você irá precisar de um servidor que já tenha, ou lhe permita instalar o <a href="http://nodejs.org">Node.js</a>.
                Isso significa algo como o (<a href="http://aws.amazon.com/ec2/">Amazon EC2</a>, <a href="http://www.digitalocean.com">DigitalOcean</a>, <a href="http://www.rackspace.com/cloud/">Rackspace Cloud</a>), VPS (<a href="https://www.webfaction.com/">Webfaction</a>, <a href="http://www.dreamhost.com/servers/vps/">Dreamhost</a>) ou outro que lhe conceda acesso SSH (terminal) & que permita instalar o Node.js. Existem vários servidores do tipo, e eles podem ser bem baratos.</p>

            <p>O que não irá funcionar no momento é uma hospedagem compartilhada (como aquelas que usam o cPanel), esse tipo de hospedagem normalmente é destinado a aplicativos que rodam algo como o PHP. Alguns já oferecem suporte ao Ruby, e talvez um dia irão oferecer suporte ao Node.js ou algo similar.

            <p>Infelizmente alguns servidores cloud específicos para utilizar o Node.js como o <strong>Nodejitsu</strong> & <strong>Heroku</strong> <strong>NÃO</strong> são compatíveis com o Ghost. Eles irão funcionar no início, mas irão deletar seus arquivos, imagens e seu banco de dados irá desaparecer. O Heroku suporta MySQL e você pode usá-lo, porém você ainda assim irá perder suas imagens enviadas.</p>

            <p>Os links a seguir contém instruções de como configurar e rodar com:
                <ul>
                    <li><a href="http://www.howtoinstallghost.com/how-to-install-ghost-on-dreamhost/">Dreamhost</a> - por <a href="http://howtoinstallghost.com">howtoinstallghost.com</a></li>
                    <li><a href="http://ghosted.co/install-ghost-digitalocean/">DigitalOcean</a> - por <a href="http://ghosted.co">Corbett Barr</a></li>
                    <li><a href="http://www.howtoinstallghost.com/how-to-install-ghost-on-webfaction-hosting/">Webfaction</a> - por <a href="http://howtoinstallghost.com">howtoinstallghost.com</a></li>
                    <li><a href="http://ghost.pellegrom.me/installing-ghost-on-ubuntu/">Rackspace</a> (Ubuntu 13.04 + linux service) - por <a href="http://ghost.pellegrom.me/">Gilbert Pellegrom</a></li>
                    <li><a href="http://0v.org/installing-ghost-on-ubuntu-nginx-and-mysql/">Ubuntu + nginx + forever</a> - por <a href="http://0v.org/">Gregg Housh</a></li>
                    <li>...veja o <a href="https://en.ghost.org/forum/installation">forum de instalação</a> para mais guias...</li>
                </ul>
            </p>

            <h2>Fazendo o Ghost rodar ininterruptamente</h2>
            <p>O método anterior descrito para iniciar o Ghost é usando o comando <code>npm start</code>. Essa é uma boa maneira para um ambiente local de desenvolvimento, mas se você usar a linha de comando para iniciar o Ghost, ele irá parar sempre que você fechar a janela do terminal ou sair do SSH. Para evitar que o Ghost pare, você tem que rodar ele como um serviço. Existem duas maneiras de fazer isso.</p>

            <h3>Forever (<a href="https://npmjs.org/package/forever">https://npmjs.org/package/forever</a>)</h3>
            <p>Você pode usar o <code>forever</code> para rodar o Ghost como uma tarefa em segundo plano. O <code>forever</code> irá tomar conta para que sua instalação fique sempre no ar, reiniciando-a caso ele dê algum erro.</p>

            <ul>
                <li>
                    Para instalar o <code>forever</code> digite <code>npm install forever -g</code>
                </li>
                <li>
                    Para iniciar o Ghost usando o <code>forever</code>, do diretório da instalação do Ghost digite <code>NODE_ENV=production forever start index.js</code>
                </li>
                <li>
                    Para parar o processo do Ghost digite <code>forever stop index.js</code>
                </li>
                <li>
                    Para saber se o Ghost está rodando no momento use o comando <code>forever list</code>
                </li>
            </ul>

            <h3>Supervisor (<a href="http://supervisord.org/">http://supervisord.org/</a>)</h3>
            <p>Distribuições Linux populares &mdash; como o Fedora, Debian, e Ubuntu &mdash; possuem o pacote Supervisor: Um sistema de controle de processos que o permite de rodar o Ghost ao iniciar a máquina, sem utilizar scripts do tipo <em>init</em>. Diferente de um script do tipo <em>init</em>, o Supervisor é compatível com várias distribuições linux e suas versões.</p>
            <ul>
                <li>
                    <a href="http://supervisord.org/installing.html">Instale o Supervisor</a> em sua distribuição Linux. Normalmente você irá usar esses comandos:
                    <ul>
                        <li>
                            Debian/Ubuntu: <code>apt-get install supervisor</code>
                        </li>
                        <li>
                            Fedora: <code>yum install supervisor</code>
                        </li>
                        <li>
                            Maioria das outras distribuições: <code>easy_install supervisor</code>
                        </li>
                    </ul>
                </li>
                <li>
                    Tenha certeza que o Supervisor está rodando, digitando <code>service supervisor start</code>
                </li>
                <li>
                    Crie um script para sua instalação do Ghost. Normalmente isso irá ser salvo em <code>/etc/supervisor/conf.d/ghost.conf</code> Por exemplo:
                    <p><pre>
[program:ghost]
command = node /path/to/ghost/index.js
directory = /path/to/ghost
user = ghost
autostart = true
autorestart = true
stdout_logfile = /var/log/supervisor/ghost.log
stderr_logfile = /var/log/supervisor/ghost_err.log
environment = NODE_ENV="production"
                    </pre></p>
                </li>
                <li>
                    Iniciar o Ghost utilizando o Supervisor: <code>supervisorctl start ghost</code>
                </li>
                <li>
                    Para parar o Ghost: <code>supervisorctl stop ghost</code>
                </li>
            </ul>
            <p>Você pode ver a <a href="http://supervisord.org">documentação do Supervisor</a> para mais informações.</p>




            <h3>Init Script</h3>
            <p>Sistemas Linux utilizam scripts <em>init</em> para rodar um processo quando o sistema iniciar. Esses scripts ficam em /etc/init.d. Para fazer o Ghost rodar sempre, mesmo que a máquina seja reiniciada, você pode usar os scripts <em>init</em> para isso. O exemplo a seguir irá funcionar no Ubuntu e foi testado no <b>Ubuntu 12.04</b>.</p>

            <ul>
                <li>
                    Criar o arquivo /etc/init.d/ghost com o seguinte conteúdo:
                    <p><pre>
                        #! /bin/sh
### BEGIN INIT INFO
# Provides:          ghost
# Required-Start:    $network $syslog
# Required-Stop:     $network $syslog
# Default-Start:     2 3 4 5
# Default-Stop:      0 1 6
# Short-Description: Ghost Blogging Platform
# Description:       Ghost: Just a blogging platform
### END INIT INFO

# Do NOT "set -e"

# PATH should only include /usr/* if it runs after the mountnfs.sh script
PATH=/sbin:/usr/sbin:/bin:/usr/bin
DESC="Ghost"
NAME=ghost
GHOST_ROOT=/var/www/ghost
GHOST_GROUP=ghost
GHOST_USER=ghost
DAEMON=/usr/bin/node
DAEMON_ARGS="$GHOST_ROOT/index.js"
PIDFILE=/var/opt/ghost/run/$NAME.pid
SCRIPTNAME=/etc/init.d/$NAME
export NODE_ENV=production

# Exit if the package is not installed
[ -x "$DAEMON" ] || exit 0

# Read configuration variable file if it is present
[ -r /etc/default/$NAME ] && . /etc/default/$NAME

# Load the VERBOSE setting and other rcS variables
. /lib/init/vars.sh
# I like to know what is going on
VERBOSE = yes

# Define LSB log_* functions.
# Depend on lsb-base (>= 3.2-14) to ensure that this file is present
# and status_of_proc is working.
. /lib/lsb/init-functions

#
# Function that starts the daemon/service
#
do_start()
{
    # Set up folder structure
    mkdir -p /var/opt/ghost
    mkdir -p /var/opt/ghost/run
    chown -R ghost:ghost /var/opt/ghost
    # Return
    #   0 if daemon has been started
    #   1 if daemon was already running
    #   2 if daemon could not be started
    start-stop-daemon --start --quiet \
        --chuid $GHOST_USER:$GHOST_GROUP --chdir $GHOST_ROOT --background \
        --pidfile $PIDFILE --exec $DAEMON --test > /dev/null \
        || return 1
    start-stop-daemon --start --quiet \
        --chuid $GHOST_USER:$GHOST_GROUP --chdir $GHOST_ROOT --background \
        --pidfile $PIDFILE --exec $DAEMON -- $DAEMON_ARGS \
        || return 2
    # Add code here, if necessary, that waits for the process to be ready
    # to handle requests from services started subsequently which depend
    # on this one.  As a last resort, sleep for some time.
}

#
# Function that stops the daemon/service
#
do_stop()
{
    # Return
    #   0 if daemon has been stopped
    #   1 if daemon was already stopped
    #   2 if daemon could not be stopped
    #   other if a failure occurred
    start-stop-daemon --stop --quiet --retry=TERM/30/KILL/5 \
        --pidfile $PIDFILE --name $NAME
    RETVAL="$?"
    [ "$RETVAL" = 2 ] && return 2
    # Wait for children to finish too if this is a daemon that forks
    # and if the daemon is only ever run from this initscript.
    # If the above conditions are not satisfied then add some other code
    # that waits for the process to drop all resources that could be
    # needed by services started subsequently.  A last resort is to
    # sleep for some time.
    start-stop-daemon --stop --quiet --oknodo --retry=0/30/KILL/5 \
        --exec $DAEMON
    [ "$?" = 2 ] && return 2
    # Many daemons don't delete their pidfiles when they exit.
    rm -f $PIDFILE
    return "$RETVAL"
}

#
# Function that sends a SIGHUP to the daemon/service
#
do_reload() {
    #
    # If the daemon can reload its configuration without
    # restarting (for example, when it is sent a SIGHUP),
    # then implement that here.
    #
    start-stop-daemon --stop --signal 1 --quiet --pidfile $PIDFILE \
        --name $NAME
    return 0
}

case "$1" in
  start)
        [ "$VERBOSE" != no ] && log_daemon_msg "Starting $DESC" "$NAME"
        do_start
        case "$?" in
                0|1) [ "$VERBOSE" != no ] && log_end_msg 0 ;;
                2) [ "$VERBOSE" != no ] && log_end_msg 1 ;;
        esac
        ;;
  stop)
        [ "$VERBOSE" != no ] && log_daemon_msg "Stopping $DESC" "$NAME"
        do_stop
        case "$?" in
                0|1) [ "$VERBOSE" != no ] && log_end_msg 0 ;;
                2) [ "$VERBOSE" != no ] && log_end_msg 1 ;;
        esac
        ;;
  status)
       status_of_proc "$DAEMON" "$NAME" && exit 0 || exit $?
       ;;
  #reload|force-reload)
        #
        # If do_reload() is not implemented then leave this commented out
        # and leave 'force-reload' as an alias for 'restart'.
        #
        #log_daemon_msg "Reloading $DESC" "$NAME"
        #do_reload
        #log_end_msg $?
        #;;
  restart|force-reload)
        #
        # If the "reload" option is implemented then remove the
        # 'force-reload' alias
        #
        log_daemon_msg "Restarting $DESC" "$NAME"
        do_stop
        case "$?" in
          0|1)
                do_start
                do_start
                case "$?" in
                        0) log_end_msg 0 ;;
                        1) log_end_msg 1 ;; # Old process is still running
                        *) log_end_msg 1 ;; # Failed to start
                esac
                ;;
          *)
                # Failed to stop
                log_end_msg 1
                ;;
        esac
        ;;
  *)
        #echo "Usage: $SCRIPTNAME {start|stop|restart|reload|force-reload}" >&2
        echo "Usage: $SCRIPTNAME {start|stop|status|restart|force-reload}" >&2
        exit 3
        ;;
esac

:
                    </pre></p>
                </li>
                <li>
                    Mude as permissões do arquivo utilizando o comando
                    <code>chmod 755 /etc/init.d/ghost</code>
                </li>
                <li>
                    Utilizando o script:
                    <ul>
                        <li>Iniciar: <code>service ghost start</code></li>
                        <li>Parar: <code>service ghost stop</code></li>
                        <li>Reiniciar: <code>service ghost restart</code></li>
                        <li>Estado Atual: <code>service ghost status</code></li>
                    </ul>
                </li>
                <li>
                    Para iniciar o Ghost junto com o sistema utilizando o script <em>init</em> que acabamos de criar, você precisa registrá-lo no sistema. Para isso, utilize os seguintes comandos no terminal: <code>update-rc.d ghost defaults</code> e <code>update-rc.d ghost enable</code>
                </li>
            </ul>

            <p>Documentação sobre como usar o <em>node forever</em> e como usar o Ghost como <em>daemon</em> no Ubuntu em breve!</p>

            <h2>Configurando o Ghost com seu domínio</h2>

            <p>Documentação utilizando nginx como proxy reverso à caminho.</p>

            {% if page.next_section || page.prev_section %}
                {% include pagination.html %}
            {% endif %}
        </section>
    </div>
</div>
