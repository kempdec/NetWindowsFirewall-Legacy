# NetWindowsFirewall Legacy

NetWindowsFirewall Legacy é uma micro biblioetca com métodos auxiliares para gerenciar o Firewall do Windows para
.NET Framework 4.8.

A biblioteca COM `NetFwTypeLib` é usada para gerenciar o Firewall do Windows pelo **NetWindowsFirewall**.

[**Veja NetWindowsFirewall para .NET 8 ou superior**](https://github.com/kempdec/NetWindowsFirewall)

## Instalação

Instale a biblioteca a partir do NuGet.

``` powershell
Install-Package KempDec.NetWindowsFirewall.Legacy
```

## Como usar

Você pode usar a instância estática, obtida através de `NetWindowsFirewall.Instance`, como no exemplo abaixo:

``` csharp
var ipAddress = IPAddress.Parse("127.0.0.1");

// Adiciona uma regra de bloqueio (de entrada) para o endereço de IP "127.0.1" no Firewall do Windows.
NetWindowsFirewall.Instance.AddBlockInIpRule($"IP {ipAddress} bloqueado", ipAddress);

// Adiciona uma regra de bloqueio (de saída) para o endereço de IP "127.0.0.1" no Firewall do Windows.
NetWindowsFirewall.Instance.AddBlockOutIpRule($"IP {ipAddress} bloqueado", ipAddress);
```

Ou você pode usar a partir de uma nova instância criada manualmente:

``` csharp
var ipAddress = IPAddress.Parse("127.0.0.1");
var netWindowsFirewall = new NetWindowsFirewall();

// Adiciona uma regra de bloqueio (de entrada) para o endereço de IP "127.0.1" no Firewall do Windows.
netWindowsFirewall.AddBlockInIpRule($"IP {ipAddress} bloqueado", ipAddress);

// Adiciona uma regra de bloqueio (de saída) para o endereço de IP "127.0.0.1" no Firewall do Windows.
netWindowsFirewall.AddBlockOutIpRule($"IP {ipAddress} bloqueado", ipAddress);
```

## Colaboração

Ajude-nos a deixar a biblioteca de código aberto cada vez melhor, criando um **pull request**.

## Autores

- [**KempDec**](https://github.com/kempdec) - Mantedora do projeto de código aberto.
- [**Vinícius Lima**](https://github.com/viniciusxdl) - Desenvolvedor .NET C#.

## Licença

[MIT](https://github.com/kempdec/NetWindowsFirewall/blob/main/LICENSE)
