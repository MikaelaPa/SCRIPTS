# SCRIPTS
Comandos para obtener la filogenia de la familia Riodinidae
## DESCARGAR SECUENCIAS

esearch -db nucleotide -query "Riodinidae[Organism] AND COI" | efetch -format fasta > Riodinidae_COI.fasta

## ALINEAMIENTO

./muscle3.8.31_i86linux64 -in Riodinidae_COI.fasta -out muscle_Riodinidae_COI.fasta -maxiters 1 -diags

## CARGAR IQtree

module load iqtree/2.2.2.6

## FILOGENIA

#!/bin/bash

#$ -l highp,h_rt=60:00:00,h_data=10G
#$ -pe shared 1
#$ -N SMPNGeneCalculator
#$ -cwd
#$ -m bea
#$ -o /u/scratch/d/dechavez/Bioinformatica-PUCE/RediseBio/MikaelaPa/TrabajoFinal/GeneCalcular$
#$ -e /u/scratch/d/dechavez/Bioinformatica-PUCE/RediseBio/MikaelaPa/TrabajoFinal/GeneCalculat$
#$ -M dechavezv

source /u/local/Modules/default/init/modules.sh
module load iqtree/2.2.2.6


iqtree2 -s muscle_Riodinidae_COI.fasta

## DESCARGAR ARCHIVO A DESKTOP PERSONAL

Desde otra pestaña nueva de Git Bash fuera de Hoffman2

cd Desktop

scp dechavez@hoffman2.idre.ucla.edu:/u/scratch/d/dechavez/Bioinformatica-PUCE/RediseBio/MikaelaPa/TrabajoFinal/muscle_Riodinidae_COI.fasta.treefile

## ATOM

Open file
Find 
Remplace in buffer
Seleccionamos .*
Usamos regular expresions


## REEMPLAZAR CODIGO NCBI CON GENERO Y ESPECIE

USAR PROGRAMA ChangeIDs.sh

## FIGTREE

Open archivo .tree (En este caso butterfly.tree)
