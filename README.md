# Projeto de Machine Learning com bases de Crédito

Projeto de ciência de dados e machine learning de base de Credict Score presente neste repositório, o projeto foi escrito na linguagem Python. Os dados estão no formato FTR e contém informações sobre clientes de uma instituição financeira. Em especial, estamos interessados em explicar a segunda coluna, chamada de **mau**, que indica se um cliente é adimplente(`mau = 0`), ou inadimplente (`mau = 1`), ou seja, queremos entender o porque um cliente deixa de honrar com suas dívidas baseado no comportamento de outros atributos, como salário, escolaridade e movimentação financeira. Uma descrição completa dos atributos está abaixo.

| Variable Name            | Description                                         | Tipo  |
| ------------------------ |:---------------------------------------------------:| -----:|
| sexo| M = 'Masculino'; F = 'Feminino' |M/F|
| posse_de_veiculo| Y = 'possui'; N = 'não possui' |Y/N|
| posse_de_imovel| Y = 'possui'; N = 'não possui' |Y/N|
| qtd_filhos| Quantidade de filhos |inteiro|
| tipo_renda|Tipo de renda (ex: assaliariado, autônomo etc) | texto |
| educacao| Nível de educação (ex: secundário, superior etc) |texto|
| estado_civil | Estado civil (ex: solteiro, casado etc)| texto |
| tipo_residencia | tipo de residência (ex: casa/apartamento, com os pais etc) | texto |
| idade | idade em anos |inteiro|
| tempo de emprego | tempo de emprego em anos |inteiro|
| possui_celular | Indica se possui celular (1 = sim, 0 = não) |binária|
| possui_fone_comercial | Indica se possui telefone comercial (1 = sim, 0 = não) |binária|
| possui_fone | Indica se possui telefone (1 = sim, 0 = não) |binária|
| possui_email | Indica se possui e-mail (1 = sim, 0 = não) |binária|
| qt_pessoas_residencia | quantidade de pessoas na residência |inteiro|
| **mau** | indicadora de mau pagador (True = mau, False = bom) |binária|

# Utilização

Este estudo tem como um dos obbjetivos realizar um estudo de crédito para entender o Score que pode ser atribuído ao cliente, tendo em vista de proteger o investimento do negócio. Para isso além de vizualização de dados também foram utilizadas técnicas de machine larning, com o objetivo de procurar mesclas de variáveis que poderiam ser responsáveis por essas análises de crédito por pessoa, definindo as variáveis que podem nos ajudar a identificar o bom e o mau pagador.

### Dependencias

Bibliotecas necessárias:

seaborn==0.12.2

matplotlib== 3.7.1

pandas==1.3.5

numpy==1.23.05

statsmodel==0.16.5

scikit.learno==1.2.2

scipy==1.10.1

pycaret==0.5.0

# Storytelling

Foram utilizados  todos os dados Categóricos para estruturar a exploração e vizualiação dos dados. Neste caso, avaliando os gráficos e levando em consideraçção apenas a inadimplência, pode-se perceber que:
- Pessoas com Mestrado apresentam um maior número de inadimplêcia;
- Pessoas com Doutorado tem o menor número de inadimplentes
- Pessoas com o salário abaixo de 40K por ano apresentam um maior número de inadimplência;

O que se torna estranho se levarmos em conta que maioria das pessoas com mestrado ganha acima de 40K por ano.
Outro fato é de que:
- Pessoas inadimplentes fazem menos tranzações;
- Pessoas inadimplentes fazem transações de menor valor;
Então apesar da maioria de inadimplentes ter mestrado e ganharem relativamente bem, a maioria inadimplente faz menos transações e de menor valor

Em contrapartida a maioria de Adimplentes: 
- Tem Mestrado;
- Ganham até 40K por ano;

Dito isto, além da exploração dos dadoos continuamos utilizando as técnicas de Machine Learning, mais espeficicamente as ferramentas do statsmodel. Ao utilizar essas ferramentas tinha-se como base o R2, que num primeiro momento apenas alterando as variáveis utilizadas chegou a um R2 pouco satisfatório de pouco mais que 35%. Em seguida continuou-se usando técnicas de estatísticas e de Machine Learning para aumentar a acurácia do modelo foram retirados outliers, escolhidas as melhores variáveis, feito um PCA para melhor escolha de variáveis, além de um passo muito importante que foi a de bivariada discreta em que se agrupou algumas variáveis renomeando-as. Após a escolha das melhores variáveis através das técnicas descritas chegou-se as cinco que dariam mais importância, para sua escolha foi utilizado o coeficiente Kappa através do uso do Pycaret.

Por fim as variáveis de maior importância, depois da tunagem do próprio modelo foram tempo_emprego, idade e renda. Porém as cinco melhores para o modelo também são: qtd_filhos, idade, tempo_emprego, qt_pessoas_residencia e renda

Por fim o modelo está tunado e pronto para uso utilizando a base de dados descrita acima, e pode ser de grande ajuda para futuros estudos com bases diferentes e talvez reais onde se queira aplicar o Credict-score.

Colocarei um video do Streamlit recebendo a base de dados e dela extraindo o modelo em formato pkl junto aos arquivos.

## Autores

[@EduardoFonteneli](https://www.linkedin.com/in/carlos-eduardo-fontineli-goncalves/)
