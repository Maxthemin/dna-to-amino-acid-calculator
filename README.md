# dna-to-amino-acid-calculator
import random

def toc():
	fun.seek(0)
	mrna.seek(0)
	count = 0
	while True:
		count = count + 1
		x = fun.read(1)#makes x equvilent to funread 
		y =mrna.read(1)#
		if not x or not y:
			break
		print(count,'\t',x,'-',y)

amino = {
	'uuu':'phe',
	'uuc':'phe',
	'uua':'leu',
	'uug':'leu',
	'cuu':'leu',
	'cuc':'leu',
	'cua':'leu',
	'cug':'leu',
	'auu':'lle',
	'auc':'lle',
	'aua':'lle',
	'aug':'met',
	'guu':'val',
	'guc':'val',
	'gua':'val',
	'gug':'val',
	'ucu':'ser',
	'ucc':'ser',
	'uca':'ser',
	'ucg':'ser',
	'ccu':'pro',
	'ccc':'pro',
	'cca':'pro',
	'ccg':'pro',
	'auc':'thr',
	'acc':'thr',
	'aca':'thr',
	'acg':'thr',
	'gcu':'ala',
	'gcc':'ala',
	'gca':'ala',
	'gcg':'ala',
	'uau':'tyr',
	'uac':'tyr',
	'uaa':'stop',
	'uag':'stop',
	'cau':'his',
	'cac':'his',
	'caa':'gin',
	'cag':'gin',
	'aau':'asn',
	'aac':'asn',
	'aaa':'lys',
	'aag':'lys',
	'gau':'asp',
	'gac':'asp',
	'gaa':'glu',
	'gag':'glu',
	'ugu':'cys',
	'ugc':'cys',
	'uaa':'stop',
	'ugg':'trp',
	'cgu':'arg',
	'cgc':'arg',
	'cga':'arg',
	'cgg':'arg',
	'agu':'ser',
	'agc':'ser',
	'aga':'arg',
	'agg':'arg',
	'ggu':'gly',
	'ggc':'gly',
	'gga':'gly',
	'ggg':'gly',
	}

mrna = open('mrna.txt','w+')
fun = open('randomfun.txt','w+')
nb = ('a','t','c','g')

for z in range(0,12):
    temp = random.choice(nb)
    fun.write (temp)

fun.seek(0)

while True:  
    covd19=fun.read(1)
    if not covd19:
    	break

    if covd19 == 'a':
        mrna.write('u')#writing to the file the new character
        #print(covd19)#prints to screen 
    elif covd19 == 't':
  	    mrna.write('a')#writing to the file the new character
  	    #print(covd19)#prints to screen 
    elif covd19 == 'g':
  	    mrna.write('c')#writing to the file the new character
  	    #print(covd19)#prints to screen 
    elif covd19 == 'c':
        mrna.write('g')#writing to the file the new character
        #print(covd19)#prints to screen 

fun.close()#closes the file fun
mrna.seek(0)
while True:
	seq = mrna.read(3)
	if not seq:
		break
	print(seq,' - ',amino.get(seq))
	


mrna.close()
