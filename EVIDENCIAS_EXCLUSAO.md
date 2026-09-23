# Evidências — confirmação de exclusão de tarefa

Implementação de diálogo Material 3 sobre a lista de tarefas: a lixeira não remove o item na hora. O usuário confirma ou cancela antes da exclusão definitiva.

Arquitetura preservada: Compose UI → ViewModel → Repository → DAO → Room.

## Sequência no emulador

### 1. Lista antes da exclusão

Duas tarefas visíveis. Nenhuma exclusão feita ainda. A tarefa que será alvo do teste aparece na lista.

![Lista de tarefas antes da exclusão](./docs/images/exclusao/01-lista-antes.png)

### 2. Diálogo aberto com a tarefa selecionada

Toque no ícone de lixeira da tarefa escolhida. O `AlertDialog` abre **sobre a lista** (não é uma tela nova), informa que a tarefa será excluída e mostra o título selecionado. Botões **Cancelar** e **Excluir**.

![Diálogo de confirmação com o título da tarefa](docs/images/exclusao/02-dialogo-aberto.png)

### 3. Resultado ao cancelar

Toque em **Cancelar**. O diálogo fecha e a lista permanece igual: as mesmas tarefas, inclusive a selecionada inicialmente.

![Lista inalterada após Cancelar](docs/images/exclusao/03-apos-cancelar.png)

### 4. Nova abertura do diálogo

Novo toque na lixeira da mesma tarefa. O diálogo abre de novo.

![Diálogo reaberto para a mesma tarefa](docs/images/exclusao/04-dialogo-reaberto.png)

### 5. Resultado após confirmar a exclusão

Toque em **Excluir**. O diálogo fecha e **somente** a tarefa selecionada some. As demais permanecem.

![Lista após confirmar a exclusão](docs/images/exclusao/05-apos-excluir.png)

