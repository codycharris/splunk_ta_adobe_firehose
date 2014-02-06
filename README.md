Add-on for Adobe Analytics Firehose
======================================================================
Author:                  Cody Harris

Add-on Name:             Splunk Add-on for Adobe Analytics Firehose

Add-on Version:          0.1.1

Add-on Date:             02.06.14


Description
------------------------------
Splunk Add-on for Adobe Analytics Firehose using the REST Modular Input. 

http://apps.splunk.com/app/1546/


## Installation of the add-on in Splunk

1. Ensure that REST Modular Input for Splunk is installed.
	http://apps.splunk.com/app/1546/ 

2. Copy the inputs.conf.example file from: 
	$SPLUNK_HOME/etc/apps/TA-Adobe_Analytics_Firehose/default to: 
	$SPLUNK_HOME/etc/apps/TA-Adobe_Analytics_Firehose/local/inputs.conf 
	(drop the “.example” extension) 

3. Edit the new inputs.conf file. Update all fields wrapped in carrots: <example>
 
4. Restart Splunk. $SPLUNK_HOME/bin/splunk restart 


## Sample Inputs Config 

    [rest://Adobe-Firehose]
    host = firehose.omniture.com
    auth_type = oauth2
    endpoint = https://firehose1.omniture.com/api/1/stream/Company-Name
    http_method = GET
    index_error_response_codes = 0
    oauth2_access_token = eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiJ9.eyJpZCI6IjEzOTE2NDU2NDE1OTktZWExNWQ3ODEtZWNjZC00MjQzLTk1N2MtYzg2Yzg2YTg1NzhhIiwiY2xpZW50X2lkIjoiU3BsdW5rIiwidXNlcl9pZCI6IjhEQzQ3RjA1NTJGMjYwRDYwQTQ5MEQ0REBBZG9iZUlEIiwiZXhwaXJlcyI6MTM5MTY0OTI2OSwidG9rZW5fdHlwZSI6ImJlYXJlciIsInNjb3BlIjoiUmVwb3J0IiwibG9naW5fY29tcGFuaWVzIjp7Im5pa2UiOm51bGx9fQ.lvnnFq-377FH7ccw_Ai2Ak6M0ojqs6h9ENIv14JQsT98xMyKNV4v-60EUzvq_1xGLnCPc-p7d9pVoE
    response_type = json
    sourcetype = adobe:firehose
    streaming_request = 1
    index = firehose
    disabled = 1
    oauth2_client_id = Splunk
    oauth2_client_secret = af382adasd252dffaf2
    oauth2_refresh_props = client_id=Splunk,response_type=code,state=1234567890
    oauth2_refresh_url = https://marketing.adobe.com/authorize
