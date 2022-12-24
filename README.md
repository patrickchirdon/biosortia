RESOURCES

https://openmolecules.org/datawarrior/

Databases-- 


GNPS library--
https://ccms-ucsd.github.io/GNPSDocumentation/gnpslibraries/

https://ec.europa.eu/food/plant/pesticides/eu-pesticides-database/start/screen/active-substances

https://cbirt.net/meta-ai-releases-esm-metagenomic-atlas-a-repository-of-over-600-million-predicted-protein-structures/

https://comptox.epa.gov/genra/

https://www.metaboanalyst.ca/MetaboAnalyst/ModuleView.xhtml

https://ipb-halle.github.io/MetFrag/projects/metfragweb/

https://hmdb.ca/spectra/ms_ms/search

https://pubchem.ncbi.nlm.nih.gov/

https://www.ebi.ac.uk/chembl/

https://ochem.eu/home/show.do

https://alphafold.ebi.ac.uk/

https://www.rcsb.org/

https://cfmid.wishartlab.com/predict
------------------------------------------------


-------------------------------------------------
QED Calculation--
https://github.com/kevinid/molecule_generator/blob/master/rdkit_contrib/qed.py
https://bioinformaticsreview.com/20220803/how-to-calculate-drug-likeness-using-rdkit/
https://sharifsuliman1.medium.com/understanding-drug-likeness-filters-with-rdkit-and-exploring-the-withdrawn-database-ebd6b8b2921e
PSA is a commonly used medicinal chemistry metric for the optimization of a drug's ability to permeate cells. Molecules with a polar surface area of greater than 140 angstroms squared (Å2) tend to be poor at permeating cell membranes.[1]
https://pubmed.ncbi.nlm.nih.gov/12036371/
https://en.wikipedia.org/wiki/Octanol-water_partition_coefficient
-------------------------------------------------

Transformers--
chapter 1-- attention is all you need
https://books.google.com/books?id=Cr0YEAAAQBAJ&printsec=frontcover#v=onepage&q&f=false

https://github.com/jadore801120/attention-is-all-you-need-pytorch

mass genie-- 
'Our transformer encoder, written in PyTorch, is composed of 12 transformer encoder layers plus 12 transformer decoder layers. The output dimensionality of all the sub-layers, as well as the embedding layers in both encoder and decoder, was set to 1024. Besides this, each Multi-Head attention layer of our transformer model was formed of 16 attention heads in total. We used dropout [89] heavily; its value for the complete transformer model was set to 20%. Lastly, the dimensionality of the feed-forward layer present inside all of the transformer encoder and decoder layers, and applied to every position individually, was set at 4096.'

https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8699281/


https://github.com/ashishpatel26/Treasure-of-Transformers

https://huggingface.co/blog/how-to-train

https://medium.com/@august.allen_51342/transforming-natural-product-drug-discovery-machine-learning-for-high-fidelity-chemical-property-94da4cd8ca73
MS2prop paper
https://www.biorxiv.org/content/10.1101/2022.10.09.511482v2.full

https://www.nature.com/articles/s41592-022-01486-3
--------------------------------------------------------------------------------------------------------
Compounds of interest---
1. Ulvan -- 
https://www.jpost.com/health-and-wellness/could-seaweed-save-humanity-from-covid-19-687775
https://onlinelibrary.wiley.com/doi/epdf/10.1002/adma.202206367
Ulvan is a plastic similar to PEI.  It's useful for covid 19 and for agriculture viruses.
https://www.newscientist.com/article/2341170-battery-made-using-seaweed-still-works-after-charging-1000-times/?utm_medium=social&utm_campaign=echobox&utm_source=Facebook#Echobox=1665398953


2. Alginate nanoparticles coated with antibodies for tumors-- partner with freenome?
https://www.science.org/doi/10.1126/science.abq6990?utm_campaign=SciMag&utm_medium=ownedSocial&utm_source=LinkedIn&cookieSet=1
https://www.freenome.com/
https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6432598/

--------------------------------------------------------------
potential partnerships--

https://www.calicolabs.com/

https://insilico.com/

https://www.envedabio.com/
----------------------------------------

TODO--- 
***** written reports with data that summarize methods and outcomes

models for binding

models for inhibition

models for solubility

lipinski rule of 5

GUI toolkit

full stack database

spinoff company with LANL? 

photographs of definitions from Molecular Descriptors for Chemoinformatics

calculate ROC curves for each of the models, plus F1

----------------------------------------------

Funding--

https://www.energy.gov/osdbu/small-business-toolbox?fbclid=IwAR1Z992CVzQaUFgU7Hsem2B81RsVv-i_fLTBlWlWQRH5RIL86jkippMeppY

https://oig.hhs.gov/oei/reports/oei-09-00-00380.pdf

---------------------------------------------------------------

Algae

https://www.frontiersin.org/articles/10.3389/fpls.2020.00279/full
https://www.newscientist.com/article/2314395-robot-made-of-magnetic-slime-could-grab-objects-inside-your-body/

-------------------------------------------------------------------

machine learning--
https://mml-book.github.io/book/mml-book.pdf

chemoinformatics-- 

https://www.google.com/books/edition/Molecular_Descriptors_for_Chemoinformati/6Zp7Yrqzv8AC?hl=en&gbpv=1&dq=molecular+descriptors+for+chemoinformatics&printsec=frontcover

---------------------------------------

Methods

Lasso regression-- least absolute shrinkage and selection operation regression is a regularized version of linear regression.  It adds a regularization term to the cost function using the l1 norm of the weight vector.   An important characteristic of lasso regression is that it tends to completely eliminate the weights of the least important features (set them to 0).  Kasso regression automatically performs feature selection and outputs a sparse model.  

elastic- elastic net is a middle ground between ridge regression and lasso regression.  the regularization term is a simple mix of both ridge and lasso's regularization terms, and you can control the mix ratio r. when r=0, elastic net is equivalent o ridge regression, and when r=1, it is equivalent to lasso regression.  ridge regression is a good default to use, but if you suspect that only a few features are actually useful, you should prefer lasso or elastic since they tend to reduce the useless features' weights down to zero.  In general elastic is preferred over lasso since lasso may behave erratically when the number of features is greater than the number of training instances or when several features are strongly correlated.

How good is a regression?
Statisticians have come up with a tool that’s easy to understand. It is called 𝑹𝟐 .

Typically, R square is looked at as a percentage value, and it can range from 0% to 100%. The higher it is,
the greater the explanatory power of the regression model (the lower the weight of unexplained
squares, the better the model).
