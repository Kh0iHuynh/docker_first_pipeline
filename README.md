# docker_first_pipeline
All files with correct_ prefix are just backup.
NOTE: in both atac and rna pipeline.sh, file inputs must be fixed to matched output of trimgalore step

# to build container with docker, Dockerfile must be in current directory ./
docker build -t bio-pipeline .

# to run atac_pipeline.sh on paired end ATAC fastq
sudo docker run -v $(pwd):/data -w /data bio-pipeline ./atac_pipeline.sh ./SRR891268_chr22_enriched_R1.fastq.gz ./SRR891268_chr22_enriched_R2.fastq.gz ./reference/chr22_hg38

# to run rna_pipeline.sh on single end RNA fastq
sudo docker run -v $(pwd):/data -w /data bio-pipeline ./rna_pipeline.sh SRR30355391_RNA.fastq ./reference/rna_reference/STAR/ ./reference/rna_reference/gencode.v29.primary_assembly.annotation.chr19.gtf
