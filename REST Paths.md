## REST paths

View responses from various API calls&nbsp;with tools such as [Fiddler](http://www.fiddler2.com/fiddler2) or [Chrome's REST Console](https://chrome.google.com/webstore/detail/rest-console/cokgbflfommojglbmbpenpphppikmonn?hl=en#detail/rest-console/cokgbflfommojglbmbpenpphppikmonn?hl=en).  

### Supported representational state transfer (REST) paths:  

[api.ers.usda.gov/REST/v1/content/topics/](http://api.ers.usda.gov/REST/v1/content/topics/)  

* Returns an array of *all root-level topic* objects.
* Includes the topicId value for each topic object.  

[api.ers.usda.gov/REST/v1/content/topics?id={topicId}](http://api.ers.usda.gov/REST/v1/content/topics?id={topicId})

### Food Market &amp; Prices topic:

[api.ers.usda.gov/REST/v1/content/topics?id=1764](http://api.ers.usda.gov/REST/v1/content/topics?id=1764)  

* Returns a *single topic* object according to the *topicId* provided.
* Accepts a topicId value of type int.  

[api.ers.usda.gov/REST/v1/content/topics?id={topicId}&getChildren=true](http://api.ers.usda.gov/REST/v1/content/topics?id={topicId}&getChildren=true)

### Children (subtopics) of Food Market & Prices topic:

[api.ers.usda.gov/REST/v1/content/topics?id=1764&getChildren=true](http://api.ers.usda.gov/REST/v1/content/topics?id=1764&getChildren=true)  

* Returns an array of* all subtopic *objects with the *parent topicId* value provided.
* Includes the subtopicId value for each subtopic object.
* Accepts a topicId value of type int.  

[api.ers.usda.gov/REST/v1/content/charts/](http://api.ers.usda.gov/REST/v1/content/charts/)  

* Returns a *large array of all chart objects*.
* Includes the chartId value for each chart object. **Note:** you must replace {count} with a number for the following path to work:

api.ers.usda.gov/REST/v1/content/charts?take={count}

### Five most recent charts:

[api.ers.usda.gov/REST/v1/content/charts?take=5](http://api.ers.usda.gov/REST/v1/content/charts?take=5)  

* Returns an array of the* most recent chart *objects limited to the *count value* provided.
* Includes the chartId value for each chart object.
* Accepts a count value of type int. **Note:** you must replace {chartId} with a chart ID number for the following path to work:  

api.ers.usda.gov/REST/v1/content/charts?id={chartId}

### Specific chart:  

[api.ers.usda.gov/REST/v1/content/charts?id=37298](http://api.ers.usda.gov/REST/v1/content/charts?id=37298)  

* Returns *a single chart* object according to the *chartId* value provided.
* Accepts a chartId value of type int.  

[api.ers.usda.gov/REST/v1/content/charts/collections/](http://api.ers.usda.gov/REST/v1/content/charts/collections/)  

* Returns an array of *chart collection* objects
* Includes the collectionAlias value for each collection object. **Note:** you must replace {collectionAlias} with a chart collection's alias name for the following path to work:  

api.ers.usda.gov/REST/v1/content/charts/collections?alias={collectionAlias}

### Charts of Note collection:  

[api.ers.usda.gov/REST/v1/content/charts/collections?alias=chartsOfNote](http://api.ers.usda.gov/REST/v1/content/charts/collections?alias=chartsOfNote)  

* Returns an array of *chart objects* *filtered* by the *collectionAlias* value provided.
* Includes the chartId value for each chart object.
* Accepts a collectionAlias value of type string. **Note:** you must replace {count} with a number for the following path to work:  

api.ers.usda.gov/REST/v1/content/charts/collections?alias={collectionAlias}&take={count}  

### Five most recent charts from the Charts of Note collection:

[api.ers.usda.gov/REST/v1/content/charts/collections?alias=chartsOfNote&take=5](http://api.ers.usda.gov/REST/v1/content/charts/collections?alias=chartsOfNote&take=5)

* Returns an array of *chart objects filtered* by the *collectionAlias* value provided and limited by the *count value* provided.
* Includes the chartId value for each chart object.
* Accepts a collectionAlias value of type string.
* Accepts a count value of type int.  

### All data products:

[api.ers.usda.gov/REST/v1/content/dataproducts/](http://api.ers.usda.gov/REST/v1/content/dataproducts/)  

* Returns an array of *all data product* objects.
* Includes the dataProductId value for each data product object.
* Includes the typeAlias value for each data product object. **Note:** you must replace {dataProductId} with a data product ID number for the following path to work:

api.ers.usda.gov/REST/v1/content/dataproducts?id={dataProductId}  

### ARMS Data Product page  

[api.ers.usda.gov/REST/v1/content/dataproducts?id=9471](http://api.ers.usda.gov/REST/v1/content/dataproducts?id=9471)  

* Returns *a single data product* object according to the *dataProductId* value provided.
* Accepts a dataProductId value of type int.  

[api.ers.usda.gov/REST/v1/content/dataproducts/types/](http://api.ers.usda.gov/REST/v1/content/dataproducts/types/)  

* Returns *a string array* (string[]) of *valid data product typeAlias* values.  

[api.ers.usda.gov/REST/v1/content/dataproducts/types?alias={typeAlias}](http://api.ers.usda.gov/REST/v1/content/dataproducts/types?alias={typeAlias})  

### Data products using Reporting Services:  

[api.ers.usda.gov/REST/v1/content/dataproducts/types?alias=reporting](http://api.ers.usda.gov/REST/v1/content/dataproducts/types?alias=reporting)  

* Returns an array of *data product objects filtered* by the *typeAlias* value.
* Includes the dataProductId value for each data product object.
* Includes the typeAlias value for each data product object.
* Accepts a typeAlias value of type string.  

### All publications:

[api.ers.usda.gov/REST/v1/content/publications/](http://api.ers.usda.gov/REST/v1/content/publications/)  

* Returns *a large array of all publication* objects.
* Includes the publicationId value for each publication object.
* Includes the seriesCode value for each publication object. **Note:** you must replace {publicationId} with a publication ID number for the following path to work:  

api.ers.usda.gov/REST/v1/content/publications?id={publicationId}

### A specific publication:  

[api.ers.usda.gov/REST/v1/content/publications?id=32387](http://api.ers.usda.gov/REST/v1/content/publications?id=32387)  

* Returns *a single publication* object according to the *publicationId* value provided.
* Accepts a publicationId value of type int.  **Note:** you must replace {count} with a number for the following path to work:

api.ers.usda.gov/REST/v1/content/publications?take={count}  

### Five most recent publications:  

[api.ers.usda.gov/REST/v1/content/publications?take=5](http://api.ers.usda.gov/REST/v1/content/publications?take=5)  

* Returns an array of the *most recent publication* objects limited by the *count value* provided.
* Includes the publicationId value for each publication object.
* Includes the seriesCode value for each publication object.
* Accepts a count value of type int.

[api.ers.usda.gov/REST/v1/content/publications/types/](http://api.ers.usda.gov/REST/v1/content/publications/types/)  

* Returns *a string array* (string[]) of *valid publication typeAlias* values.  

[api.ers.usda.gov/REST/v1/content/publications/types?alias={typeAlias}](http://api.ers.usda.gov/REST/v1/content/publications/types?alias={typeAlias})  

### All Outlook Publications:  

[api.ers.usda.gov/REST/v1/content/publications/types?alias=Outlook](http://api.ers.usda.gov/REST/v1/content/publications/types?alias=Outlook)  

* Returns an array of *publication objects filtered* by the *typeAlias* value provided.
* Includes the publicationId value for each publication object.
* Includes the seriesCode value for each publication object.
* Accepts a typeAlias value of type string. **Note:** you must replace {count} with a number for the following path to work:  

api.ers.usda.gov/REST/v1/content/publications/types?alias={typeAlias}&take={count}  

### Five most recent Outlook Publications:  

[api.ers.usda.gov/REST/v1/content/publications/types?alias=Outlook&take=5](http://api.ers.usda.gov/REST/v1/content/publications/types?alias=Outlook&take=5)  

* Returns an array of *publication objects filtered* by the *typeAlias* value provided and limited by the *count value* provided.
* Includes the publicationId value for each publication object.
* Includes the seriesCode value for each publication object.
* Accepts a typeAlias value of type string.
* Accepts a count value of type int.  

[api.ers.usda.gov/REST/v1/content/publications/series/](http://api.ers.usda.gov/REST/v1/content/publications/series/)  

* Returns a *string array* (string[]) of valid *publication seriesCode* values.  

[api.ers.usda.gov/REST/v1/content/publications/series?code={seriesCode}](http://api.ers.usda.gov/REST/v1/content/publications/series?code={seriesCode})  

### All AIB Publications:  

[api.ers.usda.gov/REST/v1/content/publications/series?code=AIB](http://api.ers.usda.gov/REST/v1/content/publications/series?code=AIB)  

* Returns an array of *publication objects filtered* by the *seriesCode* value provided.
* Includes the publicationId value for each publication object.
* Includes the seriesCode value for each publication object.
* Accepts a seriesCode value of type string.  

[api.ers.usda.gov/REST/v1/content/publications/series?code={seriesCode}&take={count}](http://api.ers.usda.gov/REST/v1/content/publications/series?code={seriesCode}&take={count})

### Five most recent AIB Publications:  

[api.ers.usda.gov/REST/v1/content/publications/series?code=AIB&take=5](http://api.ers.usda.gov/REST/v1/content/publications/series?code=AIB&take=5)  

* Returns an array of *publication objects filtered* by the *seriesCode* value provided and limited by the *count value* provided.
* Includes the publicationId value for each publication object.
* Includes the seriesCode value for each publication object.
* Accepts a seriesCode value of type string.
* Accepts a count value of type int.

### All Amber Waves articles:

[api.ers.usda.gov/REST/v1/content/amberwaves/](http://api.ers.usda.gov/REST/v1/content/amberwaves/)  

* Returns an array of *all AmberWaves* article objects.
* Includes the articleId value for each AmberWave article object. **Note:** you must replace {articleId} with an article ID number for the following path to work:  

api.ers.usda.gov/REST/v1/content/amberwaves?id={articleId}  

### A specific Amber Waves article    

[api.ers.usda.gov/REST/v1/content/amberwaves?id=35553](http://api.ers.usda.gov/REST/v1/content/amberwaves?id=35553)    

* Returns *a single AmberWaves article* object according to the *articleId* value provided.    
* Accepts an articleId value of type int. **Note:** you must replace {count} with a number for the following path to work:  

api.ers.usda.gov/REST/v1/content/amberwaves?take={count}    

### Five most recent Amber Waves articles  

[api.ers.usda.gov/REST/v1/content/amberwaves?take=5](http://api.ers.usda.gov/REST/v1/content/amberwaves?take=5)    

* Returns an array of *AmberWaves article objects* limited by the *count value* provided.
* Includes the articleId value for each AmberWave article object.
* Accepts a count value of type int.  

[api.ers.usda.gov/REST/v1/content/amberwaves/sections/](http://api.ers.usda.gov/REST/v1/content/amberwaves/sections/)  

Returns a *string array* (string[]) of valid *AmberWaves* article *sectionAlias* values.  

[api.ers.usda.gov/REST/v1/content/amberwaves/sections?alias={sectionAlias}](http://api.ers.usda.gov/REST/v1/content/amberwaves/sections?alias={sectionAlias})  

**All "Markets and Trade" Amber Waves articles:**  

[api.ers.usda.gov/REST/v1/content/amberwaves/sections?alias=Markets_and_Trade](http://api.ers.usda.gov/REST/v1/content/amberwaves/sections?alias=Markets_and_Trade)  

* Returns an array of *AmberWaves article objects filtered *by the *sectionAlias* value provided.
* Includes the articleId value for each AmberWaves article object.
* Accepts a sectionAlias value of type string. **Note:** you must replace {count} with a number for the following path to work:  

api.ers.usda.gov/REST/v1/content/amberwaves/sections?alias={sectionAlias}&take={count}  

**Five most recent "Markets and Trade" Amber Waves articles:**  

[api.ers.usda.gov/REST/v1/content/amberwaves/sections?alias=Markets_and_Trade&take=5](http://api.ers.usda.gov/REST/v1/content/amberwaves/sections?alias=Markets_and_Trade&take=5) 

* Returns an array of *AmberWaves article* objects filtered by the *sectionAlias* value provided and limited by the *count value*.
* Includes the articleId value for each AmberWaves article object.
* Accepts a sectionAlias value of type string.
* Accepts a count value of type int.
