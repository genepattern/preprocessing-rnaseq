# Preprocessing Bulk RNA-seq raw counts

---
#### Main takeaway
When using GSEA or ComparativeMarkerSelection, users must provide a file whith counts which are **not log-normalized**

---
<div class="alert alert-warning">
<p class="lead"> Internal note:  <i class="fa fa-exclamation-triangle"></i></p>
ComparativeMarkerSelection does have a parameter which asks if values are log-normalized, however I do not see difference in the results when selecting it.
</div>

#### Summary of results
1. Voom changes the shape of the distribution of counts, DESeq2 does not. Also, Voom drops more genes than DESeq2. Both DESeq2 and Voom keep the relative order of the unfiltered genes.
2. When using DESeq2's normalized counts in GSEA and ComparativeMarkerSelection, we observe biologically accurate results. When using Voom's non-log-normalized counts we see equivalent results. When using (Voom's) log-normalized counts we observe biologically non-accurate results

The following images were generated here (for point 1):
https://github.com/genepattern/preprocessing-rnaseq/blob/master/Bulk%20RNA-seq%20Preprocessing%20for%20GSEA%2B%20draft%203.ipynb

Summary of results for point 2:
GSEA RNK file's summary:
- Running GSEA

APS1829
