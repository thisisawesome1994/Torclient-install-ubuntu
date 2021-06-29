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
SocksPort 9318
SocksPort 9320
SocksPort 9322
SocksPort 9324
SocksPort 9326
SocksPort 9328
SocksPort 9330
SocksPort 9332
SocksPort 9334
SocksPort 9336
SocksPort 9338
SocksPort 9340
SocksPort 9342
SocksPort 9344
SocksPort 9346
SocksPort 9348
SocksPort 9350
SocksPort 9352
SocksPort 9354
SocksPort 9356
SocksPort 9358
SocksPort 9360
SocksPort 9362
SocksPort 9364
SocksPort 9366
SocksPort 9368
SocksPort 9370
SocksPort 9372
SocksPort 9374
SocksPort 9376
SocksPort 9378
SocksPort 9380
SocksPort 9382
SocksPort 9384
SocksPort 9386
SocksPort 9388
SocksPort 9390
SocksPort 9392
SocksPort 9394
SocksPort 9396
SocksPort 9398
SocksPort 9400
SocksPort 9402
SocksPort 9404
SocksPort 9406
SocksPort 9408
SocksPort 9410
SocksPort 9412
SocksPort 9414
SocksPort 9416
SocksPort 9418
SocksPort 9420
SocksPort 9422
SocksPort 9424
SocksPort 9426
SocksPort 9428
SocksPort 9430
SocksPort 9432
SocksPort 9434
SocksPort 9436
SocksPort 9438
SocksPort 9440
SocksPort 9442
SocksPort 9444
SocksPort 9446
SocksPort 9448
SocksPort 9450


```
and paste inside bottom of file: /etc/tor/torrc

For public setup, such as in a VPS, 
you could make the torroutes private, since
you dont want your connection to tor to be public.

To do this, add this instead:

(Dont Forget to change the IP address presented as X.X.X.X)


```
SocksPort 0.0.0.0:9050
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9052
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9054
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9056
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9058
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9060
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9062
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9064
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9066
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9068
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9070
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9072
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9074
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9076
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9078
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9080
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9082
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9084
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9086
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9088
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9090
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9092
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9094
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9096
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9098
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9100
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9102
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9104
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9106
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9108
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9110
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9112
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9114
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9116
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9118
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9120
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9122
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9124
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9126
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9128
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9130
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9132
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9134
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9136
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9138
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9140
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9142
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9144
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9146
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9148
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9150
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9152
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9154
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9156
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9158
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9160
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9162
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9164
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9166
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9168
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9170
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9172
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9174
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9176
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9178
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9180
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9182
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9184
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9186
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9188
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9190
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9192
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9194
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9196
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9198
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9200
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9202
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9204
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9206
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9208
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9210
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9212
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9214
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9216
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9218
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9220
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9222
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9224
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9226
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9228
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9230
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9232
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9234
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9236
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9238
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9240
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9242
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9244
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9246
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9248
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9250
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9252
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9254
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9256
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9258
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9260
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9262
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9264
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9266
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9268
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9270
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9272
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9274
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9276
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9278
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9280
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9282
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9284
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9286
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9288
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9290
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9292
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9294
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9296
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9298
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9300
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9302
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9304
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9306
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9308
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9310
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9312
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9314
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9316
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9318
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9320
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9322
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9324
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9326
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9328
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9330
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9332
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9334
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9336
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9338
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9340
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9342
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9344
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9346
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9348
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9350
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9352
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9354
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9356
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9358
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9360
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9362
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9364
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9366
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9368
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9370
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9372
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9374
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9376
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9378
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9380
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9382
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9384
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9386
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9388
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9390
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9392
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9394
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9396
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9398
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9400
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9402
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9404
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9406
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9408
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9410
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9412
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9414
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9416
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9418
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9420
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9422
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9424
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9426
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9428
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9430
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9432
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9434
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9436
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9438
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9440
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9442
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9444
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9446
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9448
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *
SocksPort 0.0.0.0:9450
SocksPolicy accept X.X.X.X/32
SocksPolicy reject *

```
