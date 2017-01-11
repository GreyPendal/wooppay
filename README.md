# Wooppay
Wooppay SOAP client

## Library is deprecated

This library is deprecated and no longer supported. Use `kolesa-team/wooppay` instead.

## Installation

    composer require kolesa-team/wooppay

## Usage example

    $client = new \Wooppay\Client($uri, $options);
    
    $client->login($username, $password);
    $client->requestConfirmationCode($phoneNumber);
    
    $result   = $client->createInvoiceExtended(…);
    $status   = $client->getOperationData([$result->getOperationId()]);
    $response = current($status);
    
    if ($status && $status->getStatus() == \Wooppay\Objects\Response\GetOperationData::STATUS_DONE) {
        echo "Operation successfully completed.";
    }
