## Transaction Additional Fields

In Paraguay, a payment process is compose by 3 differents stages, 
- finantialObligation (Obligación): when the suppliers make the invoice to receive the payment.
- paymentRequest (Solicitud de Transferencia STR): when the buyer makes the request to the Ministerio de Hacienda to do the payment
- transaction (Orden de Transferencia OT): when the payment is done by Ministerio de Hacienda and the money is deposit to the supplier.
The current transaction object only covers the last part of the process, and the other two stages are relevant for the process, too.
Also, the Orden de Transferencia OT in Paraguay have the extra fields that are not in the transaction object: description, requestDate and budgetSource 

## Example
```javascript
"transactions": 
[
    {
        "id": "194382",
        "value": {
            "amount": 7132364,
            "currency": "PYG"
        },
        "date": "2016-08-30T00:00:00Z",
        "payer": {
            "id": "PY-PGN-12-7",
            "name": "007-MINISTERIO DE EDUCACION Y CIENCIAS"
        },
        "payee": {
            "id": "PY-RUC-1056838-7",
            "name": "ALDO ENRIQUE CENTURI"
        },
        "uri": "https://datos.hacienda.gov.py/id/transferencias/anio/2016/nivel/12/entidad/7/ot/194382",
        "description": "PAGO DIRECTO A PROVEEDORES",
        "requestDate": "2016-08-30T00:00:00Z",
        "budgetSources": ["2016/12/7/2/1/5/0/1/99/200/260/260/10/1000000/57"],
        "finantialObligations": [{
            "id": 41084,
            "bill": {
                "id": "001-001-0000201",
                "type": "FACTURA",
                "description": "OBLIG. POR CONSULTORIAS, ASESORIAS E INVESTIGACIONES - ALDO ENRIQUE CENTURION LOPEZ - CD Nº 02/2016 - 1ER DESEMBOLSO - FACTURA Nº 001-001-0000201 - AC.-",
                "date": "2016-05-25T00:00:00Z",
                "amount": {
                    "amount": 7500000,
                    "currency": "PYG"
                }
            },
            "retentions": [{
                "type": "tax",
                "name": "IVA",
                "amount": {
                    "amount": 204545,
                    "currency": "PYG"
                }
            }, {
                "type": "tax",
                "name": "Renta",
                "amount": {
                    "amount": 136364,
                    "currency": "PYG"
                }
            }, {
                "type": "fee",
                "name": "DNCP",
                "amount": {
                    "amount": 26727,
                    "currency": "PYG"
                }
            }, {
                "type": "penalty",
                "name": "Incumplimiento",
                "amount": {
                    "amount": 0,
                    "currency": "PYG"
                }
            }, {
                "type": "other",
                "name": "Otras retenciones",
                "amount": {
                    "amount": 0,
                    "currency": "PYG"
                }
            }],
            "description": "OBLIG. POR CONSULTORIAS, ASESORIAS E INVESTIGACIONES - ALDO ENRIQUE CENTURION LOPEZ - CD Nº 02/2016 - 1ER DESEMBOLSO - FACTURA Nº 001-001-0000201 - AC.-",
            "creationDate": "2016-07-25T00:00:00Z",
            "approvalDate": "2016-07-25T00:00:00Z",
            "modificationDate": null,
            "cancellationDate": null,
            "paymentRequestIds": [88154]
        }],
        "paymentRequests": [{
            "id": 88154,
            "description": "CONSULTORIAS, ASESORIAS E INVESTIGACIONES - ALDO ENRIQUE CENTURION LOPEZ -",
            "status": "TRANSFERIDO",
            "creationDate": "2016-07-27T00:00:00Z",
            "authorizationDate": null,
            "modificationDate": "2016-08-30T00:00:00Z",
            "treasuryReceptionDate": "2016-08-01T00:00:00Z",
            "requestedAmount": {
                "amount": 7500000,
                "currency": "PYG"
            },
            "totalRetentionAmount": {
                "amount": 367636,
                "currency": "PYG"
            },
            "payedAmount": {
                "amount": 7500000,
                "currency": "PYG"
            },
            "finantialObligationIds": ["41084"]
        }]
    }
]
```