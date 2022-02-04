### Como instalar o Docker

Para instalar o Docker desktop, voçe vai acessar o [Site oficial](https://docs.docker.com/desktop/windows/install/).

Antes de tudo, devemos instalar o **WSL 2 backend** que vai funcionar em background como uma maquina virtual linux.

**Pré-requisitos de hardware são necessários para executar com êxito o WSL 2 no Windows 10 ou Windows 11:**

- Processador de 64 bits;
- 4GB de RAM do sistema;
- O suporte à virtualização de hardware no nível do BIOS deve ser ativado nas configurações do BIOS.

### Instalando WSL

Para isso, voçe vai abri o **Windows Power Shell** no menu iniciar e rodar o seguinte comando:

```Powershell
wsl --install
```

Logo em seguida deverá reiniciar sua máquina.

Com isso, os componentes do kernel do linux(mais recentes) serão instalados em sua máquina, o mesmo ultiliza ubuntu como padrão.
 
 ### Verificando a versão do WSL
 
 Para verificar qual versão foi instalada, utilizaremos o seguinte comando:
 
 ```Powershell
wsl -l -v
```

### Instalando Docker no windows

1. Você irá baixar o instalador no site [Docker Hub](https://hub.docker.com/editions/community/docker-ce-desktop-windows/)

2. Execute o instalador, e no processo de instalação, certifique-se que a opçao **Habilitar Recursos do Windows Hyper-V** ou **Instalar os componentes necessários do Windows para WSL 2** esteja selecionada.

IMAGEM AQUI

3. Siga o passo a passo do assistente de instalação até finalizar todo processo.

4. Ao fim da instalação bem-sucedida, aperte em **fechar** para concluir a instalação.

5. Se sua conta de administrador for diferente de sua conta de usuário, você deverá adicionar o usuário ao grupo docker-users . Execute o Gerenciamento do Computador como administrador e navegue até Usuários e Grupos Locais > Grupos > usuários docker . Clique com o botão direito do mouse para adicionar o usuário ao grupo. Saia e faça login novamente para que as alterações entrem em vigor.

