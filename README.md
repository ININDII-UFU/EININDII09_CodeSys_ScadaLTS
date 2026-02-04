# 📘 EININIDII - Instalação/Configuração do SCADA‑LTS
> **Professor**: Josué Morais  
> **Disciplina**: Instrumentação Industrial II  
> **Curso**: Engenharia de Controle e Automação  
> **Instituição**: Universidade Federal de Uberlândia — FEELT  

---

## Colaboradores

Este projeto é resultado de um esforço conjunto. A participação das pessoas abaixo foi essencial:

- **Amanda Caetano Alvarenga**
- **Gabriel Zuccolotto Alecrim**
- **Luan Rafael Pereira Santos**

A cada um(a), nosso agradecimento pelo compromisso, pela parceria e pela qualidade do trabalho entregue.

---

<details open>
  <summary><strong>📑 Índice</strong></summary>

- Instalação do OpenJDK  
- Instalação do SCADA‑LTS  
- Acesso ao SCADA‑LTS (Service Manager)  
- MODBUS Server — CODESYS  
- MODBUS Client — SCADA‑LTS  

</details>

---

<details open>
  <summary><strong>☕ 1. Instalação do OpenJDK</strong></summary>

Para realizar a instalação do OpenJDK, utilize o link oficial (Microsoft Build of OpenJDK):  
🔗 **Download:** https://aka.ms/download-jdk/microsoft

O **OpenJDK (Java Development Kit)** fornece compilador, JVM e bibliotecas padrão para desenvolvimento/execução de aplicações Java.

1. **Baixe e execute** o instalador do OpenJDK.  
![Figura 1 — Instalador do OpenJDK](img/image1.png)

2. **Aceite os termos de licença.**  
![Figura 2 — Aceite dos termos de licença](img/image2.png)

3. Na tela de customização, ative **“Set JAVA_HOME variable”**.  
![Figura 3 — Customização e JAVA_HOME](img/image3.png)

4. Clique em **Install**.  
![Figura 4 — Pronto para instalar](img/image4.png)

5. Edite as variáveis de ambiente do sistema.  
![Figura 5 — Variáveis de ambiente](img/image5.png)

6. Em **Path**, adicione o diretório do JDK.  
![Figura 6 — Path](img/image6.png)

7. Confirme o caminho do JDK.  
![Figura 7 — Diretório JDK](img/image7.png)

8. Confirme **JAVA_HOME**.  
![Figura 8 — JAVA_HOME](img/image8.png)

9. Valide no Prompt:
```bat
java -version
```
![Figura 9 — java -version](img/image9.png)

</details>

---

<details open>
  <summary><strong>🖥️ 2. Instalação do SCADA‑LTS</strong></summary>

Baixe o instalador:
🔗 https://github.com/SCADA-LTS/windows-installer/releases

![Figura 10 — Aviso de segurança](img/image10.png)

Clique em **Mais informações → Executar assim mesmo**.

![Figura 11 — Idioma](img/image11.png)
![Figura 12 — Executar](img/image12.png)

Selecione o idioma.
![Figura 13 — Idioma](img/image13.png)

Avance no assistente.
![Figura 14 — Assistente](img/image14.png)

Aceite o contrato.
![Figura 15 — Licença](img/image15.png)

Escolha o diretório.
![Figura 16 — Diretório](img/image16.png)

Avance com padrões.
![Figura 17](img/image17.png)
![Figura 18](img/image18.png)

Configure porta, usuário e senha.
![Figura 19 — Porta HTTP](img/image19.png)

⚠️ **Marque instalar servidor local**
![Figura 20 — Servidor local](img/image20.png)

Finalize.
![Figura 21](img/image21.png)
![Figura 22](img/image22.png)

</details>

---

<details open>
  <summary><strong>🌐 3. Acesso ao SCADA‑LTS (Service Manager)</strong></summary>

Abra no navegador:
```
http://localhost:8080/Scada-LTS/
```

Caso não abra, utilize o **Scada‑LTS Service Manager**:

1. Defina **Startup Type = Automatic**
2. Clique em **Start**
3. Clique em **OK**

![Figura 23 — Service Manager](img/image23.png)

</details>

---

<details open>
  <summary><strong>📡 4. MODBUS Server — CODESYS</strong></summary>

Crie um novo projeto no CODESYS.

![Figura 24](img/image24.png)
![Figura 25](img/image25.png)
![Figura 26](img/image26.png)

Adicione Ethernet e Modbus TCP Server.

![Figura 27](img/image27.png)
![Figura 28](img/image28.png)
![Figura 29](img/image29.png)
![Figura 30](img/image30.png)

Inicie o PLC.
![Figura 31](img/image31.png)
![Figura 32](img/image32.png)

Configure o servidor Modbus.
![Figura 35](img/image35.png)

Mapeie variáveis.
![Figura 36](img/image36.png)

Faça download.
![Figura 37](img/image37.png)
![Figura 38](img/image38.png)

</details>

---

<details open>
  <summary><strong>🔁 5. MODBUS Client — SCADA‑LTS</strong></summary>

Acesse **Ferramentas → Data Sources**.
![Figura 39](img/image39.png)

Adicione Modbus IP.
![Figura 40](img/image40.png)

Configure Host e Porta.
![Figura 41](img/image41.png)

Crie Data Points.
![Figura 42](img/image42.png)
![Figura 43](img/image43.png)
![Figura 44](img/image44.png)

</details>

---

<details open>
  <summary><strong>⚠️ Observações finais</strong></summary>

- Verifique portas 8080 e 502
- Confirme PLC em execução
- Ajuste firewall se necessário

</details>
