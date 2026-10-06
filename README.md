# IPE-IFPE - Plataforma de Disponibilização de Oportunidades

Plataforma web para gerenciar oportunidades acadêmicas (monitoria, pesquisa e extensão) entre professores e estudantes do IFPE.

## Visão Geral

O sistema permite que professores criem e gerenciem oportunidades de trabalho acadêmico, enquanto estudantes podem se inscrever conforme os critérios estabelecidos. O processo inclui análise de inscrições, seleção de candidatos, períodos de recurso e divulgação de resultados.

## Funcionalidades Principais

### Para Professores
- Criar oportunidades (monitoria, pesquisa, extensão)
- Definir vagas (com e sem bolsa)
- Especificar requisitos (coeficiente, notas em disciplinas, etc.)
- Configurar períodos de inscrição
- Analisar inscrições de estudantes
- Registrar aprovação/reprovação com justificativa
- Analisar recursos apresentados por estudantes
- Divulgar resultados

### Para Estudantes
- Visualizar oportunidades disponíveis
- Se inscrever em oportunidades (conforme cursos permitidos)
- Enviar histórico escolar
- Verificar status da inscrição
- Apresentar recursos durante o período especificado
- Consultar resultado final

## Entidades do Sistema

### Oportunidade
- Tipo: monitoria, pesquisa, extensão
- Descrição dos requisitos
- Requisitos mínimos (coeficiente, notas em disciplinas)
- Cursos permitidos (específicos ou todos)
- Vagas sem bolsa (1 a N)
- Vagas com bolsa (0 a N)
- Datas:
  - Criação
  - Início e fim de inscrição
  - Resultado parcial
  - Início e fim de recurso
  - Resultado final

### Estudante
- Nome
- Matrícula
- Curso
- Histórico escolar

### Professor
- Nome
- Matrícula/ID
- Oportunidades gerenciadas

### Inscrição
- Estudante
- Oportunidade
- Data de inscrição
- Histórico escolar (anexado)
- Status (aguardando análise, apto, não apto, recurso enviado, recurso analisado)
- Justificativa da análise (quando não apto)
- Texto do recurso (quando aplicável)

## Fluxo de Processo

1. **Criação da Oportunidade**: Professor cria oportunidade com todos os detalhes
2. **Período de Inscrição**: Estudantes se inscrevem dentro do prazo
3. **Análise de Inscrições**: Professor analisa candidatos e marca como apto/não apto
4. **Divulgação de Resultado Parcial**: Sistema divulga primeiros resultados
5. **Período de Recurso**: Estudantes não aptos podem entrar com recurso
6. **Análise de Recursos**: Professor analisa recursos
7. **Resultado Final**: Sistema divulga resultado final das seleções

## Períodos Importantes

- **Inscrição**: Data início e data fim
- **Recurso**: Data início e data fim
- **Divulgação**: Resultado parcial e resultado final

## Documentação

- [Requisitos Funcionais](docs/requisitos-funcionais.md)
- [Modelo de Dados](docs/modelo-dados.md)
- [Arquitetura do Sistema](docs/arquitetura.md)
- [Casos de Uso](docs/casos-uso.md)

## Stack Tecnológico

_A ser definido_

## Contribuições

Para contribuir com este projeto, abra uma issue ou pull request.

## Licença

MIT License

Copyright (c) 2026

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
