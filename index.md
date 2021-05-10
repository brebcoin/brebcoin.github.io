# Welcome to breb


## breb explorer - http://78.47.183.108/

## Getting started
- download brebcoin core https://github.com/brebcoin/brebcoin/releases/tag/0.4.2.0
- make brebcoin.conf in %appdata%\Brebcoin or edit the file by clicking `open configuration file` in settings -> options on the bottom left
- add these lines
  - `addnode=78.47.159.46:1337`
  - `addnode=78.47.183.108:1337`

## To receive breb:
  - under the 'receive' tab, click 'request payment', copy the address
  - You will also need a legacy address. Open the console from window -> console. Enter `getnewaddress addrnamehere legacy`

## To solo mine:
 - add `server=1` to brebcoin.conf
 - Find brebcoin-cli.exe (should be at C:\Program Files\Brebcoin\daemon )
 - Make a .bat script in the same location with the following script:
```
echo Mining... Press [CTRL+C] to stop
:loop
	brebcoin-cli.exe generatetoaddress 1 youraddresshere
goto loop
```

## To mine on brebpool:
 - download a scrypt miner (here's one https://github.com/pooler/cpuminer/releases/tag/v2.5.1)
 - mine to stratum+tcp://78.47.159.46:3032, **MAKING SURE TO USE YOUR LEGACY ADDRESS**
 - example .bat for cpuminer (where -t refers to the number of mining threads):
```
minerd.exe --url=stratum+tcp://78.47.159.46:3032 --userpass=LEGACYADDRESSHERE:doesntmatter -t 1
```
