# DBSCAN-spatial
Mapping out the ideal branch network for a high street estate agent

# Goal
Assuming I am new to the property market and looking to open new high street branches operating under 2 brands (call them prime and value where prime branch will specialise in high end properties in the area) then:
1) How many branches will I have
2) Where would these branches be located
3) What is the potential revenue opportunity for each branch

# Approach
Model was built using sklearn's DBSCAN to cluster land registry prime and value transactions to identify hotspots within a postcode area eg 'MK'
DBSCAN takes 2 parameters:
Max distance - in this case, the max distance within 2 transaction points within a cluster. This was calculated using the 25th percentile of distances between points within a post area for a prime cluster and a tenth of the average of all distances of a value cluster as they need to be tighter.
Min sample - This is the minimum count of transaction points a cluster should have for me to consider opening a branch within it.
This is calculated using the average number of instructions a successful prime/ value agent in that area wins. Assuming a 50% conversion rate and 7% market share, I can translate instructions to land registry completions.

Tuning these parameters for both markets within all post area, I am able to come up with clusters which are essentially hotspots. Finally mapping the centre of the clusters to the nearest place of interest such as high street or retail park giving me the ideal branch network.
