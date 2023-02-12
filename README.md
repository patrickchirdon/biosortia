Results

https://www.slideshare.net/PatrickChirdon1/biosortia2proppptx?fbclid=IwAR26psj1zzyKpBClr-FbtDCS4pg0tfsc613hVGixxt84aE5jcVqgz9NyPT8



library--https://hmdb.ca/metabolites?utf8=%E2%9C%93&quantified=1&blood=1&urine=1&saliva=1&csf=1&feces=1&sweat=1&breast_milk=1&bile=1&amniotic_fluid=1&other_fluids=1&microbial=1&filter=true

for solubility lasso lars had r^2 of 1, lasso r^2 of 1, and elastic r^2 of 1 on test data.
bioavailability-- lasso lars had a r^2 of 1 on test data, lasso r^2 of 1, and elastic r^2 of 1.
for fraction of sp3 hybridized carbons (a measure of selectivity of binding)-- lasso lars had a r^2 of 1 on training data (first model for lasso lars to work), lasso r^2 of 1, and elastic r^2 of 1.
alogp and psa with an r^2 of 1 on test data. 
mglur5 (autism target), hsp90a (neuroinflammatory target, charcot marie tooth disease), calpain 1 (covid 19 target), aphid mortality model. r^2 of 1 with elastic, lasso, and lasso_lars models

on the QED test data set--
Mean absolute error: 0.14206431066163
Mean squared error: 0.84021645902190
Root mean squared error: 0.91663

Test set of CNS compounds vs non CNS compounds it was not trained on r^2 of .78 for logP and .84 for PSA for CNS compounds.  The non CNS compounds had a r^2 of .97 for PSA.  non CNS compounds had a logP r^2 of 1.  


ms2prop had an r2 of .73 on the independent test set across all the QED properties, we have an r2 of 88%


https://stackabuse.com/linear-regression-in-python-with-scikit-learn/



RESOURCES

https://www.rosettacommons.org/

https://openmolecules.org/datawarrior/

https://pubchem.ncbi.nlm.nih.gov//edit3/index.html

https://www.chemdiv.com/catalog/complete-list-of-compounds-libraries/?https://www.chemdiv.com/complete-list-of-compounds-libraries/&gclid=EAIaIQobChMIh4OokPKN_QIVVAetBh075gGEEAAYAyAAEgJlPvD_BwE

https://sciencesolutions.wiley.com/solutions/technique/gc-ms/mass-spectra-of-flavors-and-fragrances-of-natural-and-synthetic-compounds-3rd-edition/

Databases-- 
https://www.nature.com/articles/s41592-022-01685-y?utm_source=nmeth_etoc&utm_medium=email&utm_campaign=toc_41592_20_2&utm_content=20230211

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

https://massbank.eu/MassBank/Search

http://www.swissadme.ch

------------------------------------------------


-------------------------------------------------
QED Calculation-- QED is lipinski + medicinal chemistry rules and aromatic ring count
https://github.com/kevinid/molecule_generator/blob/master/rdkit_contrib/qed.py
https://bioinformaticsreview.com/20220803/how-to-calculate-drug-likeness-using-rdkit/
https://sharifsuliman1.medium.com/understanding-drug-likeness-filters-with-rdkit-and-exploring-the-withdrawn-database-ebd6b8b2921e
PSA is a commonly used medicinal chemistry metric for the optimization of a drug's ability to permeate cells. Molecules with a polar surface area of greater than 140 angstroms squared (Å2) tend to be poor at permeating cell membranes.[1]

for CNS compounds, moderately polar (PSA<79 Å2) and relatively lipophilic (log P from +0.4 to +6.0) molecules have a high probability to access the CNS.
https://pubmed.ncbi.nlm.nih.gov/12036371/
https://en.wikipedia.org/wiki/Octanol-water_partition_coefficient
https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2628535/
https://pubmed.ncbi.nlm.nih.gov/12036371/

rotatable bonds also influence oral bioavailability according to the article above. octanol-water partition coefficient (ALOGP, a measure of solubility) and psa/polar surface area (cell permeability)

source of the SMARTS structures used by the QED algorithm-- https://application.wiley-vch.de/contents/jc_2452/2008/f700139_s.pdf
**To do-- look these up on mass bank.

https://pubmed.ncbi.nlm.nih.gov/22270643/

https://pubs.acs.org/doi/10.1021/jm301008n
https://pubs.acs.org/doi/10.1021/jm301008n

https://www.linkedin.com/dms/D5606AQGeryI_9cl_7Q/messaging-attachmentFile/0/1674513398949?m=AQL5KPz_EwQh3wAAAYXkrUq6wHaqMwgb4_G7ydlgu24zKcy_ik-93L9tHg&ne=1&v=beta&t=rOhzAL2fx-vmgZ9IzqNa6rk23IVgdBAGTrDQYQ4DOpU

https://www.linkedin.com/dms/D5606AQFnA5phyhh1Ww/messaging-attachmentFile/0/1674513446947?m=AQKAk--8d5TVggAAAYXkqQqA2dyAomZLVYOzG3h_wiVQ-KwhL3dijfbD6A&ne=1&v=beta&t=pVNO2cO_uWBbVDN99Hb1f8fRDkP851UyoTmTdAnB5tE

https://www.linkedin.com/dms/D5606AQHFP0qB8dGvrA/messaging-attachmentFile/0/1674513472574?m=AQLnPQbbdt3KKwAAAYXkqQqE-3nS5yJDHoF_O_MTtnzO49CJczmmmJSm5A&ne=1&v=beta&t=web29rjIYFypV9EACZhoXk23w3sanlzH2ULN355LwVQ



-------------------------------------------------

Transformers--
chapter 1-- attention is all you need
https://books.google.com/books?id=Cr0YEAAAQBAJ&printsec=frontcover#v=onepage&q&f=false

https://github.com/jadore801120/attention-is-all-you-need-pytorch

mass genie-- 
'Our transformer encoder, written in PyTorch, is composed of 12 transformer encoder layers plus 12 transformer decoder layers. The output dimensionality of all the sub-layers, as well as the embedding layers in both encoder and decoder, was set to 1024. Besides this, each Multi-Head attention layer of our transformer model was formed of 16 attention heads in total. We used dropout [89] heavily; its value for the complete transformer model was set to 20%. Lastly, the dimensionality of the feed-forward layer present inside all of the transformer encoder and decoder layers, and applied to every position individually, was set at 4096.'

https://metabolomics.blog/2021/07/msnovelist/

in an evaluation with 3,863 MS2 spectra from the Global Natural Product Social Molecular Networking site, MSNovelist predicted 25% of structures correctly on first rank, retrieved 45% of structures overall and reproduced 61% of correct database annotations, without having ever seen the structure in the training phase. Similarly, for the CASMI 2016 challenge, MSNovelist correctly predicted 26% and retrieved 57% of structures, recovering 64% of correct database annotations.

https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8699281/


https://github.com/ashishpatel26/Treasure-of-Transformers

https://huggingface.co/blog/how-to-train

https://medium.com/@august.allen_51342/transforming-natural-product-drug-discovery-machine-learning-for-high-fidelity-chemical-property-94da4cd8ca73
MS2prop paper
https://www.biorxiv.org/content/10.1101/2022.10.09.511482v2.full

https://www.nature.com/articles/s41592-022-01486-3


--------------------------------------------------------------------------------------------------------
pesticides
https://www.uky.edu/Ag/Entomology/PSEP/6environment.html

soil adsorbability index
https://www.linkedin.com/dms/D5606AQEgcWcLR_yhFg/messaging-attachmentFile/0/1674504979609?m=AQK5bavmYsSpvwAAAYXkrUq66YbktsJuyGBvBvoll0ApvRsXKvn7hpi73A&ne=1&v=beta&t=CjfffuOksOUyLZcVi4I_AwXQ4G3EerqDSSTAbbmMR7g

leach indexes
https://www.linkedin.com/dms/D5606AQEhQUv25jx_eA/messaging-attachmentFile/0/1674509768012?m=AQI0u7yWMwK2OwAAAYXkrUrC7bSEnBAHY71Z1A5kQCgM81wjpk8cDHHciw&ne=1&v=beta&t=QvkX8bDxF-egUE5_pz5i_hkGyOT4LXa0325eBtVz4UE
https://www.linkedin.com/dms/D5606AQFkxSg1WZatqA/messaging-attachmentFile/0/1674509799625?m=AQL9miSKBIcreAAAAYXkrUq94h9EBtXcge5Vh8eyy4m4ReJsBNZkPu0k0g&ne=1&v=beta&t=iJZ7VNQX8VGbvd2IifErn1Y71oL3nR3MUd2Ntr_4foM

soil sorption index coefficient
https://www.linkedin.com/dms/D5606AQFIQK8Zma1nQg/messaging-attachmentFile/0/1674513719308?m=AQIuJhEupjf3fgAAAYXkqQqGMyUDx8SU8r54Dwa4xX7vPkZSBNbEjemC7g&ne=1&v=beta&t=oVnDAxFRH8iCRUX0e9JRsDVZncKyVLzSuEDn2SCwt5c


----------------------------------------------------------------------------------------------------------
binding affinity
https://www.linkedin.com/dms/D5606AQHUpCK33-KUOg/messaging-attachmentFile/0/1674515181359?m=AQIMPcGes0W9sQAAAYXkqQqBhPDT8InzBgGRM70cRxoPdc2RqQkculIFQg&ne=1&v=beta&t=6AegRZrUODouanZ4JIFxm4OrALCbdHZHukjqM8az_qw
https://www.linkedin.com/dms/D5606AQFmoEPphHlyvQ/messaging-attachmentFile/0/1674515187920?m=AQKF8Xh3-Y72SAAAAYXkqQp-OiETjLkYF9l85xTcB-jJ9Mb2aw0XeTUZpw&ne=1&v=beta&t=zJzQ9AmFOQId7JZy4iJeTYYQBbTaiD4pF9sGwcr4Rtg


--------------------------------------------------------------------------------------------------------

ADME--

https://admetmesh.scbdd.com/service/evaluation/index
https://www.google.com/books/edition/Lipid_Nanoparticles_Production_Character/bOVhBAAAQBAJ?hl=en&gbpv=1&dq=lipid+nanoparticles+production+characterization+stability&printsec=frontcover
https://academic.oup.com/nar/article/49/W1/W5/6249611
https://academic.oup.com/nar/article/45/W1/W356/3791213
https://aip.scitation.org/doi/pdf/10.1063/1.4937259

https://chemistry-europe.onlinelibrary.wiley.com/doi/full/10.1002/cmdc.201600182
https://pubs.acs.org/doi/abs/10.1021/ci500467k
https://pubmed.ncbi.nlm.nih.gov/19827778/
https://pubmed.ncbi.nlm.nih.gov/15857122/
https://www.nature.com/articles/srep42717

The Egan rule considers good bioavailability for compounds with 0 ≥ tPSA ≤ 132 Å2 and -1≥ logP ≤ 6 [15]. The Bayer Oral Physchem Score is computed using a Bayer in house system to flag chemical compounds and it takes values between 0 and 10.

cns vs non-cns

https://www.linkedin.com/dms/D5606AQHxRiRfXgfXIg/messaging-attachmentFile/0/1674515816273?m=AQKLDYOhLmHeGgAAAYXkqQp-2A0Ne_VAmVmP4CXrliVNj4k6oZVtU2DJGg&ne=1&v=beta&t=v2iPj_uDSoxHaD_yL6Tue_e6uFSaAe7y4PQ9k4McWDc

--------------------------------------
Compounds of interest---
1. Ulvan -- 
https://www.jpost.com/health-and-wellness/could-seaweed-save-humanity-from-covid-19-687775
https://onlinelibrary.wiley.com/doi/epdf/10.1002/adma.202206367
Ulvan is a plastic similar to PEI.  It's useful for covid 19 and for agriculture viruses.
https://www.newscientist.com/article/2341170-battery-made-using-seaweed-still-works-after-charging-1000-times/?utm_medium=social&utm_campaign=echobox&utm_source=Facebook#Echobox=1665398953
https://www.sciencedirect.com/science/article/pii/S2211926418308373


2. Alginate nanoparticles coated with antibodies for tumors-- partner with freenome?
https://www.science.org/doi/10.1126/science.abq6990?utm_campaign=SciMag&utm_medium=ownedSocial&utm_source=LinkedIn&cookieSet=1
https://www.freenome.com/
https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6432598/

3.Gratzel cells
https://www.researchgate.net/publication/256549423_Brown_seaweed_pigment_as_a_dye_source_for_photoelectrochemical_solar_cells

4. omega 3

5. sunscreen

6. nanoparticles-- https://www.mdpi.com/2306-5354/7/4/129
https://www.sciencedirect.com/science/article/abs/pii/S1773224721004408

------------------------------------------------------------
papers of interest to pathology
https://www.newscientist.com/article/2355262-vagus-nerve-receptors-may-be-key-to-controlling-inflammation/

target prediction with pharmacophores
https://academic.oup.com/nar/article/45/W1/W356/3791213

 http://crdd.osdd.net/servers/avcpred/
 
 http://chembl.blogspot.com/2020/05/malaria-inhibitor-prediction-platform.html
 
 https://uantwerpen.vib.be/group/VincentTimmerman
 
 https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3120161/
 
 https://www.harringtondiscovery.org/
 
 https://molecular-cancer.biomedcentral.com/articles/10.1186/s12943-020-01291-6
 
 https://rupress.org/jcb/article/220/8/e202103090/212429/The-long-journey-to-bring-a-Myc-inhibitor-to-the
 
 https://time.com/6246864/reverse-aging-scientists-discover-milestone/
 
 https://www.nationalgeographic.com/magazine/science/article/zombie-cells-could-hold-the-secret-to-alzheimers-cure
 

--------------------------------------------------------------
potential partnerships--

https://www.calicolabs.com/

https://insilico.com/

https://www.envedabio.com/

https://www.energy.gov/osdbu/small-business-toolbox

https://www.trialspark.com/
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
https://www.google.com/books/edition/Hands_On_Machine_Learning_with_Scikit_Le/HnetDwAAQBAJ?hl=en&gbpv=1&dq=hands+on+machine+learning&printsec=frontcover
chemoinformatics-- 

https://www.google.com/books/edition/Molecular_Descriptors_for_Chemoinformati/6Zp7Yrqzv8AC?hl=en&gbpv=1&dq=molecular+descriptors+for+chemoinformatics&printsec=frontcover

---------------------------------------

Methods

Lasso regression-- least absolute shrinkage and selection operation regression is a regularized version of linear regression.  It adds a regularization term to the cost function using the l1 norm of the weight vector.   An important characteristic of lasso regression is that it tends to completely eliminate the weights of the least important features (set them to 0).  Kasso regression automatically performs feature selection and outputs a sparse model.  

elastic- elastic net is a middle ground between ridge regression and lasso regression.  the regularization term is a simple mix of both ridge and lasso's regularization terms, and you can control the mix ratio r. when r=0, elastic net is equivalent o ridge regression, and when r=1, it is equivalent to lasso regression.  ridge regression is a good default to use, but if you suspect that only a few features are actually useful, you should prefer lasso or elastic since they tend to reduce the useless features' weights down to zero.  In general elastic is preferred over lasso since lasso may behave erratically when the number of features is greater than the number of training instances or when several features are strongly correlated.

How good is a regression?

statisticians have come up with a tool that’s easy to understand. It is called r^2. Typically, R square is looked at as a percentage value, and it can range from 0% to 100%. The higher it is,the greater the explanatory power of the regression model (the lower the weight of unexplained squares, the better the model).

https://medium.com/wwblog/evaluating-regression-models-using-rmse-and-r%C2%B2-42f77400efee

------------------------------------------
books
  https://books.google.com/books/about/Why_Digital_Transformations_Fail.html?id=L_T1uwEACAAJ
  
  https://www.linkedin.com/feed/update/urn:li:activity:7006165405937373184/?utm_source=share&utm_medium=member_desktop
  
  https://books.google.com/books/about/Why_Digital_Transformations_Fail.html?id=L_T1uwEACAAJ
  ------------------------------------------
  tasty treats
  
  https://www.submariner-network.eu/recipe-for-a-veggie-burger-with-algae
  
