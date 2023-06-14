# Configuração de Ambiente Flutter 

## Passo a Passo do que Baixar!
### Java/JDK
- Chocolatey - https://chocolatey.org/install
- Abrir e executar como ADM o PowerShell e colcar o codigo que pede no link acima
- Depois instala o git com -  choco install git
- Logo depois a instala a JDK(no caso uso a 11)
- Instala a JDK - https://www.oracle.com/br/java/technologies/javase/jdk11-archive-downloads.html
- Para ficar organizado crie uma hierarquia de pastas:
- No C: crie uma pasta com o nome de DevPrograms/jdk/jdk11
- Inicie o instalador do Java/JDK e escolha o caminho acima para a instalação
- Caso a versão da JDK necessite do JRE , instale no caminho DevPrograms/jre/jre+numero da versão
- Após instalar vá até as variaveis de ambiente e retire do path as ligações a JDK feita por padrão.
- Abra o PowerShell como ADM e digite:
- New-Item -Itemtype Symbolic -Path "C:\Devprograms\jdk\current" -Target "C:\DevPrograms\jdk\jdk11" no ultimo caminho a versao desejada
- Vá para as variaveis de ambiente e nas variaveis do usuário crie uma com o nome de JAVA_HOME com o valor de C:\DevPrograms\jdk\current
- Vá para path clique em novo e coloque %JAVA_HOME%\bin
- Caso queira alterar a variavel do java para outra JDK abra o Power Shell como ADM e digite:
- New-item -Itemetype Symbolic -Path "C:\Devprograms\jdk\current" -Target "C:\DevPrograms\jdk\versao_do_java . Se ja tiver instalada coloca -Force no final
- Com o comando acima consegue alterar entre as versoes.

### Configuração do Android
- Para a configurar o Android, utilize o AndroidStudio. Facilita a vida
- Instale baixando em - https://developer.android.com/studio
- Usa a configuração Standard
- Aceita os termos de tudo e da Finish
- Baixado tudo vai em More Actions -> SDK Manager(Onde esta a Instalação do Android)
- Copie o caminho do Android SDK Location e crie 2 novas váriaveis de ambiente %ANDROID_HOME% e %ANDROID_SDK_ROOT% com o valor desse caminho 
- No path do usuário cria o %ANDROID_HOME%\tools e %ANDROID_HOME%\platform-tools
- Vá ao PowerShell e digite adb se aparecer um textao deu bom
- No AndroidStudio no SDK Platforms baixa umas versão do Android
- Em SDK Tools deixe selecionado os que vem por padrão, mas adiciona Android SDK Command-line Tools e se usar AMD e não tiver selecionado o Android Emulator hypervision driver e da Apply
- Em Plugins instala o do Dart e Flutter


### Configuração do Emulador
- Clique em More Actions -> Virtual Device Manager -> Create Device e escolhe um Pixel
- Quando escolher um instale as versões do android que você quiser
- Vai nas configurações avançadas
- Se tiver mais memorias aumenta a RAM dedicada
- Meu Padrao, enable frame e keybord. E aumenta apenas a RAM
- Lembrar de ativar a Virtualização na BIOS

### Usando Device Físico
- Ativar o modo desenvolvedor do celular
-- Deixar habilitado o Permanecer Ativo e Depuração por USB
- Baixar Vysor ou  scrpy com choco install scrpy

### FVM ou Flutter Nativo
- Se tiver alguma variavel de ambiente ligado ao Flutter remova
- Usar FVM pra usar mais de uma versão do Flutter
--  https://fvm.app/docs/getting_started/installation
-- Para instalar use - choco install fvm

### Comandos FVM
- Tipos de versões: 
-- Mostra todas as versões do Flutter disponíveis : fvm releases 
-- Versões recomendadas para projetos em produção :  stable
-- As que vem nas próximas versõe : beta
-- As que trocam sempre, atualizações sempre e pode quebrar do nada : dev
- Para instalar uma versão do Flutter Global (buscar instalar a stable):
-- fvm global versão , para usar a stable fvm global stable
-- Ele da um caminho no terminal pegar esse caminho coloca dentro do path
- Dart:
-- Todos comandos que seria dart alguma coisa se torna fvm dart alguma coisa
-- A mudança se da por que a versão que foi utlizada na instalação do Flutter foi diferente
- Instalação do Dartion
-- fvm dart pub global activate dartion -> instala um pacote]
-- Pega o caminho do terminal e coloca no path 

### VSCODE e Extensões
- Instalar os plugins do Dart e Flutter
- Instalar IntelliJ IDEA Keybindings
- Material Icon
- Awesome Flutter Snippets
- Dart Data Class Generator
- Flutter & Dart Utilities
- bloc
- Error Lens
- Image Preview
- Pubspec Dependency Search
- Live Share
- Settings-> Extensions -> Flutter & Dart Utilities -> Generate Template : Colocar Clean Code
- Configuração do FVM no VSCODE:
-- Criar uma pasta .vcscode , criar um arquivo settings.json. Dentro dele coloque o codigo:
-- ``{
    "dart.sdkPath":"C:/Users/guilh/fvm/default/bin/cache/dart-sdk"
}``
-- Ou settigns -> SDKPath do dart -> e o codigo acima na variavel


## Primeiro Projeto
- ``fvm dart create -t console-full nomeProjeto``
- Estrutura do projeto:
--bin: Arquivo unicial -> Main
-- lib: Arquivos que você vai criar
-- test: Testes da aplicação
-- gitignore: Ignora a pasta build e puxa da pub
-- analysis_options: O que analisa o código e tras melhorias, se a empresa tiver padrão da pra configurar nele
-- changelog: Para falar sobre mudanças no codigo
--pubspec.lock: Não se mexe
--pubspec.yaml: Descritor do projeto com o nome, descrição, versao, variaveis de ambiente,dependencias
--Readme.md: Para falar o que o projeto faz e observações

