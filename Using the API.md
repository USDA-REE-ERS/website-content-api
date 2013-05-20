### Using the API

The example below is written with C#, using .NET 4.0.

The API supports REST formatted requests, and can provide a response in JSON format, depending upon the content type specified in the header request.

* JSON Response = Content-Type:application/json
* XML Response = Content-Type:text/json

The examples are for JSON-formatted responses.

Making the request to the REST service involves a simple HTTP request and response. The following is a simple method that makes an HTTP request using the URL provided 

and returns an HttpWebResponse. The HttpWebRequest and HttpWebResponse are part of the System.Net namespace.

  _**protected HttpWebResponse MakeRequest(string requestUrl)**_  
  _**{**_

_**HttpWebRequest _request = HttpWebRequest.Create(requestUrl) as HttpWebRequest;**_  
_**_request.ContentType = "application/json";**_  
_**HttpWebResponse _response = _request.GetResponse() as HttpWebResponse;**_

_**if ( _response.StatusCode != HttpStatusCode.OK)**_  
_**{**_

_**throw new Exception(String.Format(**_

_**"Server error (HTTP {0}: {1}).",**_  
_**_response.StatusCode,**_  
_**_response.StatusDescription));**_

_**}**_  
_**else**_  
_**{**_

_**return _response;**_


_**}**_


_**}**_

The JSON response must be deserialized to a .NET class. You can use the built-in DataContractJsonSerializer which means you will need to create a DataContract class to 

describe the JSON.

_**[DataContract]**_  
_**public class Topic**_  
_**{**_

_**[DataMember(Name = "Id")]**_  
_**public int Id { get; set; }**_  
_**[DataMember(Name = "ParentId")]**_  
_**public int ParentId { get; set; }**_  
_**[DataMember(Name = "Title")]**_  
_**public string Title { get; set; }**_   
**[DataMember(Name = "Url")]**_  
_**public string Url { get; set; }**_   
**[DataMember(Name = "CreateDate")]**_  
_**public string CreateDate { get; set; }**_   
**[DataMember(Name = "ReleaseDate")]**_  
_**public string ReleaseDate { get; set; }**_  
_**[DataMember(Name = "UpdateDate")]**_**_  
_**public string UpdateDate { get; set; }**_   
**[DataMember(Name = "Properties")]**_  
_**public Property[] Properties { get; set; }**_

_**}**_

Once you have the DataContract class, you can use it with the DataContractJsonSerializer to deserialize the JSON response into a .NET class to easily access the 

information. The following method deserializes the JSON response from the provided URL and returns a list of topic objects.

_**public List&lt;Topic> RequestTopics(string requestUrl)**_  
_**{**_

_**HttpWebResponse _response = this.MakeRequest(requestUrl);**_  
_**DataContractJsonSerializer _jsonSerializer = new DataContractJsonSerializer(typeof(List<Topic>));**_   
_**List&lt;Topic> _serializedObject = _jsonSerializer.ReadObject( _response.GetResponseStream()) as List&lt;Topic>;**_  
_**return _serializedObject;**_

_**}**_

Once the JSON response has been deserialized into a .NET object (or list of objects), you can access the standard .NET properties.

_**public void BindTopics(string requestUrl)**_  
_**{**_

_**List&lt;Topic> _topics =this._apiHelper.RequestTopics(requestUrl);**_  
_**PlaceHolder _placeHolder = new PlaceHolder();**_


_**foreach (Topic _topic in _topics)**_

_**{**_

_**_placeHolder.Controls.Add(new LiteralControl("&lt;div>"));**_

_**_placeHolder.Controls.Add(new LiteralControl("&lt;p>"));**_

_**HyperLink _hlnk = new HyperLink();**_

_**_hlnk.Text = _topic.Title;**_

_**_hlnk.Font.Bold = true;**_

_**_hlnk.NavigateUrl = "http://www.ers.usda.gov"; + _topic.Url;**_

_**_placeHolder.Controls.Add(_hlnk);**_

_**_placeHolder.Controls.Add(new LiteralControl("&lt;br />"));**_
 
_**_placeHolder.Controls.Add(new LiteralControl(_topic.Properties.SingleOrDefault(p => p.keyField == "description").propertyValueField));**_

_**_placeHolder.Controls.Add(new LiteralControl("&lt;/p>"));**_

_**_placeHolder.Controls.Add(new LiteralControl("&lt;/div>"));**_

_**_placeHolder.Controls.Add(new LiteralControl("&lt;hr />"));**_

_**}**_

_**Page.Controls.Add(_placeHolder);**_
