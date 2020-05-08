# dynamosoft-serverless-test
Prueba de concepto para verificar que el api de dyanamosoft se puede desplegar en ambiente serverless


## Configuración
Solicitar trial apikey en pagina ofocial de dynamosoft, en el handler.js sustituir 'API-KEY' por la llave.

**npm install**

## Despliegue
### Ejecutar la funcion:
**serverless deploy**
```
El resultado esperado sera:

Serverless: WarmUp: setting 1 lambdas to be warm
Serverless: WarmUp: pruebaDynamosftNodeJS-dev-hello
Serverless: Packaging service...
Serverless: Excluding development dependencies...
Serverless: Excluding development dependencies...
Serverless: Uploading CloudFormation file to S3...
Serverless: Uploading artifacts...
Serverless: Uploading service pruebaDynamosftNodeJS.zip file to S3 (4.23 MB)...
Serverless: Uploading service warmUpPlugin.zip file to S3 (1.07 KB)...
Serverless: Validating template...
Serverless: Updating Stack...
Serverless: Checking Stack update progress...
....................
Serverless: Stack update finished...
Service Information
service: pruebaDynamosftNodeJS
stage: dev
region: us-east-1
stack: pruebaDynamosftNodeJS-dev
resources: 16
api keys:
  None
endpoints:
  POST - https://8261487aka.execute-api.us-east-1.amazonaws.com/dev/hello
functions:
  hello: pruebaDynamosftNodeJS-dev-hello
  warmUpPlugin: pruebaDynamosftNodeJS-dev-warmup-plugin
layers:
  None
Serverless: Removing old service artifacts from S3...
Serverless: Run the "serverless" command to setup monitoring, troubleshooting and testing.
serverless invoke local -f imageAnalysis -p post.json
```
## Uso
Enviar una petición http tipo POST con el siguiente body
```
{
	"base64Image": "/9j/4AAQSkZJRgABAQAASABIAA..."
}
```
El atributo base64Image es la imagen en cadena base64. La imagen debe pertenecer a un iD o licencia del AAMVA.

## Resultado al poder obtener la infromación del PDF417 de un ID del AAMVA:

```
{
  "message": "Go Serverless v1.0! Your function executed successfully!",
  "dataId": [
    "18039AZ0146710140701",
    "@\n\rANSI 636026080102ID00410275ZA03160015IDDAQD10496891\nDCSESCOBAR DARIO\nDDEN\nDACCRISTHIAN\nDDFN\nDADROBERT\nDDGN\nDBD02082018\nDBB07011990\nDBA12102018\nDBC1\nDAU061 in\nDAYBRO\nDAG4030 N 44TH AVE APT 1101\nDAIPHOENIX\nDAJAZ\nDAK850312971  \nDCF6065B7212E1652C0\nDCGUSA\nDAW175\nDAZBRO\nDCK18039AZ0146710140701\nDDAN\nDDB02142014\nDDD1\rZAZAAN\nZAB\nZAC\r"
  ]
}
```
