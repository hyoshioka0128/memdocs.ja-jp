---
title: スクリプトを作成して実行する
titleSuffix: Configuration Manager
description: クライアント デバイスで PowerShell スクリプトを作成して実行します。
ms.date: 04/30/2020
ms.prod: configuration-manager
ms.technology: configmgr-app
ms.topic: conceptual
ms.assetid: cc230ff4-7056-4339-a0a6-6a44cdbb2857
author: mestew
ms.author: mstewart
manager: dougeby
ms.openlocfilehash: 2113baf43c377379a2a996c59fd13e55072cf898
ms.sourcegitcommit: d05b1472385c775ebc0b226e8b465dbeb5bf1f40
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2020
ms.locfileid: "82605186"
---
# <a name="create-and-run-powershell-scripts-from-the-configuration-manager-console"></a>Configuration Manager コンソールから PowerShell スクリプトを作成して実行する

*適用対象:Configuration Manager (Current Branch)*

<!--1236459-->
Configuration Manager には、PowerShell スクリプトを実行するための統合機能があります。 PowerShell には、高度な自動化されたスクリプトを作成できるという利点があります。PowerShell スクリプトは、多くの方が参加するコミュニティで理解され、共有されています。 このスクリプトを使用すると、ソフトウェアを管理するカスタム ツールを簡単に構築できます。また、大規模なジョブをより簡単に、一貫した方法で実行できるので、日常のタスクをすぐに完了できるようになります。  

> [!Note]  
> Configuration Manager では、このオプション機能は既定で無効です。 この機能は、使用する前に有効にする必要があります。 詳細については、「[Enable optional features from updates](../../core/servers/manage/install-in-console-updates.md#bkmk_options)」 (更新プログラムのオプション機能の有効化) を参照してください。<!--505213-->  


Configuration Manager でのこの統合により、*スクリプトの実行*機能を使用して以下を実行することができます。

- Configuration Manager と共に使用するようにスクリプトを作成して編集する。
- ロールとセキュリティ スコープを使用してスクリプトの使用法を管理する。 
- コレクションまたは個々のオンプレミスの管理対象 Windows PC でスクリプトを実行する。
- クライアント デバイスから高速に集計されたスクリプト結果を取得する。
- スクリプトの実行を監視し、スクリプトの出力からレポート結果を表示する。

> [!WARNING]
> - スクリプトを利用する場合は、目的を持って注意して使用することをお勧めします。 分離されたロールとスコープという、開発時に役立つ追加の保護策も組み込まれています。 意図しないスクリプトの実行を防ぐために、実行前にスクリプトが正しいことを検証し、信頼できる発行元のスクリプトであることを確認してください。 拡張文字や他の難読化を配慮し、スクリプトのセキュリティ保護について学習してください。 [PowerShell スクリプトのセキュリティの詳細情報](learn-script-security.md)
> - 特定のマルウェア対策ソフトウェアでは、誤って Configuration Manager 実行スクリプトまたは CMPivot 機能に対してイベントがトリガーされることがあります。 %Windir%\CCM\ScriptStore を除外することをお勧めします。これにより、マルウェア対策ソフトウェアでこれらの機能を許可し、干渉なしで実行することができます。

## <a name="prerequisites"></a>[前提条件]

- PowerShell スクリプトを実行するには、クライアントで PowerShell バージョン 3.0 以降を実行している必要があります。 ただし、実行するスクリプトに、より新しいバージョンの PowerShell の機能が含まれている場合、スクリプトを実行するクライアントがそのバージョンの PowerShell を実行している必要があります。
- Configuration Manager クライアントがスクリプトを実行するには、1706 リリース以降のクライアントを実行している必要があります。
- スクリプトを使用するには、適切な Configuration Manager のセキュリティ ロールのメンバーである必要があります。
- スクリプトをインポートおよび作成するには: **SMS スクリプト**への**作成**アクセス許可がアカウントに付与されている必要があります。
- スクリプトを承認または拒否するには: **SMS スクリプト**への**承認**アクセス許可がアカウントに付与されている必要があります。
- スクリプトを実行するには: **コレクション**への**スクリプトの実行**アクセス許可がアカウントに付与されている必要があります。

Configuration Manager セキュリティ ロールの詳細については、以下を参照してください。</br>
[スクリプトの実行のセキュリティ スコープ](#security-scopes)</br>
[スクリプトの実行のセキュリティ ロール](#bkmk_ScriptRoles)</br>
[ロール ベース管理の基礎](../../core/understand/fundamentals-of-role-based-administration.md)。

## <a name="limitations"></a>制限事項

現在、スクリプトの実行は以下をサポートしています。

- スクリプト言語:PowerShell
- パラメーターの型: 整数、文字列、リスト。


>[!WARNING]
>パラメーターを使用する場合、潜在的な PowerShell インジェクション攻撃のリスクが伴うことに注意してください。 パラメーター入力を検証するための正規表現の使用や、定義済みパラメーターの使用など、さまざまな緩和および回避方法があります。 通常は PowerShell スクリプトのシークレットに含めないことをお勧めします (パスワードなしなど)。 [PowerShell スクリプトのセキュリティの詳細情報](learn-script-security.md) <!--There are external tools available to validate your PowerShell scripts such as the [PowerShell Injection Hunter](https://www.powershellgallery.com/packages/InjectionHunter/1.0.0) tool. -->


## <a name="run-script-authors-and-approvers"></a>スクリプトの実行の作成者と承認者

スクリプトの実行では、スクリプトの実装と実行に別のロールとして*スクリプト作成者*と*スクリプト承認者*の概念を使用しています。 作成者ロールと承認者ロールが分かれているので、スクリプトの実行という強力なツールの重要なプロセス チェックが可能になります。 スクリプトの実行は許可するが、スクリプトの作成や承認は許可しない、追加の "*スクリプト ランナー*" ロールがあります。 「[スクリプトのセキュリティ ロールの作成](#bkmk_ScriptRoles)」を参照してください。

### <a name="scripts-roles-control"></a>スクリプト ロールの制御

既定では、ユーザーは自分が作成したスクリプトを承認できません。 スクリプトは強力で用途が広く、多くのデバイスに展開される可能性があるため、スクリプトを作成する人と、そのスクリプトを承認する人とでロールを分けることができます。 ロールを分けることで、監視なしのスクリプト実行に対してセキュリティ レベルがさらに高くなります。 テストの場合は、便宜的に二次的承認を無効にすることもできます。

### <a name="approve-or-deny-a-script"></a>スクリプトの承認または拒否

スクリプトを実行するには、*スクリプト承認者*ロールが事前に承認する必要があります。 スクリプトを承認するには、次の手順を実行します。

1. Configuration Manager コンソールで、 **[ソフトウェア ライブラリ]** をクリックします。
2. **[ソフトウェア ライブラリ]** ワークスペースで **[スクリプト]** をクリックします。
3. **[スクリプト]** リストで、承認または拒否するスクリプトを選択し、 **[ホーム]** タブの **[スクリプト]** グループで、 **[承認]/[拒否]** をクリックします。
4. **[スクリプトの承認/拒否]** ダイアログ ボックスで、スクリプトの **[承認]** または **[拒否]** を選択します。 必要に応じて、決定に関するコメントを入力します。  スクリプトを拒否すると、クライアント デバイス上でそのスクリプトを実行できません。 <br>
![スクリプト - 承認](./media/run-scripts/RS-approval.png)
1. ウィザードを完了します。 **[スクリプト]** リストの **[承認状態]** 列は、行った操作に応じて変わります。

### <a name="allow-users-to-approve-their-own-scripts"></a>ユーザーが自身のスクリプトを承認できるようにする

この承認は、主にスクリプト開発のテスト フェーズで使用されます。

1. Configuration Manager コンソールで、 **[管理]** をクリックします。
2. **[管理]** ワークスペースで **[サイトの構成]** を展開して、 **[サイト]** をクリックします。
3. サイトの一覧で、自分のサイトを選択し、 **[ホーム]** タブの **[サイト]** グループで **[階層設定]** をクリックします。
4. **[階層設定のプロパティ]** ダイアログ ボックスの **[全般]** タブで、 **[スクリプトの作成者には追加のスクリプト承認者が必要]** チェック ボックスをオフにします。

>[!IMPORTANT]
>ベスト プラクティスとして、スクリプト作成者に自分のスクリプトの承認を許可しないようにする必要があります。 これは、ラボ設定でのみ許可する必要があります。 運用環境でこの設定を変更する場合の影響を慎重に検討してください。

## <a name="security-scopes"></a>セキュリティ スコープ
  
スクリプトの実行は、Configuration Manager の既存の機能であるセキュリティ スコープを使用し、ユーザー グループを表すタグを割り当てることで、スクリプトの作成と実行を制御しています。 セキュリティ スコープの使用の詳細については、「[Configuration Manager のロール ベース管理の構成](../../core/servers/deploy/configure/configure-role-based-administration.md)」を参照してください。

## <a name="create-security-roles-for-scripts"></a><a name="bkmk_ScriptRoles"></a> スクリプトのセキュリティ ロールの作成
Configuration Manager では、スクリプトを実行するために使用される 3 つのセキュリティ ロールが既定で作成されません。 スクリプト ランナー、スクリプト作成者、スクリプト承認者のロールを作成するには、概説されている手順に従います。

1. Configuration Manager コンソールで、 **[管理]**  > **[セキュリティ]**  > **[セキュリティ ロール]** の順に移動します。
2. ロールを右クリックして、 **[コピー]** をクリックします。 コピーするロールには既にアクセス許可が割り当てられています。 必要なアクセス許可のみを使用するようにしてください。 
3. カスタム ロールの**名前**と**説明**を入力します。 
4. セキュリティ ロールに、以下に概説されているアクセス許可を割り当てます。  

### <a name="security-role-permissions"></a>セキュリティ ロールのアクセス許可  

**ロール名**:スクリプト ランナー  
- **説明**:これらのアクセス許可では、このロールで、以前他のロールで作成および承認されたスクリプトのみを実行できるようにします。  
- **アクセス許可:** 以下が **[はい]** に設定されていることを確認します。  

|カテゴリ|アクセス許可|状態|
|---|---|---|
|コレクション|スクリプトを実行する|はい|
|サイト|読み取り|はい|
|SMS スクリプト|読み取り|はい|


**ロール名**:スクリプトの作成者  
- **説明**:これらのアクセス許可では、このロールでスクリプトを作成できるようにしますが、承認したり、実行したりすることはできません。  
- **アクセス許可**:次のアクセス許可が設定されていることを確認します。
 
|カテゴリ|アクセス許可|状態|
|---|---|---|
|コレクション|スクリプトを実行する|いいえ|
|サイト|読み取り|はい|
|SMS スクリプト|作成|はい|
|SMS スクリプト|読み取り|はい|
|SMS スクリプト|削除|はい|
|SMS スクリプト|変更|はい|


**ロール名**:スクリプトの承認者  
- **説明**:これらのアクセス許可によってこのロールでスクリプトを承認することが可能になりますが、スクリプトを作成したり、実行したりすることはできません。  
- **アクセス許可:** 次のアクセス許可が設定されていることを確認します。  

|カテゴリ|アクセス許可|状態|
|---|---|---|
|コレクション|スクリプトを実行する|いいえ|
|サイト|読み取り|はい|
|SMS スクリプト|読み取り|はい|
|SMS スクリプト|承認|はい|
|SMS スクリプト|変更|はい|

     
**スクリプト作成者ロールの SMS スクリプト アクセス許可の例**  

 ![スクリプト作成者ロールの SMS スクリプト アクセス許可の例](./media/run-scripts/script_authors_permissions.png)


## <a name="create-a-script"></a>スクリプトの作成

1. Configuration Manager コンソールで、 **[ソフトウェア ライブラリ]** をクリックします。
2. **[ソフトウェア ライブラリ]** ワークスペースで **[スクリプト]** をクリックします。
3. **[ホーム]** タブの **[作成]** グループで、 **[スクリプトの作成]** をクリックします。
4. **スクリプトの作成**ウィザードの **[スクリプト]** ページで、次の設定を構成します。
    - **[スクリプト名]** : スクリプトの名前を入力します。 同じ名前の複数のスクリプトを作成できますが、重複する名前を使用すると、Configuration Manager コンソールで必要なスクリプトを見つけるのがより困難になります。
    - **[スクリプト言語]** : 現時点では、PowerShell スクリプトのみがサポートされています。
    - **[インポート]** : PowerShell スクリプトをコンソールにインポートします。 スクリプトは **[スクリプト]** フィールドに表示されます。
    - **[クリア]** : [スクリプト] フィールドから現在のスクリプトを削除します。
    - **[スクリプト]** : 現在インポートされたスクリプトが表示されます。 必要に応じて、このフィールドでスクリプトを編集できます。
5. ウィザードを完了します。 新しいスクリプトが **[承認を待っています]** の状態で **[スクリプト]** リストに表示されます。 このスクリプトをクライアント デバイスで実行するには、先にそのスクリプトを承認する必要があります。 

> [!IMPORTANT]
> スクリプトの実行機能を使用する場合は、デバイスのリブートや Configuration Manager エージェントの再起動のスクリプトを実行することは避けてください。 そうすると、リブート状態が続くことになりかねません。 必要な場合は、クライアント通知機能に対する拡張機能を使用して、デバイスの再起動を有効にできます。 [[再起動を保留しています] 列](../../core/clients/manage/manage-clients.md#restart-clients)は、再起動が必要なデバイスを特定するのに役立ちます。 
> <!--SMS503978  -->

## <a name="script-parameters"></a>スクリプト パラメーター

スクリプトにパラメーターを追加すると、作業の柔軟性が向上します。 最大 10 個のパラメーターを含めることができます。 ここでは、スクリプトの実行機能の現在の機能とスクリプト パラメーター (*文字列*、*整数*データ型) の概要について説明します。 プリセット値の一覧も掲載します。 スクリプトにサポートされないデータ型が含まれている場合は、警告を受け取ります。

**[スクリプトの作成]** ダイアログの **[スクリプト]** で **[スクリプト パラメーター]** をクリックします。

スクリプトの各パラメーターには独自のダイアログがあり、詳細や検証を追加できます。 スクリプト内に既定のパラメーターがある場合、それはパラメーターの UI に列挙され、設定することができます。 Configuration Manager では、スクリプトが直接変更されることはないため、既定値は上書きされません。 これは、"事前入力済みの提案された値" が UI で提供されるが、Configuration Manager によって実行時に "既定の" 値に対するアクセスが提供されることはない、と考えることができます。 適切な既定値を含むようスクリプトを編集することによって、これを回避できます。 <!--17694323-->

>[!IMPORTANT]
> パラメーター値に単一引用符を含めることはできません。 </br></br>
> 単一引用符が含まれるパラメーター値または単一引用符で囲まれているパラメーター値は、スクリプトに正しく渡されないという、既知の問題があります。 スクリプト内に空白が含まれる既定のパラメーター値を指定するときは、代わりに二重引用符を使用します。 **スクリプト**を作成または実行する際に既定のパラメーター値を指定するときは、値にスペースが含まれているかどうかに関係なく、二重引用符または単一引用符で既定値を囲む必要はありません。

### <a name="parameter-validation"></a>パラメーターの検証

スクリプト内の各パラメーターには、そのパラメーターに検証を追加するための **[Script Parameter Properties]\(スクリプト パラメーター プロパティ\)** ダイアログがあります。 検証を追加した後に、その検証を満たしていないパラメーターの値を入力すると、エラーが発生します。

#### <a name="example-firstname"></a>例:*FirstName*

この例では、文字列パラメーター *FirstName* のプロパティを設定できます。

![スクリプトのパラメーター - 文字列](./media/run-scripts/RS-parameters-string.png)


**[スクリプト パラメーターのプロパティ]** ダイアログの検証セクションでは、次のフィールドを使用できます。

- **[最小の長さ]** - *[FirstName]* フィールドの最小の文字数。
- **[最大の長さ]** - *[FirstName]* フィールドの最大の文字数。
- **[RegEx]** - *正規表現 (Regular Expression)* の短縮形。 正規表現の使用方法については、次のセクション「*正規表現による検証を使用する*」をご覧ください。
- **[カスタム エラー]** - システム検証エラー メッセージの代わりに使う、独自のカスタム エラー メッセージを追加するのに役立ちます。

#### <a name="using-regular-expression-validation"></a>正規表現による検証を使用する

正規表現はプログラミングのコンパクトな形式で、エンコードされた検証に対して文字列をチェックします。 たとえば、 *[RegEx]* フィールドに `[^A-Z]` を指定することによって、 *[FirstName]* フィールド内の大文字アルファベット文字の有無をチェックすることができます。

このダイアログ ボックスの正規表現処理は、.NET Framework でサポートされています。 正規表現の使用方法の詳細については、「[.NET の正規表現](https://docs.microsoft.com/dotnet/standard/base-types/regular-expressions)」および「[正規表現言語](https://docs.microsoft.com/dotnet/standard/base-types/regular-expression-language-quick-reference)」をご覧ください。


## <a name="script-examples"></a>スクリプトの例

この機能で利用する可能性があるスクリプトの例をいくつか紹介します。

### <a name="create-a-new-folder-and-file"></a>新しいフォルダーとファイルの作成

このスクリプトでは、入力した名前に基づいて、新しいフォルダーを作成し、そのフォルダー内にファイルを作成します。

``` PowerShell
Param(
[Parameter(Mandatory=$True)]
[string]$FolderName,
[Parameter(Mandatory=$True)]
[string]$FileName
)

New-Item $FolderName -type directory
New-Item $FileName -type file
```

### <a name="get-os-version"></a>OS バージョンの取得

このスクリプトは WMI を使用してコンピューターに OS バージョンを照会します。

``` PowerShell
Write-Output (Get-WmiObject -Class Win32_operatingSystem).Caption
```

## <a name="edit-or-copy-powershell-scripts"></a><a name="bkmk_psedit"></a> PowerShell スクリプトの編集またはコピー
<!--3705507-->
" *(バージョン 1902 で導入されました)* "  
**スクリプトの実行**機能で使用される既存の PowerShell スクリプトを **[編集]** または **[コピー]** できます。 変更する必要があるスクリプトを再作成するのではなく、直接編集できるようになりました。 どちらのアクションでも、新しいスクリプトを作成するときと同じウィザード エクスペリエンスが使われます。 スクリプトを編集またはコピーするときに、Configuration Manager では承認状態が保持されません。

> [!Tip]  
> クライアント上でアクティブに実行されているスクリプトは編集しないでください。 元のスクリプトの実行が完了せず、このようなクライアントから意図した結果が得られない可能性があります。  

### <a name="edit-a-script"></a>スクリプトの編集

1. **[ソフトウェア ライブラリ]** ワークスペースの **[スクリプト]** ノードにアクセスします。
1. 編集するスクリプトを選択し、リボンの **[編集]** をクリックします。 
1. スクリプトを変更または再インポートするには、 **[スクリプトの詳細]** ページを使用します。
1. **[次へ]** をクリックして **[概要]** を表示し、編集が終了したときに **[閉じる]** をクリックします。

### <a name="copy-a-script"></a>スクリプトのコピー

1. **[ソフトウェア ライブラリ]** ワークスペースの **[スクリプト]** ノードにアクセスします。
1. コピーするスクリプトを選択し、リボンの **[コピー]** をクリックします。
1. **[スクリプト名]** フィールドでスクリプトの名前を変更し、必要に応じて追加の編集を行います。
1. **[次へ]** をクリックして **[概要]** を表示し、編集が終了したときに **[閉じる]** をクリックします。


## <a name="run-a-script"></a>[スクリプトの実行]

スクリプトが承認されたら、1 つのデバイスまたはコレクションに対してそのスクリプトを実行できます。 スクリプトの実行を開始すると、それは 1 時間以内にタイムアウトする優先度の高いシステムを使用してすばやく起動されます。 そしてスクリプトの結果は、状態メッセージ システムを使用して返されます。

スクリプトのターゲットのコレクションを選択するには、以下の操作を行います。

1. Configuration Manager コンソールで、 **[資産とコンプライアンス]** をクリックします。
2. [資産とコンプライアンス] ワークスペースで **[デバイス コレクション]** をクリックします。
3. **[デバイス コレクション]** リストで、スクリプトを実行するデバイスのコレクションをクリックします。
4. コレクションを選択し、 **[スクリプトの実行]** をクリックします。
5. **スクリプトの実行**ウィザードの **[スクリプト]** ページで、リストからスクリプトを選択します。 承認済みスクリプトのみが表示されます。
6. **[次へ]** をクリックして、ウィザードを完了します。

> [!IMPORTANT]
> ターゲット デバイスの電源が 1 時間のあいだ切れているなどの理由で、スクリプトが実行されない場合は、再実行する必要があります。

### <a name="target-machine-execution"></a>ターゲット コンピューターの実行

スクリプトは、対象となるクライアントの*システム* アカウントまたは*コンピューター* アカウントとして実行されます。 このアカウントのネットワーク アクセスは制限されています。 スクリプトによるリモート システムおよびリモートの場所へのアクセスは、その点を考慮して準備する必要があります。

## <a name="script-monitoring"></a>スクリプトの監視

デバイスのコレクション上でスクリプトの実行を開始した後は、次の手順で操作を監視します。 実行中のスクリプトをリアルタイムで監視することができ、後で特定のスクリプトの実行に関する状態と結果に戻ることができます。 スクリプトの状態データは、[[期限切れのクライアント操作を削除] メンテナンス タスク](../../core/servers/manage/reference-for-maintenance-tasks.md)、またはスクリプト削除の一部としてクリーンアップされます。<br>

![スクリプト モニター - スクリプトの実行ステータス](./media/run-scripts/RS-monitoring-three-bar.png)

1. Configuration Manager コンソールで、 **[監視]** をクリックします。
2. **[監視]** ワークスペースで、 **[スクリプトのステータス]** をクリックします。
3. **[スクリプトのステータス]** リストには、クライアント デバイスで実行した各スクリプトの結果が表示されます。 スクリプトの終了コード **0** は、通常、スクリプトが正常に実行されたことを示します。

 
   ![スクリプト モニター - 切り詰められたスクリプト](./media/run-scripts/Script-monitoring-truncated.png)

## <a name="script-output"></a>スクリプトの出力

スクリプトの結果を [ConvertTo-Json](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-json) コマンドレットにパイプすることにより、JSON 形式を使用してクライアントからスクリプトの出力を返します。 JSON 形式では、読み取り可能なスクリプトの出力が一貫して返されます。 出力としてオブジェクトを返さないスクリプトの場合、ConvertTo-Json コマンドレットでは出力が単純な文字列に変換され、JSON ではなくそれがクライアントから返されます。  

- 不明な結果を取得するスクリプトや、クライアントがオフラインだったスクリプトは、グラフやデータ セットには表示されません。 <!--507179-->
- 大きいスクリプトの出力は 4 KB に切り捨てられるため、そのような出力が返されないようにしてください。 <!--508488-->
- スクリプトで列挙オブジェクトを文字列値に変換して、JSON 形式で適切に表示されるようにしてください。 <!--508377-->

   ![列挙オブジェクトを文字列値に変換する](./media/run-scripts/enum-tostring-JSON.png)

詳細なスクリプトの出力を、生の形式または構造化された JSON 形式で表示できます。 この書式設定を行うと、出力の読み取りと分析が容易になります。 スクリプトによって有効な JSON 形式のテキストが返される場合、または [ConvertTo-Json](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-json) PowerShell コマンドレットを使用して出力を JSON に変換できる場合は、 **[JSON 形式の出力]** または **[未加工で出力]** として詳細出力を表示します。 それ以外の場合は、 **[スクリプトの出力]** が唯一のオプションです。

### <a name="example-script-output-is-convertible-to-valid-json"></a>例:スクリプトの出力を有効な JSON に変換できる

コマンド: `$PSVersionTable.PSVersion`  

``` Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      16299  551
```

### <a name="example-script-output-isnt-valid-json"></a>例:スクリプト出力が有効な JSON ではない

コマンド: `Write-Output (Get-WmiObject -Class Win32_OperatingSystem).Caption`  

``` Output
Microsoft Windows 10 Enterprise
```

## <a name="log-files"></a>ログ ファイル

- クライアントでは、既定で C:\Windows\CCM\logs に次のログがあります。  
  - **Scripts.log**  
  - **CcmMessaging.log**  

- MP では、既定で C:\SMS_CCM\Logs に次のログがあります。
  - **MP_RelayMsgMgr.log**  

- サイト サーバーでは、既定で C:\Program Files\Configuration Manager\Logs に次のログがあります。
  - **SMS_Message_Processing_Engine.log**

## <a name="see-also"></a>関連項目

- [Configuration Manager に対してロール ベース管理を構成する](../../core/servers/deploy/configure/configure-role-based-administration.md)
- [ロール ベース管理の基礎](../../core/understand/fundamentals-of-role-based-administration.md)
