# 1

Vamos ver o como validar os tipos de variáveis passadas para funções.
Quando forem de tipos errados vamos ter erros como esse 

```
Exemplo de erro
```

Queremos isso para evitar que ocorram erros de utilização da nossa função e assim nosso código seja mais escalável e confiável.

Para implementar isso vamos usar decoradores para interceptar os parâmetros e marshmallow para validar os tipos.


# 2

O problema que estamos tendo hoje é que não é temos nativamente um jeito de forçar um método em python a receber apenas um tipo de variável. Por exemplo:

``` python
def imprime_int(
    a:int
):
    print(a)
```

Embora explicitamente pedimos apenas `int` ainda é possível mandar qualquer tipo de variável.

Temos então:

``` 
$ imprime_int(1)
1

$ imprime_int("a")
a

$ imprime_int([1,2,3])
[1,2,3]
```

E isso é um problema pelos seguintes motivos.

- Se trabalhamos em grupo algum colega pode tentar utilizar o método de forma errada.
- Se temos muitas funções podemos nos perder e esquecer como funciona exatamente a função.
- Ligado ao item acima, é mais escalável e caso haja algum erro ele será detectado nos testes.

Do que precisamos.

Para fazer o nosso verificador precisamos da biblioteca marshmallow, então vamos iniciar instalando ela assim:

```bash
pip install marshmallow
```

ou

```bash
pip3 install marshmallow
```

> Use ambientes de desenvolvimento virtual para melhor gerenciar suas bibliotecas

Como usamos marshmallow.

Precisamos das variáveis que esperamos receber e das variáveis que vão ser verificadas, assim, por nome, vamos ver um a um se os tipos e variáveis casam.

Então vamos por partes, como definimos o que é esperado.

``` Python
from marshmallow import fields, Schema

class InputsEsperados(Schema):
    a = fields.Integer(required=True)
```

Dizemos aqui que o parâmetro "a" é esperado no formato de número inteiro, além disso, esse parâmetro é obrigatório. Note os imports de `fieds` e `Schema` da biblioteca marshmallow.

Para fazer a validação do parâmetro com marshmallow podemos fazer assim:

```

```

Assim acabamos de entender como podemos utilizar o marshmallow para validar.

Em seguida vamos ver como interceptamos os parâmetros para validá-los antes de entrar na função e de quebra podemos validar a resposta também.