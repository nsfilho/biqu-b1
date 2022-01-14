# Firmware Biqu B1 SE com BL Touch

Os firmwares compilados no diretorio `Firmware` sao para a impressora Biqu B1 SE, com as seguintes características:

- Drivers de Motor: TMC 2225
- Placa controladora: BTT SKR 1.4
- Display Touch Screen: TFT v3.0
- **Com BL Touch**: Triangle, Antclabs, e similares

## Recomendacoes

- Primeiro faça um nivelamento manual da mesa;
- Garanta que o seu eixo X, com a estrusora esteja nivela dos 2 lados igualmente;
- Para que as configuraçoes de `probe offset` funcionem por padrão é necessário utilizar o suporte original;
- Siga as instruçoes de upgrade ccorretamente

## Como realizar o upgrade

- Primeiro no display touch, inicie ele no modo marlin (por segurar o touch por alguns segundos e selecionar a opçao marlin);
- Depois copie o conteudo da pasta Firmware para um SD Card (que esteja formatado no padrao FAT32, recomendo usar o SD Card original que vem com a impressora porque ele já está neste padrao);
- Apos copiar, coloque o SD Card primeiramente na controladora (o SLOT de cartao que fica mais ao fundo da impressora, proximo da entrada USB);
- Aperte o botao de reset que fica embaixo do encoder (botao que girar e clica na frente da impressora);
- Aguarde até que o firmware seja instalado na controladora, e inicie dizendo que está na versao 2.0.9.3;
- Va ate o menu, configuracoes, avancadas, e reinicialize a EEPROM;
- Agora processa da seguinte maneira, reset suas configuracoes para as originais de fábrica (atraves do menu, configuracoes, reset default);
- Agora salve tudo isto com a opçao store settings;
- Remova o SD card da controladora e coloque-o na placa touch (slot sd card mais a frente);
- Pressione o touchscreen por alguns segundos e escolha o modo grafico;
- Após entrar nele, aperte o botao de reset abaixo do encoder;
- Aguarde até que seja feita a copia de todo o conteúdo;
- Agora remova o cartao SD Card e apague TODO o conteudo de firmwares que vc copiou para ele, pois se este cartao continuar inserido e vc reiniciar um erro será apresentado, e voce vai precisar repetir este processo todo;
- Agora va ao marlin, e execute: primeiro um homing de todos os eixos, depois um BED Leveling, salve tudo isto;
- Para finalizar, va em Settings, Advanced e selecione Probe Offset, e no final do menu, a opcao Wizard;
- Após a maquina se posicionar, ajuste até que o bico da extrusora raspe em uma folha de sulfite, entre ele e a mesa;
- Nao se esqueca de salvar tudo, e volte para o modo gráfico;

Agora é só alegria. Basta testar tudo.

## Arquivos fontes

Os principais arquivos de configuracao para cada uma das compilacoes estao aqui, para que seja possivel personalizar ainda mais. Para tanto faca um clone dos projetos disponiveis em: 

- [Marlin](https://github.com/MarlinFirmware/Marlin/tree/2.0.9.3)
- [Touch](https://github.com/bigtreetech/BIGTREETECH-TouchScreenFirmware/tree/Vx.x.27)

Lembrando que a versao do TFT Touch só funciona com Marlin 2.0.8.x ou superior. Alguns firmwares disponibilizados, nao levam em conta isto. Neste caso, as opcoes escolhidas sao 100% compativeis.
