# Makefile for an eosio smart contact

CC=eosio-cpp
Contract=onesgamemine
Account=onesgamemine

build:
	@echo "Building"
	$(CC) -abigen $(Contract).cpp -o $(Contract).wasm -I ./
 	#$(CC) $(Contract).cpp -o $(Contract).wasm

clean:
	rm -f *.abi
	rm -f $(Contract).wasm

test: 
	cleos --url=https://jungle3.cryptolions.io set contract $(Account) ../$(Contract) --abi ./$(Contract).abi  -p $(Account)@active

testabi: 
	cleos --url=https://jungle3.cryptolions.io set abi $(Account) ./$(Contract).abi  -p $(Account)@active

deploy:
	cleos --url=https://eospush.tokenpocket.pro set contract $(Account) ../$(Contract) --abi ./$(Contract).abi -p $(Account)@active

deployabi:
	cleos --url=https://eospush.tokenpocket.pro set abi $(Account) ./$(Contract).abi -p $(Account)@active

deployall:
	cleos --url=https://eospush.tokenpocket.pro set contract $(Account) ../$(Contract) --abi ./$(Contract).abi  -p $(Account)@active

unlockmain:
	cleos wallet unlock -n onesmain --password PW5KJP1STVLLTJeNaX9kaQEGnVCHSoAEjLZLvARrktJADMKi1nDRG 

unlocktest:
	cleos wallet unlock -n onestest --password PW5JBAmM8mX3V5NpszdrjASxpmomj3hp1R1wsxxZm2YrJZHc33QSD
	
buyram:
	cleos --url=https://jungle3.cryptolions.io system buyram "${Account}" "${Account}" "10.0000 EOS"

issuemarkettest:
	cleos --url=https://jungle3.cryptolions.io push action eosonestoken issue '[ "onesgamemine", "36.0000 ONES", "issuemarket,3,0" ]' -p onesgameplay@active

transfertest:
	cleos --url=https://jungle3.cryptolions.io push action eosio.token transfer '[ "onesgamehero", "onesgamemine", "1.0000 EOS", "mine" ]' -p onesgamehero@active

inittest:
	cleos --url=https://jungle3.cryptolions.io  push action onesgamemine init '[]' -p onesgamemine@active

minetest:
	cleos --url=https://jungle3.cryptolions.io  push action onesgamemine mineswap '["onesgamehero","10.0000 EOS"]' -p onesgamedefi@active

init:
	cleos --url=https://eospush.tokenpocket.pro push action onesgamemine init '[]' -p onesgamemine@active

remove:
	cleos --url=https://jungle3.cryptolions.io push action "${Account}" remove '[ "100" ]' -p onesgamehero@active

addcode:
	cleos --url=https://jungle3.cryptolions.io set account permission onesgamemine active onesgamemine --add-code