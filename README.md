# diagnostico-recuperacao-windows
Estudo de caso prático sobre diagnóstico e recuperação de perfil de usuário no Windows.

# Diagnóstico e Recuperação de Perfil de Usuário no Windows

**Área:** Suporte Técnico e Sistemas Operacionais  
**Tipo:** Estudo de caso prático  
**Status:** Concluído

## Objetivo

Documentar a investigação e a recuperação de uma falha que impedia o carregamento normal do perfil de usuário do Windows.

## Problema identificado

Ao iniciar o notebook, o Windows apresentou a mensagem:

> Falha na entrada do serviço Serviço de Perfil de Usuário. Não é possível carregar o perfil de usuário.

Após reiniciar, o sistema carregou uma área de trabalho diferente da habitual, associada a um perfil temporário. Algumas pastas pessoais não estavam visíveis nesse ambiente, mas os arquivos continuavam acessíveis pelo OneDrive.

## Investigação realizada

- Verificação das pastas de usuários do Windows.
- Identificação de diretórios com nomes iniciados por `TEMP`.
- Consulta ao perfil ativo pelo Prompt de Comando, utilizando `echo %USERPROFILE%`.
- Verificação da integridade dos arquivos do sistema.

## Procedimento executado

Foi executado o comando `sfc /scannow` em um Prompt de Comando aberto como administrador.

O Windows informou que encontrou arquivos corrompidos e conseguiu repará-los.

Após a reinicialização, o perfil habitual voltou a ser carregado no caminho `C:\Users\arian`.

## Validação

- A área de trabalho habitual voltou a aparecer.
- Os arquivos e programas voltaram a ficar acessíveis.
- O perfil correto foi confirmado pelo Prompt de Comando.
- Uma nova reinicialização ocorreu normalmente, sem repetição do erro.

## Resultado

O ambiente habitual do Windows foi recuperado e permaneceu funcionando normalmente após uma nova reinicialização.

O SFC reparou arquivos corrompidos do sistema. Não foi possível confirmar se essa era a única causa original da falha.

## Aprendizados

- Investigação de problemas em sistemas operacionais.
- Uso de ferramentas de diagnóstico do Windows.
- Verificação de perfis e diretórios de usuários.
- Validação de resultados após procedimentos de recuperação.
- Importância de backups e proteção dos dados.

## Próximos passos

- Monitorar o funcionamento do sistema.
- Confirmar a sincronização do OneDrive.
- Manter cópias de segurança dos arquivos importantes.
- Investigar com cuidado as pastas temporárias remanescentes antes de qualquer remoção.

---

*Este projeto documenta uma experiência prática pessoal de aprendizado e não um atendimento profissional prestado a terceiros.*
