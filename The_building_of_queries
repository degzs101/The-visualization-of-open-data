<!--#include virtual="top.html" -->
<title> Graph Builder - Easy Graphs </title>
<script>
      var endpoint = "http://sws.ifi.uio.no/sparql/world";
      var query = "PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>PREFIX owl: <http://www.w3.org/2002/07/owl#>PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>PREFIX w: <http://sws.ifi.uio.no/ont/world.owl#>PREFIX dbpo: <http://dbpedia.org/ontology/>PREFIX geo: <http://www.w3.org/2003/01/geo/wgs84_pos#>PREFIX dct: <http://purl.org/dc/terms/>PREFIX fn: <http://www.w3.org/2005/xpath-functions#>PREFIX afn: <http://jena.hpl.hp.com/ARQ/function#>PREFIX npdv: <http://sws.ifi.uio.no/vocab/npd#>PREFIX npdv2: <http://sws.ifi.uio.no/vocab/npd-v2#>PREFIX geos: <http://www.opengis.net/ont/geosparql#>SELECT * WHERE{ []  a w:Country ; w:hasName ?Name ; w:hasCountryPopulation ?Population ; } ORDER BY DESC(?Population) LIMIT 10" ;
	  
      // Define a callback function to receive the SPARQL JSON result.
      function myCallback(str) {
        // Convert result to JSON
        var jsonObj = eval('(' + str + ')');

        // Build up a table of results.
        /*var result1 = "<table border='2' cellpadding='9'>" ;
        for(var i = 0; i <  jsonObj.head.vars.length; i++) {
          result1 += " <tr> <td>" + jsonObj.head.vars[i].Name.value;
		  result1 += " </td></tr>"; 
		}	*/	
        for(var i = 0; i <  jsonObj.results.bindings.length; i++) {
          result += " <tr> <td>" + jsonObj.results.bindings[i].Name.value;
		  result += " <tr> <td>" + jsonObj.results.bindings[i].Population.value;
          result += " </td></tr>"; 
        } 
        /*result1 += "</table>" ;
        document.getElementById("result1").innerHTML = result1;*/
		result += "</table>" ;
        document.getElementById("results").innerHTML = result;
     }
      
     // Make the query.
     sparqlQueryJson(query, endpoint, myCallback, true);
      
    </script>
<h2>Welcome to our Graph Building page where you can build your own graphs from data sources with a SPARQL endpoint.</h2>
<p>For more information on SPARQL, visit our <a href="info.shtml">SPARQL Information</a> page</p>
<h3 style= "color:red"> Note: all queries must be retured on an (x,y) axis for use in a .json format</h3>
<form name='graphBuilderForm'>
<table border=0>
	<tr>
		<td><b>Enter SPARQL endpoint URI:</b></td>
		<td><textarea name='endPointURI' rows='1' cols='50'></textarea></td>
	</tr>
	<tr>
		<td><b>Enter your SPARQL query:</b></td>
		<td><textarea name='query' rows='10' cols='50'></textarea></td>
	</tr>
	<tr>
		<td><b>Enter graph name:</b></td>
		<td><textarea name='graphName' rows='1' cols='50'></textarea></td>
	</tr>
	<tr>
		<td><b>Select graph type:</b></td>
		<td><select name='chartType'>
			<option value='pie'>Pie Chart</option>
			<option value='bar'>Bar Chart</option>
			<option value='column'>Column Chart</option>
			<option value='table'>Table</option>
			</select>
		</td>
	</tr>
	<tr>
		<td><b>Select colour:</b></td>
		<td><select name='chartColour'>
			
			<option value='red' style= "color:red">RED</option>
			<option value='blue' style= "color:blue">BLUE</option>
			<option value='green' style= "color:green">GREEN</option>
			<option value='yellow' style= "color:yellow">Yellow</option>
			<option value='pink' style= "color:pink">PINK</option>
			<option value='purple' style= "color:purple">PURPLE</option>
			</select>
		</td>
	</tr>
	<tr>
		<td><b>Measurements:</b></td>
		<td><b>Height:<textarea name='graphHeight' rows='1' cols='10'></textarea>Width:<textarea name='graphWidth' rows='1' cols='10'></textarea></b></td>
	</tr>
	<tr>
		<td><b>Select values for each axis:</b></td>
		<td><b>X-axis:<textarea name='graphHeight' rows='1' cols='10'></textarea><b>Y-axis:<textarea name='graphWidth' rows='1' cols='10'></textarea></b></td>
	</tr>
	</table>
	
    </div>
	<div id="results">
      It may take a few moments for the info to be displayed here...
      <br/><br/>
      Run me in Internet Explorer or I get Cross Domain HTTP Request errors!
    </div>
<!--#include virtual="bottom.html" -->
