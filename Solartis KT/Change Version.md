#builder #solartis #solartis_builder 

### When to create change version ?
#change_version

	* Once we made some changes in product, we have to create a change version for that particular product in builder.
	* After that, we have to update the cv in log table using the latest primary key which we fetch in the object sequence table.
	* And finally we should transfer the product into next environment by updating the cv in pipeline.
	

### Notes:- 
#change_version

	In production environment we have no concept like cv, so that we have to add executable sql files in the production line. So only it can make changes in the higher environment when we add this changes to the pipeline.