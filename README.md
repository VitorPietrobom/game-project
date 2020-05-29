# Projeto EaD Corona Run

# Equipe
* Vitor Rodrigues Pietrobom - 245584
* Guilherme Tezoli Bakaukas - 217332

# Descrição Resumida do Projeto
O projeto consiste num jogo feito em espaco celular baseado em turnos.

O jogo tem como personagens um jogador e dois antagonistas, a Unicamp e um doente, sendo que a primeira solta atividades e o segundo solta corona virus.

A cada turno o jogador pode realizar um movimento e os antagonistas e personagens se movem,

# Vídeo do Projeto
[![Video explicativo sobre o projeto](https://img.youtube.com/vi/https://youtu.be/el5MtHRGmbc/0.jpg)](https://youtu.be/el5MtHRGmbc)

# Diagrama Geral de Componentes

Este é um diagrama inicial do jogo proposto:

![Diagrama Jogos](diagrama_componentes-jogo.PNG)

Diagrama de herança das interfaces:

![Diagrama Interfaces](Interfaces_heranca-jogo.PNG)

Diagrama geral:

![Diagrama Geral](modelo_geral_dos_componentes-jogo.PNG)

Para cada componente será apresentado um documento conforme o modelo a seguir:

# Componente `<Nome do Componente>`

![Componente](diagrama-componente.png)

## Interfaces

Interfaces associadas a esse componente:

![Diagrama Interfaces](diagrama-interfaces.png)

Campo | Valor
----- | -----
Classe | `<caminho completo da classe com pacotes>` <br> Exemplo: `pt.c08componentes.s20catalog.s10ds.DataSetComponent`
Autores | `<nome dos membros que criaram o componente>`
Objetivo | `<objetivo do componente>`
Interface | `<interface em Java do componente>`
~~~
public interface ITableProducer {
  String[] requestAttributes();
  String[][] requestInstances();
}
public interface IDataSource {
  public String getDataSource();
  public void setDataSource(String dataSource);
}
public interface IDataSet extends ITableProducer, IDataSource {
}
~~~

## Detalhamento das Interfaces

### Interface Imovimento
Analisar o movimento e colisão das peças, determinar se é ou não possível movimentar.

Método | Objetivo
-------| --------
move(pos_x: int, pos_y: int, tabuleiro: Itabuleiro): boolean | Analisar se o movimento é válido. Os parâmetros pos_x e pos_y indicam a posição final da peça, o tabuleiro é passado como parâmetro para ter acesso à matriz em que estão as peças do jogo
collision(pos_x: int, pos_y: int, tabuleiro: ITabuleiro)|Analisar o caso de colisões . Os mesmos parâmetros são passados.

### Interface ITabuleiro

Realizar a movimentação de uma peça. 

Método | Objetivo
-------| --------
move(destino:pos_x: int, pos_y: int, tabuleiro: ITabuleiro, peca:Ipeca) | Realizar a movimentação de uma peça. Os parâmetros são passados para localizar a peça e sua posição final.

