t2t = ./t2t.mjs


all : abcidentity abcjs abccl abcpy test.abcmeta abcmetajs abcmetapy

abcjs : abc.ohm abcjs.rwr test.abc ${t2t}
	@echo 'Javascript'
	@node ${t2t} abc.ohm abcjs.rwr test.abc
	@echo

abccl : abc.ohm abccl.rwr test.abc ${t2t}
	@echo 'Lisp'
	@node ${t2t} abc.ohm abccl.rwr test.abc
	@echo

abcpy : abc.ohm abcpy.rwr test.abc ${t2t}
	@echo 'Python'
	@node ${t2t} abc.ohm abcpy.rwr test.abc
	@echo

abcidentity : abc.ohm abcidentity.rwr test.abc ${t2t}
	@echo 'Identity'
	@node ${t2t} abc.ohm abcidentity.rwr test.abc
	@echo

abcmetajs : abcmeta.ohm abcmetajs.rwr test.abcmeta ${t2t}
	@echo 'Javascript from Meta (test.abcmeta)'
	@node ${t2t} abcmeta.ohm abcmetajs.rwr test.abcmeta
	@echo

abcmetapy : abcmeta.ohm abcmetapy.rwr test.abcmeta ${t2t}
	@echo 'Python from Meta (test.abcmeta)'
	@node ${t2t} abcmeta.ohm abcmetapy.rwr test.abcmeta
	@echo

test.abcmeta : abccl
	@echo 'Meta'
	@node ${t2t} abc.ohm abccl.rwr test.abc >test.abcmeta
	@cat test.abcmeta
	@echo

install-js-requires:
	npm install yargs prompt-sync ohm-js
