---
title: Microsoft Intune - Azure でのデバイス プロファイルのトラブルシューティング | Microsoft Docs
description: プロファイルの変更がユーザーまたはデバイスに適用されない、新しいポリシーがデバイスにプッシュされるのにかかる時間、複数のポリシーがあるときに適用される設定、プロファイルが消去または削除された場合に起こること、その他 Microsoft Intune でのデバイス ポリシーとプロファイルに関する一般的な質問と回答。
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/18/2020
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 67d0d271b5befc65ad286a8da6e00f647973d73d
ms.sourcegitcommit: 7f17d6eb9dd41b031a6af4148863d2ffc4f49551
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "79364462"
---
# <a name="common-questions-issues-and-resolutions-with-device-policies-and-profiles-in-microsoft-intune"></a>Microsoft Intune でのデバイス ポリシーとプロファイルの一般的な質問、問題と解決策

Intune でデバイス プロファイルとポリシーを使用する場合の、一般的な質問に対する回答を得ます。 この記事には、チェックイン時刻の間隔のリストもあり、競合などの詳細についても提供します。

## <a name="why-doesnt-a-user-get-a-new-profile-when-changing-a-password-or-passphrase-on-an-existing-wi-fi-profile"></a>既存の Wi-Fi プロファイルでパスワードやパスフレーズを変更すると、ユーザーに新しいプロファイルが与えられません。

企業の Wi-Fi プロファイルを作成し、それをグループに展開し、パスワードを変更し、プロファイルを保存します。 プロファイルが変更されたときに一部のユーザーが新しいプロファイルを取得できないことがあります。

この問題を軽減するには、ゲスト Wi-Fi を設定します。 企業の Wi-Fi に問題がある場合は、ユーザーがゲスト Wi-Fi に接続できます。 自動的に接続設定を有効にしてください。 ゲスト Wi-Fi プロファイルをすべてのユーザーに展開します。

追加の推奨事項:  

- 接続先の Wi-Fi ネットワークがパスワードまたはパスフレーズを受け取る場合は、Wi-Fi ルーターに直接接続できることを確認します。 iOS/iPadOS デバイスでテストできます。
- Wi-Fi エンドポイント (Wi-Fi ルーター) に正常に接続されたら、SSID と使用した資格情報 (この値はパスワードまたはパスフレーズです) をメモします。
- 事前共有キー フィールドに SSID と資格情報 (パスワードまたはパスフレーズ) を入力します。 
- ユーザー数が限られているテスト グループに展開します。IT チームに限定することをお勧めします。 
- iOS/iPadOS デバイスを Intune に同期します。 登録していない場合、登録します。 
- (最初の手順で説明した) 同じ Wi-Fi エンドポイントへの接続をもう一度テストします。
- より大きなグループにロールアウトし、最後には、展開が求められる組織の全ユーザーに展開します。 

## <a name="how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned"></a>デバイスへのポリシー、プロファイル、アプリの割り当て後にそれらが取得されるまでどれくらいの時間がかかりますか。

Intune では、Intune サービスにチェックインするようデバイスに通知されます。 通知の時間は即時から数時間後までさまざまです。 これらの通知時間は、プラットフォームによっても異なります。

最初の通知後、デバイスがチェックインしてポリシーまたはプロファイルを取得しなかった場合、Intune ではさらに 3 回試行されます。 電源がオフになっていたり、ネットワークから切断されていたりするようなオフライン デバイスでは、通知が受信されない可能性があります。 この場合、デバイスでは次回のスケジュールされた Intune サービスへのチェックインでポリシーまたはプロファイルを取得します。 同様のことが、準拠している状態から準拠していない状態に移行するデバイスを含む、コンプライアンス違反の確認に適用されます。

"**推定**" 頻度:

| プラットフォーム | 更新サイクル|
| --- | --- |
| iOS/iPadOS | 約 8 時間ごと |
| macOS | 約 8 時間ごと |
| Android | 約 8 時間ごと |
| デバイスとして登録された Windows 10 PC | 約 8 時間ごと |
| Windows Phone | 約 8 時間ごと |
| Windows 8.1 | 約 8 時間ごと |

最近登録したデバイスでは、コンプライアンス、コンプライアンス違反、構成のチェックインの実行頻度が高くなります。次のように "**推定**" されています。

| プラットフォーム | 頻度 |
| --- | --- |
| iOS/iPadOS | 1 時間まで 15 分ごと、その後は約 8 時間ごと |  
| macOS | 1 時間まで 15 分ごと、その後は約 8 時間ごと | 
| Android | 15 分まで 3 分ごと、その後の 2 時間は 15 分ごと、その後は約 8 時間ごと | 
| デバイスとして登録された Windows 10 PC | 15 分まで 3 分ごと、その後の 2 時間は 15 分ごと、その後は約 8 時間ごと | 
| Windows Phone | 15 分まで 5 分ごと、その後の 2 時間は 15 分ごと、その後は約 8 時間ごと | 
| Windows 8.1 | 15 分まで 5 分ごと、その後の 2 時間は 15 分ごと、その後は約 8 時間ごと | 

ユーザーはいつでもポータル サイト アプリを開き、 **[設定]**  >  **[同期]** でポリシーまたはプロファイルの更新をすぐに確認できます。

## <a name="what-actions-cause-intune-to-immediately-send-a-notification-to-a-device"></a>どのような操作を行うと Intune は通知をデバイスにすぐに送信しますか。

ポリシー、プロファイル、またはアプリの割り当て (または割り当て解除)、更新、削除など、通知をトリガーするさまざまなアクションがあります。 これらのアクションの時間はプラットフォームによって異なります。

デバイスは、チェックインを指示する通知を受け取ったとき、またはスケジュールされたチェックイン時に Intune にチェックインします。 ロック、パスコードのリセット、アプリ、プロファイルまたはポリシーの割り当てなどの操作でデバイスまたはユーザーを対象とする場合、チェックインしてこれらの更新プログラムを受信するように Intune からデバイスにすぐに通知されます。

ポータル サイト アプリの連絡先情報の修正など、他の変更ではデバイスへの通知はすぐに行われません。

ポリシーまたはプロファイルの設定は、チェックインのたびに適用されます。 [Windows 10 MDM ポリシー更新のブログ投稿](https://www.petervanderwoude.nl/post/windows-10-mdm-policy-refresh/)を参照することをお勧めします。

## <a name="if-multiple-policies-are-assigned-to-the-same-user-or-device-how-do-i-know-which-settings-gets-applied"></a>複数のポリシーが同じユーザーまたはデバイスに割り当てられる場合、どの設定が適用されるのかどうすればわかりますか。

2 つ以上のポリシーが同じユーザーまたはデバイスに割り当てられる場合、適用される設定は個々の設定レベルで行われます。

- コンプライアンス ポリシーの設定は、常に構成プロファイルの設定よりも優先されます。

- 別のコンプライアンス ポリシーの同じ設定についてコンプライアンス ポリシーを評価する場合、最も制限の厳しいコンプライアンス ポリシーの設定が適用されます。

- 構成ポリシーの設定が別の構成ポリシーの設定と競合する場合、Intune にこの競合が表示されます。 これらの競合は手動で解決します。

## <a name="what-happens-when-app-protection-policies-conflict-with-each-other-which-one-is-applied-to-the-app"></a>アプリ保護ポリシー同士が競合している場合はどうなりますか。 どのポリシーがアプリに適用されますか。

競合している値は、リセットする前の PIN の試行などの、番号入力フィールドを*除き*、アプリ保護ポリシーで使用可能な最も制限の厳しい設定になっています。 番号入力フィールドは、推奨設定のオプションを使用して MAM ポリシーを作成した場合と同じ値に設定されます。

競合は、2 つのプロファイル設定が同じ場合に発生します。 たとえば、コピー/貼り付けの設定以外は同じ MAM ポリシーを 2 つ構成したとします。 この場合、コピー/貼り付けの設定は最も厳しい値に設定されますが、残りの設定は構成したとおりに適用されます。

ポリシーがアプリに展開され、有効になります。 2 番目のポリシーが展開されます。 このシナリオでは、最初のポリシーが優先され、適用されたままになります。 2 つ目のポリシーは競合を示しています。 両方を同時に適用する (つまり、優先されるポリシーがない) 場合、両方が競合の状態になります。 競合する設定は、最も制限の厳しい値に設定されます。

## <a name="what-happens-when-iosipados-custom-policies-conflict"></a>iOS/iPadOS カスタム ポリシーが競合するとどうなりますか。

Intune は Apple 構成ファイルのペイロードまたはカスタム Open Mobile Alliance Uniform Resource Identifier (OMA-URI) ポリシーを評価しません。 配信メカニズムとしてのみ機能します。

カスタム ポリシーを割り当てるときは、構成した設定がコンプライアンス、構成、または他のカスタム ポリシーと競合していないことを確認してください。 カスタム ポリシーとその設定が競合している場合、設定がランダムに適用されます。

## <a name="what-happens-when-a-profile-is-deleted-or-no-longer-applicable"></a>プロファイルが削除された場合または適用できなくなった場合はどうなりますか。

プロファイルを削除したり、プロファイルを持つグループからデバイスを削除したりすると、次に示されているように、デバイスからプロファイルと設定が削除されます。

- Wi-Fi、VPN、証明書、電子メールのプロファイル:これらのプロファイルは、すべてのサポートされる登録デバイスから削除されます。
- 他のすべてのプロファイルの種類:  

  - **Windows および Android デバイス**:設定はデバイスから削除されません
  - **Windows Phone 8.1 デバイス**:次の設定は削除されます。  
  
    - モバイル デバイスのロックを解除するパスワードを要求する
    - 単純なパスワードを許可する
    - パスワードの最小文字数
    - 必要なパスワードの種類
    - パスワードの有効期限 (日)
    - パスワードの履歴を記憶する
    - デバイスをワイプするまでの連続サインイン エラーの数
    - パスワードが必要になるまでの非アクティブ状態の時間 (分)
    - 必要なパスワードの種類 - 文字セットの最小数
    - カメラを許可する
    - モバイル デバイスの暗号化を要求する
    - リムーバブル記憶域を許可する
    - Web ブラウザーを許可する
    - アプリケーション ストアを許可する
    - 画面のキャプチャを許可する
    - 位置情報を許可する
    - Microsoft アカウントを許可する
    - コピーと貼り付けを許可する
    - Wi-Fi テザリングを許可する
    - 無料 Wi-Fi スポットへの自動接続を許可する
    - Wi-Fi スポットの報告を許可する
    - ワイプを許可する
    - Bluetooth を許可する
    - NFC を許可する
    - Wi-Fi を許可する

  - **iOS/iPadOS**:以下を除き、すべての設定が削除されます。
  
    - 音声通話ローミングを許可する
    - データ ローミングを許可する
    - ローミング中の自動同期を許可する

## <a name="i-changed-a-device-restriction-profile-but-the-changes-havent-taken-effect"></a>デバイス制限プロファイルを変更しましたが、変更内容が適用されていません

Windows Phone デバイスから、MDM または EAS を使用して設定されたセキュリティ ポリシーのセキュリティを一度設定した後に緩くすることはできません。 たとえば、**パスワードの最小文字数** を 8 に設定してから、 4 に減らしてみます。 より制限の厳しいプロファイルが既にデバイスに適用されています。

プロファイルを安全度の低い値に変更するには、セキュリティ ポリシーをリセットします。 たとえば、Windows 8.1 で、デスクトップを右からスワイプして、 **[設定]**  >  **[コントロール パネル]** の順に選択します。 **[ユーザー アカウント]** アプレットを選択します。 左側のナビゲーション メニューの下部に、 **[セキュリティ ポリシーのリセット]** リンクがあります。 これを選択し、 **[ポリシーのリセット]** を選択します。

Android、Windows Phone 8.1 以降、iOS/iPadOS、Windows 10 などのその他の MDM デバイスでは、制限の緩いプロファイルを適用するにはいったんデバイスを削除して、Intune に再登録しなければならない場合があります。

## <a name="some-settings-in-a-windows-10-profile-return-not-applicable"></a>Windows 10 プロファイルの一部の設定で "適用できません" が返される

Windows 10 デバイスの一部の設定では、"適用できません" と表示される場合があります。 この場合、その特定の設定が、デバイスで実行されているバージョンまたはエディションの Windows でサポートされていません。 このメッセージは、次の理由で表示される可能性があります。

- 設定が、デバイス上の現在のオペレーティング システム (OS) のバージョンではなく、新しいバージョンの Windows でのみ使用可能である。
- 設定が、特定の Windows エディションまたは特定の SKU (Home、Professional、Enterprise、Education など) でのみに使用可能である。

さまざまな設定に対するバージョンと SKU 要件の詳細については、[構成サービス プロバイダー (CSP) のリファレンス](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference)に関するページを参照してください。

## <a name="next-steps"></a>次のステップ

さらに支援が必要ですか? 「[Microsoft Intune のサポートを受ける方法](../fundamentals/get-support.md)」を参照してください。