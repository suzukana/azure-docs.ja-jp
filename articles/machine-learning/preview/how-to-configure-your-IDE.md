---
title: "IDE を使用する Azure Machine Learning Workbench の構成方法  | Microsoft Docs"
description: "IDE を使用する Azure Machine Learning Workbench の構成方法のガイドです。"
services: machine-learning
author: svankam
ms.author: svankam
manager: mwinkle
ms.reviewer: garyericson, jasonwhowell, mldocs
ms.service: machine-learning
ms.workload: data-services
ms.topic: article
ms.date: 09/05/2017
ms.openlocfilehash: 4e18a413a0559b1ddebecf1b29722d21ef35c337
ms.sourcegitcommit: 6699c77dcbd5f8a1a2f21fba3d0a0005ac9ed6b7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/11/2017
---
# <a name="how-to-configure-azure-machine-learning-workbench-to-work-with-an-ide"></a>IDE を使用する Azure Machine Learning Workbench の構成方法 

Azure Machine Learning Workbench は、一般的な Python IDE (統合開発環境) と動作するように構成することができます。 この構成を行うことで、データの準備、コードの作成、追跡と操作化の実行などを行き来する、スムーズなデータ サイエンス開発エクスペリエンスを可能にします。 現在サポートされている IDE は次のとおりです。
- Microsoft Visual Studio Code 
- JetBrain PyCharm 

## <a name="configure-workbench"></a>ワークベンチの構成
1. アプリの左上隅にある **[ファイル]** メニューをクリックします。 
2. ポップアップから **[Configure Project IDE]\(プロジェクト IDE の構成\)** オプションを選択します。 
3. **[名前]** フィールドに、`VS Code` または `PyCharm` で入力します (名前は任意)。
4. **[実行パス]** に、IDE 実行可能ファイルの場所 (実行可能ファイル名と拡張子を含む完全パス) を入力します。

### <a name="default-install-path-for-visual-studio-code"></a>Visual Studio Code の既定のインストール パス  

* Windows 32-bit - `C:\Program Files (x86)\Microsoft VS Code\Code.exe`
* Windows 64-bit - `C:\Program Files\Microsoft VS Code\Code.exe`
* macOS - アプリのパス (例: `/Applications/Visual Studio Code.app`) を選択すると、アプリ側で残りのパスを追加します。 実行可能ファイルの完全パスは、既定では `/Applications/Visual Studio Code.app/Contents/Resources/app/bin/code` です。 VS Code で `Shell Command: Install 'code' command in PATH` コマンドを実行した場合、その VS Code スクリプトは `/usr/local/bin/code` でも参照することができます。

### <a name="default-install-path-for-pycharm"></a>PyCharm の既定のインストール パス 

* Windows 32-bit - `C:\Program Files (x86)\JetBrains\PyCharm Community Edition 2017.2.1\bin\pycharm.exe`。 
* Windows 64-bit - `C:\Program Files\JetBrains\PyCharm Community Edition 2017.2.1\bin\pycharm64.exe`。
* macOS - アプリのパス (例: /Applications/PyCharm CE.app) を選択すると、アプリ側で残りのパスを追加します。 実行可能ファイルの完全パスは、既定では `/Applications/PyCharm CE.app/Contents/MacOS/pycharm` です。 また、bin フォルダー `/usr/local/bin/charm`にも PyCharm があります。

## <a name="open-project-in-ide"></a>IDE でプロジェクトを開く 
構成が完了したら、Azure Machine Learning Workbench の **[ファイル]** メニューを開いてから **[プロジェクトを開く (<IDE_Name>)]** をクリックして、Azure Machine Learning プロジェクトを開くことができます。 この操作により、構成済みの IDE 内に現在のアクティブなプロジェクトが開かれます。 _注: プロジェクトに参加していない場合は、**[プロジェクトを開く (<IDE_Name>)]** は無効になります。_

## <a name="configuring-the-integrated-terminal-in-visual-studio-code"></a>Visual Studio Code での統合ターミナルの構成

### <a name="windows"></a>Windows 
既定のシェルが、PowerShell ではなく cmd になるようにオーバーライドしました。 **[プロジェクトを開く (<IDE_Name>)]** をクリックすると、プロンプトが表示されます。 

_シェル: `C:\windows\System32\cmd.exe` (ワークスペース設定として定義されている) をターミナルで起動することを許可しますか?_

`yes` と応答し、シェルが Azure ML Workbench コマンドライン インターフェイスとシームレスに動作するよう構成することを許可します。

### <a name="mac"></a>Mac
Mac で Visual Studio Code の統合ターミナルを使用して `az` コマンドを実行するには、`PATH` を、`terminal.integrated.env.osx` キーでプロジェクトの `.vscode/settings.json` ファイルの `PATH` と同じ値になるように手動で設定する必要があります。 ターミナルで次のコマンドを実行すると、これを行うことができます: `PATH=<PATH in .vscode/settings>`
