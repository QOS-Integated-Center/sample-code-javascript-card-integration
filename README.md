# sample-code-javascript-card-integration

Intégration de du checkout 

Prérequis
Créer un compte sur la plateforme Qos et obtenir la clé qos .
Souscrire au paiement par carte
Souscrire au paiement mobile du Bénin et Togo 

Initier la transaction 
Avant la redirection sur le checkout vous devez d’abord initier la transaction avec les informations suivante:

Methode : POST

url: https://b-checkout-api.qosic.net/public/v1/initTransaction
Body: 
 {
                "type": "all", // in checkout value is mobile/card/all ==> m
                "transref": "Test001235869", // transref ===> m et unique
                "qosKey": "qos123456789", // is provided by qos platform  ==> m
  "returnUrl": "https://www.qosic.com", // is callback redirection with parameter transref ans status ==> m
                "amountDetails": {
                    "totalAmount": 10, // amount wil be pay by customer //  ==> m
                    "currency": "XOF"
                },
                "saleDetails": {
                    "firstName": "jac", // m
                    "lastName": "Djac", // m
                    "middleName": "KJ",
                    "nameSuffix": "jac",
                    "title": "Mr",  // m
                    "address1": "Cotonou", // m
                    "address2": "Cococodji",
                    "address4": "string",
                    "locality": "Litoral",   // m
                    "administrativeArea": "",
                    "postalCode": "229",  // m
                    "country": "Benin",  // m
                    "district": "Bj",   // m
                    "buildingNumber": "string",
                    "email": "jacques@qosic.com",  // m
                    "emailDomain": "string",
                    "phoneNumber": "66895585",   // m
                    "phoneType": "cel"  // m
                }
            }


 m = obligatoire 
Response :
{
token: '5852d651-5ece-4dcd-ae3e-a5da9e1b1758', 
responseCode:'00', 
url:'http://checkout.qosic.net:4243/pay/5852d651-5ece-4dcd-ae3e-a5da9e1b1758'
}

Après initiation de la transaction redirigée sur la plateforme du checkout 
Dans la réponse de l’initialisation vous recevez url de redirection donc rediriger votre site web sur ce dernier et laisser le processus continuer.

Url de retour:
l’url de retour n’est rien d’autre que le retour  sur votre site web après paiement effectuté avec succès ou non.

Méthode : GET
Params : status et transref
Url : https://yoursiteweb.xx?status=SUCESS&transref=TS00001
 

l’exemple du code d'intégration sur notre github 
contactez le support en cas de difficulté.


## English version 
