t2t = ~/projects/t2t/t2t.mjs


all : abcjs abccl abcmetajs abcmetapy

abcjs : abc.grammar abcjs.rewrite test.abc ${t2t}
	node ${t2t} abc.grammar abcjs.rewrite test.abc

abccl : abc.grammar abccl.rewrite test.abc ${t2t}
	node ${t2t} abc.grammar abccl.rewrite test.abc

abcmetajs : abcmeta.grammar abcmetajs.rewrite test.abcmeta ${t2t}
	node ${t2t} abcmeta.grammar abcmetajs.rewrite test.abcmeta

abcmetapy : abcmeta.grammar abcmetapy.rewrite test.abcmeta ${t2t}
	node ${t2t} abcmeta.grammar abcmetapy.rewrite test.abcmeta

test.abcmeta : abccl
	node ${t2t} abc.grammar abccl.rewrite test.abc >test.abcmeta
