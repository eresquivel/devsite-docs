> CLIENT_SIDE
>
> h1
>
> Cambiar textos

| - | Descripción |
| --- | --- |
| Momento de personalización  | Al renderizar el Brick  |
| Propiedad  | customization.visual.texts.{cardNumber, cardExpirationDate, cardSecurityCode, cardholderName, cardholderIdentification, cardholderEmail, formTitle, emailSectionTitle, installmentsSectionTitle, selectInstallments, formSubmit}  |
| Atributo  | label, placeholder  |
| Tipo  | String  |
| Observaciones  | Al enviar texto vacío, la pantalla presentará el texto definido por el layout predeterminado. Por otro lado, al enviar un texto personalizado, reemplazará el texto predeterminado. Para comprobar cuáles son los textos por defecto, consulta la [sección Layout](/developers/es/docs/checkout-bricks/card-payment-brick/introduction) del Card Payment Brick.  Si los textos personalizados son más grandes que el espacio disponible, el texto mostrado se interrumpirá hasta el tamaño máximo permitido y el excedente será reemplazado por el símbolo "...".  |

[[[
```Javascript
const settings = {
    ...,
    customization: {
        visual: {
            texts: {
                formTitle: 'string',
                installmentsSectionTitle: 'string',
                ...,
            },
        }
    },
}
```
```react-jsx
const customization = {
 visual: {
   texts: {
     formTitle: 'string',
     installmentsSectionTitle: 'string'
     ...,
   }
 }
};

```
]]]