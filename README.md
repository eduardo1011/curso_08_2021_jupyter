fasta = open('fastas/CONIDIATION_RELATED.fasta')
fastas = fasta.read()
fasta.close()
fasta2 = open('phosphoproteomic_FDR1_all_conditions.fasta')
fastas2 = fasta2.read()
fasta2.close()
fasta3 = open('500485.fasta')
fastas3 = fasta3.read()
fasta3.close()
def find_seq(iden = '', org = ''):
    if org == 'nidu':
        for i in fastas.split('>')[1:]:
            i = i.rstrip()
            identificador = re.search('\w+', i).group()
            if iden == identificador:
                secuencia = re.sub(identificador, '', i)
                secuencia = re.sub('\n', '', secuencia)
                secuencia = re.sub('[*]', '', secuencia)
                return secuencia
                break
    if org == 'peni':
        for i in fastas2.split('>')[1:]:
            i = i.rstrip()
            identificador = re.search('\w+', i).group()
            if iden == identificador:
                secuencia = re.sub(identificador, '', i)
                secuencia = re.sub('\n', '', secuencia)
                secuencia = re.sub('[*]', '', secuencia)
                return secuencia
                break
    if org == 'peniRef':
        for i in fastas3.split('>')[1:]:
            i = i.rstrip()
            identificador = re.search('\w+', i).group()
            if iden == identificador:
                secuencia = re.sub(identificador, '', i)
                secuencia = re.sub('\n', '', secuencia)
                secuencia = re.sub('[*]', '', secuencia)
                return secuencia
                break
