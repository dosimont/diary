#Experiments
The goal of these experiments is to check whether filtering provides better performances when performed by the Database (with an SQL query in our case) or by the application afterward. 

##Thread Parameters
There are two parameters that are tested: 
	* The number of thread loading events (and performing the filtering)
		* 4
		* 8
		* 16
	* The number of events fetched by a thread at each iteration
		* 100
		* 1000
		* 10000
		* 100000

##Traces
Synthetic traces with temporal indexation. All traces have 100 EP and 10 ET. The trace have different number of events: 
	* 1000000, 
	* 10000000,
	* 100000000,
	* 1000000000,
	* 2^31 (~2140000000).
Events are in average distributed in a uniform fashion over all the dimensions: spatial, temporal and their type. So when filtering one or several dimensions it is possible to know how many events we loaded.

##Filtering
### Temporal (T)
	* No filtering
	* 10% of total time
	* 25%
	* 50%
	* 66%
	* 90%
	
### Spatial (S)
	* No Filtering
	* 1/10
	* 2/10
	* 5/10
	* 7/10
	* 9/10
	
### Event Type (ET)
	* No filtering
	* 10% ef event types
	* 25% of event types
	* 50% 
	* 66%
	* 90%
	
Then we perform the tests with all the combination of the above filters:
	* T
	* S
	* ET
	* T + S
	* T + ET 
	* S + ET
	* T + S + ET

## Query Operators
Three operators were implemented to test the solution:
	* The normal query, where all the filtering is performed by the Database manager
	* The manual query, where all the events of the fetched by the databse, but filtered afterward in the tool
	* The hybrid query, where the DB manager only perform the filtering on the temporal dimension (since the trace are indexed on this dimension), and other filter are performed by our tool 
	
### Experimental Setup
The test will be executed for all the combination of the parameters described above i.e.: the thread parameters, the traces, the filtering and the query.

