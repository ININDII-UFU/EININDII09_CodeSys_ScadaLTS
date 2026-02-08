# 📘 EININIDII - Instalação/Configuração do SCADA‑LTS
> **Professor**: Josué Morais  
> **Disciplina**: Instrumentação Industrial II  
> **Curso**: Engenharia de Controle e Automação  
> **Instituição**: Universidade Federal de Uberlândia — FEELT  

<details>
  <summary><strong>📑 Índice </strong></summary>

- [🎯 Objetivo](#objetivo)
- [🤝 Colaboradores](#colaboradores)
- [🧰 Pré-requisitos](#pre-requisitos)
  - [Software](#software)
  - [Hardware](#hardware)

- [☕ Instalação do OpenJDK](#instalacao-openjdk)
- [🖥️ Instalação do SCADA‑LTS](#instalacao-scadalts)
- [🌐 Acesso ao SCADA‑LTS (Service Manager)](#acesso-scadalts)
- [📡 MODBUS Server — CODESYS](#modbus-server)
- [🔁 MODBUS Client — SCADA‑LTS](#modbus-client)
- [⚠️ Observações finais](#observacoes)

</details>

---

<a id="objetivo"></a>
<details open>
  <summary><strong>🎯 Objetivo</strong></summary>

Este tutorial tem como objetivo orientar, de forma **didática e passo a passo**, a **instalação e configuração do SCADA‑LTS**, integrando-o a um **servidor Modbus configurado no CODESYS**, permitindo leitura e escrita de dados industriais via **Modbus TCP**.

Ao final deste procedimento, o sistema estará:
- ✅ SCADA‑LTS instalado e operacional
- ✅ Comunicação Modbus funcional
- ✅ Integração entre CODESYS e SCADA‑LTS validada

</details>

---

<a id="colaboradores"></a>
<details>
  <summary><strong>🤝 Colaboradores</strong></summary>

Este projeto é resultado de um esforço conjunto. A participação das pessoas abaixo foi essencial:

- **Amanda Caetano Alvarenga**
- **Gabriel Zuccolotto Alecrim**
- **Luan Rafael Pereira Santos**

A cada um(a), nosso agradecimento pelo compromisso, pela parceria e pela qualidade do trabalho entregue.

</details>

---

<a id="pre-requisitos"></a>
<details>
  <summary><strong>🧰 Pré-requisitos</strong></summary>

<a id="software"></a>
### Software
- ✅ Windows 10 ou 11
- ✅ OpenJDK (Microsoft Build)
- ✅ SCADA‑LTS (Windows Installer)
- ✅ CODESYS V3.5 (para o servidor Modbus)

<a id="hardware"></a>
### Hardware
- ✅ Computador com acesso à rede
- ⚠️ PLC virtual (CODESYS Control Win) ou PLC físico/soft-PLC equivalente

</details>

---

<a id="instalacao-openjdk"></a>
<details>
  <summary><strong>☕ Instalação do OpenJDK</strong></summary>

Para realizar a instalação do OpenJDK, utilize o link oficial (Microsoft Build of OpenJDK):  
🔗 **Download:** https://aka.ms/download-jdk/microsoft

O **OpenJDK (Java Development Kit)** fornece compilador, JVM e bibliotecas padrão para desenvolvimento/execução de aplicações Java.

<a id="openjdk-passo-1"></a>
### 🔹 Passo 1 – Baixar e executar o instalador
![fig1](assets\instalLTS\img1.png)

1. Acesse o link de download
2. Baixe o instalador do OpenJDK
3. Execute o arquivo baixado

---

<a id="openjdk-passo-2"></a>
### 🔹 Passo 2 – Aceitar os termos de licença
![fig2](assets\instalLTS\img2.png)

1. Leia os termos de licença
2. Marque/aceite os termos
3. Clique em **Next** para continuar

---

<a id="openjdk-passo-3"></a>
### 🔹 Passo 3 – Configurar “JAVA_HOME”
![fig3](assets\instalLTS\img3.png)

1. Na tela de customização, **marque** a opção **Set JAVA_HOME variable**
2. Clique em **Next**

---

<a id="openjdk-passo-4"></a>
### 🔹 Passo 4 – Iniciar a instalação
![fig4](assets\instalLTS\img4.png)

1. Clique em **Install**
2. Aguarde a instalação finalizar

---

<a id="openjdk-passo-5"></a>
### 🔹 Passo 5 – Abrir variáveis de ambiente
![fig5](assets\instalLTS\img5.png)

1. Abra as **Configurações do Windows**
2. Pesquise por **Variáveis de ambiente**
3. Abra a tela de edição das variáveis

---

<a id="openjdk-passo-6"></a>
### 🔹 Passo 6 – Editar o Path
![fig6](assets\instalLTS\img6.png)

1. Em **Variáveis do sistema**, selecione **Path**
2. Clique em **Editar**

---

<a id="openjdk-passo-7"></a>
### 🔹 Passo 7 – Adicionar o diretório do JDK ao Path
![fig7](assets\instalLTS\img7.png)

1. Clique em **Novo**
2. Adicione o caminho do JDK (pasta **bin**)
3. Confirme em **OK**

---

<a id="openjdk-passo-8"></a>
### 🔹 Passo 8 – Conferir/confirmar JAVA_HOME
![fig8](assets\instalLTS\img8.png)

1. Verifique se a variável **JAVA_HOME** foi criada corretamente
2. Confirme o caminho apontando para a pasta do JDK

---

<a id="openjdk-passo-9"></a>
### 🔹 Passo 9 – Validar no Prompt de Comando
![fig9](assets\instalLTS\img9.png)

1. Abra o Prompt (CMD)
2. Execute:
```bat
java -version
```
3. Confirme se a versão do Java aparece corretamente

</details>

---

<a id="instalacao-scadalts"></a>
<details>
  <summary><strong>🖥️ Instalação do SCADA‑LTS</strong></summary>

Baixe o instalador:
🔗 https://github.com/SCADA-LTS/windows-installer/releases

<a id="scada-passo-1"></a>
### 🔹 Passo 1 – Aviso de segurança do Windows
![fig10](assets\instalLTS\img10.png)

1. Ao executar o instalador, o Windows pode exibir aviso
2. Clique em **Mais informações**

---

<a id="scada-passo-2"></a>
### 🔹 Passo 2 – Executar assim mesmo
![fig11](assets\instalLTS\img11.png)

1. Clique em **Executar assim mesmo**

---

<a id="scada-passo-3"></a>
### 🔹 Passo 3 – Selecionar idioma (início)
![fig12](assets\instalLTS\img12.png)

1. Inicie o instalador
2. Selecione o idioma quando solicitado

---

<a id="scada-passo-4"></a>
### 🔹 Passo 4 – Selecionar idioma (confirmar)
![fig13](assets\instalLTS\img13.png)

1. Confirme o idioma selecionado
2. Clique em **OK/Avançar**

---

<a id="scada-passo-5"></a>
### 🔹 Passo 5 – Tela do assistente
![fig14](assets\instalLTS\img14.png)

1. Avance no assistente de instalação

---

<a id="scada-passo-6"></a>
### 🔹 Passo 6 – Aceitar o contrato de licença
![fig15](assets\instalLTS\img15.png)

1. Leia o contrato
2. Aceite os termos
3. Clique em **Next**

---

<a id="scada-passo-7"></a>
### 🔹 Passo 7 – Escolher diretório de instalação
![fig16](assets\instalLTS\img16.png)

1. Escolha o diretório (ou mantenha o padrão)
2. Clique em **Next**

---

<a id="scada-passo-8"></a>
### 🔹 Passo 8 – Opções padrão (tela 1)
![fig17](assets\instalLTS\img17.png)

1. Mantenha as opções padrão, se aplicável
2. Clique em **Next**

---

<a id="scada-passo-9"></a>
### 🔹 Passo 9 – Opções padrão (tela 2)
![fig18](assets\instalLTS\img18.png)

1. Continue avançando com as opções padrão

---

<a id="scada-passo-10"></a>
### 🔹 Passo 10 – Configurar porta, usuário e senha
![fig19](assets\instalLTS\img19.png)

1. Defina a porta HTTP (ex.: **8080**)
2. Crie/defina usuário e senha de administrador

---

<a id="scada-passo-11"></a>
### 🔹 Passo 11 – Instalar servidor local (obrigatório)
![fig20](assets\instalLTS\img20.png)

1. **Marque a opção de instalar servidor local**
2. Avance para continuar

---

<a id="scada-passo-12"></a>
### 🔹 Passo 12 – Finalização (tela 1)
![fig21](assets\instalLTS\img21.png)

1. Aguarde a instalação concluir
2. Avance/Finalize quando disponível

---

<a id="scada-passo-13"></a>
### 🔹 Passo 13 – Finalização (tela 2)
![fig22](assets\instalLTS\img22.png)

1. Clique em **Finish**
2. O SCADA‑LTS estará instalado

</details>

---

<a id="acesso-scadalts"></a>
<details>
  <summary><strong>🌐 Acesso ao SCADA‑LTS (Service Manager)</strong></summary>

<a id="acesso-passo-1"></a>
### 🔹 Passo 1 – Acessar pelo navegador
![fig23](assets\instalLTS\img23.png)

1. Abra o navegador e acesse:
```
http://localhost:8080/Scada-LTS/
```
2. Caso não carregue, abra o **Scada‑LTS Service Manager**
3. Defina **Startup Type = Automatic**
4. Clique em **Start**
5. Clique em **OK**

</details>

---

<a id="modbus-server"></a>
<details>
  <summary><strong>📡 MODBUS Server — CODESYS</strong></summary>

Nesta etapa você irá configurar o CODESYS como **Servidor Modbus TCP**, disponibilizando variáveis para o SCADA‑LTS ler/escrever.

<a id="codesys-passo-1"></a>
### 🔹 Passo 1 – 
![fig24](assets\codesys\img1.png)


---

<a id="codesys-passo-2"></a>
### 🔹 Passo 2 – 
![fig25](assets\codesys\img2.png)


---

<a id="codesys-passo-3"></a>
### 🔹 Passo 3 – 
![fig26](assets\codesys\img3.png)


---

<a id="codesys-passo-4"></a>
### 🔹 Passo 4 – 
![fig27](assets\codesys\img4.png)


---

<a id="codesys-passo-5"></a>
### 🔹 Passo 5 – 
![fig28](assets\codesys\img5.png)


---

<a id="codesys-passo-6"></a>
### 🔹 Passo 6 – 
![fig29](assets\codesys\img6.png)


---

<a id="codesys-passo-7"></a>
### 🔹 Passo 7 – 
![fig30](assets\codesys\img7.png)


---

<a id="codesys-passo-8"></a>
### 🔹 Passo 8 – 
![fig31](assets\codesys\img8.png)


---

<a id="codesys-passo-9"></a>
### 🔹 Passo 9 – 
![fig32](assets\codesys\img9.png)


---

<a id="codesys-passo-10"></a>
### 🔹 Passo 10 – 
![fig33](assets\codesys\img10.png)


---

<a id="codesys-passo-11"></a>
### 🔹 Passo 11 – 
![fig34](assets\codesys\img11.png)


---

<a id="codesys-passo-12"></a>
### 🔹 Passo 12 – 
![fig35](assets\codesys\img12.png)


---

<a id="codesys-passo-13"></a>
### 🔹 Passo 13 – 
![fig36](assets\codesys\img13.png)


---

<a id="codesys-passo-14"></a>
### 🔹 Passo 14 – 
![fig37](assets\codesys\img14.png)


---

<a id="codesys-passo-15"></a>
### 🔹 Passo 15 – 
![fig38](assets\codesys\img15.png)

1. Confirme as mensagens de sucesso
2. Garanta que o PLC permaneça em **RUN**

---

<a id="codesys-passo-16"></a>
### 🔹 Passo 16 –  
![fig38](assets\codesys\img16.png)


---

<a id="codesys-passo-17"></a>
### 🔹 Passo 17 – 
![fig38](assets\codesys\img17.png)



</details>

---

<a id="modbus-client"></a>
<details>
  <summary><strong>🔁 MODBUS Client — SCADA‑LTS</strong></summary>

Aqui você irá configurar o SCADA‑LTS para **conectar no servidor Modbus (CODESYS)** e criar os **Data Points**.

<a id="scada-client-passo-1"></a>
### 🔹 Passo 1 – Abrir Data Sources
![fig39](assets\configLTS\img1.png)

1. No SCADA‑LTS, vá em **Ferramentas → Data Sources**
2. Clique para adicionar uma nova fonte de dados

---

<a id="scada-client-passo-2"></a>
### 🔹 Passo 2 – Selecionar “Modbus IP”
![fig40](assets\configLTS\img2.png)

1. No tipo de Data Source, selecione **Modbus IP**
2. Confirme para criar a fonte

---

<a id="scada-client-passo-3"></a>
### 🔹 Passo 3 – Configurar Host e Porta
![fig41](assets\configLTS\img3.png)

1. Em **Host**, coloque o IP do servidor (ex.: `localhost` ou IP do PC/PLC)
2. Em **Port**, coloque a porta Modbus (padrão **502**)
3. Salve a configuração

---

<a id="scada-client-passo-4"></a>
### 🔹 Passo 4 – Criar Data Point (tela 1)
![fig42](assets\configLTS\img4.png)

1. Dentro do Data Source criado, clique em **Add Data Point**
2. Defina nome e tipo do ponto (conforme o registrador)

---

<a id="scada-client-passo-5"></a>
### 🔹 Passo 5 – Criar Data Point (tela 2)
![fig43](assets\configLTS\img5.png)

1. Configure endereço, função e demais parâmetros
2. Salve o Data Point

---

<a id="scada-client-passo-6"></a>
### 🔹 Passo 6 – Validar Data Points (tela final)
![fig44](assets\configLTS\img6.png)

1. Confirme os Data Points criados
2. Verifique status de conexão e leitura/escrita

</details>

---

<a id="observacoes"></a>
<details>
  <summary><strong>⚠️ Observações finais</strong></summary>

- Verifique portas **8080** (SCADA‑LTS) e **502** (Modbus)
- Confirme PLC em **RUN**
- Ajuste firewall do Windows se necessário
- Se não conectar via rede, teste primeiro com **localhost** (quando SCADA e CODESYS estão no mesmo PC)

</details>
