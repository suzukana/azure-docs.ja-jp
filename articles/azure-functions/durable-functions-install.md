---
title: "Durable Functions 拡張機能とサンプルをインストールする - Azure"
description: "Azure Functions、ポータル開発、または Visual Studio 開発用に Durable Functions 拡張機能をインストールする方法を説明します。"
services: functions
author: cgillum
manager: cfowler
editor: 
tags: 
keywords: 
ms.service: functions
ms.devlang: multiple
ms.topic: article
ms.tgt_pltfrm: multiple
ms.workload: na
ms.date: 09/29/2017
ms.author: azfuncdf
ms.openlocfilehash: 58f23406f20f6b0e75ec65197e4cebb6e4e788ac
ms.sourcegitcommit: b07d06ea51a20e32fdc61980667e801cb5db7333
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/08/2017
---
# <a name="install-the-durable-functions-extension-and-samples-azure-functions"></a>Durable Functions 拡張機能とサンプルをインストールする (Azure Functions)

Azure Functions の [Durable Functions](durable-functions-overview.md) 拡張機能は、NuGet パッケージ [Microsoft.Azure.WebJobs.Extensions.DurableTask](https://www.nuget.org/packages/Microsoft.Azure.WebJobs.Extensions.DurableTask) に提供されます。 この記事では、次の開発環境用のパッケージとサンプル セットをインストールする方法を示します。

* Visual Studio 2017 (推奨) 

* Azure ポータル

## <a name="visual-studio-2017"></a>Visual Studio 2017

現時点では、Durable Functions を使用するアプリを開発するための 最適なエクスペリエンスは Visual Studio が提供します。  開発した関数はローカルに実行でき、Azure に発行することもできます。 空のプロジェクトまたはサンプル関数セットから始めることができます。

### <a name="prerequisites"></a>前提条件

* [Visual Studio の最新バージョン](https://www.visualstudio.com/downloads/)のインストール (バージョン 15.3 以降)。 **[Azure の開発]** ワークロードをセットアップ オプションに含めます。

### <a name="start-with-sample-functions"></a>サンプル関数から始める

1. [Visual Studio 用のサンプル アプリの .zip ファイル](https://azure.github.io/azure-functions-durable-extension/files/VSDFSampleApp.zip)をダウンロードします。 NuGet 参照はサンプル プロジェクトに既に含まれているため、追加する必要はありません。
2. [Azure Storage Emulator](https://docs.microsoft.com/azure/storage/storage-use-emulator) バージョン 5.2 以降をインストールして実行します。 または、*local.appsettings.json* ファイルを実際の Azure Storage の接続文字列で更新できます。
3. Visual Studio 2017 でプロジェクトを開きます。 
4. このサンプルの実行方法については、[関数チェーン - Hello シーケンス サンプル](durable-functions-sequence.md)に記載されている手順から始めてください。 サンプルは、ローカルで実行することも Azure に発行することもできます。

### <a name="start-with-an-empty-project"></a>空のプロジェクトから始める
 
サンプルから始めるのと同じ手順に従いますが、*.zip* ファイルをダウンロードする代わりに次の手順に従います。

1. Function App プロジェクトを作成します。
2. 次の NuGet パッケージ参照を *.csproj* ファイルに追加します。

   ```xml
   <PackageReference Include="Microsoft.Azure.WebJobs.Extensions.DurableTask" Version="1.0.0-beta" />
   ```
   
## <a name="visual-studio-code"></a>Visual Studio Code

Visual Studio Code では、すべての主要なプラットフォーム (Windows、macOS、Linux) をカバーするローカルの開発エクスペリエンスを提供します。  開発した関数はローカルに実行でき、Azure に発行することもできます。 空のプロジェクトまたはサンプル関数セットから始めることができます。

### <a name="prerequisites"></a>前提条件

* [Visual Studio Code の最新バージョン](https://code.visualstudio.com/Download)をインストールします 

* 「[Azure Functions をローカルでコーディングしてテストする](https://docs.microsoft.com/azure/azure-functions/functions-run-local)」の「Azure Functions Core Tools のインストール」の手順に従います

    >[!IMPORTANT]
    > Azure Functions クロス プラットフォーム ツールが既にある場合は、使用可能な最新バージョンに更新します。

*  [Azure Storage Emulator](https://docs.microsoft.com/azure/storage/storage-use-emulator) バージョン 5.2 以降をインストールして実行します。 または、*local.appsettings.json* ファイルを実際の Azure Storage の接続で更新できます。 


### <a name="start-with-sample-functions"></a>サンプル関数から始める

1. [Durable Functions リポジトリ](https://github.com/Azure/azure-functions-durable-extension.git)を複製します。
2. マシン上の [C# スクリプトのサンプル フォルダー](https://github.com/Azure/azure-functions-durable-extension/tree/master/samples/csx)に移動します。 
3. コマンド プロンプト/ターミナル ウィンドウで次のコマンドを実行して、Azure Functions Durable Extension をインストールします。

    ```bash
    func extensions install -p Microsoft.Azure.WebJobs.Extensions.DurableTask -v 1.1.0-beta2
    ```
4. Azure Storage Emulator を実行するか、*local.appsettings.json* ファイルを実際の Azure Storage の接続文字列で更新します。
3. Visual Studio Code でプロジェクトを開きます。 
5. このサンプルの実行方法については、[関数チェーン - Hello シーケンス サンプル](durable-functions-sequence.md)に記載されている手順から始めてください。 サンプルは、ローカルで実行することも Azure に発行することもできます。
6. コマンド プロンプト/ターミナルで次のコマンドを実行して、プロジェクトを開始します:
    ```bash
    func host start
    ```

### <a name="start-with-an-empty-project"></a>空のプロジェクトから始める
 
1. コマンド プロンプト/ターミナルで、関数アプリをホストするフォルダーに移動します。
2. コマンド プロンプト/ターミナル ウィンドウで次のコマンドを実行して、Azure Functions Durable Extension をインストールします。

    ```bash
    func extensions install -p Microsoft.Azure.WebJobs.Extensions.DurableTask -v 1.1.0-beta2
    ```
3. 次のコマンドを実行して Function App プロジェクトを作成します。

    ```bash
    func init
    ``` 
4. Azure Storage Emulator を実行するか、*local.appsettings.json* ファイルを実際の Azure Storage の接続文字列で更新します。
5. 次に、次のコマンドを実行して新しい関数を作成し、ウィザードの手順に従います。

    ```bash
    func new
    ```
    >[!IMPORTANT]
    > 現時点で Durable Function テンプレートは使用できませんが、サポートされるオプションのいずれかで開始して、コードを変更できます。 参照用に、[オーケストレーション クライアント](https://github.com/Azure/azure-functions-durable-extension/tree/master/samples/csx/HttpStart)、[オーケストレーション トリガー](https://github.com/Azure/azure-functions-durable-extension/tree/master/samples/csx/E1_HelloSequence)、[アクティビティ トリガー](https://github.com/Azure/azure-functions-durable-extension/tree/master/samples/csx/E1_HelloSequence)のサンプルを使用してください。

6. Visual Studio Code でプロジェクト フォルダーを開き、テンプレート コードを修正して続行します。 
7. コマンド プロンプト/ターミナルで次のコマンドを実行して、プロジェクトを開始します:
    ```bash
    func host start
    ```

## <a name="azure-portal"></a>Azure ポータル

必要に応じて、Durable Functions 開発で Azure ポータルを使用できます。

### <a name="create-an-orchestrator-function"></a>オーケストレーター関数を作成する

1. [functions.azure.com](https://functions.azure.com/signin) で関数アプリを新規作成します。

2. 関数アプリを [2.0 ランタイム バージョン](functions-versions.md)を使用するように構成します。

3. **[カスタム関数を作成する]** を選択して新しい関数を作成します。

4. **[言語]** を **[C#]** に、**[シナリオ]** を **[Durable Functions]**  に変更し、**[Durable Functions Http Starter - C#]\(Durable Functions Http スターター - C#\)** テンプレートを選択します。

5. **[拡張機能がインストールされていません]** の下の **[インストール]** をクリックして、NuGet.org から拡張機能をダウンロードします。 

6. インストールが完了したら、オーケストレーション クライアント関数 (**[Durable Functions Http Starter - C#]\(Durable Functions Http スターター - C#\)** テンプレートを選択して作成される **"HttpStart"**) の作成に進みます。

7. ここで、オーケストレーション関数 **"HelloSequence"** を **[Durable Functions Orchestrator - C#]\(Durable Functions オーケストレーター - C#\)** テンプレートから作成します。

8. 最後に呼び出される関数は、**[Durable Functions Activity - C#]\(Durable Functions アクティビティ - C#\)** テンプレートの **"Hello"** です。

9. **"HttpStart"** 関数に移動し、その URL をコピーします。

10. Postman または cURL を使用して、Durable Function を呼び出します。 テストする前に、URL **{functionName}** をオーケストレーター関数名 **HelloSequence** で置換します。  データは必要ありません、POST 動詞のみを使用します。 

    ```bash
    curl -X POST https://{your function app name}.azurewebsites.net/api/orchestrators/HelloSequence
    ```

11. 次に、**"statusQueryGetUri"** エンドポイントを呼び出し、Durable Function の現在の状態を確認します

    ```json
        {
            "runtimeStatus": "Running",
            "input": null,
            "output": null,
            "createdTime": "2017-12-01T05:37:33Z",
            "lastUpdatedTime": "2017-12-01T05:37:36Z"
        }
    ```

12. 状態が **"完了"**に変わるまで **"statusQueryGetUri"** エンドポイントの呼び出しを続けます 

    ```json
    {
            "runtimeStatus": "Completed",
            "input": null,
            "output": [
                "Hello Tokyo!",
                "Hello Seattle!",
                "Hello London!"
            ],
            "createdTime": "2017-12-01T05:38:22Z",
            "lastUpdatedTime": "2017-12-01T05:38:28Z"
        }
    ```

ご利用ありがとうございます。 最初の Durable Function が Azure Portal で稼働しています。

## <a name="next-steps"></a>次のステップ

> [!div class="nextstepaction"]
> [関数チェーンのサンプルを実行する](durable-functions-sequence.md)
