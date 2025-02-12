# Migración de bóveda PCI

Con **Mercado Pago** puedes migrar tu base de clientes y tarjetas de forma segura y transparente para tus usuarios. Puedes transferir los datos de tu proveedor de servicio de pagos actual a Mercado Pago sin necesidad de que tus usuarios realicen alguna acción.

Para transferir los datos de tarjeta de forma segura, Mercado Pago brindará a la empresa que realiza la exportación un servidor SFTP para subir el archivo encriptado **siguiendo la normativa PCI**.

Para encriptar el archivo y transferirlo de forma segura, **use la clave PGP a continuación**.

[[[
```pgp
===
Migration key
===
-----BEGIN PGP PUBLIC KEY BLOCK-----

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
rt+/GYfDo9OZVgr6eupH
=e+ov

-----END PGP PUBLIC KEY BLOCK-----
```

]]]