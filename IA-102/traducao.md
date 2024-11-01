Ciência de Dados em 5 minutos: O que é Limpeza de Dados? \- Comunidade DEV
Ir para o conteúdo
Menu de navegação
Procurar
Ativado por
Procurar
Algolia
Procurar
Iniciar sessão
Criar conta
Comunidade DEV
Fechar
Adicionar reação
Gostar
Unicórnio
Cabeça Explosiva
Mãos levantadas
Fogo
Ir para os comentários
Salvar
Mais...
Copiar link
Copiar link
Copiado para a área de transferência
Compartilhar no Twitter
Compartilhar no LinkedIn
Compartilhar no Reddit
Compartilhar com Hacker News
Compartilhar no Facebook
Compartilhar no Mastodon
Denunciar abuso
Erin Schaffer
para Educativo
Postado em 29 de abril de 2021
• Publicado originalmente em educative.io
Ciência de Dados em 5 minutos: O que é Limpeza de Dados?
\# ciência de dados
\# aprendizado de máquina
\# limpeza de dados
Ao trabalhar com dados, sua análise e insights são tão bons quanto os dados que você usa. Se você estiver realizando análise de dados com dados sujos, sua organização não poderá tomar decisões eficientes e eficazes com esses dados. A limpeza de dados é uma parte crítica do gerenciamento de dados que permite validar se você tem dados de alta qualidade.
A limpeza de dados inclui mais do que apenas corrigir erros de ortografia ou sintaxe. É um aspecto fundamental da análise de ciência de dados e uma importante técnica de aprendizado de máquina. Hoje, aprenderemos mais sobre a limpeza de dados, seus benefícios, problemas que podem surgir com seus dados e as próximas etapas para seu aprendizado.
Nós vamos cobrir:
O que é limpeza de ciência de dados?
Benefícios e etapas da limpeza de dados
Próximos passos para o seu aprendizado
O que é limpeza de ciência de dados?
A limpeza de dados, ou limpeza de dados, é o importante processo de correção ou remoção de dados incorretos, incompletos ou duplicados em um conjunto de dados. A limpeza de dados deve ser a primeira etapa do seu fluxo de trabalho. Ao trabalhar com grandes conjuntos de dados e combinar várias fontes de dados, há uma forte possibilidade de duplicar ou rotular dados incorretamente. Se você tiver dados imprecisos ou incorretos, eles perderão sua qualidade e seus algoritmos e resultados se tornarão não confiáveis.
A limpeza de dados difere da transformação de dados porque, na verdade, você está removendo dados que não pertencem ao seu conjunto de dados. Com a transformação de dados, você está alterando seus dados para um formato ou estrutura diferente. Os processos de transformação de dados às vezes são chamados de data wrangling ou data munging. O processo de limpeza de dados é o que vamos focar hoje.
Então, como posso saber se meus dados estão limpos?
Para determinar a qualidade dos dados, você pode estudar seus recursos e pesá\-los de acordo com o que é importante para sua organização e seu projeto.
Existem cinco recursos principais a serem observados ao avaliar seus dados:
Consistência: seus dados são consistentes em todos os seus conjuntos de dados?
Precisão: Seus dados estão próximos dos valores reais?
Completude: Seus dados incluem todas as informações necessárias?
Validade : Seus dados correspondem às regras e/ou restrições de negócios?
Uniformidade: Seus dados são especificados usando unidades de medida consistentes?
Agora que sabemos como reconhecer dados de alta qualidade, vamos nos aprofundar no processo de limpeza da ciência de dados, por que é importante e como fazê\-lo de forma eficaz.
Benefícios e etapas da limpeza de dados
Vamos discutir algumas etapas de limpeza que você pode seguir para garantir que está trabalhando com dados de alta qualidade. Os cientistas de dados gastam muito tempo limpando dados porque, uma vez que seus dados estão limpos, é muito mais fácil realizar análises de dados e criar modelos.
Primeiro, discutiremos alguns problemas que você pode enfrentar com seus dados e o que fazer com eles.
Tratamento de dados ausentes
É comum que grandes conjuntos de dados tenham alguns valores ausentes. Talvez a pessoa que registrou os dados tenha esquecido de inseri\-los ou talvez tenha começado a coletar essas variáveis de dados ausentes no final do processo de coleta de dados. Não importa o que aconteça, os dados ausentes devem ser gerenciados antes de trabalhar com conjuntos de dados.
Filtrando exceções indesejadas
Os outliers contêm informações essenciais sobre seus dados, mas ao mesmo tempo tiram seu foco do grupo principal. É uma boa ideia examinar seus dados com e sem valores discrepantes. Se você descobrir que deseja usá\-los, certifique\-se de escolher um método robusto que possa lidar com seus valores discrepantes. Se você decidir não usá\-los, você pode simplesmente abandoná\-los.
Você também pode filtrar outliers indesejados usando este método:
\# Obtenha o 98º e o 2º percentil como os limites de nossos outliers
upper\_limit \= np.percentile(train\_df.logerror.values, 98\)
lower\_limit \= np.percentile(train\_df.logerror.values, 2\)
\# Filtre os outliers do dataframe
data\['target'].loc\[train\_df\['target']\>upper\_limit] \= upper\_limit
data\['target'].loc\[train\_df\['target']\<lower\_limit] \= lower\_limit
Entre no modo de tela cheia
Sair do modo de tela cheia
Padronizando seus dados
Os dados em suas variáveis de recurso devem ser padronizados. Isso torna o exame e a modelagem de seus dados muito mais fáceis. Por exemplo, vejamos dois valores que chamaremos de "cachorro" e "gato" que estão na variável "animal". Se você coletou dados, poderá receber valores de dados diferentes que não previu, como:
CÃO, GATO (inserido em maiúsculas)
Cachorro, Gato (inserido com as primeiras letras maiúsculas)
DOF, carrinho (inserido como erros de digitação)
Se convertêssemos a variável de recurso em floats categóricos, não obteríamos os valores 0 e 1 que queremos, obteríamos algo mais parecido com isto:
{
'cachorro': 0,
«gato»: 1,
«CÃO»: 2,
«GATO»: 3,
'Cão': 4,
'Gato': 5,
«dof»: 6,
'carrinho': 7
}
Entre no modo de tela cheia
Sair do modo de tela cheia
Para lidar efetivamente com os problemas de capitalização e ajudar a padronizar seus dados, você pode fazer algo assim:
\# Torne a string minúscula
s.lower()
\# Coloque a primeira letra em maiúscula
s.capitalize()
Entre no modo de tela cheia
Sair do modo de tela cheia
Se houver um problema com erros de digitação, você pode usar uma função de mapeamento:
value\_map \= {'dof': 'cachorro', 'carrinho': 'gato'}
pd\_dataframe\['animais'].map(value\_map)
Entre no modo de tela cheia
Sair do modo de tela cheia
Nota: Outra maneira de lidar com erros de digitação é executar uma verificação ortográfica e gramatical no Microsoft Excel .
Removendo observações indesejadas
Às vezes, você pode ter alguns dados irrelevantes que devem ser removidos. Digamos que você queira prever as vendas de uma revista. Você está examinando um conjunto de dados de revistas encomendadas da Amazon no ano passado e percebe uma variável de recurso chamada "font\-type" que observa qual fonte foi usada no livro.
Este é um recurso bastante irrelevante e provavelmente não ajudaria você a prever as vendas de uma revista. Este é um recurso que pode ser descartado assim:
df.drop('feature\_variable\_name', eixo\=1\)
Entre no modo de tela cheia
Sair do modo de tela cheia
A remoção dessas observações indesejadas não apenas facilita a exploração de dados, mas também ajuda a treinar seu modelo de aprendizado de máquina.
Dados sujos incluem quaisquer pontos de dados que estão errados ou simplesmente não deveriam estar lá. As duplicatas ocorrem quando os pontos de dados são repetidos em seu conjunto de dados. Se você tiver muitas duplicatas, isso pode atrapalhar o treinamento do seu modelo de aprendizado de máquina.
Para lidar com dados sujos, você pode descartá\-los ou usar um substituto (como converter pontos de dados incorretos nos corretos).
Para lidar com problemas de duplicação, você pode simplesmente removê\-los de seus dados.
Removendo dados em branco
Obviamente, você não pode usar dados em branco para análise de dados. Os dados em branco são um grande problema para os analistas porque enfraquecem a qualidade dos dados. Idealmente, você deve remover os dados em branco na fase de coleta de dados, mas também pode escrever um programa para fazer isso por você.
Eliminando o espaço em branco
O espaço em branco é um problema pequeno, mas comum, em muitas estruturas de dados. Uma função TRIM irá ajudá\-lo a eliminar o espaço em branco.
Nota: A função TRIM é categorizada em funções de texto do Excel. Ajuda a remover espaços extras nos dados. Você pode usar a fórmula \=TRIM(texto).
Corrigindo erros de conversão
Às vezes, ao exportar dados, os valores numéricos são convertidos em texto. O método VALUE é uma ótima maneira de ajudar com esse problema.
O processo de limpeza de dados parece demorado, mas facilita o trabalho com seus dados e permite que você aproveite ao máximo seus dados. Ter dados limpos aumenta sua eficiência e garante que você esteja trabalhando com dados de alta qualidade.
Alguns benefícios da limpeza de dados incluem:
Existem ferramentas de limpeza de dados, como DemandTools ou Oracle Enterprise Data Quality, que ajudam a aumentar sua eficiência e acelerar o processo de tomada de decisão.
Você pode monitorar melhor seus erros para ajudá\-lo a eliminar dados incorretos, corrompidos ou inconsistentes.
Você cometerá menos erros no geral.
Você pode mapear diferentes funções e o que seus dados devem fazer.
É fácil remover erros em várias fontes de dados.
Etc.
Próximos passos para o seu aprendizado
A limpeza de dados é uma parte importante do fluxo de trabalho de gerenciamento de dados da sua organização. Agora que você aprendeu mais sobre esse processo, está pronto para aprender conceitos mais avançados em aprendizado de máquina. Aqui estão algumas coisas recomendadas para aprender:
Reconhecimento de imagem
Processamento de linguagem natural
Aprendizado de máquina aplicado
Etc.
Para se familiarizar com as técnicas modernas de aprendizado de máquina, confira o Caminho de Aprendizagem da Educative, Torne\-se um Engenheiro de Aprendizado de Máquina . Neste roteiro de aprendizado, você explorará técnicas essenciais de aprendizado de máquina para ajudá\-lo a se destacar da concorrência. No final, você terá habilidades prontas para o trabalho na criação de pipeline de dados, implantação de modelo e inferência.
Bom aprendizado!
Continue lendo sobre ciência de dados
Como aceitar a entrevista com um cientista de dados do Facebook
Os 10 principais algoritmos de ML para ciência de dados em 5 minutos
Ciência de Dados Aplicada: funções serverless, pipelines e PySpark
Principais comentários (0\)
Subscrever
Pessoal
Usuário confiável
Criar modelo
Os modelos permitem que você responda rapidamente a perguntas frequentes ou armazene snippets para reutilização.
Enviar
Visualizar
Demitir
Código de Conduta
•
Denunciar abuso
Tem certeza de que deseja ocultar este comentário? Ele ficará oculto em sua postagem, mas ainda estará visível por meio do link permanente do comentário.
Ocultar comentários de crianças também
Confirmar
Para outras ações, você pode considerar bloquear essa pessoa e/ou denunciar abusos
Leia a seguir
Supervisão de IA por meio de regulamentação baseada em leilões: equilibrando inovação e controle
Mike Young \- 5 de outubro
Desbloqueie o potencial da geometria do coletor: MANTRA, o conjunto de dados de triangulações versáteis
Mike Young \- 5 de outubro
O aprendizado por reforço ajusta os LLMs de código com feedback de execução
Mike Young \- 5 de outubro
5 melhores ferramentas de ETL: um guia de comparação abrangente
Sourabh Gupta \- 28 de outubro
Educativo
Seguir
Aprenda qualquer coisa, desde CSS até Design de Sistemas, de forma interativa.
Suba de nível com as habilidades tecnológicas sob demanda \- no seu próprio ritmo.
Cursos baseados em texto com ambientes de codificação incorporados ajudam você a aprender sem problemas.
Experimente uma visualização
Mais aplicativos de Educativo
Noções básicas de lógica difusa
\# ciência de dados
\# aprendizado de máquina
\# programação
\# tutorial
O que é clustering: uma introdução
\# aprendizado de máquina
\# programação
\# tutorial
\# produtividade
Abraçando a mudança: à prova de IA em sua carreira
\# IA
\# aprendizado de máquina
\# carreira
\# produtividade
Obrigado ao nosso Patrocinador Diamante Neon por apoiar nossa comunidade.
Comunidade DEV — Uma rede social construtiva e inclusiva para desenvolvedores de software. Com você a cada passo de sua jornada.
Casa
DEV\+\+
Podcasts
Vídeos
Tags
Ajuda DEV
Loja Forem
Anuncie no DEV
Desafios de desenvolvimento
Demonstração de DEV
Sobre
Contato
Banco de dados Postgres gratuito
Guias
Comparações de software
Código de Conduta
Política de privacidade
Termos de uso
Construído no Forem \- o software de código aberto que alimenta o DEV e outras comunidades inclusivas.
Feito com amor e Ruby on Rails . Comunidade © DEV 2016 \- 2024\.
Somos um lugar onde os programadores compartilham, se mantêm atualizados e desenvolvem suas carreiras.
Iniciar sessão
Criar conta