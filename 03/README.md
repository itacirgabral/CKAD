# **Configuração e Storage**

9. Crie um Secret `db-secret` com chave `PASSWORD=12345`.
10. Crie um Pod que monta esse Secret como variável de ambiente.
11. Crie um Pod com `initContainer` que escreve em um `emptyDir` volume e um container principal que lê esse arquivo.