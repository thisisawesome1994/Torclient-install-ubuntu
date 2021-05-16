# Torclient-install-ubuntu
How to install tor client on ubuntu 20.04 LTS

(run as sudo or root, and run "apt update" before running any command. One command per line)
```
apt install apt-transport-https curl
echo "deb https://deb.torproject.org/torproject.org/ $(lsb_release -cs) main" > /etc/apt/sources.list.d/tor.list
curl https://deb.torproject.org/torproject.org/A3C4F0F979CAA22CDBA8F512EE8CBC9E886DDD89.asc | gpg --import
gpg --export A3C4F0F979CAA22CDBA8F512EE8CBC9E886DDD89 | apt-key add -
apt update
apt install tor tor-geoipdb torsocks deb.torproject.org-keyring
```


For creating tor routes, copy this:
```
SocksPort 9050
SocksPort 9052
SocksPort 9054
SocksPort 9056
SocksPort 9058
SocksPort 9060
SocksPort 9062
SocksPort 9064
SocksPort 9066
SocksPort 9068
SocksPort 9070
SocksPort 9072
SocksPort 9074
SocksPort 9076
SocksPort 9078
SocksPort 9080
SocksPort 9082
SocksPort 9084
SocksPort 9086
SocksPort 9088
SocksPort 9090
SocksPort 9092
SocksPort 9094
SocksPort 9096
SocksPort 9098
SocksPort 9100
SocksPort 9102
SocksPort 9104
SocksPort 9106
SocksPort 9108
SocksPort 9110
SocksPort 9112
SocksPort 9114
SocksPort 9116
SocksPort 9118
SocksPort 9120
SocksPort 9122
SocksPort 9124
SocksPort 9126
SocksPort 9128
SocksPort 9130
SocksPort 9132
SocksPort 9134
SocksPort 9136
SocksPort 9138
SocksPort 9140
SocksPort 9142
SocksPort 9144
SocksPort 9146
SocksPort 9148
SocksPort 9150
SocksPort 9152
SocksPort 9154
SocksPort 9156
SocksPort 9158
SocksPort 9160
SocksPort 9162
SocksPort 9164
SocksPort 9166
SocksPort 9168
SocksPort 9170
SocksPort 9172
SocksPort 9174
SocksPort 9176
SocksPort 9178
SocksPort 9180
SocksPort 9182
SocksPort 9184
SocksPort 9186
SocksPort 9188
SocksPort 9190
SocksPort 9192
SocksPort 9194
SocksPort 9196
SocksPort 9198
SocksPort 9200
SocksPort 9202
SocksPort 9204
SocksPort 9206
SocksPort 9208
SocksPort 9210
SocksPort 9212
SocksPort 9214
SocksPort 9216
SocksPort 9218
SocksPort 9220
SocksPort 9222
SocksPort 9224
SocksPort 9226
SocksPort 9228
SocksPort 9230
SocksPort 9232
SocksPort 9234
SocksPort 9236
SocksPort 9238
SocksPort 9240
SocksPort 9242
SocksPort 9244
SocksPort 9246
SocksPort 9248
SocksPort 9250
SocksPort 9252
SocksPort 9254
SocksPort 9256
SocksPort 9258
SocksPort 9260
SocksPort 9262
SocksPort 9264
SocksPort 9266
SocksPort 9268
SocksPort 9270
SocksPort 9272
SocksPort 9274
SocksPort 9276
SocksPort 9278
SocksPort 9280
SocksPort 9282
SocksPort 9284
SocksPort 9286
SocksPort 9288
SocksPort 9290
SocksPort 9292
SocksPort 9294
SocksPort 9296
SocksPort 9298
SocksPort 9300
SocksPort 9302
SocksPort 9304
SocksPort 9306
SocksPort 9308
SocksPort 9310
SocksPort 9312
SocksPort 9314
SocksPort 9316
```
and paste inside bottom of file: /etc/tor/torrc
