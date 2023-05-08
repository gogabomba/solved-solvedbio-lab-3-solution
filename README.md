Download Link: https://assignmentchef.com/product/solved-solvedbio-lab-3-solution
<br>
Input:

· Input files: one or more GFF files

· Reference files: FASTA file(s) of the entire sequence of contigs referenced by the GFF file(s). (note: Number values in columns 4 and 5 of the GFF files indicate a nucleotide position in the respective reference file)

· see attachment for how to interpret a GFF file

Processing Instructions:

For each input file calculate:

1. Average gene span per contig/fosmid. Average number of nucleotides between the highest position indicated and the lowest position indicated in all features with the same gene_id in column 9

2. Average length of CDS per contig/fosmid. Average coding DNA sequence size, sum of the CDS regions with the same gene_id (see Figure 1 below)

3. Average size of exon per contig/fosmid. Average number of nucleotides between the first position and the last position indicated in features marked CDS in the GFF files.

4. Average size of intron per contig. Average number of nucleotides between the last position of a CDS region and the first position of the subsequent CDS region with the same transcript_id (see Figure 1 below)

5. Average intergenic region size per contig. Average number of nucleotides between the last nucleotide of the stop codon and the first nucleotide of the next gene (distance between subsequent gene spans with different gene_id’s in column 9 of the GFF file, see Figure 2 below).

6. Average density of nucleotides in a CDS span per contig. Average number of nucleotides in each “Coding DNA Sequence,” multiplied by the number different gene_id’s, divided by the total number of nucleotides in the entire reference sequence.

7. Average density of nucleotides in a CDS region per contig. Average number of nucleotides in each CDS region, multiplied by the number different gene_id’s, divided by the total number of nucleotides in the entire reference sequence

8. Proportion of CDS nucleotides per contig. Total number of nucleotides in all CDS regions divided by total number of nucleotides in the reference sequence. If one or more CDS regions overlap, choose the longest CDS region for calculations (see Figure 3 below)

9. Average Number of Genes per 10KB total number of gene spans with the same gene_id in column 9 divided by total number of nucleotides in the reference sequence multiplied by 10^4 (1 KB = 10^3 nucleotides)

10. KB’s per Gene total number of nucleotides in the reference sequence in KB’s (1 KB = 10^3 nucleotides) divided by the number of gene spans with different gene_id’s in column 9

11. Predicted protein sequence use features with identical labels in column 9 and marked CDS to obtain nucleotide sequence to be used, join these sequences in order of lowest position to highest position indicated by these features. If column 7 is marked + then proceed to translation, if column 7 is marked – then the reverse complement needs to be created before translation. Translate the appropriate sequence using chart in Figure 4 below

Figure 1. Gene Span vs. Coding DNA Sequence Size

Figure 2. Intergenic Region

Figure 3. In the Case of Overlapping Exons/CDS Regions

Figure 4. Codon Translation Chart

Output instructions:

· data should be organized as follows:

Input 1Input 2Average gene length

Average length of CDS

Average size of exon

Average size of intron

Average intergenic region size

Average density of nucleotides in a CDS span

Average density of nucleotides in a CDS region

Proportion of CDS nucleotides

Genes per 10 KB

KB’s per Gene

Predicted Protein Sequence

GFF Format:

Column 1: sequence name (example: fosmid 10, contig 18, etc.)

Column 2: name of the program that generated the sequence (database, research project name, etc)

Column 3: feature type (mRNA = entire coding DNA sequence of all exons with no stop codon, CDS = DNA sequence of an individual exon including any stop codons)

Column 4: number/position of the first nucleotide in the indicated feature if numbering starts at the beginning of the reference sequence and starts with 1

Column 5: number/position of the last nucleotide in the indicated feature if numbering starts at the beginning of the reference sequence and starts with 1

Column 6: score = floating point value… I don’t actually know what that means, and the example we were given shows them all as blank…

Column 7: which strand the indicated feature is on; + = forward strand, – = reverse strand

Column 8: frame number; 0 = first base of the indicated feature is the first base of a codon, 1 = second base of the indicated feature is the second base of a codon, 2 = third base of the indicated feature is the first base of a codon

Column 9: provides additional information about each feature, with information surrounded by quotation marks and each piece is separated by a semicolon and the field ends with a semicolon. gene_id = gene name, transcript_id = isoform of the gene (ex: gene_id “CG7970”; transcript_id “CG7970-RB”)

Additional information to keep in mind:

each row is called a featurefields must be tab-separatedall fields within each feature line must contain a valueif a column needs to be “empty” then it is denoted by a “.”file may contain additional features with feature names “cigar” and “score,” these are to be ignoredfeatures may not be listed in any order

Example:

fosmid10 . mRNA 736 4493 . – . gene_id “alphaCop”; transcript_id “alphaCop-RA”;

fosmid10 . CDS 3548 4493 . – . gene_id “alphaCop”; transcript_id “alphaCop-RA”;

fosmid10 . CDS 733 3491 . – . gene_id “alphaCop”; transcript_id “alphaCop-RA”;

fosmid10 . mRNA 736 4493 . – . gene_id “alphaCop”; transcript_id “alphaCop-RB”;

fosmid10 . CDS 3548 4493 . – . gene_id “alphaCop”; transcript_id “alphaCop-RB”;

fosmid10 . CDS 733 3491 . – . gene_id “alphaCop”; transcript_id “alphaCop-RB”;

fosmid10 . mRNA 5056 5448 . + . gene_id “CG13919”; transcript_id “CG13919-RA”;

fosmid10 . CDS 5056 5451 . + . gene_id “CG13939”; transcript_id “CG13919-RA”;

IF IN NEED OF THE OTHER BIO LABS PLEASE INBOX ME