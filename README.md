# Maximum-laptop-bomb
This Comands make my bad laptop run "good" Test this comands on you CMD


- sfc /scannow
  
Verifica a integridade dos arquivos do sistema: Ele examina todos os arquivos protegidos do Windows.
Repara arquivos corrompidos: Se encontrar arquivos danificados ou ausentes, o sfc tenta substituí-los automaticamente por versões corretas do cache do sistema.

- bcdedit /set useplatformtick yes   - synthetic timers
  
Ele força o Windows a usar o timer de hardware da plataforma (HPET - High Precision Event Timer) em vez dos timers sintéticos gerados pelo sistema operacional ou pelo processador.

- bcdedit /set disabledynamictick yes  - dynamic tick
  
Ele desativa o Dynamic Tick, que é um recurso do Windows usado para economizar energia reduzindo as interrupções do timer quando o sistema está ocioso.

- bcdedit /deletevalue useplatformclock - hpet
  
  Esse comando remove a configuração manual do HPET (High Precision Event Timer) no Windows.

- cleanmgr.exe C
  
  executa o Liberador de Espaço em Disco do Windows (cleanmgr.exe) para a unidade C:.

- Fsutil behavior query memoryusage
  
é usado para verificar as configurações de uso de memória do sistema de arquivos NTFS no Windows.

- Fsutil behavior set memory usage 2
  
Esse comando tenta configurar o uso de memória do NTFS para o valor 2, mas esse valor é obsoleto e não é mais suportado nas versões modernas do Windows.
Na prática, o Windows provavelmente retornará um erro ou simplesmente não aplicará a alteração.

- powercfg.exe /hibernate off
  
Esse comando desativa a hibernação no Windows, o que também remove o arquivo hiberfil.sys do disco.

- Fsutil behavior query DisableDeleteNotify
  
  Esse comando verifica se o TRIM está ativado ou desativado no Windows. O TRIM é um comando essencial para o desempenho e a longevidade de SSDs, pois permite que o sistema operacional informe ao SSD quais blocos de dados não são mais usados e podem ser apagados.
  
- fsutil behavior set disabledeletenotify 0
  
Esse comando ativa o TRIM no Windows para SSDs. O TRIM ajuda a manter o desempenho e a longevidade de um SSD, informando ao dispositivo quais blocos de dados não são mais necessários e podem ser apagados.

- powercfg -duplicatescheme e9a42b02-d5df-448d-aa00-03f14749eb61
  
Esse comando cria um plano de energia duplicado no Windows, baseado no identificador de esquema fornecido: e9a42b02-d5df-448d-aa00-03f14749eb61.

- ipconfig /release
  
O comando ipconfig /release libera o endereço IP atualmente atribuído ao seu dispositivo pela rede. Em outras palavras, ele remove o IP da interface de rede e desconecta o dispositivo da rede local.
Isso é útil quando você deseja renovar a conexão ou quando há problemas de conectividade, forçando o dispositivo a obter um novo IP.

- ipconfig /renew
  
O comando ipconfig /renew solicita ao servidor DHCP (Dynamic Host Configuration Protocol) que renove o endereço IP do seu dispositivo. Em outras palavras, ele obtém um novo endereço IP da rede, seja para a interface Ethernet ou Wi-Fi.
Esse comando é útil após o uso do comando ipconfig /release (que libera o IP), ou se você estiver com problemas de conexão e precisar forçar o dispositivo a obter um novo IP.

- ipconfig /flushdns
  
Esse comando limpa o cache de DNS do seu computador. O DNS (Domain Name System) é responsável por resolver os nomes de domínio (como www.exemplo.com) em endereços IP. Quando você acessa um site, o Windows armazena temporariamente essa informação no cache de DNS para acelerar as futuras conexões.
Ao usar o comando ipconfig /flushdns, você limpa esse cache, forçando o sistema a consultar novamente os servidores DNS para resolver os nomes de domínio. Isso pode ser útil quando há problemas de resolução de nomes de domínio, como um site sendo acessado com um endereço antigo ou alterado.

- netsh winsock reset
  
Esse comando reinicializa o catálogo Winsock no Windows, que é responsável pela comunicação de rede e pelas conexões de Internet no sistema. "Winsock" é uma abreviação para Windows Socket e, basicamente, é uma API (Interface de Programação de Aplicações) que define como os aplicativos de rede devem se comunicar com o sistema operacional.
Ao executar esse comando, o Windows irá resetar o catálogo Winsock para seu estado original. Esse comando é útil para resolver problemas de conectividade de rede causados por configurações ou corrupção no Winsock, que pode ocorrer devido a problemas com drivers de rede, configurações de proxy ou malware.

- netsh advfirewall firewall add rule name="StopThrottling" dir=in action=block remoteip=173.194.55.0/24,206.111.0.0/16 enable=yes
  
Este comando adiciona uma regra de firewall no Windows para bloquear conexões de rede de IPs específicos. Vamos analisar os parâmetros:
name="StopThrottling": Nomeia a regra como "StopThrottling".
dir=in: A regra se aplica a conexões de entrada (ou seja, de IPs remotos para o seu computador).
action=block: A ação da regra é bloquear essas conexões de rede.
remoteip=173.194.55.0/24,206.111.0.0/16: Define os intervalos de endereços IP remotos que serão bloqueados:
173.194.55.0/24: Bloqueia todos os endereços IPs no intervalo de 173.194.55.0 a 173.194.55.255.
206.111.0.0/16: Bloqueia todos os endereços IPs no intervalo de 206.111.0.0 a 206.111.255.255.
enable=yes: A regra será habilitada imediatamente após ser adicionada.
