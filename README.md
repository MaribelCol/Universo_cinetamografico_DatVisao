
# Analises de dados: *Estrategias de lucro no universo cinematográfico* 🎬✨
### *Projeto Speed Hiring da [TOTI](https://totidiversidade.com.br/)* ✨

## Resumo
O gerente de vendas do cinema CINEX, da cidade de São Paulo, percebeu uma queda na venda dos bilhetes para assistir aos filmes e gostaria de incrementar o lucro das atividades do cinema após anos de pandemia. Os dados fornecidos pelo cliente incluem as vendas dos bilhetes no mês de março e abril de 2023.

Com a finalidade de analisar as vendas, o gerente contratou, mediante a [TOTI](https://totidiversidade.com.br/), o grupo de análise de dados DatVisão.

**Análise dos dados:** 📈
 - Total de bilhetes vendidos
 -  Valor total arrecadado
 - Dias com menos venda
 - Horários
 - Programação (Sessões): Filme mais visto e menos visto
 - Categorias dos filmes
 - Tipos de sala
 - Filmes com ranking ou classificação indicativa
## Linguagens: 
![](https://img.shields.io/badge/SQLite-07405E?style=for-the-badge&logo=sqlite&logoColor=white) ![](https://img.shields.io/badge/Python-FFD43B?style=for-the-badge&logo=python&logoColor=blue) ![](https://img.shields.io/badge/PowerBI-F2C811?style=for-the-badge&logo=Power%20BI&logoColor=white)
## Modelo relacional (SQL)  
 - CREATE TABLE `theater` (
  `MovTheID` int,
  `ScreenType` varchar(10),
  `Capacity` int,
  PRIMARY key (`MovTheID`));

 - CREATE TABLE `movies` (
  `MovieID` int,
  `Title` varchar(100),
  `Category` varchar(50),
  `Rating` text,
  `Rank` text,
  `Award-winning` boolean, 
  PRIMARY KEY (`MovieID`));
  
 - CREATE TABLE `movieshow` (
  `ShowID` int,
  `MovieID` int,
  `MovTheID` int,
  `Date` date,
  `Day` text,
  `Month` text,
  `Week` text,
  `Time` time,
  PRIMARY KEY (`ShowID`),
  FOREIGN KEY (`MovieID`) REFERENCES `movies`(`MovieID`),
  FOREIGN KEY (`MovTheID`) REFERENCES `theater`(`MovTheID`));

 - CREATE TABLE `ticket` (
  `TicketID` int,
  `ShowID` int(11),
  `SeatNumber` varchar(5),
  `Price` decimal(10,2),
  `PromoID` int,
  `PaymentMethod` varchar(20),
  PRIMARY KEY (`TicketID`),
  FOREIGN KEY (`ShowID`) REFERENCES `movieshow`(`ShowID`),
  FOREIGN KEY (`PromoID`) REFERENCES `promotions`(`PromoID`));

 - CREATE TABLE `promotions` (
  `PromoID` int,
  `Promo` varchar,
  `Discount` varchar,
  PRIMARY KEY (`PromoID`));

[Visualização do modelo relacional](https://viewer.diagrams.net/?tags=%7B%7D&highlight=0000ff&layers=1&nav=1&title=theater.drawio#R7Zxtc6I6FIB%2FjTN7P3SHF0H86Fu73dW2q27be7%2FciRAlKxAvxir762%2BAgNBEW7sVWUun0yEn4S15zsk5OaE1teNurnywsAfYgk5NkaxNTe3WFMUwJPo3FASxQAtLoWDmIysWSVvBCP2CsVBOpCtkwSWTxSKCsUPQIi80sedBk%2BRkwPfxOt9sih0rJ1iAGeQEIxM4vPQBWcRmr6U0tvIvEM3s5M6y3oxrJsCcz3y88tj9POzBuMYFyWXYOy5tYOF1RqT2amrHx5jER%2B6mA52wV5Mee7gOHpz%2BXL%2F6%2Bn35H%2FjR%2Fja%2Bub%2BIL3Z5yCnpy%2FnQI2%2B%2B9K%2F59PLLff3n4%2BLu8vtaumpNvl6wU6Qn4KxYT45tCAj02SuTIOnh5Rq5DqCdo7an2CMjViPTMnDQzKPHJn08eqbafoI%2BQXRwWqyC4AWVmjZyrD4I8Cp8iSWhPZ%2BU2jb20S96WeCwa9JqnzDOFD3XYhSeScUSlfpwSdvcJT0jp6I%2BWBLWxsSOAxZLNEkf2AX%2BDHltTAh2kwuFCEAruXsy1FL0KD6ep1iF1Q6YQKedktPBDqav3Y3Yod2DHCcR1RQVqqYhSazbMnIp%2Bkmvn6kxGg0lPYP1gVyn5VdywHgJRwFuMvrBuLiC2IXED2gTVqsxNWHKT58tLq%2B3qiQ3WBs7p0aJCjP1naWXTu82pOoOvBnt%2B%2FR26fXZ%2FeS64H66xN%2BPgpC7HXAobx7FtR0OwzKLPz3IvOlWFCnFAQoicwoywE9UR667NbVFK65vxr2r3pAefbr79henNXQASEZDHDglO%2FVjuQAm8mb9qE23vpUMWQ%2BEIkzPnToRmzayLOhF7BJAQIx3iM0CI49EXaS16S%2FtyI70Watp9IE6tCxvy%2FQ3bO5TLj2KIUARV5DqzhqG%2BvNMLV7gPkOrKqR1rwl6mdYgT8FLdD6nJQtnDpNDmVA4JkamD%2BlQKNI4WMAYjPvWsPOlNfwkS%2BdORc5Y2sR12GE5aNGUE9OicrR0QDiCJHhmQSpITgZJwzgxJDrvhyFzDknlhr2XG6bXG7rROMQNC%2BW6XqQbptZzfpGm8H6RIukCP8xovsUPk5%2F5YapRXj%2BssUNBKj%2FsvYym%2Fmpcd%2FthQjqPZjQN3g%2Bz8VpAxOXZE1Ho9HowKQIf7GikBEP5X9u4nwy09qhpukrLvl0IfLA7H7v4Q6JSDiQEHlexxkPml75GEJCblTsJnadsCKedHxJZ35H3u8qBiCzVT80Iv%2Fpz5yOTRfjdXud60Op%2FCknqKOfHSCmZECxNFjuV1HkkQODS1xxAYmMrZznCCUU5%2B%2FWfkpChndodlXkvY4CfEFxy418F8YXlUhqSLklygUG8quWD%2BLosiKmbPJayoezmcncMX5fyMbwoldIoRwgv86Yz0o9dITx9QlWW0qGq7Och9jM1Rr%2BVVhGB%2Bh72E2IwNdzN5Q0Klp27%2Fo0nTbEg1TZGxOHSKdV8WgwPosRJoTzwabYOtU8z7AfPwjOpMhZFwyFKmBQKB%2B9rDQGhAxWjMe49jisQigBBFKQfjQRhQMZPG0PgzT9SbrUsKIi2DRWKAj9jtNbAty7WyPNS29C%2Bve33WjcVE4UwIYjKj8aE%2BJn5zGEcldt0ZKrA%2FKTZdVUtNDDXc5GyootmLtGmjyQtf1hkrml%2F0C7HV6dSq%2BT62yxn49W47gvHi9ySJDfFhvNDJk0Lza8fDoswVi90SyyfTd25T7qi5cS0CIP3QmnhY7Yund9YWrU17lV8nJIPcUx%2FJEAm6sX1o7%2Fy7VtNvf%2FnckN%2BLFqCmL4Lgg%2BztFN2PIRxfpF4iCYbL3yUCpBSACIM%2BosEhF8IeoBwXvFREj6SVPfpHBAekDFymQMyvh5UDshpY1%2BpQA9VuJLMf48TbRgmiHYvx0a1ani%2B3%2BSkvvCeb3LkpmAVT042GJ%2FFNzlCJeFX1nftqq9WDV%2BynHut0G8tGorgPJrd5NeRIyS4XbHa2e%2FiOdYU%2Bz6giBYMCwWFX1zuoqVJe4R8QFbKwYRoWbBQJmSdG2dozWDiT9HutPEMe8DpbaXPenLbpo%2FDwY%2BEPyEhAetBsCJ4q5BhLdwg8pg5%2FjscbTqMcam7YYMfFYKk4NH3fcwWMmeFxe1pUSk57%2BWBTkQWnIKVQw72bJZ45Ztwnzcet6M%2B5Azu89oTPyccgb30%2BNABBD1lGx2DjcYfx4b857FRfyUcSW6wLHAYFRxHh8N4LRtGudhonpIN6U1sfJZkPc%2BHXFdfICQq3UEf0W4LVxpOgM2%2BT6%2Bz2OwLJo9ODS1u%2F2VfHAlv%2FyOi2vsf)
 
 ## Video de PoweBi
<iframe width="560" height="315" src="https://www.youtube.com/embed/8naZkbl860s" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

 ## Insights

 1. Observa-se um aumento nas vendas de bilhetes diários (n = 600) e consequente um aumento nos ingressos arrecadados no mês de abril em comparação com o mês de março.
 2. De modo geral, o valor total arrecadado do cinema CINEX foi de R$17.000,00. Os quais o mês de abril teve maior lucro do cinema de R$9.281,00 (55,8%) no total das vendas, em comparação com o mês de março, onde o dinheiro arrecadado foi de R$7.340,00 (44,2%). Tendo um aumento de 14% no valor arrecadado nas segundas e terças do mês de abril.
 3. Enquanto a característica do cinema CINEX, o filme “The Super Mario Bros" foi o que mais ingressos vendeu (n= 143). A categoria aventura foi a que apresentou maior quantidade de ingressos vendidos (> 370) durante os meses avaliados.
4. No geral, o filme “The Super Mario Bros" foi o que mais ingressos vendeu, porém não foi o que mais dinheiro arrecadou (R$2.059,00); provavelmente porque não foi exibido nas salas mais custosas, como VIP. Porém, o filme Creed III vendeu R$2.653,00 mas foi exibido nas salas VIP (68,22%) e 3D (31,78%).
5. Os testes estatísticos estabeleceram que não existem diferenças significativas entre as vendas de bilhetes nem o dinheiro arrecadado, durante os dois meses avaliados.

## Recomendações: 🎬✨

 - [x] _O filme que tem mais sucesso na primeira semana de exibição poderia ser mantido em cartaz durante uma semana a mais do período estabelecido._
 - [x] _O cliente que apresentar uma nota fiscal superior a R$100,00 em compras no shopping, poderá reverter em um desconto na compra do ingresso de 30% de segunda até sexta-feira, com a finalidade de incrementar o lucro na semana._
- [x] _Aumentar a quantidade de exibições às terças dos filmes com classificação top 3 de bilheteria na sala 4D com a finalidade de aumentar 25% o lucro._ 
 - [x] _Os filmes do gênero Aventura tiveram 36,6% dos bilhetes vendidos, arrecadando 34,7% do total de vendas. Poderiam ser adquiridos e exibidos, nas quatro salas, mais filmes desse tipo durante uma semana a mais do período estabelecido._

## Equipe DatVisão: 📈
> Projeto criado pelos analistas de dados: 
> <img src="https://avatars.githubusercontent.com/u/101608754?v=4" width="20px" height="20px"> Alejandro Ariza | [![Github Badge](https://img.shields.io/badge/-Github-000?style=flat-square&logo=Github&logoColor=white&link=https://github.com/Arzeus17)](https://github.com/Arzeus17) | [![Linkedin Badge](https://img.shields.io/badge/-LinkedIn-blue?style=flat-square&logo=Linkedin&logoColor=white&link=https://www.linkedin.com/in/arzeus17/)](https://www.linkedin.com/in/arzeus17/) 
> <img src="https://avatars.githubusercontent.com/u/105130154?v=4" width="20px" height="20px"> Maria de los Angeles Rondon | [![Github Badge](https://img.shields.io/badge/-Github-000?style=flat-square&logo=Github&logoColor=white&link=https://github.com/mmediccil)](https://github.com/mmedicci) | [![Linkedin Badge](https://img.shields.io/badge/-LinkedIn-blue?style=flat-square&logo=Linkedin&logoColor=white&link=https://www.linkedin.com/in/mariamedicci/)](https://www.linkedin.com/in/mariamedicci/)
> <img src="https://avatars.githubusercontent.com/u/89041735?v=4 " width="20px" height="20px"> Maribel Colmenares | [![Github Badge](https://img.shields.io/badge/-Github-000?style=flat-square&logo=Github&logoColor=white&link=https://github.com/MaribelCol)](https://github.com/MaribelCol) | [![Linkedin Badge](https://img.shields.io/badge/-LinkedIn-blue?style=flat-square&logo=Linkedin&logoColor=white&link=https://www.linkedin.com/in/maribel-colmenaresarteaga/)](https://www.linkedin.com/in/maribel-colmenaresarteaga/)
> <img src="https://avatars.githubusercontent.com/u/85193747?v=4" caption="Marioxis Macías" width="20px" height="20px"> Marioxis Macías | [![Github Badge](https://img.shields.io/badge/-Github-000?style=flat-square&logo=Github&logoColor=white&link=https://github.com/marioxis)](https://github.com/marioxis) | [![Linkedin Badge](https://img.shields.io/badge/-LinkedIn-blue?style=flat-square&logo=Linkedin&logoColor=white&link=https://www.linkedin.com/in/marioxis-macias-cuyare/)](https://www.linkedin.com/in/marioxis-macias-cuyare/)