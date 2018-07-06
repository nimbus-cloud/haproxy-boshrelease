#!/bin/bash -e

export PATH=/var/vcap/packages/ruby/bin:$PATH
RUN_DIR=/var/vcap/sys/run/tcp-agent
LOG_DIR=/var/vcap/sys/log/tcp-agent
PIDFILE=$RUN_DIR/tcp-agent.pid
JOB_DIR=/var/vcap/jobs/tcp-agent
DATA_DIR=/var/vcap/data/tcp-agent

export TMPDIR=/var/vcap/data/tcp-agent/tmp

source /var/vcap/packages/common/utils.sh

case $1 in

  start)
    pid_guard $PIDFILE "DEA"

    mkdir -p $RUN_DIR
    mkdir -p $LOG_DIR
    mkdir -p $DATA_DIR
    mkdir -p $TMPDIR
    
    chown -R vcap:vcap $RUN_DIR
    chown -R vcap:vcap $LOG_DIR
    chown -R vcap:vcap $DATA_DIR
    chown -R vcap:vcap $TMPDIR 

    echo $$ > $PIDFILE

    ulimit -c unlimited

    cd /var/vcap/packages/tcp-agent
    export RACK_ENV=production
    export SETTINGS_FILENAME=$JOB_DIR/config/settings.yml
    exec chpst -u vcap:vcap bundle exec rackup <% unless p('tcp_agent.managed_by_broker') %>--host 127.0.0.1<% end %> \
         >>$LOG_DIR/tcp-agent.stdout.log \
         2>>$LOG_DIR/tcp-agent.stderr.log

    ;;

  stop)
    kill_and_wait $PIDFILE 40

    ;;

  *)
    echo "Usage: tcp-agent_ctl {start|stop}"

    ;;

esac
