## Codelab de Introdução ao Jetpack Compose

Este repositório contém o código desenvolvido durante o Codelab "Jetpack Compose Basics" do Android Developers. 
O codelab explora os fundamentos do Jetpack Compose, um toolkit moderno para desenvolvimento de UI no Android.

**O que foi estudado:**

O codelab aborda os seguintes tópicos:

*   **Introdução ao Jetpack Compose**: É apresentado o Jetpack Compose e seus princípios:
    *   **Natureza Declarativa:** Em vez de definir a UI passo-a-passo como no sistema de Views tradicional, o Compose permite descrever a UI desejada e o framework cuida da atualização da tela.
    *   **Simplicidade:** Compose utiliza funções simples em Kotlin (funções composables) para construir a interface do usuário.

*   **Construção de UIs**:
    *   **Composables Básicos**: O codelab demonstra como usar composables como `Column`, `Row`, `Surface` e `Text` para criar layouts.
        *   **Column:** Organiza os elementos filhos verticalmente.
        *   **Row:** Organiza os elementos filhos horizontalmente.
        *   **Surface:** Um componente Material Design que fornece uma superfície para desenhar outros elementos, com suporte a elevação e cor de fundo.
        *   **Text:** Exibe texto na tela.

    *   **Modificadores:** Aprende-se a usar modificadores para personalizar a aparência e o comportamento dos composables, como `padding`, `fillMaxWidth` e `weight`.
        *   **Exemplo de modificador `padding`**:
            ```kotlin
            import androidx.compose.foundation.layout.padding
            import androidx.compose.ui.unit.dp
            // ...
            @Composable
            fun Greeting(name: String, modifier: Modifier = Modifier) {
                Surface(color = MaterialTheme.colorScheme.primary) {
                    Text(
                        text = "Hello $name!",
                        modifier = modifier.padding(24.dp)
                    )
                }
            }
            ```

*   **Gerenciamento de Estado**:
    *   **`remember` e `mutableStateOf`**: O codelab ensina a usar a função `remember` para armazenar o estado dentro de um composable e a função `mutableStateOf` para criar variáveis de estado que, quando alteradas, disparam a recomposição da UI.
    *   **Recomposição:** É explicado o conceito de recomposição, onde a UI é automaticamente atualizada quando o estado muda.
 
       ![Gerenciamento de Estado](https://developer.android.com/static/codelabs/jetpack-compose-basics/img/6675d41779cac69.gif)

*   **Criação de Listas Eficientes**:
    *   **`LazyColumn`**: É introduzido o `LazyColumn`, um componente para criar listas longas que renderiza apenas os itens visíveis na tela, similar ao `RecyclerView` do sistema tradicional de Views.
        *   **Exemplo de `LazyColumn`**:
            ```kotlin
            import androidx.compose.foundation.lazy.LazyColumn
            import androidx.compose.foundation.lazy.items
            // ...
            @Composable
            private fun Greetings(
                modifier: Modifier = Modifier,
                names: List<String> = List(1000) { "$it" }
            ) {
                LazyColumn(modifier = modifier.padding(vertical = 4.dp)) {
                    items(items = names) { name ->
                        Greeting(name = name)
                    }
                }
            }
            ```

            ![Listas](https://developer.android.com/static/codelabs/jetpack-compose-basics/img/284f925eb984fb56.gif)

*   **Animações**:
    *   **`animateDpAsState`**: O codelab mostra como usar a função `animateDpAsState` para animar propriedades de tamanho de forma simples.
    *   **Animações Baseadas em Mola**: São exploradas animações com mola usando a função `spring`, que permitem criar animações mais naturais e realistas.
 
      ![Animações](https://developer.android.com/static/codelabs/jetpack-compose-basics/img/9efa14ce118d3835.gif)

*   **Estilos e Temas**:
    *   **`MaterialTheme`**: É apresentado o `MaterialTheme`, um componente que fornece estilos e temas predefinidos de acordo com as especificações do Material Design.
    *   **Customização de Temas**: Aprende-se a personalizar cores, estilos de texto e formas usando o `MaterialTheme`.

**O que foi utilizado:**

*   **Android Studio**: A IDE oficial para desenvolvimento Android foi utilizada para criar o projeto, escrever o código e visualizar a UI usando o Preview do Compose.
*   **Kotlin**: A linguagem de programação Kotlin foi fundamental para escrever as funções composables, gerenciar o estado e implementar a lógica do aplicativo.
*   **Jetpack Compose**: O foco do codelab, o Jetpack Compose foi utilizado para criar todos os elementos da UI do aplicativo.
*   **Material Design 3**: O sistema de design do Google foi utilizado para fornecer estilos, temas e componentes visuais pré-construídos, como `Surface`, `Button` e `Card`.

**App Final:**

![Exemplo de GIF](https://developer.android.com/static/codelabs/jetpack-compose-basics/img/8d24a786bfe1a8f2.gif)


**Assuntos aprendidos:**

Ao final do codelab, aprendi alguns conceitos-chave do Jetpack Compose:

*   **Princípios do Jetpack Compose:**
    *   **Declaratividade:** Descrever a UI desejada em vez de especificar os passos para construí-la.
    *   **Recomposição:** Atualização automática da UI quando o estado muda.
    *   **Imutabilidade:** Os objetos de estado são imutáveis, o que facilita o rastreamento de mudanças e a recomposição da UI.
*   **Funções Composable:** Funções em Kotlin anotadas com `@Composable` que descrevem a UI.
*   **Modificadores:** Elementos que permitem customizar a aparência, layout e comportamento dos composables.
*   **Estado e Hoisting de Estado:** Como gerenciar o estado dentro da UI do Compose e elevá-lo para um ancestral comum quando necessário.
*   **Listas Lazy:** Criação de listas eficientes e performantes que renderizam apenas os itens visíveis.
*   **Animações:** Técnicas para animar propriedades dos composables, incluindo animações baseadas em mola.
*   **Estilização e Temas:** Aplicação de estilos e temas predefinidos do Material Design e customização de temas para criar a aparência desejada.

