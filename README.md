# Bem-vindo ao Pix por Piggly #

**Sempre atualize para continuar aproveitando**

O **Pix** é o mais novo método de pagamento eletrônico criado pelo Banco Central do Brasil.
Você encontra todos os detalhes na [página oficial](https://www.bcb.gov.br/estabilidadefinanceira/pix) do Pix.

O propósito deste plugin é permitir que você utilize o método de pagamento Pix em sua loja **Woocommerce** sem qualquer custo de forma simples, rápida e direta. Acesse as configurações do plugin em `Woocommerce > Configurações > Pagamentos > Pix`.

**Quer saber mais?** Assista ao vídeo tutorial de configuração no [Youtube](https://www.youtube.com/watch?v=PqRqXFgWOsg&t=200s).

> Se você apreciar a função deste plugin e quiser apoiar este trabalho, sinta-se livre para fazer qualquer doação para a chave aleatória Pix `aae2196f-5f93-46e4-89e6-73bf4138427b` ❤.

> Não esqueça de deixar a sua avaliação sobre o plugin! Isso nos incentivará a lançar mais atualizações e continuar prestando um suporte de qualidade.

# Novidades da versão 1.2.0 #

A versão **1.2.0** mudou completamente o núcleo do plugin, para torná-lo mais eficiente e poderoso. Se você fez mudanças na estrutura do plugin esteja ciente que elas serão perdidas. Os templates de e-mail e do pagamento Pix foram atualizados para atender as melhorias.

## Principais Melhorias ##

* ✅ Reformulação das configurações;
* ✅ Criação da metabox Pix nos pedidos pagos via Pix;
* ✅ Otimização para geração dos QR Codes;
* ✅ Desconto automático para pagamento via Pix.

## Performance do QR Code ##

Antes, o plugin gerava o QR Code toda vez que o Pix era visto. E apresentava um "fix" para um e-mail que salvada um arquivo `.png` toda vez que o e-mail era enviado.

Para melhorar a performance do Pix e evitar processar desnecessariamente a imagem dos QR Codes. Agora, o plugin gerar o Pix pela primeira vez, salva o QR Code na pasta `uploads > pix-por-piggly > qr-codes` em um arquivo `.png` e grava nos meta dados do Pedido.

Dessa forma, se o pedido já foi pago, os meta dados serão mantidos e você sempre poderá conferir por qual chave aquele Pix foi pago, mesmo que decida mudar a chave.

Se o Pix ainda não foi pago, será gerado novamente somente se você mudar a chave Pix por qualquer razão. Do contrário, os meta dados gravado no pedido serão utilizados.

# Recursos #

* ✅ Tratamento automático de dados, não se preocupe com o que você digita. O plugin automaticamente detecta melhorias;
* ✅ Permita que o cliente envie o comprovante por uma página, pelo Whatsapp e/ou Telegram;
* ✅ Teste o seu Pix a qualquer hora, antes mesmo de habilitar o plugin;
* ✅ Aplique desconto automático, sem criação de cupons, ao realizar o pagamento via Pix;
* ✅ Visualize os dados do Pix gerado na página do pedido;
* ✅ Com problema na hora de preencher os dados do Pix? Importe os dados Pix de uma chave Pix válida e não tenha mais preocupações;
* ✅ Utilize **Merge Tags**, em campos disponíveis, para substituir variáveis e customizar ainda mais as funções do plugin.
* ✅ Use o shortcode `[pix-por-piggly order_id="$id"]` para importar o template do Pix em qualquer lugar;
* ✅ Selecione o modelo de e-mail onde o Pix será enviado e o status do pedido enquanto aguarda a conferência do pagamento Pix.

# Como funciona? #

Assim como é feito atualmente com uma transferência eletrônica no Woocommerce, o **Pix por Piggly** permite aos consumidores escolherem o método de pagamento Pix, então eles recebem as instruções de pagamento e enviam o comprovante. Você também pode aplicar um desconto automático para pagamentos via Pix.

Bem simples né?

Para permitir isso, nosso plugin segue todas as propostas do padrão EMV®1, implementado pelo Banco Central do Brasil, você pode ler mais sobre isso em [Especificações Técnicas](https://www.bcb.gov.br/content/estabilidadefinanceira/forumpireunioes/Anexo%20I%20-%20QRCodes%20-%20Especifica%C3%A7%C3%A3o%20-%20vers%C3%A3o%201-1.pdf). Utilizamos a nossa bibliteca [piggly/php-pix](https://github.com/piggly-dev/php-pix) para manipular e gerar os códigos pix.

Dessa forma, nosso plugin gera os três principais métodos de pagamento Pix:

1. Um **QR Code** com o código Pix;
2. O código Pix em formato de texto para utilização da função **Pix Copia & Cola**; 
3. Pagamento manual com os dados Pix fornecidos.

Nosso plugin gera de forma automática o código Pix com base nas informações do Pedido e nas informações preenchidas na configuração do plugin. 

> Não importa como você digita a chave Pix, ela será automaticamente convertida para os formatos apropriados, okay? Caso ela esteja inválida, de acordo com o formato escolhido, você será notificado.

# Funcionalidades #

Nas configurações do plugin você é capaz de manipular as seguintes funções:

1. Importar configurações de um código Pix pré-existente;
2. Habilitar/Desabilitar o método de pagamento;
3. Alterar o título e descrição do pagamento;
4. Exibir os métodos QR Code, Pix Copia & Cola e Pagamento Manual;
5. Informar o nome da loja para a descrição do Pix;
6. Inserir o nome e a cidade do titular da conta Pix;
7. Escolher o tipo de chave e informar o valor da chave Pix;
8. Escrever as instruções para envio do comprovante de pagamento;
9. Alterar o formato do identificador do Pix;
10. Incluir uma página para enviar o comprovante;
11. Testar o pix com qualquer valor.

## Quer receber comprovantes? O que sugerimos: ##

> **Cuidado com o envio de comprovantes**. O upload de arquivos no Wordpress é delicado. É necessário tomar certas precauções e por isso utilize alguns plugins que já fazem isso muito bem como o **Gravity Forms** ou **WP Forms**.

Crie uma nova página no Wordpress com um formulário para envio de arquivos, permitindo apenas as extensões jpg, png e pdf. Isso pode ser feito utilizando os plugins citados acima. Posteriormente, nas configurações do Pix em **Página para Comprovante** insira a URL da página para enviar o comprovante. 

Você pode utilizar `{{pedido}}` na URL pois esse termo será substituído pelo número do pedido. Assim, caso seu formulário permita o auto preenchimento via URL conseguirá preencher automaticamente o número do pedido para o cliente.

Por exemplo, com o número do pedido `1234` defina a URL em **Página para Comprovante** como, por exemplo, `https://minhaloja.com.br/comprovante-pix/?order_id={{pedido}}`. Nosso plugin traduzirá essa URL para `https://minhaloja.com.br/comprovante-pix/?order_id=1234`, basta então ler o campo `order_id` da URL com o seu formulário no campo apropriado.

Você também pode inserir seu número do Whatsapp e/ou usuário do Telegram para que seu cliente envie o comprovante de pagamento Pix por esses canais.

## Testes realizados ##

O código Pix gerado por esse plugin, incluindo a função **QR Code** e **Pix Copia & Cola**, foi testado nos seguintes aplicativos de banco:

* Banco do Brasil;
* Banco Inter;
* BMG;
* Bradesco;
* C6;
* Itaú;
* Mercado Pago;
* Nubank;
* PagPank;
* Santander.

Como o código utiliza o padrão do Pix é possível que funcione em todos os bancos. Mas, caso encontre problemas ou dificuldades não hesite em abrir uma [thread](https://wordpress.org/support/plugin/pix-por-piggly/) no Suporte do Plugin ou enviar um e-mail para **[dev@piggly.com.br](mailto:dev@piggly.com.br)**.

# Perguntas Frequentes #

## Qual é a licença do plugin? ##

Este plugin esta licenciado como GPLv2. Ele é distrubuido de forma gratuita.

## O que eu preciso para utilizar este plugin? ##

* Ter instalado o Wordpress 4.0 ou superior;
* Ter instalado o plugin WooCommerce 3.0 ou superior;
* Utilizar a versão 7.2 do PHP;
* Ter a extensão `gd` para PHP habilitada, veja detalhes [aqui](https://www.php.net/manual/pt_BR/book.image.php);
* Possuir uma conta bancária com Chave Pix.

## Posso utilizar com outros gateways de pagamento? ##

Sim, esse plugin funciona apenas como um método de pagamento adicional, assim como acontece com o método de transferência eletrônica.

## Como aplicar desconto automático? ##

Na página de configurações do Plugin, acesse **Pedidos & E-mails** e insira um valor e um rótulo para o desconto Pix. O desconto será automaticamente aplicado quando o cliente escolher o método de pagamento Pix.

## Como conferir o pagamento Pix? ##

A conferência do Pix ainda é manual, assim como acontece em uma transferência eletrônica. Para facilitar, o plugin gera os Pix com um código identificador. Esse código possuí o número do pedido e você pode personalizá-lo na página de configurações do Plugin. 

Abra o pedido criado no Woocommerce e verifique o código identificador do Pix, ao abrir o aplicativo do seu banco, você poderá ver detalhes sobre o recebimento Pix e, na maioria dos bancos, o pagamento estará identificado com o código identificador do Pix.

## Não tem como atualizar o pagamento Pix automáticamente? ##

Para validar se um Pix foi pago a maioria dos bancos emissores irão cobrar taxas, assim como os intermediadores de pagamento. Se você faz parte de um banco emissor que já implementa a API Pix, pode entrar em contato com a gente em [dev@piggly.com.br](mailto:dev@piggly.com.br) para que possamos implementar a solução.

## Gerei o código Pix, mas não consigo efetuar o pagamento. E agora? ##

Nas configurações do Plugin acesse "Suporte" e verifique a seção "O plugin gera o QR Code, mas não consigo pagá-lo", lá estarão algumas dicas automáticas que podem ajudar você. Se ainda sim precisar de algum suporte, abra um chamado enviando um e-mail para [dev@piggly.com.br](mailto:dev@piggly.com.br).

## Como customizar os templates? ##

Nas configurações do Plugin acesse "Suporte" e verifique a seção "Como substituir os templates de e-mail e da página de obrigado".

> **AVISO**: Ao customizar os templates você pode perder funcionalidades importantes do plugin e comportamentos pré-existentes nos templates originais. Tenha certeza sobre o que está fazendo para garantir que tudo funcione como deve ser. **Não prestaremos suporte para customizações**.

# Como instalar? #

## No diretório oficial do Wordpress ##

A página oficial do plugin pode ser encontrada em: [wordpress@pix-por-piggly](https://wordpress.org/plugins/pix-por-piggly/).

## No repositório do Github ##

Vá para [Releases](https://github.com/piggly-dev/piggly-views-wordpress/releases) neste repositório e faça o download em `.zip` da versão mais recente.

Então, no **Painel Administrativo** do Wordpress, vá em `Plugins > Adicionar novo` e clique em `Upload plugin` no topo da página para enviar o arquivo `.zip`.

> Você precisará, posteriormente, ir até a pasta do plugin no terminal do seu servidor Web e executar o comando `composer install` caso escolha essa opção.

## Da origem ##

Você precisará do Git instalado para contruir da origem. Para completar os passos a seguir, você precisará abrir um terminal de comando. Clone o repositório:

`git clone https://github.com/piggly-dev/wc-piggly-pix.git`

> Você precisará, posteriormente, executar o comando `composer install` caso escolha essa opção.

# Como utilizar? #

Após a instalação do plugin, vá até `Plugins > Plugins instalados`, ative o plugin **Pix por Piggly para Woocommerce**. Assim que você ativar, o plugin já estará disponível em `Woocommerce > Configurações > Pagamentos` e você poderá inserir todas as configurações pertinentes.

**Preencha corretamente a sua chave Pix. Você pode testar nas configurações do plugin o funcionamento do Pix mesmo que o módulo esteja desativado.**

# Screenshots #

1. Exemplo do método de pagamento durante o Checkout;
2. Exemplo das instruções com as informações de pagamento;
3. Método de pagamento nas configurações do Woocommerce;
4. Configurações do método de pagamento.

# Changelog #

## 1.2.0 ##

* Reformulação das configurações;
* Criação da metabox Pix nos pedidos pagos via Pix;
* Otimização da geração dos QR Codes;
* Desconto automático para pagamento via Pix.

## 1.1.14 ##

* Dicas de apoio para preenchimento do Pix;
* Correções dos botões Whatsapp e Telegram no e-mail;
* Link para ver o pedido no e-mail ao invés do link para pagamento;
* Correções ao salvar configurações;
* Adição do caminho para sobrescrever os templates.

## 1.1.13 ##

* Adição do botão de configuração e ajustes na importação;

## 1.1.12 ##

* Correções de bugs;

## 1.1.11 ##

* Melhorias no texto de apoio e captura de erros com textos de apoio;

## 1.1.10 ##

* Correção de bug no envio de e-mail;

## 1.1.9 ##

* Correção de bugs para versões 7.3- do PHP;

## 1.1.8 ##

* Correção de bugs, melhorias da documentação, controle de erros e inserção nas instruções via e-mail;

## 1.1.7 ##

* Correções e melhorias;

## 1.1.6 ##

* Correção do bug no campo Whatsapp, correção dos bugs com chaves vazias, controladores de e-mail e status;

## 1.1.5 ##

* Atualização da formatação do campo **Identificador**;

## 1.1.4 ##

* Botões para Whatsapp e Telegram, além de melhorias no layout;

## 1.1.3 ##

* Suporte para o PHP 7.2 (conforme solicitado por muitos utilizadores);

## 1.1.2 ##

* Atualização da biblioteca `piggly/php-pix` e do painel de configurações;

## 1.1.1 ##

* Atualização da biblioteca `piggly/php-pix`;

## 1.1.0 ##

* Correções de bugs;
* Melhorias na exibição do Pix no e-mail e na tela;
* Ajuste de visualizações com base nas opções selecionadas;
* Melhorias no núcleo do plugin;

## 1.0.3/1.0.4 ##

* Correções de bugs e reposicionamento das descrições;

## 1.0.2 ##

* Melhorias no design das informações de pagamento;

## 1.0.1 ##

* Melhorias no design das informações de pagamento;
* Correções de pequenos bugs;
* Inclusão para encaminhar até a página para upload de arquivos;
* Inclusão da página "Teste seu Pix".

## 1.0.0  ##

* Versão inicial do plugin.