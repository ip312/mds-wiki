To access the Mobility Data Space in a convenient way you need to install the Dataspace Connector and the MDS Frontend as well as to obtain the DAPS token.  
For the access to the MDS test environment please take the following steps <br>
(for the productive environment follow the same steps + set your unique DAPS Token and the URL of the MDS Catalog instead of Test Catalog)

<img src="https://user-images.githubusercontent.com/91048868/173030556-0a80320c-5361-47b5-858b-e2358b6c9993.jpg" width=800><br>

## Set-up the connector

1. Download [a last release of the Dataspace Connector](https://github.com/International-Data-Spaces-Association/DataspaceConnector/releases).

2. For test purposes you can use [a generic DAPS token](https://github.com/Fraunhofer-AISEC/trusted-connector/tree/master/examples/etc). <br>
For the productive usage please request the DAPS token at [daps-certificates@aisec.fraunhofer.de](mailto:daps-certificates@aisec.fraunhofer.de)

3. Configure the connector. In the configuration file `resources/conf/config.json` <br>
a) set the path to the DAPS Token (keystore) <br>
b) change the connector deploy mode to PRODUCTIVE:<br>
`"ids:connectorDeployMode" : { "@id" : "idsc:PRODUCTIVE_DEPLOYMENT },`<br>
c) set the connector accessURL <br>
d) configure [another parameters](https://international-data-spaces-association.github.io/DataspaceConnector/Deployment/Configuration) if needed

4. Deploy and start the connector

5. If everything worked fine, the connector for the local build is available at `https://localhost:8080/.` 

## Set-up the frontend

1. Download [a last release of the Dataspace Connector Frontend](https://github.com/Mobility-Data-Space/DataspaceConnectorUI/releases).

2. Install [Node.js v.14](https://nodejs.org/en/download/)

3. Install the frontend: `npm install --no-audit`

4. Start the frontend `npm start`. 

5. If everything worked fine, the frontend for the local build is available at `https://localhost:8082/.` 

<img src="https://user-images.githubusercontent.com/91048868/169023128-e79a8770-0469-4264-9894-9ceed79deba8.jpg" width=600><br>

6. Using _Advanced View => Settings => General_ set the connector name, connector description, connector curator (as URL) and connector maintainer )as URL).
**Please be aware that this information is accurate and complete**. These fields represent the connector in the MDS catalog.

<img src="https://user-images.githubusercontent.com/91048868/169081507-66ef0389-08ab-47ac-a240-4e588a9e6752.jpg" width=600>

## Register the MDS Test Catalog/Broker

1. Using _IDS Ecosystem => Brokers => Add Broker_ set the URL of the MDS Test Catalog.

<img src="https://user-images.githubusercontent.com/91048868/170670873-a8123104-c33e-4cf9-9c1d-6a8d62d006e0.jpg" width=400><br>

2. Click _REGISTER_ (on the right side).

<img src="https://user-images.githubusercontent.com/91048868/170673882-9004f4c5-6d88-4b7e-8192-f2bbfe8714e1.jpg" width=600><br>

If everything worked fine, the connector is now available in the MDS Test Catalog.

## Data consumption

1. Using _Data Consumption => Requests => Request Resource_ select a desired resourse. You can directly enter the Connector URL (Access URL in the MDS Catalog) and select _Show available reasources_

<img src="https://user-images.githubusercontent.com/91048868/170651063-4cb93e89-cca8-44c2-aaff-a4a371c2db54.jpg" width=600><br>

Alternatively you can select _BROKER_ tab, enter the [Catalog URL](https://github.com/Mobility-Data-Space/mobility-data-space/wiki#broker--metadata-catalog) ([URL]/infrastructure) und a search term for the direct search of desired resources in the MDS Catalog.

2. Select a desired resource and click the icon _Show representations_ (second last on the right side).

<img src="https://user-images.githubusercontent.com/91048868/170658417-77c046df-c136-4b86-a709-012a38cb8c90.jpg" width=600><br>

3. Click the URL-Button under _Select representation_ and subsequently click the icon _Request artifact_ (last on the right side).

<img src="https://user-images.githubusercontent.com/91048868/170659186-66eb5861-6300-498b-b271-144180d27310.jpg" width=600><br>

4. Check the list of rules (usage policies), and a licence and click _ACCEPT_ if you agree with the usage policies. Additionally you can turn on _Subscribe_ to get a subscription for the resource. 

<img src="https://user-images.githubusercontent.com/91048868/170662482-56dd90dd-9bf4-4f76-81aa-ba021a472b30.jpg" width=400><br>

5. Click the URL-Button under _Download_ to download the requested artifact.

## Data offering

1. Using _Data Offering => Offerings => Add Offering_ set the offer title, offer description, offer publisher (as URL), keywords, license (as URL), language and payment modality and click the _NEXT_ button. 
**Please be aware that this information is accurate and complete**. These fields represent the offer in the MDS catalog. 

<img src="https://user-images.githubusercontent.com/91048868/170665339-0edb7376-de3b-43bc-991b-69bf69d233b3.jpg" width=600><br>

2. Create a new usage policy pattern or use a template if available and acceptable and click the _NEXT_ button.

<img src="https://user-images.githubusercontent.com/91048868/170666289-5b549773-7bf7-4bef-8cb3-6a62d7699b35.jpg" width=400><br>

3. Define an artifact you want to offer as a local file or external data source. For the last one you have a choice between a REST-Interface with basic or API-Key Identification and a database request with an SQL Query. Set a file type if not automatically set, then click the _NEXT_ button.

<img src="https://user-images.githubusercontent.com/91048868/170668168-dd0ab024-0955-4994-bcca-3a7f68599b7b.jpg" width=400><br>

4. Add a catalog for your offer or use an existing one and click the _NEXT_ button. Please don't mix up this catalog with the MDS Catalog/Broker. In this case the catalog is just an (arbitrary defined by the data publisher) directory for data offers originating from the same domain (e.g. mobility data) or fulfilling similar purposes.

<img src="https://user-images.githubusercontent.com/91048868/170673032-d8ad5994-7266-47ca-8279-3feb513a90ad.jpg" width=600><br>

5. Select the MDS Catalog/Broker and click the _SAVE_ button. 

<img src="https://user-images.githubusercontent.com/91048868/170673109-714c9f51-a683-4a8b-a894-15940f4300ae.jpg" width=600><br>

If everything worked fine, the offer (resource) is now available in the MDS Catalog.