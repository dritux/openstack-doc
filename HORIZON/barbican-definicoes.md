# Barbican

Levantamento chave de api para criar instancias de interação com módulos  

Barbican keys support

- Private Key
- Certificate
- Password
- SSH Keys

Componentes:
3 clientes de api  
- Interface de usuário (called Palisade)  
- file-system-based, agente baseado em sistema de arquivos para proteger servidores (Postern)  
- Cliente command line (called python-barbicanclient).  

------------------------------------------------------------------------
Features:  

- inclui recursos de criptografia em vários serviços de OpenStack  
- chaves simétricas e assimétricas  
- suporte para certificados SSL de públicas e privados  
- provisionamento e o gerenciamento dos chaves  

------------------------------------------------------------------------
Pesquisar :

- HSMs
- Postern
- Projetos de OpenStack que atualmente estão integrando com Barbican para armazenamento de dados seguro.
- Castellan. biblioteca que ajuda projetos OpenStack a falar com Barbican.

------------------------------------------------------------------------
secret_type:  

symmetric - utilizado para armazenar matrizes de bytes como chaves apropriadas para criptografia simétrica.  
public - utilizado para armazenar a chave pública de um par de chaves assimétrica.  
private - utilizado para armazenar a chave particular de um par de chaves assimétrica.  
passphrase - usado para armazenar senhas de texto sem formatação.  
certificate - usado para armazenar certificados de criptografia como certificados x. 509.  
opaque - usado para trás compatibilidade com versões anteriores da API sem segredos digitados. Novas aplicações são incentivadas para especificar um dos outros tipos de secreto.  
------------------------------------------------------------------------

