# Canvas do SuperForça

Transcrição em Markdown do Canvas do projeto, organizada para reproduzir a disposição dos blocos do PDF. A tabela usa HTML para manter as colunas e células mescladas; a apresentação pode variar um pouco entre visualizadores.

**Arquivo de origem:** `uchub_10837-2026-2UH_outro_21-10-2026-23_36_37.pdf`, fornecido em `Downloads`. A página com instruções genéricas do modelo não foi reproduzida.

<table>
  <colgroup>
    <col width="22%">
    <col width="16%">
    <col width="25%">
    <col width="18%">
    <col width="19%">
  </colgroup>
  <tbody>
    <tr>
      <td rowspan="3" valign="top">
        <strong>Quais os tipos de usuários estarão no projeto?</strong>
        <p><strong>Representantes dos supermercados:</strong> RH, gestores e responsáveis por cadastrar demandas e selecionar profissionais.</p>
        <p><strong>Trabalhadores:</strong> cadastro de perfil, disponibilidade e candidatura às oportunidades.</p>
        <p><strong>Administradores:</strong> gestão dos cadastros, suporte e acompanhamento da operação.</p>
      </td>
      <td rowspan="3" valign="top">
        <strong>Contribuições esperadas da ferramenta</strong>
        <p>Apoiar os supermercados no atendimento à falta de mão de obra e às demandas sazonais e emergenciais, agilizando a conexão com profissionais disponíveis.</p>
        <p>Para os trabalhadores, ampliar as oportunidades de ganhos extras durante folgas ou horários ociosos.</p>
        <p>Centralizar informações e avaliações para facilitar a seleção e a gestão dos serviços.</p>
      </td>
      <td rowspan="3" valign="top">
        <strong>Objetivo geral do app/sistema</strong>
        <p>Desenvolver uma plataforma digital que conecte supermercados de São Paulo a profissionais disponíveis para demandas sazonais e emergenciais, considerando função, qualificação (em algumas atividades), proximidade, disponibilidade e valor do serviço.</p>
      </td>
      <td valign="top">
        <strong>Desafios e riscos do app/sistema</strong>
        <ul>
          <li>Proteção de dados e LGPD.</li>
          <li>Responsabilidades na contratação.</li>
          <li>Autenticidade dos cadastros e qualificações.</li>
          <li>Adesão de supermercados e profissionais.</li>
          <li>Desistências, faltas e divergências.</li>
          <li>Segurança de acesso e funcionamento.</li>
        </ul>
      </td>
      <td rowspan="3" valign="top">
        <strong>Quais análises estatísticas e estratégicas podem ser feitas com o uso do app/sistema?</strong>
        <ul>
          <li>Demanda por função, região e período.</li>
          <li>Taxa de preenchimento das oportunidades.</li>
          <li>Tempo entre publicação e confirmação.</li>
          <li>Disponibilidade de profissionais versus demanda dos supermercados.</li>
          <li>Frequência e padrões de cancelamentos e faltas.</li>
          <li>Avaliações e satisfação de ambas as partes.</li>
          <li>Valores combinados por função e período, sem confirmar pagamentos recebidos.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td valign="top">
        <strong>Desafios e riscos das análises de dados</strong>
        <ul>
          <li>Cadastros desatualizados.</li>
          <li>Poucos registros no início.</li>
          <li>Avaliações injustas ou tendenciosas.</li>
          <li>Critérios que favoreçam alguns perfis.</li>
          <li>Privacidade e acesso aos relatórios.</li>
          <li>Pagamento externo impede confirmar ganhos efetivamente recebidos.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td valign="top">
        <strong>Desafios e riscos das ferramentas</strong>
        <ul>
          <li>Custos e limites de hospedagem e banco.</li>
          <li>Dependência de localização e notificações externas.</li>
          <li>Integração de interface, banco e recomendação.</li>
          <li>Testes, manutenção e backups.</li>
          <li>Aprendizado das tecnologias.</li>
          <li>Segurança e permissões de acesso.</li>
          <li>Compatibilidade da PWA.</li>
          <li>Desempenho nos períodos de pico.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td colspan="2" valign="top">
        <strong>Quais dados são administrados no projeto?</strong>
        <p><strong>Trabalhadores:</strong> nome, contato, CPF, localização aproximada, experiências, funções, qualificações e disponibilidade.</p>
        <p><strong>Supermercados:</strong> razão social, CNPJ, unidades, endereços e responsável.</p>
        <p><strong>Oportunidades:</strong> função, atividades, requisitos, local, data, horário, quantidade e valor.</p>
        <p><strong>Candidaturas/serviços:</strong> profissional, oportunidade, convite, confirmação e situação.</p>
        <p><strong>Avaliações:</strong> notas e comentários. Pagamento fora da plataforma no MVP.</p>
      </td>
      <td rowspan="2" valign="top">
        <strong>Referências científicas para o problema</strong>
        <p>CARNEIRO, Laila Leite et al. Demandas e recursos no trabalho mediado por plataformas digitais: uma revisão de escopo da literatura. <em>Organizações &amp; Sociedade</em>, v. 30, n. 104, 2023.</p>
        <p>CAVALCANTI, Herodes. Novas tecnologias e reestruturação comercial no segmento supermercadista: impactos sobre o trabalho nas grandes redes de São Paulo. <em>Revista da ABET</em>, v. 23, n. 1, 2024.</p>
        <p>SILVA, Lucas Vicente Medeiros da; ANDRADE, Jailza do Nascimento Tomaz. Desafios na gestão de recursos humanos em supermercados: um estudo sobre estratégias para reduzir a alta rotatividade de funcionários. <em>ID on line. Revista de Psicologia</em>, v. 19, n. 76, p. 47–63, 2025.</p>
      </td>
      <td colspan="2" rowspan="2" valign="top">
        <strong>Referências científicas para as ferramentas</strong>
        <p>PONTES, Guilherme. <em>Progressive Web Apps: construa aplicações progressivas com React</em>. São Paulo: Casa do Código, 2018.</p>
        <p>HEUSER, Carlos Alberto. <em>Projeto de banco de dados</em>. 7. ed., 2024.</p>
        <p>JONAS, Eric et al. <em>Cloud programming simplified: a Berkeley view on serverless computing</em>. Berkeley: University of California, 2019. Relatório técnico UCB/EECS-2019-3.</p>
      </td>
    </tr>
    <tr>
      <td colspan="2" valign="top">
        <strong>Quais os trabalhos relacionados a esta proposta?</strong>
        <p>OLIVEIRA, Herbert Paolo Salles de; BRITTO, Jorge Nogueira de Paiva. Gerenciamento e disciplina algorítmica: uma análise focalizada em plataformas de emprego de elevada qualificação. <em>Economia e Sociedade</em>, v. 32, n. 3, 2023. DOI: 10.1590/1982-3533.2023v32n3art06.</p>
      </td>
    </tr>
  </tbody>
</table>
