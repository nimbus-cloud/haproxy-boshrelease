#!/bin/bash

RUN_DIR=/var/vcap/sys/run/tcp-agent
PIDFILE=$RUN_DIR/tcp-agent.pid

if [ -f $PIDFILE ]; then
  pid=$(cat $PIDFILE)
  kill $pid        # process is running; kill it softly
  sleep 10         # wait a bit
  kill -9 $pid     # kill it hard
  rm -rf $PIDFILE # remove pid file
fi

echo 0 # ok to exit; do not wait for anything

exit 0