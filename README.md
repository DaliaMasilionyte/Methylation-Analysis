# Methylation-Analysis
Reproducing results of an article "Genome-wide Methylation Profiles Reveal Quantitative Views of Human Aging Rates" with R.

##   PASTEBEJIMAI
 1) Mum nereikia siustis anotacijos atskirai, kadangi dabar ir pats datasetas(GSE40279) ir platforma GPL13534 yra 450k. Pirmam darbe reikejo nes skyresi.
 2) Imputuoti nieko nereikia - sum(is.na(betaMatrix) parodo kad missing values nera.
 3) anotacija <- fData((GSE40279[[1]])) ->
 4) Naudojo autosomines chromosomas - reikia salinti lytines
 5) Lasteliu kiekiai jau yra - su mefill(daug dependencies) gse35069 - standartinis kraujui.
 
# Tyrimas
 - 2 grupės -> N1 = 482, N2 = 174 (656 is viso)
 - is mix populiacijos - 426 Caucasian ir 230 Hispanic(656 is viso)
 - Amzius : nuo 19 iki 101.
 - Krauja paeme ir naudojo 450 k Illumina
 - Metilinimo reiksme tarp 0<x<1 >
 
# Metodai
 1) Mėginių rinkimo ir testavimo procedūros(paruosia meginius - is sito nieko nedarome).
 2) Veiksmai kuriuos reikia atlikti pries tai - DONE.
 3) Metilinimo kokybės kontrolė
	- PCA
	- Lytiniu salinimas
	- Outliers
	- PCA
	- Z-statistika(?) - su Gaussian cumulative distribution and the Benjamini-Hochberg procedure.
	
 4) Association testing
	- F testas, linear modeliai.
	-  Kovariatoriai
	-  Binomial test, TCGA
 
 5) Annotation Enrichment
 	- Illumina db is Bioconductor
	- Fisher testas
 
 6) Senejimo modelis
 	- glmnet paketas
	- Lasso and ridge regresija
	- crossvalidation
	- bootstrap analize
	- AMAR
  
  7) Genetinių variantų asociacijos
	- F testas, linear models
	- Kovariatoriai
		
  8) Computing Methylation Deviance
	- Metilinimo trendu salinimas
	- Shapiro Wilk
	- Benjamini-Hochberg
		
  9) Entropija
        - Shannon entropy
		
  10) CpG saleliu mappinimas
	- ...
# Pagrindine mintis		
	The search for molecular markers of age that can be used to predict, monitor, and provide insight into age-associated physiological decline and disease. 
	One such marker is telomere length, a molecular trait strongly correlated with age 
	Another marker is gene expression, especially for genes that function in metabolic and DNA repair 
pathways, which are predictive of age across a range of different tissue types and organisms
	Thus, the idea of the epigenome as a fixed imprint is giving way to the model of the epigenome as a dynamic landscape that reflects a variety of chronological changes.
	The current challenge is to determine whether these changes can be systematically described and modeled to detect different rates of human aging, and to tie these rates to related clinical or environmental variables.
