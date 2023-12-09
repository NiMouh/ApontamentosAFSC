# Aula 6 - Dispositivos de armazenamento

## *Hard Disk Drive* (HDD)
É uma forma não volátil de armazenamento magnético.

Existe dois tipos de **acesso**:
 - **Acesso Direto (s/BIOS)**: Consiste na escrita e leitura de dados diretamente pelo controlador do disco.
 - **Acesso Sequencial (c/BIOS)**: Consiste na escrita e leitura de dados através do sistema operativo. 

Nota: O acesso sequencial é mais lento que o acesso direto, no entanto, o acesso sequencial é mais simples de implementar.

### Estrutura
Um HDD é composto por:
 - **Trilhas (tracks)**: os endereços começam do exterior (o endereço das trilhas pode ser representado pelo número da *head*).
 - **Cilindros (cylindres)**: todas as trilhas num determinado endereço em todos os pratos (o endereço dos cilindros pode ser representado pelo número do *cylinder*)
 - **Sectores (sectors)**: subdivisão de trilhas, tipicamente 512 bytes (o endereço dos sectores pode ser representado pelo número do *sector*).

Para obter  o endereço de um determinado setor, é necessário saber o número do *cylinder*, o número da *head* e o número do *sector* (CHS).

Nota: Esta tradução está limitada a apenas 8,1 GB de espaço de endereçamento.

Outro modo é o LBA (Logical Block Addressing), que consiste em endereçar os setores sequencialmente, começando no 0. A conversão de CHS para LBA é feita através da seguinte fórmula:
```LBA = (C * Max(H) + H) * Max(S) + (S - 1)```


## *Advanced Technology Attachment* (ATA)
É um padrão de interface para a conexão de dispositivos de armazenamento, como discos rígidos e drives ópticas, em computadores.

No surgimento de ATA-4 e ATA-6, respetivamente, foram introduzidas as seguintes áreas de armazenamento de dados:
 - **Host Protected Area (HPA)**: É uma área de armazenamento de dados que o sistema operativo não consegue aceder. Esta área é usada para armazenar dados de diagnóstico e de recuperação de dados.
 - **Device Configuration Overlay (DCO)**: É uma área de armazenamento de dados que o sistema operativo não consegue aceder. Esta área é projetado para armazenar informações de configuração da unidade.


## *Small Computer System Interface* (SCSI)
É um conjunto de padrões para conectar dispositivos e periféricos a um computador. 

## *Solid State Drive* (SSD)
Semelhante a um HDD em termos de componentes, no entanto, o SSD tem a sua própria unidade de processamento e memória, o que permite que o SSD seja mais rápido que o HDD, pois a sua leitura não depende da localização física dos dados (ao contrário do HDD).

Existem os seguintes tipos de SSD:
 - **DRAM**: É um tipo de memória volátil, ou seja, quando o computador é desligado, os dados são perdidos.
 - **Flash memory**: É um tipo de memória não volátil, ou seja, quando o computador é desligado, os dados não são perdidos (pode ser NAND ou NOR).


## *Bad Blocks*
Um bloco é considerado mau quando não é possível ler ou escrever dados nesse bloco.

## *Wear Leveling*
*Wear leveling* é uma técnica usada em dispositivos de armazenamento, especialmente em SSDs (Solid State Drives), para distribuir uniformemente as operações de gravação e apagar dados em todas as células de armazenamento. O *wear leveling* procura evitar esse desgaste desigual, movendo dinamicamente os dados entre as células de armazenamento. Dessa forma, todas as células são usadas de maneira mais equitativa, prolongando a vida útil do dispositivo como um todo.

## USB Pen Drive
É um dispositivo de armazenamento portátil que utiliza memória flash para armazenar dados. Não possui o seu próprio processador, mas sim um controlador que permite a comunicação com o computador, usando o CPU para calcular o ECC (Error Correction Code), bad blocks, wear leveling, etc.

## Protocolos dos conectores SSD, interfaces e transferência de dados
 - Conector: camada 1, parte física dos dispositivos de armazenamento.
 - Interface: camada 2, protocolo de comunicação entre o controlador e o dispositivo de armazenamento.
 - Transferência de dados: camada 3, protocolo de comunicação entre o sistema operativo e o controlador.

M.2 é um conector que suporta vários protocolos de interface, como SATA, PCIe e USB:
- **SATA**: Serial ATA, é um protocolo de interface para transferência de dados entre o controlador e o dispositivo de armazenamento.
- **PCIe**: Peripheral Component Interconnect Express, é um protocolo de interface para transferência de dados entre o controlador e o dispositivo de armazenamento.
- **USB**: Universal Serial Bus, é um protocolo de interface para transferência de dados entre o controlador e o dispositivo de armazenamento.








