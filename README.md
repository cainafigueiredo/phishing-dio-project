# **Informações gerais sobre o projeto**

Primeiro projeto prático do curso "Formação Cybersecurity Specialist", ministrado pelo professor [Cassiano Peres](https://github.com/cassiano-dio) através da plataforma DIO. O objetivo deste projeto é gerar um clone de uma página de login utilizando a ferramenta [setoolkit](https://github.com/trustedsec/social-engineer-toolkit) em um ambiente *Kali Linux* hospedado em uma máquina virtual. Dentre outras funcionalidades, o *setoolkit* permite clonar uma página web, a qual é imediatamente servida pela máquina que realizou o clone. A partir desse momento, as credenciais informadas pelo usuário na página falsa são exibidas no terminal onde o servidor clone está rodando. Esse tipo de ataque é conhecido como *phishing* e é categorizado como um ataque de engenharia social. Este repositório é inspirado no [repositório com a solução do professor](https://github.com/cassiano-dio/cibersecurity-desafio-phishing). 

# **Clonando a página da DIO**

Na solução original, o professor do curso exemplicou o ataque clonando a página de login do *Facebook*. Em minha solução, irei clonar a página de login do [GitHub](https://github.com/login). Para isso, seguiremos as seguintes etapas:

1) Inicie uma máquina virtual com o Kali Linux e garanta que ela possui acesso à internet (em suas configurações de rede, altere o modo de conexão para ```Placa em modo Bridge```)

2) Abra um terminal e adquira privilégios de administrador: ```$ sudo su```

3) Execute o setoolkit: ```$ setoolkit```

4) Escolha a opção ```1) Social-Engineering Attacks```

5) Escolha a opção ```2) Website Attack Vectors```

6) Escolha a opção ```3) Credential Harvester Attack Method```

7) Escolha a opção ```2) Site Cloner```

8) Ao ser solicitado o endereço IP onde o servidor clone será hospedado, apenas pressione ```ENTER```. Anote o endereço IP que é exibido por padrão. Iremos acessá-lo após subir o servidor com a página clonada. 

9) Ao ser solicitado a URL da página a ser clonada, forneça o endereço da página desejada (e.g., https://www.instagram.com/)

10) Em um navegador, acesse o endereço IP informado no passo 8. A essa altura, você deve estar conseguindo acessar a página clone.

11) Digite as credenciais do usuário nos campos de e-mail e senha. Após isso, aperte em ```Sign In```. Você irá perceber que haverá um redirecionamento para a página oficial.

![Página clone de login](https://github.com/cainafigueiredo/phishing-dio-project/blob/main/login_clone.png)

12) Volte ao terminal do Kali Linux e procure pelas informações do usuário que você digitou na etapa anterior

![Credenciais do usuário coletadas pela página clone](https://github.com/cainafigueiredo/phishing-dio-project/blob/main/credenciais.png)

