
from PAMI.frequentPattern.basic import Apriori  as alg
inputFile = '/userData/likhitha/new/frequentPattern/transactional_T10I4D100K.csv'

minimumSupportCount=1000  #Users can also specify this constraint between 0 to 1.

seperator='\t'       
obj = alg.Apriori(iFile=inputFile, minSup=minimumSupportCount, sep=seperator)    #initialize
obj.startMine()            #Start the mining process
Frequent patterns were generated successfully using Apriori algorithm 
obj.save(outFile='frequentPatternsMinSupCount1000.txt')
frequentPatternsDF= obj.getPatternsAsDataFrame()
print('Total No of patterns: ' + str(len(frequentPatternsDF)))
Total No of patterns: 385
print('Runtime: ' + str(obj.getRuntime()))
Runtime: 486.54657435417175
print('Memory (RSS): ' + str(obj.getMemoryRSS()))
print('Memory (USS): ' + str(obj.getMemoryUSS()))
Memory (RSS): 267091968
Memory (USS): 228372480