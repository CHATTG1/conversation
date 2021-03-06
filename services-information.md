---

copyright:
  years: 2015, 2018
lastupdated: "2018-06-29"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}
{:pre: .pre}
{:codeblock: .codeblock}
{:screen: .screen}
{:javascript: .ph data-hd-programlang='javascript'}
{:java: .ph data-hd-programlang='java'}
{:python: .ph data-hd-programlang='python'}
{:swift: .ph data-hd-programlang='swift'}

# IBM Cloud services information
{: #services-information}

The assistant is a hosted service that is managed by IBM Cloud, which means you do not need to worry about maintaining the infrastructure to support the service; it is taken care of for you.
{: shortdesc}

## Service details
{: #service-details}

Explore the {{site.data.keyword.conversationshort}} [service plan options ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://console.bluemix.net/catalog/services/watson-assistant-formerly-conversation){: new_window}.

### Limits by artifact
{: #limits}

For information about artifact limits per plan, see these topics:

- [Workspaces](configure-workspace.html#workspace-limits)
- [Dialog nodes](dialog-build.html#dialog-node-limits)
- [Intents](intents.html#intent-limits)
- [Entities](entities.html#entity-limits)
- [Logs](logs_convo.html#log-limits)

### API call limits
{: #api-limits}

The number of API calls allowed per instance depends on your service plan. See your plan description for details.

If you have a Lite plan and reach your API call limit, but the logs show that you have made fewer calls than expected, remember that the Lite plan stores log information for only 7 days.

If you want to upgrade from one plan to another, see [Upgrading](upgrading.html).

## Data centers
{: #regions}

IBM Cloud has a network of global data centers that provide performance benefits to its cloud services. See [IBM Cloud global data centers ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/cloud/data-centers/){: new_window} for more details.

{{site.data.keyword.cloud_notm}} is migrating from managing user access with Cloud Foundry to using token-based Identity and Access Management (IAM) authentication. IAM is being rolled out in different regions at different times. For more information about IAM, see [Authenticating with IAM tokens ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://console.bluemix.net/docs/services/watson/getting-started-iam.html){: new_window}.

You can create {{site.data.keyword.conversationshort}} service instances that are hosted in the following data center regions:

| Region      | Region code | Authentication type | IAM adoption date | Notes |
|-------------|-------------|---------------------|-------------------|-------|
| Sydney      | syd         | IAM                 | 7 May 2018 | Instances created before May 7 were syndicated to the US South data center |
| Germany     | eu-de       | Cloud Foundry       | N/A              | N/A |
| United Kingdom |  eu-gb   | N/A                 | All Instances are syndicated to the US South data center |
| US East     | us-east     | IAM                 | 14 June 2018 | N/A |
| US South    | us-south    | Cloud Foundry       | N/A              | N/A |
{: caption="Data center regions" caption-side="top"}

The authentication mechanism used by your service instance impacts how you must provide credentials when making an API call.

### Cloud Foundry API calls
{: #cf-api}

- Provide your username and password credentials.

```curl
curl -X GET \
 --user {username}:{password} \
   'https://gateway.watson.net/assistant/api/v1/workspaces?version=2017-05-26'
```
{: codeblock}

### IAM API calls
{: #iam-api}

- The base url must include the region. Use the syntax `gateway-<region>.watsonplatform.net` to specify the region in which you created the service instance. The region codes are listed in the *Data center regions* table above.
- Provide the appropriate type of token in the header. In this example, a bearer token is being used. See [Authenticating with IAM tokens ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://console.bluemix.net/docs/services/watson/getting-started-iam.html){: new_window}.

```curl
curl -X GET \
'https://gateway-syd.watsonplatform.net/assistant/api/v1/workspaces?version=2017-05-26' \
 --header 'Authorization: Bearer eyJhbGciOiJIUz......sgrKIi8hdFs'
```
{: codeblock}

See [Services by region ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://console.bluemix.net/docs/resources/services_region.html#services_region){: new_window} for information about the data centers in which other IBM Cloud services are hosted.

## Terms and security
{: #terms}

To learn more about service terms and data security, read the following information:

- [Service terms ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/software/sla/sladb.nsf/sla/bm-0038-08){: new_window}
- [Data security and privacy ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/software/sla/sladb.nsf/sla/csdsp?OpenDocument){: new_window}
- [Information security](information-security.html)

See [Platform overview ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://console.bluemix.net/docs/overview/ibm-cloud.html#overview){: new_window} for more information about IBM Cloud.
