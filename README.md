# Atividade Prática: Pipeline CI/CD com Python e GitHub Actions

**Link do Repositório:** https://github.com/caiodoti/ci-cd-python

### Respostas do Desafio:

**1. O que representa a etapa de CI neste projeto?**
A etapa de CI aqui funciona como um filtro de qualidade automático (um quality gate). Toda vez que a gente manda código novo pro GitHub, o CI roda sozinho pra preparar o ambiente, instalar o Python e rodar os testes. Isso serve pra garantir que o código novo não vai quebrar nada que já estava funcionando antes.

**2. O que impede a execução do Continuous Delivery quando existe um defeito?**
É a regrinha `needs: ci` que a gente colocou no arquivo pipeline.yml. Esse comando amarra as coisas: a parte de entrega (delivery) só vai rodar se a parte de integração (ci) der sucesso. Então, se algum teste falhar por causa de um erro no código, o CI trava na mesma hora e não deixa gerar o pacote final.

**3. Qual seria a próxima etapa necessária para transformar este pipeline em Continuous Deployment?**
Do jeito que tá agora, o pipeline só faz Continuous Delivery, ou seja, ele cria o artefato (o pacote validado) e para por aí. Para virar Continuous Deployment de verdade, a gente precisaria criar mais um "job" no final do arquivo para pegar esse pacote e publicar automaticamente em um servidor real. Assim, a nova versão iria direto para os usuários finais, sem ninguém precisar apertar nenhum botão.