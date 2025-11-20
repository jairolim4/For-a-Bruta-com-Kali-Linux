# Força-Bruta-com-Kali-Linux

Auditoria de Segurança com Ataques de Força Bruta
  FTP • HTTP • SMB usando Kali Linux e Medusa

Este repositório contém a documentação, evidências e arquivos utilizados durante o desafio prático de auditoria de segurança.
O objetivo principal é demonstrar o uso de ataques de força bruta em ambiente controlado, utilizando o Kali Linux e a ferramenta Medusa, além de registrar todo o processo de forma clara, técnica e organizada.

  •	Compreender ataques de força bruta em diferentes serviços (FTP, Web, SMB);
  •	Utilizar o Kali Linux e o Medusa para auditoria de segurança;
  •	Documentar processos técnicos de forma estruturada;
  •	Identificar vulnerabilidades e propor medidas de mitigação;
  •	Utilizar o GitHub como portfólio técnico para registrar e compartilhar evidências.

 - Tecnologias Utilizadas:

     Ambiente configurado utilizando máquinas virtuais no VirtualBox em rede Host-Only.

      Kali Linux – Máquina atacante
      Metasploitable 2 – Máquina vulnerável
      DVWA – Aplicação web vulnerável
      Comunicação via rede interna
      Wordlists e scripts executados via Kali
      Kali Linux: Ambiente de auditoria
      Medusa:	Ataques de força bruta
      FTP/SMB/HTTP:	Serviços-alvo utilizados
      Nano:	Edição de scripts
        
 - Procedimentos Realizados
  
   1. Preparação do Ambiente
        •	Instalação e configuração do Kali Linux
        •	Verificação dos serviços-alvo
        •	Configuração de wordlists personalizadas
      
        - Teste de credenciais fracas
        - Wordlists simples e Wordlists personalizadas
        - Identificação de acessos válidos
        - Automação de Tentativas em Formulário Web (DVWA)
        - Inspeção do formulário
        - Testes automatizados de login
        - Enumeração de usuários
        - Teste de senha única aplicada a múltiplos usuários
        - Identificação de reuso de senhas
      
   3. Ataque de Força Bruta – FTP
  
      Comando utilizado:
      medusa -h 192.168.0.10 -u admin -P wordlists/senha.txt -M ftp
      
   4. Ataque de Força Bruta – SMB
      
      Comando utilizado:
      medusa -h 192.168.0.10 -U users.txt -P passwords.txt -M smbnt
      
   5. Ataque de Força Bruta – HTTP (Formulário Web)

      medusa -h 192.168.0.10 -U users.txt -P passwords.txt -M web-form -m FORM:"login.php:username=^USER^&password=^PASS^:F=Login Failed"

- Medidas de Mitigação:
  
  Com base nos testes realizados, recomenda-se:
  
    •	Implementação de proteção por rate limiting
    •	Uso de bloqueio automático após tentativas consecutivas
    •	Políticas de senha forte
    •	Habilitar MFA (Autenticação Multifator)
    •	Monitoramento e análise de logs
