### Linguagem de Programação
#### Strings II
---

### Na Aula Anterior

Strings
- Entrada e saída
- Algoritmos da biblioteca `cstring`
---

### Objetivo da Aula
- Introduzir comando para leitura de strings com espaços em branco `' '`
- Exercícios
---

### Strings
#### Relembrando

- Vetor de caracteres:<br>
  `char s[] = {'e', 'c', 't'};`
- String $\rightarrow$ vetor de caracteres terminados com `\0`:<br>
  `char s[] = {'e', 'c', 't', '\0'};`<br>
  `char s[] = "ect";`
---

### Strings
#### Relembrando

- Comando de entrada `cin` insere `\0` automaticamente
- Comando de saída `cout` imprime variável do tipo string diretamente

```C++
  int main(){
        char s[51];
        cin >> s;
        cout << s << endl;
        return 0;
  }
```
---

### Strings

Entretanto, com o comando `cin`, não é possível ler strings com espaços:

- Na entrada, espaços em branco ou quebras de linha (tecla enter) informam o final da string digitada pelo usuário
- É necessário algum comando que permita a leitura de strings com espaços em branco
---

### Strings
#### Leitura de Strings com Espaços em Branco
- Para ler strings com espaços em branco, a função
  `cin.getline` deve ser utilizada
- A entrada do teclado é lida até que uma quebra de linha (tecla enter) seja digitada
---

### Strings
#### Leitura de Strings com Espaços em Branco
`cin.getline` - recebe dois parâmetros:
1. variável do tipo string onde o texto deve ser armazenado
2. número máximo de caracteres a serem lidos contando com o `\0`
---

### Strings
#### Leitura de Strings com Espaços em Branco

Exemplo:

```C++
int main(){
    char s[51];
    cin.getline(s, 51); //le 50 caracteres
    cout << s << endl;
    return 0;
}
```
---

### Lista de Presença

<img src="https://chart.apis.google.com/chart?cht=qr&chs=300x300&chld=L%7C1&chl=https%3A%2F%2Fbit.ly%2F3HCZDWJ" alt="QR Code" border="0" />

<a href="https://bit.ly/3HCZDWJ"><p style="text-align:center;">https://bit.ly/3HCZDWJ</p></a>

---

### Strings
#### Leitura de Strings com Espaços em Branco
Problemas acontecem quando o `cin.getline`
é executado _após_ o comando `cin`:

```C++
const int STRMAX = 31;
int main(){
    char s[STRMAX];
    int x;
    cout << "Informe um inteiro:\n";
    cin >> x;
    cout << "Inteiro informado: " << x << endl;
    cout << "Informe uma string:\n";
    cin.getline(s, STRMAX);
    cout << "String informada: " << s << endl;
    return 0;
}  
```
---

### Strings
#### Leitura de Strings com Espaços em Branco
Ou seja, a entrada para a string é ignorada

```
Informe um inteiro:
5
Inteiro informado: 5
Informe uma string:
String:
```
---

### Strings
#### Leitura de Strings com Espaços em Branco

Portanto, se for usar `cin.getline` após o `cin`:
- Usar função `cin.ignore()` logo após o `cin`
- Isto evita que o `\n` seja considerado como a string digitada
---

### Strings
#### Leitura de Strings com Espaços em Branco
Código correto:

```C++
const int STRMAX = 31;
int main(){
    char s[STRMAX];
    int x;
    cout << "Informe um inteiro:\n";
    cin >> x;
    cin.ignore();
    cout << "Inteiro informado: " << x << endl;
    cout << "Informe uma string:\n";
    cin.getline(s, STRMAX);
    cout << "String informada: " << s << endl;
    return 0;
}
```
---

### Exercícios

Implemente uma função que remova os espaços
em branco de uma string:
- Entrada:<br>
  `Estudos␣de␣LIP`
- Saída:<br>
  `EstudosdeLIP`

Armazene o resultado em um parâmetro de saída.

Implemente também a função `main` para testar
a função solicitada.

---

### Exercícios
Um palíndromo é uma palavra/frase que pode ser lida tanto da esquerda para a direita quanto da direita para a esquerda. Exemplos:<br>
- `osso`
- `radar`
- `ame o poema`
- `subi no onibus`
---

### Exercícios
Implemente uma função que receba como parâmetro uma string e retorne verdadeiro caso
ela seja um palíndromo ou falso caso contrário.
---

### Exercícios
Existem duas versões para o problema:
1. Considerando espaços em branco como parte da string:<br>
 - `osso` é palíndromo
 - `o␣s␣s␣o` é palíndromo
 - `subi␣no␣onibus` não é palíndromo
2. Desconsiderando espaços em branco como parte da string:<br>
 - `subi␣no␣onibus` é palíndromo
 - `subi␣␣␣␣␣no␣␣onibus` é palíndromo
---

## Sumário
Na aula de hoje:
- Strings: leitura de strings com espaços
- Exercícios
---
