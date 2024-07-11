# Trabalhando com Collections

## Referência: Curso de Desenvolvimento Java, Giuliana Silva Bezerra
[Compre aqui](https://www.udemy.com/course/curso-de-desenvolvimento-java/)
<hr>

## Tópicos

- []()

<hr>

## Arrays vs Collections

Já sabemos que para iniciar uma Array, fazemos dessa forma:
```java
String[] nomes = new String[3];

//ou

String[] nomes = {"Giuliana", "Leia", "Rey"};
```

O problema dos Arrays, é que a gente define o tamanho deles. Muita das vezes a gente não sabe o tamanho dos arrays.

Para vencer essa limitação de tamanho fixo, usamos **Collections**, como o **ArrayList**.

```java
import java.util.ArrayList;

ArrayList<String> nomesArrayList = new ArrayList<>();
```

Passamos dentro do ``<>`` o tipo do array e iniciamos com o construtor. Não precisa, portanto, informar o tamanho
desse Array. **Ele é criado por padrão, com tamanho 10.**
<hr>

## Declarando um ArrayList

O ArrayList implementa ``List<>``. Ele é, portanto, um array e uma lista. :)

Nós podemos usar no Array, propriedades específicas da lista, por exemplo:

```java
import java.util.ArrayList;
import java.util.List;

List<String> nomesArrayList = new ArrayList<>();
// iniciamos essa List com o ArrayList. (Tipo mais concreto).
```
<hr>

## Adicionando Elementos no ArrayList

Para colocar valores dentro do array, usamos ``.add``, veja:
```java
import java.util.ArrayList;
import java.util.List;

List<String> nomesArrayList = new ArrayList<>();
nomesArrayList.add("1")
nomesArrayList.add("2")
```

Podemos iniciar esses ``.add``, dentro da propria inicialização do ArrayList:
```java
import java.util.ArrayList;
import java.util.List;

List<String> nomesArrayList = new ArrayList<>() {{
    add("1");
    add("2");
    // não precisa passar o nome do list dentro do {}, pois estamos referenciando a  
    // variável usando o ".this", internamente.
}};
```
<hr>

## Get no ArrayList
Para obtermos um elemento do ArrayList, basta usar ``.get(index)`` passando o index desejado dentro.

```java
nomesArrayList.get(0);
```
<hr>

## Insert e Update no ArrayList

Para inserimos e atualizamos um elemento do ArrayList em posições específicas, usamos o ``.set()``.

```java
nomesArrayList.set(0, "1");
//passamos o index desejado a ser substituido, e depois o que queremos substituir.
```

**Não podemos passar no ``.set``, uma posição maior que o tamanho atual da Array!**
<hr>

## Delete no ArrayList

Para deletarmos um elemento do ArrayList, basta utilizar ``.remove``.

```java
//podemos remover com o indíce
nomesArrayList.remove(1);

//ou remover passando o objeto em sí (como ele está declarado dentro da Array).
nomesArrayList.remove("1");
```
<hr>

## Sort no ArrayLit

Muitas vezes precisamos trabalhar com uma lista ordenada, para fazermos calculos específicos, por exemplo.

Para isso, utilizamos ``.sort()``. 

**Se for String, ele colocará em ordem alfabética. Se for número, em ordem crescente.**

```java
import java.util.Collection;

Collection.sort(nomesArrayList);
```
<hr>

## Percorrendo um ArrayList - For vs Iterator

A gente já sabe fazer isso com o for (usando forEach).

![img.png](img.png)

Mas podemos iretar com os "iterators".

```java
import java.util.Iterator;
//precisamos passar o tipo de Array, pois é um método genérico.
Iterator<String> it = nomesArrayList.iterator();

while (it.hasNext()) {
    String itemAtual = it.next();
    System.out.println(itemAtual);
}
```

Esse ``it``, possui um método ``hasNext()``, que funcionará como um "ponteiro", percorrendo da esquerda para direita.
E enquanto tiver um next (um item), ele continuará iterando.
<hr>

## Conversão entre Array e ArrayList