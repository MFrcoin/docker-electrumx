
# MFCoin electrumx-docker

An easily configurable Docker image for running an Electrum server.

## Run

Make sure your local docker and docker-compose installation can handle docker-compose syntax `3.5`. This basically means: "run latest code".

> mkdir -p  /opt/electrum/{mfcoin,db}

> docker-compose up -d

or

```
docker run \
  -v $HOME/electrumx:/data \
  -e DAEMON_URL=user:pass@host \
  -e COIN=MFCoin \
  -p 50002:50002 \
  mfcoin/electrumx
```

## Tweak

Edit "environment" sections of `mfcoind` and `electrumx` in `docker-compose.yml` to setup the ElectrumX daemon.
Note: Your electrumx DAEMON_URL **must** end in `@mfcoind` e. g. `DAEMON_URL=USER:PASS@mfcoind`

You can view all ElectrumX environment variables here: https://github.com/kyuupichan/electrumx/blob/master/docs/environment.rst
