#  Predicting future climate policy actions: an analysis using AI & ML techniques


This is the software repository for files related to my MTP project on **Predicting future climate policy actions: an analysis using AI & ML techniques**

This reposiroty contains all the software for reproducing the paper, and some sample documents.

## Notes
Do not change the names of any folders or files before finishing the pipeline, as the scripts look in folders with these specific names.

Step 1:  

In the folder 'PDF_files' the following PDF documents are contained.  
'Adaptation policy documents' - Training data for adaptation policies  
'Mitigation policy documents' - Training data for mitigation policies  
'Non-climate policy documents' - Training data for non-climate documents  
'Mixed policy documents' - Testing data, any PDF document(s) you want to predict on.  

Step 2:  
In the folder 'Python Scripts' every script in the pipeline is contained.  

### Main pipeline  
`pdf_parser.py` - Extract raw text from PDf documents (parsed_files)  
`text_cleanup.py` - Filters, cleansand structurizes data into 'bags-of-words' (structured_files)  
`sqlite_db.py` - Builds database and inserts cleaned data (climate.db)  
`numberizer.py` - Builds vocabulary from training data (conversion_dictionary.txt)  
`TF_classification_BW.py` - Builds neural network and stores it (tensorflow/logdir)  
`TF_classification_predict.py` - Uses stored model to predict on new data. Results stored in database.  

### Optional scripts  
`pipeline.py` - Runs every script in the main pipeline in order.  
`web_scraper.py` - Retrieves documents from gov.uk website (PDF_files\Scraped documents) -- OUTDATED  
`blocklength_dist.py` - Plots distribution of block lengths (Plots)  
`document_prediction.py` - Plots histogram of test set blocks and their labels. WARNING: Only use few documents  
`confidence_analysis.py` - Visualization for fraction of high confidence blocks  
`tensorboard_launch.py` - Launch tensorboard from stored model  
