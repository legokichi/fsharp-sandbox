
* https://code.visualstudio.com/docs/other/dotnet
* https://qiita.com/usagi/items/ee8300f897d7b85f6956
* http://fsharp.org/use/linux/
* https://ardalis.com/how-to-add-a-nuget-package-using-dotnet-add
* https://github.com/Azure/azure-sdk-for-media-services
* https://github.com/Azure/azure-sdk-for-media-services-extensions
* satoshitoriumifuturestandar.onmicrosoft.com
* https://mediaservicehackfest2017.restv2.japaneast.media.azure.net/api/
* https://rest.media.azure.net
* https://qiita.com/acple@github/items/e80bef939583fc2b0e5e
* F1o9p3Nrst4UoSH092k7O6rXT3rvyq8OAP2v6SEYxhs=
* .NET Standard - API 仕様
* .NET Framework - windows runtime - net46 = netstandard1.3
* .NET Core - crossplatform - netcoreapp1.0 = netstandard1.6
* Mono - Linux, Mac (.NET Framework互換)
* Xamarin - Mono を使った IDE. Android, iOS対応
* NuGet - .net 系 のpackage インストーラ & インフラ (nuget.org) npm みたいなやつ
* dotnet cli - visual studio 相当のことができる cli。ビルドとか。
* foo.csproj - .Net 系共通の設定ファイル。かつての.net core のproject.jsonは死んだ。
* NETStandard.Library - std. .NET Standard の仕様だけ。実装はランタイム依存。
* Microsoft.NETCore.App - ランタイム
* netcoreapp1.0/netstandard1.0/net46 - ランタイムの種類とかバージョンとか。Target Framework Moniker(TFM)なる実行環境の種別。nugetがプラットフォームを解釈するのにつかう
* netstandard1.0 - .Net 標準 API に対応したライブラリ
* net46/net451/ - windows での .NET Framework で動くライブラリ。
* netcoreapp1.0 - .net core 環境でのライブラリ。
* https://docs.microsoft.com/ja-jp/dotnet/core/
* https://docs.microsoft.com/ja-jp/dotnet/fsharp/get-started/get-started-command-line

```sh
curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-xenial-prod xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
sudo apt-get update
sudo apt-get install dotnet-sdk-2.0.2
sudo apt-get install dotnet-dev-1.0.4
dotnet --version

sudo apt-get update
sudo apt-get install mono-complete fsharp nuget
sudo apt-get install dotnet-sdk-2.0.2


#dotnet new console
dotnet new console -lang F#
dotnet restore
dotnet build
dotnet run
dotnet add package windowsazure.mediaservices.extensions
dotnet add package NETStandard.Library Microsoft.NETCore.App

dotnet new sln -o FSNetCore
cd FSNetCore
dotnet new lib -lang F# -o src/Library
dotnet new lib -lang F# -o src/Main
dotnet sln add src/Library/Library.fsproj
dotnet sln add src/Main/main.fsproj
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
dotnet add src/Main/Main.fsproj reference src/Library/Library.fsproj
```

* https://docs.microsoft.com/en-us/rest/api/media/operations/rest-api-functions
* REST API - https://docs.microsoft.com/en-us/rest/api/media/operations/mediaprocessor