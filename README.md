SD-ControleConcorrenciaJava

Este repositório contém implementações de controle de concorrência em Java utilizando diferentes técnicas. Abaixo estão as análises das execuções dos programas.

 Análises das Execuções

1. Concorrente (Sem Controle de Concurrency)
Observamos que, sem controle de concorrência, múltiplos clientes tentaram acessar o saldo ao mesmo tempo, o que causou falhas nos saques. Isso indica que, sem nenhum tipo de bloqueio, o programa não consegue garantir a integridade dos dados compartilhados.

2. Lock (Controle com Lock)
O uso de ReentrantLock garantiu que apenas um cliente acessasse a conta por vez. Embora o controle de concorrência tenha sido eficaz, o desempenho foi afetado pela necessidade de os threads aguardarem sua vez para acessar a conta.

3. RwLock (Controle com Read-Write Lock)
O uso de ReadWriteLock foi eficiente, permitindo que múltiplos clientes realizassem leituras simultâneas da conta, mas restringindo os saques a um único thread por vez. Isso mostrou ser uma boa solução para cenários de alta leitura e baixa escrita.

4. Synk (Controle com`synchronized)
A implementação com synchronized garantiu que apenas um cliente acessasse a conta de cada vez. Embora isso tenha resolvido os problemas de concorrência, o desempenho foi prejudicado em situações de alta concorrência devido ao bloqueio exclusivo de cada thread.



