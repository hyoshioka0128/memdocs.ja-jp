---
title: Windows 10 MDM 用の Intune セキュリティ ベースラインの設定
titleSuffix: Microsoft Intune
description: Microsoft Intune で管理できる Windows MDM セキュリティ ベースラインの異なるバージョンの既定の設定と使用可能な設定を確認します。
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/06/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
zone_pivot_groups: windows-mdm-versions
ms.reviewer: laarrizz
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9cc2cf4531c2e2d7a2847ccdbce87c8b938a46d6
ms.sourcegitcommit: b90d51f7ce09750e024b97baf6950a87902a727c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2020
ms.locfileid: "86022230"
---
# <a name="windows-mdm-security-baseline-settings-for-intune"></a>Intune 用の Windows MDM セキュリティ ベースラインの設定

Windows 10 以降が実行されているデバイスに対して Microsoft Intune でサポートされる MDM セキュリティ ベースラインの設定を示します。 このベースラインの設定の既定値は、該当するデバイスに対する推奨される構成を表しています。 あるベースラインの既定値が、他のセキュリティ ベースラインの既定値や、このベースラインの他のバージョンの既定値と、一致しない場合があります。

- セキュリティ ベースラインを Intune で使用する方法と、セキュリティ ベースライン プロファイルでベースラインのバージョンをアップグレードする方法については、[セキュリティ ベースラインの使用](security-baselines.md)に関する記事をご覧ください。
- ベースラインの最新のバージョンは、**2019 年 5 月の MDM セキュリティ ベースライン**です

以前のバージョンからのこのバージョンのベースラインの変更点を確認するには、このベースラインの *[バージョン]* ウィンドウを表示すると使用可能になる [[ベースラインの比較]](../protect/security-baselines.md#compare-baseline-versions) 操作を使用します。

表示するベースラインのバージョンを選択してください。
<!-- Cookies might be required to enable some browsers to display the zone options -->

::: zone pivot="mdm-may-2019"

**2019 年 5 月の MDM セキュリティ ベースライン**:  
> [!NOTE]
> "*2019 年 5 月の MDM セキュリティ ベースライン*" は、2019 年 6 月に、(プレビューではなく) 一般提供としてリリースされました。 このバージョンのセキュリティ ベースラインでは、前のベースラインである "*2018 年 10 月の MDM セキュリティ ベースライン*" が置き換えられます。  2019 年 5 月のベースラインが使用可能になる前に作成されたプロファイルは、2019 年 5 月のバージョンの設定と値を反映するように更新されることはありません。  プレビュー テンプレートを基にして新しいプロファイルを作成することはできませんが、プレビュー テンプレートを基にして以前に作成したプロファイルを編集し、引き続き使用することはできます。

このバージョンのベースラインで、前のバージョンから変更された内容については、「[新しいテンプレートでの変更点](#whats-changed-in-the-new-template)」をご覧ください。

::: zone-end
::: zone pivot="mdm-preview"

**プレビュー - 2018 年 10 月の MDM セキュリティ ベースライン**:  
> [!NOTE]
> これは、2018 年 10 月にリリースされた MDM セキュリティ ベースラインのプレビュー バージョンです。 このプレビュー ベースラインは、(プレビューではなく) 一般提供の "*2019 年 5 月の MDM セキュリティ ベースライン*" テンプレートのリリースによって、2019 年 5 月に置き換えられました。 *2019 年 5 月の MDM セキュリティ ベースライン*が使用可能になる前に作成されたプロファイルは、2019 年 5 月の MDM セキュリティ ベースライン バージョンの設定と値を反映するように更新されることはありません。 プレビュー テンプレートを基にして新しいプロファイルを作成することはできませんが、プレビュー テンプレートを基にして以前に作成したプロファイルを編集し、引き続き使用することはできます。

::: zone-end
::: zone pivot="mdm-may-2019,mdm-preview"

## <a name="above-lock"></a>Above Lock (上でロック)

詳細については、Windows の「[Policy CSP - AboveLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-abovelock)」(ポリシー CSP - AboveLock) を参照してください。  

- **[Block display of toast notifications]\(トースト通知の表示をブロックする\)** :  
  このポリシー設定を使用すると、アプリの通知がロック画面に表示されないようにすることができます。 このポリシー設定を有効にした場合、アプリ通知はロック画面に表示されません。 このポリシー設定を無効にした場合、または構成しなかった場合、ロック画面に通知を表示するアプリをユーザーが選択できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067101)

  **既定値**:はい

::: zone-end
::: zone pivot="mdm-may-2019"

- **[ロック画面から音声でアプリをアクティブ化する]** :  
  **既定値**:無効

::: zone-end
::: zone pivot="mdm-may-2019,mdm-preview"

## <a name="app-runtime"></a>[アプリ実行時]

詳細については、Windows の「[Policy CSP - AppRuntime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-appruntime)」(ポリシー CSP - AppRuntime) を参照してください。

- **[Microsoft accounts optional for Windows Store apps]\(Windows ストア アプリで Microsoft アカウントの省略を許可する\)** :  
  このポリシー設定を使用すると、サインインにアカウントを必要とする Windows ストア アプリに対して Microsoft アカウントを省略可能にするかどうかを制御できます。 このポリシーは、それがサポートされている Windows ストア アプリにのみ影響します。 このポリシー設定を有効にした場合、通常はサインインに Microsoft アカウントが必要な Windows ストア アプリではなく、エンタープライズ アカウントを使用してユーザーがサインインできるようになります。 このポリシー設定を無効にした場合、または構成しなかった場合、ユーザーは Microsoft アカウントを使用してサインインする必要があります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067104)
  
  **既定値**:Enabled

## <a name="application-management"></a>アプリケーション管理

詳細については、Windows の「[Policy CSP - ApplicationManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement)」(ポリシー CSP - ApplicationManagement) を参照してください。

::: zone-end
::: zone pivot="mdm-may-2019"

- **インストールに対するユーザー制御をブロックする**:  
  このポリシー設定を使用すると、ユーザーは、通常であればシステム管理者のみが使用できるインストール オプションを変更できます。 このポリシー設定を有効にした場合、Windows インストーラーの一部のセキュリティ機能がバイパスされます。 このポリシーを使用すると、通常はセキュリティ違反のため強制的に中止されるインストールを完了させることができます。 このポリシー設定を無効にした場合、または構成しなかった場合、Windows インストーラーでは、通常システム管理者のみに許可されているインストールのオプション (たとえば、ファイルのインストール先ディレクトリの指定) をユーザーが変更することはできません。 ユーザーによる保護されたオプションの変更がインストール パッケージで許可されていることを Windows インストーラーが検出した場合、インストールは停止され、メッセージが表示されます。 これらのセキュリティ機能は、ユーザーは拒否されるディレクトリにアクセスできる特権セキュリティ コンテキストでインストール プログラムが実行されている場合にのみ動作します。 このポリシー設定は、制限の少ない環境向けに設計されています。 ソフトウェアのインストールが妨げられるインストール プログラムでのエラーを回避するために使用できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067060)

  **既定値**:はい

- **昇格された特権による MSI アプリのインストールをブロックする**:  
  このポリシー設定では、システムにプログラムをインストールするときに管理者特権のアクセス許可を使用するよう、Windows インストーラーに指示されます。

  - "*このポリシー設定を有効にすると*"、特権がすべてのプログラムに適用されます。 通常、これらの特権はユーザー (デスクトップ上で提供されている) に割り当てられたプログラム、コンピューター (自動的にインストールされている) に割り当てられたプログラム、またはコントロール パネルの [プログラムの追加と削除] で利用できるプログラム用に予約されています。 このプロファイル設定を使用すると、ユーザーは、制限の厳しいコンピューター上のディレクトリを含め、ユーザーが表示または変更するアクセス許可を持っていない可能性があるディレクトリへのアクセスを必要とするプログラムをインストールできます。

  - "*このポリシー設定を無効にした場合、または構成しなかった場合*"、システム管理者から配布または提供されていないプログラムのインストール時に、システムによってユーザーの現在のアクセス許可が適用されます。 注:このポリシー設定はどちらも、[コンピューターの構成] および [ユーザーの構成] フォルダーにあります。 このポリシー設定を有効にするには、両方のフォルダーで有効にする必要があります。 注意:熟練ユーザーは、このポリシー設定で付与されるアクセス許可を利用して、特権を変更し、制限されているファイルやフォルダーに永続的にアクセスすることができます。 このポリシー設定の [ユーザーの構成] バージョンのセキュリティ保護は必ずしも安全ではありません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067134)

  **既定値**:はい

::: zone-end
::: zone pivot="mdm-preview,mdm-may-2019"

- **[Block game DVR (desktop only)]\(ゲーム DVR をブロックする (デスクトップのみ)\)**  
  ゲームの録画とブロードキャストを許可するかどうか設定します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067056)

  **既定値**:はい

## <a name="auto-play"></a>Auto Play (自動再生)

詳細については、Windows の「[Policy CSP - Autoplay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-autoplay)」(ポリシー CSP - Autoplay) を参照してください。

- **[Auto play default auto run behavior]\(自動再生の既定の自動実行の動作\)**  
  この設定は、自動実行コマンドの既定の動作に影響します。 自動実行コマンドは、autorun.inf ファイルに保存されており、インストール プログラムやその他のルーチンを開始できます。 これを*有効*にすると、管理者は Windows Vista 以降を実行するデバイスの自動実行の既定の動作を変更することができます。 次の動作に設定できます: a) 自動実行コマンドを完全に無効にする、b) 自動実行コマンドを自動的に実行する Windows Vista 以前の動作に戻す。 *無効*または*未構成*にすると、Windows Vista 以降を実行するコンピューターで自動実行コマンドを実行するかユーザーはたずねられます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067133)

  **既定値**:Do not execute (実行しない)

- **[Auto play mode]\(自動再生のモード\)**  
  このポリシー設定を使用すると、自動再生機能を無効にできます。 自動再生では、ドライブにメディアを挿入するとすぐにドライブからの読み取りが開始されます。 その結果、プログラムのセットアップ ファイルとオーディオ メディアの音楽がすぐに開始されます。 Windows XP SP2 以前では、自動再生は、フロッピー ディスク ドライブなどのリムーバブル ドライブ (CD-ROM ドライブは除く) およびネットワーク ドライブ上では既定で無効になっています。 Windows XP SP2 以降では、Zip ドライブや一部の USB 大容量記憶装置など、リムーバブル ドライブでも自動再生が有効になっています。 このポリシー設定を有効にした場合、自動再生は、CD-ROM ドライブとリムーバブル メディア ドライブで、またはすべてのドライブで無効になります。 このポリシー設定では、追加のドライブの種類での自動再生は無効になります。 この設定を使用して、既定で無効になっているドライブ上の自動再生を有効にすることはできません。 このポリシー設定を無効にした場合、または構成しなかった場合、自動再生が有効になります。 注:このポリシー設定は [コンピューターの構成] フォルダーおよび [ユーザーの構成] フォルダーにあります。 ポリシー設定が競合する場合、[コンピューターの構成] でのポリシーが [ユーザーの構成] でのポリシー設定より優先されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2066793)

  **既定値**:無効

- **[Block auto play for non-volume devices]\(ボリューム以外のデバイスの自動再生をブロックする\)** :  
  このポリシー設定では、カメラや電話などの MTP デバイスでの自動再生が許可されません。 このポリシー設定を有効にした場合、カメラや電話などの MTP デバイスの自動再生が許可されません。 このポリシー設定を無効にした場合、または構成しなかった場合、ボリューム以外のデバイスに対する自動再生が有効になります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067106)

  **既定値**:Enabled

## <a name="bitlocker"></a>BitLocker

詳細については、Windows ドキュメントの「[ポリシー CSP - BitLocker](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bitlocker)」を参照してください。

- **[BitLocker removable drive policy]\(Bitlocker のリムーバブル ドライブのポリシー\)**  
  このポリシー設定は、暗号化方法および暗号化強度を制御するために使用します。 このポリシーの値は、BitLocker が暗号化に使用する暗号化強度を決定します。 企業では、セキュリティを強化するために、暗号化のレベルを制御したい場合があります (AES-256 は AES-128 よりも強力です)。 この設定を有効にした場合は、固定データ ドライブやオペレーティング システム ドライブ、リムーバブル データ ドライブのそれぞれに、暗号化アルゴリズムとキーの暗号化強度を構成できます。 固定ドライブやオペレーティング システム ドライブには、XTS-AES アルゴリズムを使用することをお勧めします。 リムーバブル ドライブには、Windows 10 バージョン 1511 以降を実行していないその他のデバイスでドライブを使用する場合は、AES-CBC 128 ビットまたは AES-CBC 256 ビットを使用する必要があります。 ドライブが既に暗号化されているか、暗号化が進行中の場合は、暗号化の種類を変更しても影響はありません。 このような場合、このポリシー設定は無視されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067140)

  BitLocker リムーバブル ドライブ ポリシーの場合は、次の設定を構成します。

::: zone-end
::: zone pivot="mdm-may-2019"

  - **[Block write access to removable data-drives not protected by BitLocker]\(BitLocker で保護されていないリムーバブル データドライブへの書き込みアクセスをブロックする\)** :  
    **既定値**:はい

::: zone-end
::: zone pivot="mdm-preview"

  - **[Require encryption for write access]\(書き込みアクセス用に暗号化が必要\)** :  
    **既定値**:はい

- **[BitLocker removable drive policy]/(Bitlocker のリムーバブル ドライブのポリシー\)**  
  このポリシー設定は、暗号化方法および暗号化強度を制御するために使用します。 このポリシーの値は、BitLocker が暗号化に使用する暗号化強度を決定します。 企業では、セキュリティを強化するために、暗号化のレベルを制御したい場合があります (AES-256 は AES-128 よりも強力です)。 この設定を有効にした場合は、固定データ ドライブやオペレーティング システム ドライブ、リムーバブル データ ドライブのそれぞれに、暗号化アルゴリズムとキーの暗号化強度を構成できます。 固定ドライブやオペレーティング システム ドライブには、XTS-AES アルゴリズムを使用することをお勧めします。 リムーバブル ドライブには、Windows 10 バージョン 1511 以降を実行していないその他のデバイスでドライブを使用する場合は、AES-CBC 128 ビットまたは AES-CBC 256 ビットを使用する必要があります。 ドライブが既に暗号化されているか、暗号化が進行中の場合は、暗号化の種類を変更しても影響はありません。 このような場合、このポリシー設定は無視されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067140)

  BitLocker リムーバブル ドライブ ポリシーの場合は、次の設定を構成します。

  - **[Require encryption for write access]\(書き込みアクセス用に暗号化が必要\)** :  
    **既定値**:はい  

  - **[暗号化方法]** :  
    **既定値**:AES 256bit CBC  

- **[BitLocker fixed drive policy]\(BitLocker の固定ドライブのポリシー\)**  
  このポリシー設定は、暗号化方法および暗号化強度を制御するために使用します。 このポリシーの値は、BitLocker が暗号化に使用する暗号化強度を決定します。 企業では、セキュリティを強化するために、暗号化のレベルを制御したい場合があります (AES-256 は AES-128 よりも強力です)。 この設定を有効にした場合は、固定データ ドライブやオペレーティング システム ドライブ、リムーバブル データ ドライブのそれぞれに、暗号化アルゴリズムとキーの暗号化強度を構成できます。 固定ドライブやオペレーティング システム ドライブには、XTS-AES アルゴリズムを使用することをお勧めします。 リムーバブル ドライブには、Windows 10 バージョン 1511 以降を実行していないその他のデバイスでドライブを使用する場合は、AES-CBC 128 ビットまたは AES-CBC 256 ビットを使用する必要があります。 ドライブが既に暗号化されているか、暗号化が進行中の場合は、暗号化の種類を変更しても影響はありません。 このような場合、このポリシー設定は無視されます。

  BitLocker 固定ドライブ ポリシーの場合は、次の設定を構成します。

  - **[暗号化方法]** :  
    **既定値**:AES 256bit XTS  

- **[BitLocker system drive policy]\(BitLocker のシステム ドライブのポリシー\)**  
  このポリシー設定は、暗号化方法および暗号化強度を制御するために使用します。 このポリシーの値は、BitLocker が暗号化に使用する暗号化強度を決定します。 企業では、セキュリティを強化するために、暗号化のレベルを制御したい場合があります (AES-256 は AES-128 よりも強力です)。 この設定を有効にした場合は、固定データ ドライブやオペレーティング システム ドライブ、リムーバブル データ ドライブのそれぞれに、暗号化アルゴリズムとキーの暗号化強度を構成できます。 固定ドライブやオペレーティング システム ドライブには、XTS-AES アルゴリズムを使用することをお勧めします。 リムーバブル ドライブには、Windows 10 バージョン 1511 以降を実行していないその他のデバイスでドライブを使用する場合は、AES-CBC 128 ビットまたは AES-CBC 256 ビットを使用する必要があります。 ドライブが既に暗号化されているか、暗号化が進行中の場合は、暗号化の種類を変更しても影響はありません。 このような場合、このポリシー設定は無視されます。

  BitLocker システム ドライブ ポリシーの場合は、次の設定を構成します。

  - **[暗号化方法]** :  
    **既定値**:AES 256bit XTS

::: zone-end
::: zone pivot="mdm-preview,mdm-may-2019"

## <a name="browser"></a>ブラウザー

詳細については、Windows の「[Policy CSP - Browser](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser)」(ポリシー CSP - Browser) を参照してください。

- **[Require SmartScreen for Microsoft Edge]\(Microsoft Edge で SmartScreen が必要\)**  
  Microsoft Edge では、(オンになった) Microsoft Defender SmartScreen を使用して、フィッシング詐欺にあう可能性や悪意のあるソフトウェアから既定でユーザーを保護しています。 また、既定では、ユーザーは Microsoft Defender SmartScreen を無効 (オフ) にできません。 このポリシーを有効にすると、Microsoft Defender SmartScreen がオフになり、ユーザーがそれをオンにできないようになります。 ユーザーが Microsoft Defender SmartScreen のオンとオフを選択できるようにする場合は、このポリシーを構成しないでください。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067029)

  **既定値**:はい

- **[Block malicious site access]\(悪意のあるサイトへのアクセスをブロックする\)** :  
  既定では、Microsoft Edge では、悪意のある可能性があるサイトに関する Microsoft Defender SmartScreen の警告をユーザーがバイパス (無視) して、サイトに進むことができます。 このポリシーを使用すると、ユーザーが警告をバイパスし、サイトに進めないように Microsoft Edge を構成できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067040)
  
  **既定値**:はい
  
- **[Block unverified file download]\(確認されていないファイルのダウンロードをブロックする\)** :  
  既定では、Microsoft Edge では、悪意のある可能性があるファイルに関する Microsoft Defender SmartScreen の警告をユーザーがバイパス (無視) して、未確認のファイルのダウンロードを続行することができます。 このポリシーを有効にすると、ユーザーはこの警告をバイパスして、確認されていないファイルをダウンロードできなくなります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067023)
  
  **既定値**:はい
  
- **[Block Password Manager]\(Password Manager をブロックする\)** :  
  Microsoft Edge で既定で Password Manager が自動的に使用されることによって、ユーザーはパスワードをローカルで管理できるようになります。 このポリシーを無効にすると、Microsoft Edge で Password Manager が使用されなくなります。 ユーザーに Password Manager を使用してローカルでパスワードを保存および管理させる場合には、このポリシーは設定しないでください。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067128)
  
  **既定値**:はい
  
- **[Prevent user from overriding certificate errors]\(ユーザーが証明書のエラーをオーバーライドできないようにする\)** :  
  このポリシー設定を有効にすると、Internet Explorer での閲覧が中断される Secure Sockets Layer/Transport Layer Security (SSL/TLS) 証明書のエラー ("期限切れ"、"失効"、"名前の不一致" など) を、ユーザーは無視できなくなります。 このポリシー設定を有効にすると、ユーザーは閲覧を継続できません。 このポリシー設定を無効にするか、構成しない場合、ユーザーは証明書エラーを無視して閲覧を継続できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067126)
  
  **既定値**:はい

## <a name="connectivity"></a>接続

詳細については、Windows の「[Policy CSP - Connectivity](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity)」(ポリシー CSP - Connectivity) を参照してください。

- **[Block Internet download for web publishing and online ordering wizards]\(Web 発行およびオンライン注文ウィザードのインターネット ダウンロードをブロックする\)** :  
  このポリシー設定では、Web 発行およびオンライン注文のウィザード用にプロバイダーの一覧を Windows でダウンロードする必要があるかどうかを指定します。 これらのウィザードを使用すると、ユーザーは、オンライン ストレージや写真印刷などのサービスを提供する会社の一覧から選択できるようになります。 既定では、レジストリで指定されているプロバイダーに加えて、Windows の Web サイトからダウンロードされたプロバイダーが表示されます。 このポリシー設定を有効にした場合、プロバイダーはダウンロードされず、ローカル レジストリにキャッシュされたサービス プロバイダーのみが表示されます。 このポリシー設定を無効にした場合、または構成しなかった場合、ユーザーが Web 発行ウィザードまたはオンライン注文ウィザードを使用するときに、プロバイダーの一覧がダウンロードされます。 レジストリでサービス プロバイダーを指定する方法などの詳細については、Web 発行ウィザードおよびオンライン注文ウィザードのドキュメントを参照してください。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067136)
  
  **既定値**:Enabled

::: zone-end
::: zone pivot="mdm-may-2019"

- **[UNC パスへのセキュリティで保護されたアクセスを構成]** :  
  このポリシー設定では、UNC パスへのセキュリティ保護されたアクセスが構成されます。 このポリシーを有効にすると、追加のセキュリティ要件が満たされた後でのみ、指定した UNC パスへのアクセスが許可されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067243)

  **既定値**:追加のセキュリティ要件を満たした後にのみ、指定された UNC パスへのアクセスを許可するように Windows を構成します。

  *[追加のセキュリティ要件を満たした後にのみ、指定された UNC パスへのアクセスを許可するように Windows を構成します]* を選択した場合は、 *[強化された UNC パスの一覧]* を構成できます。

  - **[強化された UNC パスの一覧]** :  
    追加のセキュリティ フラグとサーバー パスを指定するには、 **[追加]** を選択します。

::: zone-end
::: zone pivot="mdm-preview,mdm-may-2019"

- **[Block downloading of print drivers over HTTP]\(プリンター ドライバーの HTTP 経由でのダウンロードをブロックする\)**  
  このポリシー設定では、このクライアントに HTTP 経由での印刷ドライバー パッケージのダウンロードを許可するかどうかを指定します。 HTTP 経由の印刷をセットアップするには、付属していないドライバーを HTTP 経由でダウンロードする必要があります。 注:このポリシー設定が有効になっている場合でも、クライアントはイントラネットやインターネットのプリンターに HTTP 経由で出力できます。 ローカルにインストールされていないドライバーのダウンロードのみを禁止します。 この設定を有効にした場合、プリンター ドライバーは HTTP 経由でダウンロードできません。 このポリシー設定を無効にした場合、または構成しなかった場合、ユーザーは HTTP 経由でプリンター ドライバーをダウンロードできます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067141)
  
  **既定値**:Enabled

## <a name="credentials-delegation"></a>資格情報の委任

詳細については、Windows の「[Policy CSP - CredentialsDelegation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-credentialsdelegation)」(ポリシー CSP - CredentialsDelegation) を参照してください。

- **[Remote host delegation of non-exportable credentials]\(リモート ホストでエクスポートできない資格情報を委任する\)**  
  リモート ホストでは、エクスポートできない資格情報を委任できます。 資格情報の委任を使用する場合、エクスポート可能なバージョンの資格情報がデバイスからリモート ホストに提供されます。これにより、ユーザーはリモート ホスト上の攻撃者に資格情報が盗まれるというリスクにさらされます。 このポリシー設定を有効にした場合、ホストは制限付き管理モードまたは Remote Credential Guard モードをサポートします。 このポリシー設定を無効にするか、構成しなかった場合、制限付き管理モードと Remote Credential Guard モードはサポートされません。 ユーザーは常に資格情報をホストに渡す必要があります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067103)
  
  **既定値**:Enabled

## <a name="credentials-ui"></a>Credentials UI (資格情報 UI)

詳細については、Windows の「[Policy CSP - CredentialsUI](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-credentialsui)」(ポリシー CSP - CredentialsUI) を参照してください。

- **[Enumerate administrators]\(管理者の列挙\)** :  
  このポリシー設定により、ユーザーが実行中のアプリケーションの昇格を試みたときに、管理者アカウントが表示されるかどうかを制御します。 既定では、ユーザーが実行中のアプリケーションの昇格を試みたときに、管理者アカウントは表示されません。 このポリシー設定を有効にした場合、PC 上のローカル管理者アカウントがすべて表示され、ユーザーがその 1 つを選択して、正しいパスワードを入力できます。 このポリシー設定を無効にした場合、ユーザーは常に昇格させるユーザー名とパスワードを入力する必要があります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067021)

  **既定値**:無効

## <a name="data-protection"></a>データ保護

詳細については、Windows の「[Policy CSP - DataProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dataprotection)」(ポリシー CSP - DataProtection) を参照してください。

- **[Block direct memory access]\(ダイレクト メモリ アクセスをブロックする\)** :  
  このポリシー設定では、ユーザーが Windows にログインするまで、ホット プラグ可能なすべての PCI ダウンストリーム ポートへのダイレクト メモリ アクセス (DMA) をブロックできます。 ユーザーがログインすると、Windows はホット プラグ PCI ポートに接続されている PCI デバイスを列挙します。 ユーザーがコンピューターをロックするたびに、ユーザーが再ログインするまで、子デバイスが接続されていないホット プラグ PCI ポートで DMA がブロックされます。 コンピューターのロックが解除された際に既に列挙されていたデバイスは、取り外されるまで機能を維持します。 このポリシー設定は、BitLocker またはデバイスの暗号化が有効な場合にのみ適用されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067031)

  **既定値**:はい

## <a name="device-guard"></a>[Device Guard]

詳細については、Windows の「[Policy CSP - DeviceGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceguard)」(ポリシー CSP - DeviceGuard) を参照してください。

- **[Credential Guard を有効にする]** :  
  ユーザーはこの設定で、次回の再起動時に資格情報が保護されるよう、仮想化ベースのセキュリティで Credential Guard をオンにできます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067044)

  **既定値**:[UEFI ロックで有効化]

::: zone-end
::: zone pivot="mdm-may-2019"

- **[仮想化ベースのセキュリティ]** :  
  **既定値**:セキュア ブートを使用して VBS を有効にします

::: zone-end
::: zone pivot="mdm-preview,mdm-may-2019"

- **[Enable virtualization based security]\(仮想化ベースのセキュリティを有効にする\)** :  
  仮想化ベースのセキュリティ (VBS) を次の再起動時にオンにします。 仮想化ベースのセキュリティは、Windows ハイパーバイザーを使ってセキュリティ サービスのサポートを提供します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067066)
  
  **既定値**:はい

- **[Launch system guard]\(System Guard を起動する\)** :  
  **既定値**:Enabled

## <a name="device-installation"></a>デバイスのインストール

詳細については、Windows の「[Policy CSP - DeviceInstallation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceinstallation)」(ポリシー CSP - DeviceInstallation) を参照してください。

- **[Hardware device installation by device identifiers]\(デバイス識別子を使用してハードウェア デバイスをインストールする\)** :  
  このポリシー設定を使用すると、Windows によるインストールが禁止されているデバイスのプラグ アンド プレイ ハードウェア ID と互換 ID の一覧を指定できます。 このポリシー設定は、Windows がデバイスをインストールできるようにするその他のポリシー設定よりも優先されます。 このポリシー設定を有効にした場合、ハードウェア ID または互換性 ID が作成した一覧に含まれているデバイスはインストールできません。 リモート デスクトップ サーバーでこのポリシー設定を有効にした場合、ポリシー設定は、リモート デスクトップ クライアントからリモート デスクトップ サーバーへの指定されたデバイスのリダイレクトに影響します。 この設定を無効にした場合、または構成しなかった場合は、他のポリシー設定に従って、デバイスのインストールや更新が許可されるかどうかが決まります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2066794)

  **既定値**:Block hardware device installation (ハードウェア デバイスのインストールをブロックする)

  *[ハードウェア デバイスのインストールをブロックする]* を選択すると、次の設定が利用できます。

  - **[Remove matching hardware devices]\(一致するハードウェア デバイスを削除する\)** :  
    この設定は *[Hardware device installation by device identifiers]\(デバイス識別子でハードウェア デバイスをインストールする\)* が *[Block hardware device installation]\(ハードウェア デバイスのインストールをブロックする\)* に設定されているときのみ使用できます。

    **既定値**:はい

  - **[Hardware device identifiers that are blocked]\(ブロックされているハードウェア デバイス識別子\)** :  
    この設定は *[Hardware device installation by device identifiers]\(デバイス識別子でハードウェア デバイスをインストールする\)* が *[Block hardware device installation]\(ハードウェア デバイスのインストールをブロックする\)* に設定されているときのみ使用できます。

    **既定値**:はい

- **[Hardware device installation by setup classes]\(セットアップ クラスを使用してハードウェア デバイスをインストールする\)** :  
  このポリシー設定を使用すると、Windows によるインストールが禁止されているデバイス ドライバーのデバイス セットアップ クラス GUID (グローバル一意識別子) の一覧を指定できます。 このポリシー設定は、Windows がデバイスをインストールできるようにするその他のポリシー設定よりも優先されます。 このポリシー設定を有効にした場合、デバイス セットアップ クラス GUID が作成した一覧に含まれているデバイス ドライバーはインストールすることも更新することもできません。 リモート デスクトップ サーバーでこのポリシー設定を有効にした場合、ポリシー設定は、リモート デスクトップ クライアントからリモート デスクトップ サーバーへの指定されたデバイスのリダイレクトに影響します。 この設定を無効にした場合、または構成しなかった場合は、他のポリシー設定に従って、デバイスのインストールや更新が許可されるかどうかが決まります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067048)

  **既定値**:Block hardware device installation (ハードウェア デバイスのインストールをブロックする)

  *[ハードウェア デバイスのインストールをブロックする]* を選択すると、次の設定が利用できます。

  - **[Remove matching hardware devices]\(一致するハードウェア デバイスを削除する\)** :  
    この設定は *[Hardware device installation by setup classes]\(設定クラスでハードウェア デバイスをインストールする\)* が *[Block hardware device installation]\(ハードウェア デバイスのインストールをブロックする\)* に設定されているときのみ使用できます。

    **既定値**:*既定の構成はありません*

  - **[Hardware device identifiers that are blocked]\(ブロックされているハードウェア デバイス識別子\)** :  
    この設定は *[Hardware device installation by setup classes]\(設定クラスでハードウェア デバイスをインストールする\)* が *[Block hardware device installation]\(ハードウェア デバイスのインストールをブロックする\)* に設定されているときのみ使用できます。

    **既定値**:*既定の構成はありません*

## <a name="device-lock"></a>デバイスのロック

詳細については、Windows の「[Policy CSP - DeviceLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock)」(ポリシー CSP - DeviceLock) を参照してください。

- **[Prevent use of camera]\(カメラの使用を禁止する\)** :  
  PC 設定のロック画面カメラ切り替えスイッチを無効にし、ロック画面でカメラが起動されないようにします。 既定では、ユーザーはロック画面で使用可能なカメラを起動できます。 この設定を有効にした場合、ユーザーは、PC 設定でロック画面カメラへのアクセスを有効または無効にできず、ロック画面でカメラを呼び出せません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067052)

  **既定値**:Enabled

- **[Require password]\(パスワードを必須にする\)** :  
  デバイスのロックを有効にするかどうかを指定します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067049)  

  **既定値**:はい
  
  *[パスワードを要求する]* を *[はい]* に設定すると、次の設定が利用できます。

  - **[Password minimum character set count]\(パスワードの最小文字セット数\)** :  
    強力な PIN またはパスワードに必要な複合要素の種類 (大文字、小文字、数字、句読点) の数です。 PIN では、デスクトップおよびモバイル デバイスに対して次の動作が強制されます。1 - 数字のみ 2 - 数字と小文字が必要 3 - 数字、小文字、および大文字が必要。 デスクトップの Microsoft アカウントおよびドメイン アカウントではサポートされていません。 4 - 数字、小文字、大文字、および特殊文字が必要。 デスクトップではサポートされていません。  
    [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067055)

    **既定値**:3

  - **[デバイスがワイプされるまでのサインイン失敗回数]** :  
    デバイスがワイプされるまでに許容される認証の失敗回数。 値 0 を指定すると、デバイスのワイプ機能が無効になります。  
    [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067030)

    **既定値**:10  

  - **[パスワードの有効期限 (日数)]** :  
    パスワードの最大有効期間ポリシー設定によって、ユーザーがパスワードの変更を要求されるまでにパスワードを使用できる期間 (日数) が決まります。 1 から 999 までの日数の経過後にパスワードが期限切れになるように設定できます。また、日数を 0 に設定することでパスワードが期限切れにならないように指定することもできます。 [Maximum password age]\(パスワードの最大有効期間\) が 1 から 999 日の間である場合、パスワードの最小有効期間はパスワードの最大有効期間よりも短くする必要があります。 [Maximum password age]\(パスワードの最大有効期間\) が 0 に設定されている場合、[Minimum password]\(パスワードの最小有効期間\) には 0 から 998 日の値を設定できます。  
    [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067028)

    **既定値**:60

  - **[必須のパスワード]** :  
    必要な PIN またはパスワードの種類を決定します。  
    [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067027)

    **既定値**:英数字

  - **[パスワードの最小文字数]** :  
    [Minimum password length]\(最小のパスワードの長さ\) ポリシー設定によって、ユーザー アカウントのパスワードを構成できる最小文字数が決まります。 1 から 14 文字の値を設定できます。また、文字数を 0 に設定して、パスワードが必須ではないことを設定できます。  
    [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067024)

    **既定値**:8

  - **[Block simple passwords]\(単純なパスワードをブロックする\)** :  
    "1111" や "1234" などの PIN またはパスワードを許可するかどうかを指定します。 デスクトップでは、ピクチャ パスワードの使用も制御します。  
    [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067127)

    **既定値**:はい  
    *[Yes]\(はい\) に設定すると、単純なパスワードを使用できなくなります。*

  - **[以前のパスワードを再利用できないようにする]** :  
    使用できないパスワードを履歴にいくつ保存するかを指定します。 この値には、ユーザーの現在のパスワードも含まれます。 たとえば、設定が *1* の場合、ユーザーは新しいパスワードを選択すると、現在のパスワードは再利用できません。 設定が *5* の場合は、ユーザーは新しいパスワードを現在のパスワードに設定することも、以前の 4 つのパスワードのいずれかに設定することもできません。  
    [詳細情報](https://go.microsoft.com/fwlink/?linkid=2066795)

    **既定値**:24

- **[Prevent slide show]\(スライド ショーを禁止する\)** :  
  PC 設定でのロック画面のスライド ショー設定を無効にし、ロック画面でスライド ショーが再生されないようにします。 既定では、ユーザーはマシンのロック後に実行されるスライド ショーを有効にできます。 この設定を有効にした場合、ユーザーは [PC 設定] でスライド ショー設定を修正することができず、スライド ショーは開始できません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067105)

  **既定値**:Enabled  

  *有効に設定すると、スライド ショーは実行されなくなります。*

- **[Password minimum age in days]\(パスワードの最小有効期間 (日)\)** :  
  パスワードの最小有効期間ポリシー設定によって、ユーザーがパスワードを変更できるようになるまでの使用する必要がある期間 (日数) が決まります。 1 から 998 日の値を設定できます。また、日数を 0 に設定することで、パスワードの変更をすぐに許可することもできます。 パスワードの最大有効期間が 0 (パスワードが期限切れにならないことを示します) に設定されている場合を除き、パスワードの最小有効期間はパスワードの最大有効期限よりも短くする必要があります。 パスワードの最大有効期間が 0 に設定されている場合、パスワードの最小有効期間は 0 から 998 の任意の値に設定できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067022)

  **既定値**:1

::: zone-end
::: zone pivot="mdm-may-2019"

## <a name="dma-guard"></a>DMA ガード

詳細については、Windows ドキュメントの「[Policy CSP - DmaGuard (ポリシー CSP - DmaGuard)](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dmaguard)」をご覧ください。

- **[Kernel DMA Protection と互換性のない外部デバイスの列挙]** :  
  このポリシーの目的は、外部 DMA 対応デバイスのセキュリティを強化することです。 これにより、DMA の再マッピング/デバイス メモリの分離およびサンドボックス化と互換性のない外部 DMA 対応デバイスの列挙をより詳細に制御できます。 このポリシーが有効になるのは、Kernel DMA Protection がシステム ファームウェアによってサポートされていて、それによって有効にされた場合のみです。 Kernel DMA Protection は、ポリシーやエンド ユーザーによる制御ができないプラットフォーム機能です。 これは、製造時にシステムによってサポートされている必要があります。 システムで Kernel DMA Protection がサポートされているかどうかを確認するには、MSINFO32.exe の概要ページにある Kernel DMA Protection フィールドを調べます。  
  [詳細情報](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dmaguard#dmaguard-deviceenumerationpolicy)

  **既定値**:すべてブロックする

::: zone-end
::: zone pivot="mdm-preview,mdm-may-2019"

## <a name="event-log-service"></a>イベント ログ サービス

詳細については、Windows の「[Policy CSP - EventLogService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-eventlogservice)」(ポリシー CSP - EventLogService) を参照してください。

- **[Security log maximum file size in KB]\(セキュリティ ログの最大ファイル サイズ (KB)\)** :  
  このポリシー設定では、ログ ファイルの最大サイズを KB 単位で指定します。 このポリシー設定を有効にすると、最大ログ ファイル サイズを 1 MB (1024 KB) から 2 TB (2147483647 KB) の範囲で、KB 単位で構成できます。 このポリシー設定を無効にした場合、または構成しなかった場合、ログ ファイルの最大サイズはローカルで構成された値に設定されます。 この値は、ローカル管理者が [ログ プロパティ] ダイアログを使用して変更でき、既定値は 20 MB です。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067042)

   **既定値**:196608

- **[System log maximum file size in KB]\(システム ログの最大ファイル サイズ (KB)\)** :  
  このポリシー設定では、ログ ファイルの最大サイズを KB 単位で指定します。 このポリシー設定を有効にすると、最大ログ ファイル サイズを 1 MB (1024 KB) から 2 TB (2147483647 KB) の範囲で、KB 単位で構成できます。 このポリシー設定を無効にした場合、または構成しなかった場合、ログ ファイルの最大サイズはローカルで構成された値に設定されます。 この値は、ローカル管理者が [ログ プロパティ] ダイアログを使用して変更でき、既定値は 20 MB です。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2066798)

  **既定値**:32768

- **[Application log maximum file size in KB]\(アプリケーション ログの最大ファイル サイズ (KB)\)** :  
  このポリシー設定では、ログ ファイルの最大サイズを KB 単位で指定します。 このポリシー設定を有効にすると、最大ログ ファイル サイズを 1 MB (1024 KB) から 2 TB (2147483647 KB) の範囲で、KB 単位で構成できます。 このポリシー設定を無効にした場合、または構成しなかった場合、ログ ファイルの最大サイズはローカルで構成された値に設定されます。 この値は、ローカル管理者が [ログ プロパティ] ダイアログを使用して変更でき、既定値は 20 MB です。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067125)

  **既定値**:32768

## <a name="experience"></a>エクスペリエンス

詳細については、Windows の「[Policy CSP - Experience](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience)」(ポリシー CSP - Experience) を参照してください。

- **[Block Windows Spotlight]\(Windows スポットライトをブロックする\)** :  
  IT 管理者がすべての Windows スポットライト機能をオフ (ブロック) できるようにします。 これには、ロック画面、Windows ヒント、Microsoft のコンシューマー機能、およびその他の関連機能のウィンドウ スポットライトが含まれます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067037)

  **既定値**:はい

  *[Block Windows Spotlight]\(Windows スポットライトをブロックする\)* を *[未構成]* に設定すると、Windows スポットライトはデバイスでブロックされなくなります。次に Windows スポットライト用に選択した項目をブロックするように次の設定を構成することができます。

  - **[Block third-party suggestions in Windows Spotlight]\(Windows スポットライトでのサードパーティのおすすめをブロックする\)** :  
    ロック画面上のスポットライト、[スタート] メニューのおすすめのアプリ、Windows のヒントなど、Windows スポットライト機能でサードパーティのソフトウェア発行元からのアプリやコンテンツのおすすめを許可するかどうかを指定します。 ただし、Microsoft の機能、アプリ、およびサービスに関するおすすめはユーザーに表示されることがあります。  
    [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067045)

    **既定値**:未構成

  - **[Block consumer specific features]\(コンシューマー向け機能をブロックする\)** :  
    通常はコンシューマー向けのエクスペリエンスを IT 管理者がオンにできるようにします。たとえば、開始時の提案、メンバーシップ通知、OOBE 後のアプリ インストール、リダイレクト タイルなどです。  
    [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067054)

    **既定値**:未構成

## <a name="exploit-guard"></a>Exploit Guard

詳細については、Windows の「[Policy CSP - ExploitGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-exploitguard)」(ポリシー CSP - ExploitGuard) を参照してください。

- **[XML をアップロードする]** :  
  IT 管理者が、組織内のすべてのデバイスに対して、目的のシステムとアプリケーションの軽減策オプションを表す構成をプッシュできるようにします。 この構成は XML で表されます。 Exploit Protection は、拡散と感染のためにエクスプロイトを使用するマルウェアからデバイスを保護するのに役立ちます。 Windows セキュリティ アプリまたは PowerShell を使用して、一連の軽減策 (構成と呼ばれます) を作成します。 次に、この構成を XML ファイルとしてエクスポートし、ネットワーク上の複数のマシンと共有して、すべてのマシンに同じ軽減策設定が適用されるようにすることができます。 既存の EMET 構成 XML ファイルを変換して Exploit Protection 構成 XML にインポートすることもできます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067035)

  **既定値**:*Sample xml is provided (サンプル XML を指定する)*

## <a name="file-explorer"></a>エクスプローラー

詳細については、Windows の「[Policy CSP - FileExplorer](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-fileexplorer)」(ポリシー CSP - FileExplorer) を参照してください。  

- **[Block data execution prevention]\(データ実行防止をブロックする\)** :  
  データ実行防止を無効にすると、特定のレガシ プラグイン アプリケーションを、エクスプローラーを終了せずに機能させることができます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067043)  

  **既定値**:無効

- **[Block heap termination on corruption]\(破損後のヒープ終了をブロックする\)** :  
  破損時のヒープ終了を無効にすると、エクスプローラーをすぐに終了させずに、特定のレガシ プラグイン アプリケーションが機能することを許可できます。ただし、エクスプローラーはその後、予期せず終了する可能性があります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067107)

  **既定値**:無効

## <a name="firewall"></a>ファイアウォール

詳細については、Windows プロトコルのドキュメントの「[2.2.2 FW_PROFILE_TYPE]( https://docs.microsoft.com/openspecs/windows_protocols/ms-fasp/7704e238-174d-4a5e-b809-5f3787dd8acc)」を参照してください。

- **[ファイアウォール プロファイル ドメイン]** :  
  ルールが属するプロファイルを指定します: ドメイン、プライベート、パブリック。 この値は、ドメインに接続されているネットワークのプロファイルを表します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2066796)

  - **[受信接続をブロック]** :  
    **既定値**:はい

  - **[送信接続が必要]** :  
    **既定値**:はい

  - **[着信通知をブロック]** :  
    **既定値**:はい

  - **[ファイアウォールの有効化]** :  
    **既定値**:許可されます。

- **[ファイアウォール プロファイル パブリック]** :  
  ルールが属するプロファイルを指定します: ドメイン、プライベート、パブリック。 この値は、パブリック ネットワークのプロファイルを表します。 これらのネットワークは、サーバー ホストで管理者によってパブリックとして分類されます。 分類は、ホストが初めてネットワークに接続したときに行われます。 通常、このようなネットワークは、空港や喫茶店など、ネットワーク内のピアまたはネットワーク管理者が信頼されていない公共の場所にあるものです。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067143)

  - **[受信接続をブロック]** :  
    **既定値**:はい

  - **[送信接続が必要]** :  
    **既定値**:はい

  - **[着信通知をブロック]** :  
    **既定値**:はい

  - **[ファイアウォールの有効化]** :  
    **既定値**:許可されます。

  - **[グループ ポリシーからの接続セキュリティ ルールをマージしない]** :  
    **既定値**:はい

  - **[グループ ポリシーからのポリシー ルールをマージしない]** :  
    **既定値**:はい

- **[ファイアウォール プロファイル プライベート]** :  
  ルールが属するプロファイルを指定します: ドメイン、プライベート、パブリック。 この値は、プライベート ネットワークのプロファイルを表します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067041)

  - **[受信接続をブロック]** :  
    **既定値**:はい

  - **[送信接続が必要]** :  
    **既定値**:はい

  - **[着信通知をブロック]** :  
    **既定値**:はい

  - **[ファイアウォールの有効化]** :  
    **既定値**:許可されます。

## <a name="internet-explorer"></a>Internet Explorer

詳細については、Windows の「[Policy CSP - InternetExplorer](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-internetexplorer)」(ポリシー CSP - InternetExplorer) を参照してください。

- **[Internet Explorer の制限付きゾーンでのスクリプトによるステータス バーの更新]** :  
  このポリシー設定を使用すると、スクリプトを介してゾーン内のステータス バーを更新できるかどうかを管理できます。

  - "*このポリシー設定を有効にすると*"、スクリプトを使用してステータス バーを更新できます。
  - "*このポリシー設定を無効にした場合、または構成しなかった場合*"、スクリプトを使用してステータス バーを更新することはできません。

  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067074)

  **既定値**:無効

::: zone-end
::: zone pivot="mdm-may-2019"

- **[Internet Explorer のインターネット ゾーンでのファイルのドラッグ アンド ドロップまたはコピーと貼り付け]** :  
  このポリシー設定を使用すると、ユーザーがゾーン内のソースからファイルのドラッグまたはファイルのコピーと貼り付けを行うことができるかどうかを管理できます。 このポリシー設定を有効にすると、自動的に、ユーザーはこのゾーンからファイルをドラッグしたり、ファイルをコピーして貼り付けたりできます。 ドロップダウン ボックスで [ダイアログを表示する] を選択すると、ユーザーは、このゾーンからファイルをドラッグまたはコピーするかどうかの選択を求められます。 このポリシー設定を無効にすると、ユーザーはこのゾーンからファイルをドラッグしたり、ファイルをコピーして貼り付けたりできません。 このポリシー設定を構成しない場合は、自動的に、ユーザーはこのゾーンからファイルをドラッグしたり、コピーして貼り付けたりできます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067076)

  **既定値**:無効化

- **[Internet Explorer の制限付きゾーンでの .NET Framework 依存コンポーネント]** :  
  このポリシー設定を使用すると、Authenticode を使用して署名されていない .NET Framework コンポーネントを Internet Explorer から実行できるかどうかを管理できます。 これらのコンポーネントには、object タグから参照されたマネージド コントロールや、リンクから参照されたマネージド実行可能ファイルが含まれます。 このポリシー設定を有効にすると、Internet Explorer では署名されていないマネージド コンポーネントが実行されます。 ドロップダウン ボックスで [ダイアログを表示する] を選択すると、Internet Explorer では、署名されていないマネージド コンポーネントを実行するかどうかをユーザーに確認するメッセージが表示されます。 このポリシー設定を無効にすると、Internet Explorer は署名済みではない管理されたコンポーネントを実行しません。 このポリシー設定を構成しない場合は、Internet Explorer によって署名済みではない管理されたコンポーネントは実行されません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067077)

  **既定値**:無効化

- **[Internet Explorer のローカル コンピューター ゾーンで Active X コントロールに対してマルウェア対策を実行しない]** :  
  このポリシー設定では、Internet Explorer で ActiveX コントロールに対してマルウェア対策プログラムを実行し、ページを読み込んでも安全か確認するかどうかが決定されます。 このポリシー設定を有効にすると、Internet Explorer では、ActiveX コントロールのインスタンスを作成しても安全かどうかを確認するための、マルウェア対策プログラムでのチェックは行われません。 このポリシー設定を無効にすると、Internet Explorer では、ActiveX コントロールのインスタンスを作成しても安全かどうかを確認するための、マルウェア対策プログラムでのチェックが常に行われます。 このポリシー設定を構成しないと、Internet Explorer では、ActiveX コントロールのインスタンスを作成しても安全かどうかを確認するための、マルウェア対策プログラムでのチェックは行われません。 ユーザーは、Internet Explorer の [セキュリティ] の設定を使用して、この動作を有効または無効に切り替えることができます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067152)

  **既定値**:無効

::: zone-end
::: zone pivot="mdm-preview,mdm-may-2019"

- **[Internet Explorer internet zone access to data sources]\(Internet Explorer のインターネット ゾーンにあるデータ ソースへのアクセス\)** :  
  このポリシー設定を使用すると、Internet Explorer が Microsoft XML パーサー (MSXML) または ActiveX Data Objects (ADO) を使用して別のセキュリティ ゾーンからデータにアクセスできるかどうかを管理できます。 このポリシー設定を有効にすると、ユーザーは、ゾーン内の別のサイトにあるデータに MSXML または ADO を使用してアクセスするゾーン内のページを読み込むことができます。 ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、ゾーン内の他のサイトにあるデータに MSXML または ADO を使用してアクセスするゾーン内のページを読み込むことを許可するかどうかをユーザーにたずねます。 このポリシー設定を無効にすると、ゾーン内の他のサイトにあるデータに MSXML または ADO を使用してアクセスするゾーン内のページを読み込むことはできません。 このポリシー設定を構成しないと、ゾーン内の他のサイトにあるデータに MSXML または ADO を使用してアクセスするゾーン内のページを読み込むことはできません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067078)  

  **既定値**:無効化

- **[Internet Explorer restricted zone drag content from different domains within windows]\(Internet Explorer の制限付きゾーンでウィンドウ内の異なるドメインからコンテンツをドラッグする\)** :  
  このポリシー設定を使用すると、移動元と移動先が同じウィンドウにあるときに、あるドメインから別のドメインにコンテンツをドラッグするオプションを設定できます。 このポリシー設定を有効にして、[有効にする] をクリックすると、ユーザーは移行元と移行先が同じウィンドウの場合、あるドメインから別のドメインにコンテンツをドラッグすることができます。 この設定はユーザーが変更できません。 このポリシー設定を有効にして、[無効にする] をクリックすると、ユーザーは移行元と移行先が同じウィンドウの場合、あるドメインから別のドメインにコンテンツをドラッグすることはできません。 ユーザーは、[インターネット オプション] ダイアログでこの設定を変更できます。 Internet Explorer 10 では、このポリシー設定を無効にする場合、または構成しない場合、[有効にする] をクリックすると、ユーザーは移行元と移行先が同じウィンドウの場合、あるドメインから別のドメインにコンテンツをドラッグできません。 ユーザーは、[インターネット オプション] ダイアログでこの設定を変更できます。 Internet Explorer 9 以前のバージョンでは、このポリシーを無効にする場合、または構成しない場合は、ユーザーは移行元と移行先が同じウィンドウの場合、あるドメインから別のドメインにコンテンツをドラッグすることができます。 ユーザーは、[インターネット オプション] ダイアログでこの設定を変更できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067079)  

  **既定値**:無効

- **[Internet Explorer certificate address mismatch warning]\(Internet Explorer の証明書アドレスの不一致についての警告\)** :  
  このポリシー設定を使用すると、証明書のアドレスの不一致についてのセキュリティ警告を有効にできます。 このポリシー設定が有効である場合、ユーザーが別の Web サイト アドレス用に発行された証明書を提示する Secure HTTP (HTTPS) Web サイトを訪問すると、警告が表示されます。 この警告により、スプーフィング攻撃を防止できます。 このポリシー設定を有効にすると、証明書のアドレスの不一致についての警告が常に表示されます。 このポリシー設定を無効にするか、構成しないと、ユーザーはインターネット コントロール パネルの [詳細] ページを使用して、証明書のアドレスの不一致についての警告を表示するかどうかを選択できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067153)  

  **既定値**:Enabled

- **[Internet Explorer restricted zone less privileged sites]\(Internet Explorer の制限付きゾーンのより権限の少ないサイト\)** :  
  このポリシー設定を使用すると、インターネット サイトなどのより特権の少ないゾーンにある Web サイトからこのゾーンに移動できるかどうかを管理できます。 このポリシー設定を有効にすると、より権限の少ないゾーンの Web サイトで、このゾーンの新しいウィンドウを開いたり、このゾーンに移動したりできます。 セキュリティ ゾーンは、[ゾーン昇格からの保護] のセキュリティ機能で提供されるセキュリティの追加レイヤーなしに実行されます。 ドロップダウン ボックスで [ダイアログを表示する] を選択すると、危険を及ぼす可能性のあるナビゲーションが実行されると、ユーザーに警告が表示されます。 このポリシー設定を無効にすると、危害を及ぼす可能性のあるナビゲーションは禁止されます。 Internet Explorer のセキュリティ機能は、[ゾーン昇格からの保護] 機能コントロールで設定されているように、このゾーンでオンになります。 このポリシー設定を構成しないと、危害を及ぼす可能性のあるナビゲーションは禁止されます。 Internet Explorer のセキュリティ機能は、[ゾーン昇格からの保護] 機能コントロールで設定されているように、このゾーンでオンになります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067148)

  **既定値**:無効化

- **[Internet Explorer restricted zone automatic prompt for file downloads]\(Internet Explorer の制限付きゾーンでのファイルのダウンロードに対する自動プロンプト\)** :  
  このポリシー設定を使用すると、ファイルのダウンロードがユーザー以外によって開始されたときにユーザーにメッセージを表示するかどうかを管理できます。 この設定に関係なく、ユーザーには、ユーザーが開始したダウンロードに対して、ファイル ダウンロード ダイアログが表示されます。 この設定を有効にすると、自動ダウンロードが試行された場合、ユーザーにファイル ダウンロード ダイアログが表示されます。 この設定を無効にした場合、または構成しなかった場合は、ユーザー以外によって開始されたファイルのダウンロードはブロックされ、ファイル ダウンロードのダイアログの代わりに通知バーがユーザーに表示されます。 ユーザーは、通知バーをクリックして、ファイルのダウンロードのプロンプトを許可できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067150)

  **既定値**:無効

- **[Internet Explorer internet zone .NET Framework reliant components]\(Internet Explorer のインターネット ゾーンでの .NET Framework 依存コンポーネント\)** :  
  このポリシー設定を使用すると、Authenticode を使用して署名されている .NET Framework コンポーネントを Internet Explorer から実行できるかどうかを管理できます。 これらのコンポーネントには、object タグから参照されたマネージド コントロールや、リンクから参照されたマネージド実行可能ファイルが含まれます。 このポリシー設定を有効にすると、Internet Explorer では署名されていないマネージド コンポーネントが実行されます。 ドロップダウン ボックスで [ダイアログを表示する] を選択すると、Internet Explorer では、署名されていないマネージド コンポーネントを実行するかどうかをユーザーに確認するメッセージが表示されます。 このポリシー設定を無効にすると、Internet Explorer は署名済みではない管理されたコンポーネントを実行しません。 このポリシー設定を構成しない場合は、Internet Explorer は署名済みではない管理されたコンポーネントを実行します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067073)

  **既定値**:無効化

- **[Internet Explorer internet zone allow only approved domains to use tdc ActiveX controls]\(Internet Explorer のインターネット ゾーンで承認済みドメインにのみ tdc ActiveX コントロールを使用できるようにする\)** :  
  このポリシー設定では、Web サイト上でユーザーが TDC ActiveX コントロールを実行できるようにするかどうかを制御します。 このポリシー設定を有効にすると、TDC ActiveX コントロールはこのゾーン内の Web サイトから実行されません。 このポリシー設定を無効にすると、TDC Active X コントロールがこのゾーンのすべてのサイトから実行されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067151)

  **既定値**:Enabled

- **[Internet Explorer restricted zone script initiated windows]\(Internet Explorer の制限付きゾーンのスクリプトによって開かれるウィンドウ\)** :  
  このポリシー設定を使用すると、スクリプトによって開始されるポップアップ ウィンドウや、タイトルとステータス バーが含まれるウィンドウに対する制限を管理できます。 このポリシー設定を有効にすると、Windows Restrictions セキュリティはこのゾーンでは適用されません。 セキュリティ ゾーンは、この機能で提供されるセキュリティの追加レイヤーなしに実行されます。 このポリシー設定を無効にすると、スクリプトによって起動されたポップアップ ウィンドウや、タイトルとステータス バーを含むウィンドウに含まれる、危害を及ぼす可能性のある動作は実行されません。 この Internet Explorer のセキュリティ機能は、プロセスの [スクリプト化されたウィンドウのセキュリティ制限] 機能コントロール設定で指定されたように、このゾーンでオンになります。 このポリシー設定を構成しないと、スクリプトによって起動されたポップアップ ウィンドウや、タイトルとステータス バーを含むウィンドウに含まれる、危害を及ぼす可能性のある動作は実行されません。 この Internet Explorer のセキュリティ機能は、プロセスの [スクリプト化されたウィンドウのセキュリティ制限] 機能コントロール設定で指定されたように、このゾーンでオンになります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067075)

  **既定値**:無効

- **[Internet Explorer internet zone include local path when uploading files to server]\(Internet Explorer のインターネット ゾーンでサーバーへのファイルのアップロード時にローカル パスを含める\)** :  
  このポリシー設定では、ユーザーが HTML フォーム経由でファイルをアップロードするときに、ローカル パス情報が送信されるかどうかが制御されます。 ローカル パス情報が送信された場合、意図せずに、一部の情報がサーバーに公開されることがあります。 たとえば、ユーザーのデスクトップから送信されたファイルに、パスの一部としてユーザー名が含まれている可能性があります。 このポリシー設定を有効にすると、ユーザーが HTML フォーム経由でファイルをアップロードするときに、パス情報が送信されます。 このポリシー設定を無効にすると、ユーザーが HTML フォーム経由でファイルをアップロードするときに、パス情報が削除されます。 このポリシー設定を構成しないと、ユーザーは、HTML フォーム経由でファイルをアップロードするときに、パス情報を送信するかどうかを選択できます。 既定では、パス情報は送信されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067072)

  **既定値**:無効

- **[Internet Explorer disable processes in enhanced protected mode]\(Internet Explorer の拡張保護モードでプロセスを無効にする\)** :  
  このポリシー設定では、64 ビット バージョンの Windows の拡張保護モードで実行される Internet Explorer 11 で、(セキュリティ向上のため) 64 ビット プロセスを使用するか、または (互換性向上のため) 32 ビット プロセスを使用するかが決定されます。 重要:64 ビット プロセスを使用する場合、一部の ActiveX コントロールおよびツール バーが使用できなくなる可能性があります。 このポリシー設定を有効にすると、Internet Explorer 11 では、64 ビット バージョンの Windows の拡張保護モードで実行するときに、64 ビット タブ プロセスが使用されます。 このポリシー設定を無効にすると、Internet Explorer 11 では、64 ビット バージョンの Windows の拡張保護モードで実行するときに、32 ビット タブ プロセスが使用されます。 このポリシー設定を構成しない場合、ユーザーは、Internet Explorer の設定を使用して、この機能を有効または無効に切り替えることができます。 この機能は既定で無効になっています。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067149)

  **既定値**:Enabled

- **[Internet Explorer ignore certificate errors]\(Internet Explorer で証明書エラーを無視する\)** :  
  このポリシー設定を有効にすると、Internet Explorer での閲覧が中断される Secure Sockets Layer/Transport Layer Security (SSL/TLS) 証明書のエラー ("期限切れ"、"失効"、"名前の不一致" など) を、ユーザーは無視できなくなります。 このポリシー設定を有効にすると、ユーザーは閲覧を継続できません。 このポリシー設定を無効にするか、構成しない場合、ユーザーは証明書エラーを無視して閲覧を継続できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067071)

  **既定値**:無効

- **[Internet Explorer internet zone loading of XAML files]\(Internet Explorer のインターネット ゾーンでの XAML ファイルの読み込み\)** :  
  このポリシー設定を使用すると、Extensible Application Markup Language (XAML) ファイルの読み込みを管理できます。 XAML は、XML をベースにした宣言型マークアップ言語であり、Windows Presentation Foundation を利用する豊富なユーザー インターフェイスやグラフィックスを作成するために一般に使用されます。 このポリシー設定を有効にして、ドロップダウン ボックスで [有効にする] を選択した場合、XAML ファイルは Internet Explorer 内で自動的に読み込まれます。 ユーザーはこの動作を変更できません。 ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、XAML ファイルを読み込むかどうかをユーザーに確認するメッセージが表示されます。 このポリシー設定を無効にすると、XAML ファイルは Internet Explorer 内で読み込まれません。 ユーザーはこの動作を変更できません。 このポリシー設定を構成しなかった場合、ユーザーは XAML ファイルを Internet Explorer 内で読み込むかどうかを選択できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067147)

  **既定値**:無効化

::: zone-end
::: zone pivot="mdm-may-2019"

- **[Internet Explorer internet zone automatic prompt for file downloads]\(Internet Explorer のインターネット ゾーンでのファイルのダウンロードに対する自動プロンプト\)** :  
  このポリシー設定を使用すると、ファイルのダウンロードがユーザー以外によって開始されたときにユーザーにメッセージを表示するかどうかを管理できます。 この設定に関係なく、ユーザーには、ユーザーが開始したダウンロードに対して、ファイル ダウンロード ダイアログが表示されます。 この設定を有効にすると、自動ダウンロードが試行された場合、ユーザーにファイル ダウンロード ダイアログが表示されます。 この設定を無効にした場合、または構成しなかった場合は、ユーザー以外によって開始されたファイルのダウンロードはブロックされ、ファイル ダウンロードのダイアログの代わりに通知バーがユーザーに表示されます。 ユーザーは、通知バーをクリックして、ファイルのダウンロードのプロンプトを許可できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067117)

  **既定値**:無効

::: zone-end
::: zone pivot="mdm-preview"

- **[Internet Explorer internet zone automatic prompt for file downloads]\(Internet Explorer のインターネット ゾーンでのファイルのダウンロードに対する自動プロンプト\)** :  
  このポリシー設定を使用すると、ファイルのダウンロードがユーザー以外によって開始されたときにユーザーにメッセージを表示するかどうかを管理できます。 この設定に関係なく、ユーザーには、ユーザーが開始したダウンロードに対して、ファイル ダウンロード ダイアログが表示されます。 この設定を有効にすると、自動ダウンロードが試行された場合、ユーザーにファイル ダウンロード ダイアログが表示されます。 この設定を無効にした場合、または構成しなかった場合は、ユーザー以外によって開始されたファイルのダウンロードはブロックされ、ファイル ダウンロードのダイアログの代わりに通知バーがユーザーに表示されます。 ユーザーは、通知バーをクリックして、ファイルのダウンロードのプロンプトを許可できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067117)

  **既定値**:Enabled

::: zone-end
::: zone pivot="mdm-preview,mdm-may-2019"

- **[Internet Explorer restricted zone security warning for potentially unsafe files]\(Internet Explorer の制限付きゾーンでの安全でない可能性があるファイルに対するセキュリティ警告\)** :  
  このポリシー設定では、ユーザーが (たとえば、エクスプローラーを使用してイントラネット ファイル共有から) 実行可能ファイルまたはその他の安全でない可能性があるファイルを開こうとしたときに、"ファイルを開く - セキュリティ警告" というメッセージが表示されるかどうかを制御します。 このポリシー設定を有効にして、ドロップダウン ボックスを [有効にする] に設定した場合、このようなファイルを開くときにセキュリティ警告は表示されません。 ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、ファイルを開く前にセキュリティ警告が表示されます。 このポリシー設定を無効にした場合、そうしたファイルは開きません。 このポリシー設定を構成しなかった場合、ユーザーがそうしたファイルの処理方法を構成できます。 既定では、このようなファイルは制限付きゾーンではブロックされ、イントラネット ゾーンとローカル コンピューター ゾーンでは有効になり、インターネット ゾーンと信頼済みゾーンではメッセージを表示するように設定されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2066797)

  **既定値**:無効化

- **[Internet Explorer internet zone cross site scripting filter]\(Internet Explorer のインターネット ゾーンのクロスサイト スクリプト フィルター\)** :  
  このポリシーでは、クロスサイト スクリプト (XSS) フィルターがこのゾーン内の Web サイトにあるクロスサイト スクリプト インジェクションを検出して防止するかどうかを制御します。 このポリシー設定を有効にすると、XSS フィルターはこのゾーン内のサイトに対して有効になり、クロスサイト スクリプト インジェクションのブロックを試みます。 このポリシー設定を無効にすると、XSS フィルターがこのゾーン内のサイトに対して無効になり、Internet Explorer でクロスサイト スクリプト インジェクションが許可されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067053)

  **既定値**:Enabled

- **[Internet Explorer fallback to SSL3]\(Internet Explorer の SSL3 へのフォールバック\)** :  
  このポリシー設定を使用すると、SSL 3.0 への安全ではないフォールバックをブロックできます。 このポリシーが有効な場合、Internet Explorer では TLS 1.0 以降が失敗すると SSL 3.0 以前を使用してサイトへの接続を試行します。 中間者攻撃を防ぐために、安全でないフォールバックを許可しないことをお勧めします。 このポリシーは、どのセキュリティ プロトコルが有効になっているかには影響しません。 このポリシー設定を無効にすると、システムの既定値が使用されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067118)

  **既定値**:サイトなし

::: zone-end
::: zone pivot="mdm-may-2019"

- **[Internet Explorer の暗号化サポート]** :  
  このポリシー設定を使用すると、トランスポート層セキュリティ (TLS) 1.0、TLS 1.1、TLS 1.2、Secure Sockets Layer (SSL) 2.0、または SSL 3.0 のブラウザーでのサポートを無効にできます。 TLS と SSL は、ブラウザーと対象サーバー間の通信を保護するのに役立つプロトコルです。 ブラウザーで対象サーバーとの保護された通信の設定が試みられると、ブラウザーとサーバーの間で使用するプロトコルとバージョンについてのネゴシエートが行われます。 ブラウザーとサーバーにより、サポートされているプロトコルとバージョンのリストが相互に照合されて、最善の組み合わせが選択されます。 このポリシー設定を有効にした場合、ブラウザーは、ユーザーがドロップダウン リストから選択した暗号化方法を使用して暗号トンネルをネゴシエートするときとしないときがあります。 このポリシー設定を無効にするか構成しない場合、ユーザーはブラウザーがサポートする暗号化方法を選択できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067057)

  **既定値**:2 項目:TLS v1.1 と TLS v1.2  
  *下矢印を選択すると、この設定で選択できるオプションが表示されます。*

::: zone-end
::: zone pivot="mdm-preview,mdm-may-2019"

- **[Internet Explorer locked down internet zone smart screen]\(Internet Explorer のロックダウンされたインターネット ゾーンでのスマート スクリーン\)** :  
  このポリシー設定では、SmartScreen フィルターを使用して、このゾーンのページで悪意のあるコンテンツをスキャンするかどうかが制御されます。 このポリシー設定を有効にすると、SmartScreen フィルターによってこのゾーンのページで悪意のあるコンテンツがスキャンされます。 このポリシー設定を無効にすると、SmartScreen フィルターはこのゾーンのページの悪意のあるコンテンツをスキャンしません。 このポリシー設定を構成しない場合、SmartScreen フィルターがこのゾーンのページの悪意のあるコンテンツをスキャンするかどうかをユーザーが選択できます。 注:Internet Explorer 7 の場合、このポリシー設定では、フィッシング詐欺検出機能がこのゾーンのページの悪意のあるコンテンツをスキャンするかどうかを制御します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067059)

  **既定値**:Enabled

- **[Internet Explorer restricted zone launch applications and files in an iFrame]\(Internet Explorer の制限付きゾーンで iFrame のアプリケーションとファイルを起動する\)** :  
  このポリシー設定を使用すると、このゾーン内のページの HTML にある IFRAME 参照からアプリケーションを実行したり、ファイルをダウンロードしたりすることができるかどうかを管理できます。 このポリシー設定を有効にすると、ユーザーは、何もしなくても、このゾーンのページ上の IFRAME からアプリケーションを実行したりファイルをダウンロードしたりできます。 ドロップダウン ボックスで [ダイアログを表示する] を選択すると、ユーザーは、このゾーンのページ上の IFRAME からアプリケーションを実行したりファイルをダウンロードしたりするかどうかの確認を求められます。 このポリシー設定を無効にすると、ユーザーはこのゾーンにあるページ上の IFRAME からアプリケーションを実行したりファイルをダウンロードしたりすることができません。 このポリシー設定を構成しない場合は、ユーザーはこのゾーンにあるページ上の IFRAME からアプリケーションを実行したりファイルをダウンロードしたりすることができません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067061)

  **既定値**:無効化

- **[Internet Explorer での一般的ではないファイルに関するスマート スクリーン警告のバイパス]** :  
  このポリシー設定では、ユーザーが SmartScreen フィルターからの警告をバイパスできるかどうかを決定します。 SmartScreen フィルター機能では、ダウンロードしたユーザー数が少ない実行可能ファイルについてユーザーに警告します。 このポリシー設定を有効にすると、ユーザーは SmartScreen フィルターの警告によってブロックされます。 このポリシー設定を無効にした場合、または構成しなかった場合、ユーザーは SmartScreen フィルター機能の警告をバイパスできます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067068)

  **既定値**:無効

- **[Internet Explorer internet zone popup blocker]\(Internet Explorer のインターネット ゾーンのポップアップ ブロッカー\)** :  
  このポリシー設定を使用すると、不要なポップアップ ウィンドウが表示されるかどうかを管理できます。 エンド ユーザーがリンクをクリックしたときに開かれるポップアップ ウィンドウはブロックされません。 このポリシー設定を有効にすると、不要なポップアップ ウィンドウは表示されません。 このポリシー設定を無効にすると、ポップアップ ウィンドウの表示は禁止されません。 このポリシー設定を構成しない場合は、不要なポップアップ ウィンドウは表示されません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067069)

  **既定値**:[ウェイクアップ時間 (デスクトップ コンピューター)] を有効にして、デスクトップ コンピューターが、スケジュールされた更新またはソフトウェアのインストールを実行するために、スリープ状態または休止状態から復帰する時刻を指定します。

- **[Internet Explorer processes consistent MIME handling]\(Internet Explorer での一貫性のある MIME 処理\)** :  
  Internet Explorer には動的なバイナリ ビヘイビアー (動作が関連付けられている HTML 要素のための特定の機能をカプセル化するコンポーネント) が含まれます。 このポリシー設定では、バイナリ ビヘイビアーのセキュリティ制限の設定を禁止するか許可するかが制御されます。 このポリシー設定を有効にすると、バイナリ ビヘイビアーはエクスプローラーおよび Internet Explorer のプロセスで使用できなくなります。 このポリシー設定を無効にすると、バイナリ ビヘイビアーはエクスプローラーおよび Internet Explorer のプロセスで使用できるようになります。 このポリシー設定を構成しない場合は、バイナリ ビヘイビアーはエクスプローラーおよび Internet Explorer のプロセスでは使用不可になります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067144)  

  **既定値**:Enabled

- **[Internet Explorer の制限付きゾーンの Java のアクセス許可]** :  
  このポリシー設定を使用すると、Java アプレットのアクセス許可を管理できます。 このポリシー設定を有効にすると、オプションをドロップダウン ボックスから選択できます。 アクセス許可の設定を個々に制御するには [カスタム] を選択します。 [安全性 - 低] を選択すると、アプレットはすべての操作を実行できます。 [安全性 - 中] を選択すると、アプレットはサンドボックス (メモリ内の領域で、その外側にはプログラムは呼び出しを実行できない) 内で実行されます。また、スクラッチ領域 (クライアント コンピューター内の安全でセキュリティで保護された記憶域) やユーザーによって制御されたファイル I/O などの機能が利用できます。 [安全性 - 高] を選択すると、アプレットはサンドボックス内で実行されます。 アプレットが実行されないようにするには、[Java を無効にする] を選択します。 このポリシー設定を無効にすると、Java アプレットは実行されません。 このポリシー設定を構成しなかった場合、Java アプレットは無効になります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067132)

  **既定値**:Java を無効にする

- **[Internet Explorer Active X controls in protected mode]\(Internet Explorer の保護モードでの ActiveX コントロール\)** :  
  このポリシー設定では、拡張保護モードが有効になっている場合に、保護モードで ActiveX コントロールを実行できなくなります。 拡張保護モードと互換性がない ActiveX コントロールがインストールされ、Web サイトがそのコントロールの読み込みを試行した場合、Internet Explorer によってユーザーに通知が行われ、Web サイトを通常の保護モードで実行するためのオプションが表示されます。 このポリシー設定を使用すると、この通知が無効になり、すべての Web サイトが拡張保護モードで強制的に実行されます。 拡張保護モードでは、64 ビット版の Windows で 64 ビット プロセスを使用することにより、悪意のある Web サイトに対する保護が強化されます。 Windows 8 以降が実行されているコンピューターでは、拡張保護モードによって、Internet Explorer が読み取り元に設定できる、レジストリとファイル システム内の場所も制限されています。 拡張保護モードが有効になっていて、拡張保護モードと互換性がない ActiveX コントロールの読み込みを試行する Web サイトをユーザーが表示しようとした場合は、Internet Explorer によってユーザーに通知が行われ、その Web サイトで拡張保護モードを無効にするためのオプションが表示されます。 このポリシー設定を有効にすると、拡張保護モードを無効にするオプションは Internet Explorer でユーザーに表示されなくなります。 保護モードの Web サイトはすべて、拡張保護モードで実行されます。 このポリシー設定を無効にした場合、または構成しない場合は、Internet Explorer によってユーザーに通知が行われ、互換性がない ActiveX コントロールが含まれている Web サイトを通常の保護モードで実行するためのオプションが表示されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067145)

  **既定値**:無効

- **[Internet Explorer restricted zone loading of XAML files]\(Internet Explorer の制限付きゾーンでの XAML ファイルの読み込み\)** :  
  このポリシー設定を使用すると、Extensible Application Markup Language (XAML) ファイルの読み込みを管理できます。 XAML は、XML をベースにした宣言型マークアップ言語であり、Windows Presentation Foundation を利用する豊富なユーザー インターフェイスやグラフィックスを作成するために一般に使用されます。 このポリシー設定を有効にして、ドロップダウン ボックスで [有効にする] を選択した場合、XAML ファイルは Internet Explorer 内で自動的に読み込まれます。 ユーザーはこの動作を変更できません。 ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、XAML ファイルを読み込むかどうかをユーザーに確認するメッセージが表示されます。 このポリシー設定を無効にすると、XAML ファイルは Internet Explorer 内で読み込まれません。 ユーザーはこの動作を変更できません。 このポリシー設定を構成しなかった場合、ユーザーは XAML ファイルを Internet Explorer 内で読み込むかどうかを選択できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067070)

  **既定値**:無効化

- **[Internet Explorer processes scripted window security restrictions]\(Internet Explorer プロセスでのスクリプト化されたウィンドウのセキュリティ制限\)**  
  Internet Explorer では、スクリプトのプログラムでさまざまな種類のウィンドウを開いたり、ウィンドウのサイズや場所を変更したりすることが許可されます。 ウィンドウ制限のセキュリティ機能は、ポップアップ ウィンドウを制限し、スクリプトがタイトル バーやステータス バーがユーザーに表示されないウィンドウ、または Windows の他のタイトル バーやステータス バーと混乱するようなウィンドウを表示することを禁止します。 このポリシー設定を有効にすると、スクリプト化されたウィンドウはすべてのプロセスで制限されます。 このポリシー設定を無効にするか、または構成しない場合は、スクリプト化されたウィンドウには制限は適用されません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067146)

  **既定値**:Enabled

- **[Internet Explorer restricted zone run Active X controls and plugins]\(Internet Explorer の制限付きゾーンで Active X コントロールおよびプラグインを実行する\)** :  
  このポリシー設定を使用すると、指定されたゾーンのページ上で ActiveX コントロールおよびプラグインが実行できるかどうかを管理できます。 このポリシー設定を有効にすると、ユーザーによる手動操作を必要とすることなく、コントロールやプラグインを実行できます。 ドロップダウン ボックスで [ダイアログを表示する] を選択すると、ユーザーはコントロールやプラグインの実行を許可するかどうかの選択を求められます。 このポリシー設定を無効にすると、コントロールやプラグインは実行されません。 このポリシー設定を構成しない場合は、コントロールとプラグインは実行されません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067114)

  **既定値**:無効化

- **[Internet Explorer restricted zone script Active X controls marked safe for scripting]\(Internet Explorer の制限付きゾーンでスクリプトを実行しても安全であるとマークされた Active X コントロールをスクリプト化する\)** :  
  このポリシー設定を使用すると、スクリプトを実行しても安全であるとマークされた ActiveX コントロールがスクリプトと対話できるかどうかを管理できます。 このポリシー設定を有効にすると、ユーザーによる手動操作を必要とすることなく、スクリプトの対話を自動的に実行できます。 ドロップダウンボックスで [ダイアログを表示する] を選択すると、ユーザーはスクリプトの対話を許可するかどうかの確認を求められます。 このポリシー設定を無効にすると、スクリプトの対話は実行されません。 このポリシー設定を構成しない場合は、スクリプトの対話は実行されません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067062)

  **既定値**:無効化

- **[Internet Explorer restricted zone logon options]\(Internet Explorer の制限付きゾーンのログオン オプション\)** :  
  このポリシー設定を使用すると、サインイン オプションの設定を管理できます。 このポリシー設定を有効にすると、次のサインイン オプションから選択できます。

  - *匿名* - HTTP 認証を無効にして、Common Internet File System (CIFS) プロトコル用にのみ guest アカウントを使用する場合は、匿名サインインを使用します。

  - *プロンプト* - ユーザーの ID とパスワードを照会するために、ユーザー名とパスワードの入力を求めます。 ユーザーが照会された後に、これらの値は残りのセッションで警告なしに使用されます。

  - *イントラネット ゾーンでのみ自動的にサインインする* - 他のゾーンでのユーザー ID とパスワードをユーザーに照会するには、このオプションを使用します。 ユーザーが照会された後に、これらの値は残りのセッションで警告なしに使用されます。

  - *現在のユーザー名とパスワードで自動的にサインインする* - Windows NT チャレンジ応答 (別名 NTLM 認証) を使用してログオンを試みるには、このオプションを使用します。 サーバーで Windows NT チャレンジ応答がサポートされている場合、サインインでは、ユーザーのサインイン用のネットワーク ユーザー名とパスワードが使用されます。 サーバーで Windows NT チャレンジ応答がサポートされていない場合、ユーザーはユーザー名とパスワードを提供する必要があります。

  このポリシー設定を無効にすると、サインインは "*イントラネット ゾーンでのみ自動的にサインインする*" に設定されます。 このポリシー設定を構成しなかった場合、サインインは "*プロンプト*" に設定されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067110)

  **既定値**:匿名

- **[Internet Explorer trusted zone initialize and script Active X controls not marked as safe]\(Internet Explorer の信頼済みゾーンで安全であるとマークされていない Active X コントロールを初期化およびスクリプト化する\)** :  
  このポリシー設定を使用すると、安全とマークされていない ActiveX コントロールを管理できます。 このポリシー設定を有効にすると、ActiveX コントロールがパラメーターを読み込んで実行され、また、信頼されていないデータまたはスクリプトに対するオブジェクトの安全性を設定することなくスクリプト化されます。 この設定は、安全でかつ管理されたゾーン以外では推奨しません。 この設定により、安全でないコントロールと安全なコントロールの両方が初期化されてスクリプト化され、スクリプト実行オプションで安全とマークされた Script ActiveX コントロールは無視されます。 このポリシー設定を有効にして、ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、コントロールにパラメーターを読み込んだりスクリプト化したりすることを許可するかどうかをユーザーにたずねます。 このポリシー設定を無効にすると、安全であるとマークできない ActiveX コントロールにパラメーターを読み込んだりスクリプト化したりすることはできません。 このポリシー設定を構成しなかった場合、コントロールにパラメーターを読み込んだりスクリプト化したりするかどうかをユーザーにたずねます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067137)

  **既定値**:無効化

- **[Internet Explorer check server certificate revocation]\(Internet Explorer でサーバー証明書の失効状態を確認する\)** :  
  このポリシー設定を使用すると、Internet Explorer でサーバーの証明書の失効状態を確認するかどうかを管理できます。 証明書は、危害を受けたか、有効ではなくなった場合に失効されます。このオプションを使うと、詐欺目的であるか、安全ではない可能性があるサイトにユーザーが機密データを送信するのを防ぐことができます。 このポリシー設定を有効にすると、サーバー証明書が失効したかどうかが Internet Explorer で確認されます。 このポリシー設定を無効にすると、サーバーの証明書が失効したかどうかが Internet Explorer によって確認されません。 このポリシー設定を構成しなかった場合、サーバーの証明書が失効したかどうかが Internet Explorer によって確認されません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067046)

  **既定値**:Enabled

- **[Internet Explorer internet zone less privileged sites]\(Internet Explorer のインターネット ゾーンのより権限の少ないサイト\)** :  
  このポリシー設定を使用すると、制限付きサイトなどのより特権の少ないゾーンにある Web サイトからこのゾーンに移動できるかどうかを管理できます。 このポリシー設定を有効にすると、より権限の少ないゾーンの Web サイトで、このゾーンの新しいウィンドウを開いたり、このゾーンに移動したりできます。 セキュリティ ゾーンは、[ゾーン昇格からの保護] のセキュリティ機能で提供されるセキュリティの追加レイヤーなしに実行されます。 ドロップダウン ボックスで [ダイアログを表示する] を選択すると、危険を及ぼす可能性のあるナビゲーションが実行されると、ユーザーに警告が表示されます。 このポリシー設定を無効にすると、危害を及ぼす可能性のあるナビゲーションは禁止されます。 Internet Explorer のセキュリティ機能は、[ゾーン昇格からの保護] 機能コントロールで設定されているように、このゾーンでオンになります。 このポリシー設定を構成しない場合は、より権限の少ないゾーンの Web サイトがこのゾーンで新しいウィンドウを開いたり、このゾーンに移動したりできます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067109)

  **既定値**:無効化

- **[Internet Explorer restricted zone file downloads]\(Internet Explorer の制限付きゾーンでのファイルのダウンロード\)** :  
  このポリシー設定を使用すると、ゾーンからのファイルのダウンロードが許可されるかどうかを管理できます。 このオプションは、ファイルの配信元のゾーンではなく、ダウンロードを開始するリンクがあるページのゾーンによって決定されます。 このポリシー設定を有効にすると、ゾーンからファイルをダウンロードできます。 このポリシー設定を無効にすると、ゾーンからファイルをダウンロードできません。 このポリシー設定を構成しない場合は、ゾーンからファイルをダウンロードできません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067038)

  **既定値**:無効化

- **Internet Explorer internet zone run .NET Framework reliant components signed with Authenticode\(Internet Explorer のインターネット ゾーンで Authenticode 署名済みの .NET Framework 依存コンポーネントを実行する\)** :  
  このポリシー設定を使用すると、Authenticode で署名されている .NET Framework コンポーネントを Internet Explorer から実行できるかどうかを管理できます。 これらのコンポーネントには、object タグから参照されたマネージド コントロールや、リンクから参照されたマネージド実行可能ファイルが含まれます。 このポリシー設定を有効にすると、Internet Explorer では署名されているマネージド コンポーネントが実行されます。 ドロップダウン ボックスで [ダイアログを表示する] を選択すると、Internet Explorer では、署名されているマネージド コンポーネントを実行するかどうかをユーザーに確認するメッセージが表示されます。 このポリシー設定を無効にすると、Internet Explorer は署名済みの管理されたコンポーネントを実行しません。 このポリシー設定を構成しない場合は、Internet Explorer は署名済みの管理されたコンポーネントを実行します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067033)

  **既定値**:無効化

- **[Internet Explorer でユーザーごとに Active X コントロールをインストールできないようにする]** :  
  このポリシー設定を使用すると、ActiveX コントロールをユーザーごとにインストールできないようにすることができます。 このポリシー設定を有効にすると、ActiveX コントロールはユーザーごとにインストールできなくなります。 このポリシー設定を無効にするか構成しないと、ActiveX コントロールはユーザーごとにインストールできます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067058)

  **既定値**:Enabled

- **[Internet Explorer prevent managing smart screen filter]\(Internet Explorer でスマート スクリーン フィルターを管理できないようにする\)** :  
  このポリシー設定は、ユーザーが SmartScreen フィルターを管理できないようにします。SmartScreen フィルターを有効にすると、"フィッシング" を通じて個人情報を不正に収集することがわかっている Web サイト、または悪意のあるソフトウェアをホストしていることがわかっている Web サイトにアクセスしようとすると警告が表示されます。 このポリシー設定を有効にすると、ユーザーには、SmartScreen フィルターを有効にするためのダイアログは表示されません。 フィルターの許可リストに含まれない Web サイトのアドレスはすべて Microsoft に自動的に送信され、ユーザーにはダイアログは表示されません。 このポリシー設定を無効にするか、構成しない場合、ユーザーには、初回実行時に SmartScreen フィルターを有効にするかどうかを選択するためのダイアログが表示されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067135)

  **既定値**:[ウェイクアップ時間 (デスクトップ コンピューター)] を有効にして、デスクトップ コンピューターが、スケジュールされた更新またはソフトウェアのインストールを実行するために、スリープ状態または休止状態から復帰する時刻を指定します。

- **[Internet Explorer processes MIME sniffing safety feature]\(Internet Explorer プロセスでの MIME スニッフィングの安全機能\)** :  
  このポリシー設定では、Internet Explorer の MIME スニッフィングによって、ある種類のファイルをより危険な種類のファイルに昇格させることができないようにするかどうかが決定されます。 このポリシー設定を有効にすると、MIME スニッフィングは、ある種類のファイルをより危険な種類に昇格することはありません。 このポリシー設定を無効にすると、Internet Explorer のプロセスで、ある種類のファイルをより危険な種類のファイルに昇格する MIME スニフが許可されます。 このポリシー設定を構成しない場合は、MIME スニッフィングは、ある種類のファイルをより危険な種類に昇格することはありません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067124)

  **既定値**:Enabled

- **[Internet Explorer restricted zone download signed Active X controls]\(Internet Explorer の制限付きゾーンで署名された Active X コントロールをダウンロードする\)** :  
  このポリシー設定を使用すると、ユーザーがゾーン内のページから署名された ActiveX コントロールをダウンロードできるかどうかを管理できます。 このポリシーを有効にすると、ユーザーの介入なしに署名されたコントロールをダウンロードできます。 ドロップダウン ボックスで [ダイアログを表示する] を選択すると、信頼されていない発行元によって署名されたコントロールをダウンロードするかどうかをユーザーに確認するメッセージが表示されます。 信頼できる発行元によって署名されたコードは、警告なしでダウンロードされます。 このポリシー設定を無効にすると、署名されたコントロールはダウンロードできません。 このポリシー設定を構成しない場合は、信頼されていない発行元によって署名されたコントロールをダウンロードするかどうかをユーザーにたずねます。 信頼できる発行元によって署名されたコードは、警告なしでダウンロードされます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067120)

  **既定値**:無効化

- **[Internet Explorer auto complete]\(Internet Explorer のオート コンプリート\)** :  
  このオートコンプリート機能では、フォーム上のユーザー名とパスワードを記憶して、候補を表示できます。 この設定を有効にすると、ユーザーは [フォームのユーザー名およびパスワード] や [パスワードを保存する確認をする] のオプションを変更できません。 フォームのユーザー名とパスワードのオートコンプリート機能は有効になります。 "パスワードを保存する確認をする" オプションを選択するかどうかを決定します。 この設定を無効にすると、ユーザーは [フォームのユーザー名およびパスワード] や [パスワードを保存する確認をする] を変更できません。 フォームのユーザー名とパスワードのオートコンプリート機能は無効になります。 ユーザーは、パスワードの保存を確認するように選択することもできません。 この設定を構成しない場合、ユーザーは、[フォームのユーザー名およびパスワード] や [パスワードを保存する確認をする] のオプションを有効にすることができます。 このオプションを表示するには、ユーザーは [インターネット オプション] ダイアログ ボックスを開いて、[コンテンツ] タブ、[設定] ボタンの順にクリックします。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067122)

  **既定値**:無効

- **[Internet Explorer internet zone allow VBscript to run]\(Internet Explorer のインターネット ゾーンで VB スクリプトの実行を許可する\)** :  
  このポリシー設定では、VB スクリプトが特定の Internet Explorer のゾーンでページを実行できるかどうかを決定できます。 次のオプションがあります。

  - "*有効*" - 対話式の操作を行くことなく、VB スクリプトが特定のゾーンのページ上で実行されます。

  - "*プロンプト*" - 従業員は VB スクリプトをそのゾーンで実行できるようにするかどうかを確認されます。

  - "*無効*" - VB スクリプトはそのゾーンで実行できないようにされます。 このポリシー設定を無効にした場合、または構成しない場合は、VBScript は特定のゾーンで対話式の操作なしで実行されます。

  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067119)

  **既定値**:無効化

- **[Internet Explorer restricted zone allow only approved domains to use tdc Active X controls]\(Internet Explorer の制限付きゾーンで承認済みドメインのみ TDC Active X コントロールを使用できるようにする\)** :  
  このポリシー設定では、Web サイト上でユーザーが TDC ActiveX コントロールを実行できるようにするかどうかを制御します。 このポリシー設定を有効にすると、TDC ActiveX コントロールはこのゾーン内の Web サイトから実行されません。 このポリシー設定を無効にすると、TDC Active X コントロールがこのゾーンのすべてのサイトから実行されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067032)

  **既定値**:Enabled

- **[Internet Explorer trusted zone do not run antimalware against Active X controls]\(Internet Explorer の信頼済みゾーンで Active X コントロールに対してマルウェア対策を実行しない\)** :  
  このポリシー設定では、Internet Explorer で ActiveX コントロールに対してマルウェア対策プログラムを実行し、ページを読み込んでも安全か確認するかどうかが決定されます。 このポリシー設定を有効にすると、Internet Explorer では、ActiveX コントロールのインスタンスを作成しても安全かどうかを確認するための、マルウェア対策プログラムでのチェックは行われません。 このポリシー設定を無効にすると、Internet Explorer では、ActiveX コントロールのインスタンスを作成しても安全かどうかを確認するための、マルウェア対策プログラムでのチェックが常に行われます。 このポリシー設定を構成しない場合、Internet Explorer では、ActiveX コントロールのインスタンスを作成しても安全かどうかを確認するための、マルウェア対策プログラムでのチェックが常に行われます。 ユーザーは、Internet Explorer の [セキュリティ] の設定を使用して、この動作を有効または無効に切り替えることができます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067115)

  **既定値**:無効

- **[Internet Explorer local machine zone java permissions]\(Internet Explorer のローカル コンピューター ゾーンでの Java のアクセス許可\)** :  
  このポリシー設定を使用すると、Java アプレットのアクセス許可を管理できます。 このポリシー設定を有効にすると、オプションをドロップダウン ボックスから選択できます。 アクセス許可の設定を個々に制御するには [カスタム] を選択します。 [安全性 - 低] を選択すると、アプレットはすべての操作を実行できます。 [安全性 - 中] を選択すると、アプレットはサンドボックス (メモリ内の領域で、その外側にはプログラムは呼び出しを実行できない) 内で実行されます。また、スクラッチ領域 (クライアント コンピューター内の安全でセキュリティで保護された記憶域) やユーザーによって制御されたファイル I/O などの機能が利用できます。 [安全性 - 高] を選択すると、アプレットはサンドボックス内で実行されます。 アプレットが実行されないようにするには、[Java を無効にする] を選択します。 このポリシー設定を無効にすると、Java アプレットは実行されません。 このポリシー設定を構成しない場合は、アクセス許可は [安全性 - 中] に設定されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067113)

  **既定値**:Java を無効にする

- **[Internet Explorer intranet zone do not run antimalware against Active X controls]\(Internet Explorer のイントラネット ゾーンで Active X コントロールに対してマルウェア対策を実行しない\)** :  
  このポリシー設定では、Internet Explorer で ActiveX コントロールに対してマルウェア対策プログラムを実行し、ページを読み込んでも安全か確認するかどうかが決定されます。 このポリシー設定を有効にすると、Internet Explorer では、ActiveX コントロールのインスタンスを作成しても安全かどうかを確認するための、マルウェア対策プログラムでのチェックは行われません。 このポリシー設定を無効にすると、Internet Explorer では、ActiveX コントロールのインスタンスを作成しても安全かどうかを確認するための、マルウェア対策プログラムでのチェックが常に行われます。 このポリシー設定を構成しないと、Internet Explorer では、ActiveX コントロールのインスタンスを作成しても安全かどうかを確認するための、マルウェア対策プログラムでのチェックは行われません。 ユーザーは、Internet Explorer の [セキュリティ] の設定を使用して、この動作を有効または無効に切り替えることができます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067138)

  **既定値**:無効

- **[Internet Explorer restricted zone scriptlets]\(Internet Explorer の制限付きゾーンのスクリプトレット\)** :  
  このポリシー設定を使用すると、ユーザーがスクリプトレットを実行できるかどうかを管理できます。 このポリシー設定を有効にすると、ユーザーはスクリプトレットを実行できます。 このポリシー設定を無効にすると、ユーザーはスクリプトレットを実行できません。 このポリシー設定を構成しなかった場合、ユーザーはスクリプトレットを有効または無効にできます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067112)

  **既定値**:無効

- **[Internet Explorer processes notification bar]\(Internet Explorer プロセスの通知バー\)** :  
  このポリシー設定を使うと、ファイルやコードのインストールが制限されている場合に、Internet Explorer プロセスに対して通知バーを表示するかどうかを管理できます。 既定では、通知バーは Internet Explorer プロセスに対して表示されます。 このポリシー設定を有効にすると、通知バーは Internet Explorer プロセスに対して表示されます。 このポリシー設定を無効にすると、通知バーは Internet Explorer プロセスに対して表示されません。 このポリシー設定を構成しない場合は、通知バーは Internet Explorer プロセスに対して表示されません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067139)

  **既定値**:Enabled

- **[Internet Explorer internet zone download signed ActiveX controls]\(Internet Explorer のインターネット ゾーンで署名された ActiveX コントロールをダウンロードする\)** :  
  このポリシー設定を使用すると、ユーザーがゾーン内のページから署名された ActiveX コントロールをダウンロードできるかどうかを管理できます。 このポリシーを有効にすると、ユーザーの介入なしに署名されたコントロールをダウンロードできます。 ドロップダウン ボックスで [ダイアログを表示する] を選択すると、信頼されていない発行元によって署名されたコントロールをダウンロードするかどうかをユーザーに確認するメッセージが表示されます。 信頼できる発行元によって署名されたコードは、警告なしでダウンロードされます。 このポリシー設定を無効にすると、署名されたコントロールはダウンロードできません。 このポリシー設定を構成しない場合は、信頼されていない発行元によって署名されたコントロールをダウンロードするかどうかをユーザーにたずねます。 信頼できる発行元によって署名されたコードは、警告なしでダウンロードされます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067064)

  **既定値**:無効化

- **[Internet Explorer restricted zone smart screen]\(Internet Explorer の制限付きゾーンのスマート スクリーン\)** :  
  このポリシー設定では、SmartScreen フィルターを使用して、このゾーンのページで悪意のあるコンテンツをスキャンするかどうかが制御されます。 このポリシー設定を有効にすると、SmartScreen フィルターによってこのゾーンのページで悪意のあるコンテンツがスキャンされます。 このポリシー設定を無効にすると、SmartScreen フィルターはこのゾーンのページの悪意のあるコンテンツをスキャンしません。 このポリシー設定を構成しない場合、SmartScreen フィルターがこのゾーンのページの悪意のあるコンテンツをスキャンするかどうかをユーザーが選択できます。 注:Internet Explorer 7 の場合、このポリシー設定では、フィッシング詐欺検出機能がこのゾーンのページの悪意のあるコンテンツをスキャンするかどうかを制御します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067034)

  **既定値**:Enabled

- **[Internet Explorer remove run this time button for outdated Active X controls]\(Internet Explorer で古い Active X コントロール用の [今回は実行] ボタンを削除する\)** :  
  このポリシー設定を使用すると、Internet Explorer で [今回は実行] ボタンが表示されないようにして、ユーザーが特定の古い ActiveX コントロールを実行できないようにすることができます。 このポリシー設定を有効にした場合、Internet Explorer で古い ActiveX コントロールがブロックされるときに表示される警告メッセージに [今回は実行] ボタンが表示されなくなります。 このポリシー設定を無効にした場合、または構成しなかった場合、Internet Explorer で古い ActiveX コントロールがブロックされるときに表示される警告メッセージに [今回は実行] ボタンが表示されます。 このボタンをクリックすると、ユーザーは古い ActiveX コントロールを 1 回実行できます。 詳細については、Internet Explorer TechNet ライブラリの古い ActiveX コントロールに関するページを参照してください。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067123)

  **既定値**:Enabled

- **[Internet Explorer internet zone launch applications and files in an iframe]\(Internet Explorer のインターネット ゾーンで IFRAME のアプリケーションとファイルを起動する\)** :  
  このポリシー設定を使用すると、このゾーン内のページの HTML にある IFRAME 参照からアプリケーションを実行したりファイルをダウンロードしたりすることができるかどうかを管理できます。 このポリシー設定を有効にすると、ユーザーは、何もしなくても、このゾーンのページ上の IFRAME からアプリケーションを実行したりファイルをダウンロードしたりできます。 ドロップダウン ボックスで [ダイアログを表示する] を選択すると、ユーザーは、このゾーンのページ上の IFRAME からアプリケーションを実行したりファイルをダウンロードしたりするかどうかの確認を求められます。 このポリシー設定を無効にすると、ユーザーはこのゾーンにあるページ上の IFRAME からアプリケーションを実行したりファイルをダウンロードしたりすることができません。 このポリシー設定を構成しない場合は、このゾーンにあるページ上の IFRAME からアプリケーションを実行したりファイルをダウンロードしたりするかどうかをユーザーにたずねます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067020)

  **既定値**:無効化

- **[Internet Explorer restricted zone navigate windows and frames across different domains]\(Internet Explorer の制限付きゾーンで異なるドメインを超えてウィンドウとフレームを移動する\)** :  
  このポリシー設定を使用すると、移動元と移動先が異なるウィンドウにあるときに、あるドメインから別のドメインにコンテンツをドラッグするオプションを設定できます。 このポリシー設定を有効にして [有効にする] をクリックすると、ユーザーは移行元と移行先が異なるウィンドウにある場合、あるドメインから別のドメインにコンテンツをドラッグすることができます。 この設定はユーザーが変更できません。 このポリシー設定を有効にして [無効にする] をクリックすると、ユーザーは移行元と移行先が異なるウィンドウにある場合、あるドメインから別のドメインにコンテンツをドラッグできません。 この設定はユーザーが変更できません。 Internet Explorer 10 では、このポリシー設定を無効にする場合、または構成しない場合、[有効にする] をクリックすると、ユーザーは移行元と移行先が異なるウィンドウの場合、あるドメインから別のドメインにコンテンツをドラッグできません。 ユーザーは、[インターネット オプション] ダイアログでこの設定を変更できます。 Internet Explorer 9 以前のバージョンでは、このポリシーを無効にする場合、または構成しない場合は、ユーザーは移行元と移行先が異なるウィンドウの場合、あるドメインから別のドメインにコンテンツをドラッグすることができます。 この設定はユーザーが変更できません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067050)

  **既定値**:無効化

- **[Internet Explorer internet zone smart screen]\(Internet Explorer のインターネット ゾーンのスマート スクリーン\)** :  
  このポリシー設定では、SmartScreen フィルターを使用して、このゾーンのページで悪意のあるコンテンツをスキャンするかどうかが制御されます。 このポリシー設定を有効にすると、SmartScreen フィルターによってこのゾーンのページで悪意のあるコンテンツがスキャンされます。 このポリシー設定を無効にすると、SmartScreen フィルターはこのゾーンのページの悪意のあるコンテンツをスキャンしません。 このポリシー設定を構成しない場合、SmartScreen フィルターがこのゾーンのページの悪意のあるコンテンツをスキャンするかどうかをユーザーが選択できます。 注:Internet Explorer 7 の場合、このポリシー設定では、フィッシング詐欺検出機能がこのゾーンのページの悪意のあるコンテンツをスキャンするかどうかを制御します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067047)

  **既定値**:Enabled

- **[Internet Explorer locked down trusted zone java permissions]\(Internet Explorer のロックダウンされた信頼済みゾーンでの Java のアクセス許可\)** :  
  このポリシー設定を使用すると、Java アプレットのアクセス許可を管理できます。 このポリシー設定を有効にすると、オプションをドロップダウン ボックスから選択できます。 アクセス許可の設定を個々に制御するには [カスタム] を選択します。 [安全性 - 低] を選択すると、アプレットはすべての操作を実行できます。 [安全性 - 中] を選択すると、アプレットはサンドボックス (メモリ内の領域で、その外側にはプログラムは呼び出しを実行できない) 内で実行されます。また、スクラッチ領域 (クライアント コンピューター内の安全でセキュリティで保護された記憶域) やユーザーによって制御されたファイル I/O などの機能が利用できます。 [安全性 - 高] を選択すると、アプレットはサンドボックス内で実行されます。 アプレットが実行されないようにするには、[Java を無効にする] を選択します。 このポリシー設定を無効にすると、Java アプレットは実行されません。 このポリシー設定を構成しなかった場合、Java アプレットは無効になります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067142)

  **既定値**:Java を無効にする

- **[Internet Explorer check signatures on downloaded programs]\(Internet Explorer でダウンロードされたプログラムの署名を確認する\)** :  
  このポリシー設定を使用すると、実行可能プログラムをダウンロードする前に、ユーザーのコンピューターでデジタル署名を確認するかどうか (署名されたソフトウェアの発行者を識別し、変更または改ざんされていないことを確認します) を管理できます。 このポリシー設定を有効にすると、ユーザーのコンピューターに実行可能プログラムをダウンロードする前に、プログラムのデジタル署名が確認され、識別情報が表示されます。 このポリシー設定を無効にすると、コンピューターに実行可能プログラムをダウンロードする前に、プログラムのデジタル署名の確認や識別情報の表示を行いません。 このポリシー設定を構成しなかった場合、コンピューターに実行可能プログラムをダウンロードする前に、プログラムのデジタル署名の確認や識別情報の表示を行いません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067051)

  **既定値**:Enabled

- **[Internet Explorer restricted zone scripting of web browser controls]\(Internet Explorer の制限付きゾーンでの Web ブラウザー コントロールのスクリプト化\)** :  
  このポリシー設定では、スクリプトによる埋め込み WebBrowser コントロールをページで制御できるかどうかが決定されます。 このポリシー設定を有効にすると、WebBrowser コントロールへのスクリプト アクセスが許可されます。 このポリシー設定を無効にすると、WebBrowser コントロールへのスクリプト アクセスは許可されません。 このポリシー設定を構成しなかった場合、ユーザーは WebBrowser コントロールへのスクリプト アクセスを有効または無効にできます。 既定では、WebBrowser コントロールへのスクリプト アクセスは、ローカル コンピューターとイントラネット ゾーンでのみ許可されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067098)

  **既定値**:無効

- **[Internet Explorer restricted zone cross site scripting filter]\(Internet Explorer の制限付きゾーンのクロスサイト スクリプト フィルター\)** :  
  このポリシーでは、クロスサイト スクリプト (XSS) フィルターがこのゾーン内の Web サイトにあるクロスサイト スクリプト インジェクションを検出して防止するかどうかを制御します。 このポリシー設定を有効にすると、XSS フィルターはこのゾーン内のサイトに対して有効になり、クロスサイト スクリプト インジェクションのブロックを試みます。 このポリシー設定を無効にすると、XSS フィルターがこのゾーン内のサイトに対して無効になり、Internet Explorer でクロスサイト スクリプト インジェクションが許可されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067178)

  **既定値**:Enabled

- **[Internet Explorer restricted zone binary and script behaviors]\(Internet Explorer の制限付きゾーンでのバイナリ ビヘイビアーとスクリプト ビヘイビアー\)** :  
  このポリシー設定を使用すると、動的なバイナリ ビヘイビアーとスクリプト ビヘイビアー (動作が関連付けられた HTML 要素のための特定の機能をカプセル化するコンポーネント) を管理できます。 このポリシー設定を有効にすると、バイナリ ビヘイビアーとスクリプト ビヘイビアーを利用できます。 ドロップダウン ボックスで [管理者の許可済み] を選択した場合、バイナリ ビヘイビアーのセキュリティ制限ポリシーで管理者によって許可されたビヘイビアーに一覧表示されているビヘイビアーのみを利用できます。 このポリシー設定を無効にした場合、アプリケーションがカスタムのセキュリティ マネージャーを実装していない限り、バイナリ ビヘイビアーとスクリプト ビヘイビアーは利用できません。 このポリシー設定を構成しない場合は、アプリケーションがカスタムのセキュリティ マネージャーを実装していない限り、バイナリ ビヘイビアーとスクリプト ビヘイビアーは利用できません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067224)

  **既定値**:無効化

- **[Internet Explorer security settings check]\(Internet Explorer のセキュリティ設定のチェック\)** :  
  このポリシー設定では、セキュリティ設定チェック機能が無効になります。この機能では、Internet Explorer のセキュリティ設定がチェックされて、いつ Internet Explorer が危険にさらされる設定になっているか判別されます。 このポリシー設定を有効にすると、機能は無効になります。 このポリシー設定を無効にするか、構成しない場合、機能は有効になります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067182)

  **既定値**:Enabled

- **[Internet Explorer internet zone security warning for potentially unsafe files]\(Internet Explorer のインターネット ゾーンでの安全でない可能性があるファイルに対するセキュリティ警告\)** :  
  このポリシー設定では、ユーザーが (たとえば、エクスプローラーを使用してイントラネット ファイル共有から) 実行可能ファイルまたはその他の安全でない可能性があるファイルを開こうとしたときに、"ファイルを開く - セキュリティ警告" というメッセージが表示されるかどうかを制御します。 このポリシー設定を有効にして、ドロップダウン ボックスを [有効にする] に設定した場合、このようなファイルを開くときにセキュリティ警告は表示されません。 ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、ファイルを開く前にセキュリティ警告が表示されます。 このポリシー設定を無効にした場合、そうしたファイルは開きません。 このポリシー設定を構成しなかった場合、ユーザーがそうしたファイルの処理方法を構成できます。 既定では、このようなファイルは制限付きゾーンではブロックされ、イントラネット ゾーンとローカル コンピューター ゾーンでは有効になり、インターネット ゾーンと信頼済みゾーンではメッセージを表示するように設定されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067204)

  **既定値**:ダイアログを表示する

- **[Internet Explorer intranet zone java permissions]\(Internet Explorer のイントラネット ゾーンでの Java のアクセス許可\)** :  
  このポリシー設定を使用すると、Java アプレットのアクセス許可を管理できます。 このポリシー設定を有効にすると、オプションをドロップダウン ボックスから選択できます。 アクセス許可の設定を個々に制御するには [カスタム] を選択します。 [安全性 - 低] を選択すると、アプレットはすべての操作を実行できます。 [安全性 - 中] を選択すると、アプレットはサンドボックス (メモリ内の領域で、その外側にはプログラムは呼び出しを実行できない) 内で実行されます。また、スクラッチ領域 (クライアント コンピューター内の安全でセキュリティで保護された記憶域) やユーザーによって制御されたファイル I/O などの機能が利用できます。 [安全性 - 高] を選択すると、アプレットはサンドボックス内で実行されます。 アプレットが実行されないようにするには、[Java を無効にする] を選択します。 このポリシー設定を無効にすると、Java アプレットは実行されません。 このポリシー設定を構成しない場合は、アクセス許可は [安全性 - 中] に設定されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067206)

  **既定値**:安全性 - 高

- **[Internet Explorer で古い Active X コントロールをブロックする]** :  
  このポリシー設定では、Internet Explorer で特定の古い ActiveX コントロールをブロックするかどうかを決定します。 イントラネット ゾーンでは、古い ActiveX コントロールがブロックされません。 このポリシー設定を有効にした場合、Internet Explorer では、古い ActiveX コントロールのブロックが停止します。 このポリシー設定を無効にした場合、または構成しなかった場合、Internet Explorer では、引き続き特定の古い ActiveX コントロールがブロックされます。 詳細については、Internet Explorer TechNet ライブラリの古い ActiveX コントロールに関するページを参照してください。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067203)

  **既定値**:Enabled

- **[Internet Explorer restricted zone popup blocker]\(Internet Explorer の制限付きゾーンでのポップアップ ブロック\)** :  
  このポリシー設定を使用すると、不要なポップアップ ウィンドウが表示されるかどうかを管理できます。 エンド ユーザーがリンクをクリックしたときに開かれるポップアップ ウィンドウはブロックされません。 このポリシー設定を有効にすると、不要なポップアップ ウィンドウは表示されません。 このポリシー設定を無効にすると、ポップアップ ウィンドウの表示は禁止されません。 このポリシー設定を構成しない場合は、不要なポップアップ ウィンドウは表示されません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067180)

  **既定値**:[ウェイクアップ時間 (デスクトップ コンピューター)] を有効にして、デスクトップ コンピューターが、スケジュールされた更新またはソフトウェアのインストールを実行するために、スリープ状態または休止状態から復帰する時刻を指定します。

- **[Internet Explorer processes MK protocol security restriction]\(Internet Explorer プロセスでの MK プロトコル セキュリティの制限\)** :  
  MK プロトコル セキュリティの制限のポリシー設定を使用すると、MK プロトコルを使用不可にすることで危険を回避できます。 MK プロトコルでホストされているリソースはエラーになります。 このポリシー設定を有効にすると、エクスプローラーおよび Internet Explorer で MK プロトコルが使用不可になり、MK プロトコルでホストされているリソースはエラーになります。 このポリシー設定を無効にすると、アプリケーションで MK プロトコル API を使用できます。 MK プロトコルでホストされているリソースは、エクスプローラーおよび Internet Explorer のプロセスで機能します。 このポリシー設定を構成しない場合は、エクスプローラーおよび Internet Explorer で MK プロトコルが使用不可になり、MK プロトコルでホストされているリソースはエラーになります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067179)

  **既定値**:Enabled

- **[Internet Explorer の信頼済みゾーンでの Java のアクセス許可]** :  
  このポリシー設定を使用すると、Java アプレットのアクセス許可を管理できます。 このポリシー設定を有効にすると、オプションをドロップダウン ボックスから選択できます。 アクセス許可の設定を個々に制御するには [カスタム] を選択します。 [安全性 - 低] を選択すると、アプレットはすべての操作を実行できます。 [安全性 - 中] を選択すると、アプレットはサンドボックス (メモリ内の領域で、その外側にはプログラムは呼び出しを実行できない) 内で実行されます。また、スクラッチ領域 (クライアント コンピューター内の安全でセキュリティで保護された記憶域) やユーザーによって制御されたファイル I/O などの機能が利用できます。 [安全性 - 高] を選択すると、アプレットはサンドボックス内で実行されます。 アプレットが実行されないようにするには、[Java を無効にする] を選択します。 このポリシー設定を無効にすると、Java アプレットは実行されません。 このポリシー設定を構成しなかった場合、アクセス許可は [安全性 - 低] に設定されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067200)

  **既定値**:安全性 - 高

- **[Internet Explorer restricted zone scripting of java applets]\(Internet Explorer の制限付きゾーンでの Java アプレットのスクリプト化\)** :  
  このポリシー設定を使用すると、ゾーン内のスクリプトにアプレットを公開するかどうかを管理できます。 このポリシー設定を有効にすると、ユーザーによる手動操作を必要とすることなく、スクリプトはアプレットに自動的にアクセスできます。 ドロップダウンボックスで [ダイアログを表示する] を選択すると、ユーザーはスクリプトにアプレットへのアクセスを許可するかどうかの確認を求められます。 このポリシー設定を無効にすると、スクリプトはアプレットにアクセスできません。 このポリシー設定を構成しなかった場合、スクリプトはアプレットにアクセスできません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067202)

  **既定値**:無効化

- **[Internet Explorer のロックダウンされた制限付きゾーンでの Java のアクセス許可]** :  
  このポリシー設定を使用すると、Java アプレットのアクセス許可を管理できます。 このポリシー設定を有効にすると、オプションをドロップダウン ボックスから選択できます。 アクセス許可の設定を個々に制御するには [カスタム] を選択します。 [安全性 - 低] を選択すると、アプレットはすべての操作を実行できます。 [安全性 - 中] を選択すると、アプレットはサンドボックス (メモリ内の領域で、その外側にはプログラムは呼び出しを実行できない) 内で実行されます。また、スクラッチ領域 (クライアント コンピューター内の安全でセキュリティで保護された記憶域) やユーザーによって制御されたファイル I/O などの機能が利用できます。 [安全性 - 高] を選択すると、アプレットはサンドボックス内で実行されます。 アプレットが実行されないようにするには、[Java を無効にする] を選択します。 このポリシー設定を無効にすると、Java アプレットは実行されません。 このポリシー設定を構成しなかった場合、Java アプレットは無効になります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067181)

  **既定値**:Java を無効にする

- **[Internet Explorer のインターネット ゾーンで承認済みドメインだけが ActiveX コントロールを使用できるようにする]** :  
  このポリシー設定では、ActiveX コントロールをインストールした Web サイト以外の Web サイトで ActiveX コントロールを実行する許可を求めるメッセージをユーザーに表示するかどうかを制御します。 このポリシー設定を有効にすると、このゾーン内の Web サイトから ActiveX コントロールが実行される前に、ユーザーにメッセージが表示されます。 ユーザーは、コントロールの実行を現在のサイトだけに許可するか、すべてのサイトに許可するかを選択できます。 このポリシー設定を無効にすると、ユーザーにはサイトごとの ActiveX 警告は表示されず、ActiveX コントロールはこのゾーン内のすべてのサイトから実行できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067091)

  **既定値**:Enabled

- **[Internet Explorer include all network paths]\(Internet Explorer ですべてのネットワーク パスを含める\)** :  
  Internet Explorer にはすべてのネットワーク パスが含まれます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067090)

  **既定値**:無効

- **[Internet Explorer internet zone protected mode]\(Internet Explorer のインターネット ゾーンの保護モード\)** :  
  このポリシー設定を使用すると、保護モードを有効にできます。 保護モードを使用すると、Internet Explorer が書き込むことができるレジストリやファイル システム内の場所を制限することで、脆弱性を悪用した攻撃から Internet Explorer を保護できます。 このポリシー設定を有効にすると、保護モードが有効になります。 ユーザーは保護モードを無効にできません。 このポリシー設定を無効にすると、保護モードが無効になります。 ユーザーは保護モードを有効にできません。 このポリシー設定を構成しなかった場合、ユーザーは保護モードを有効または無効にできます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067171)

  **既定値**:[ウェイクアップ時間 (デスクトップ コンピューター)] を有効にして、デスクトップ コンピューターが、スケジュールされた更新またはソフトウェアのインストールを実行するために、スリープ状態または休止状態から復帰する時刻を指定します。

- **[Internet Explorer internet zone initialize and script Active X controls not marked as safe]\(Internet Explorer のインターネット ゾーンで安全であるとマークされていない Active X コントロールを初期化およびスクリプト化する\)** :  
  このポリシー設定を使用すると、安全とマークされていない ActiveX コントロールを管理できます。 このポリシー設定を有効にすると、ActiveX コントロールがパラメーターを読み込んで実行され、また、信頼されていないデータまたはスクリプトに対するオブジェクトの安全性を設定することなくスクリプト化されます。 この設定は、安全でかつ管理されたゾーン以外では推奨しません。 この設定により、安全でないコントロールと安全なコントロールの両方が初期化されてスクリプト化され、スクリプト実行オプションで安全とマークされた Script ActiveX コントロールは無視されます。 このポリシー設定を有効にして、ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、コントロールにパラメーターを読み込んだりスクリプト化したりすることを許可するかどうかをユーザーにたずねます。 このポリシー設定を無効にすると、安全であるとマークできない ActiveX コントロールにパラメーターを読み込んだりスクリプト化したりすることはできません。 このポリシー設定を構成しなかった場合、安全であるとマークできない ActiveX コントロールにパラメーターを読み込んだりスクリプト化したりすることはできません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067170)

  **既定値**:無効化

- **[Internet Explorer のロックダウンされた制限付きゾーンでのスマート スクリーン]** :  
  このポリシー設定では、SmartScreen フィルターを使用して、このゾーンのページで悪意のあるコンテンツをスキャンするかどうかが制御されます。 このポリシー設定を有効にすると、SmartScreen フィルターによってこのゾーンのページで悪意のあるコンテンツがスキャンされます。 このポリシー設定を無効にすると、SmartScreen フィルターはこのゾーンのページの悪意のあるコンテンツをスキャンしません。 このポリシー設定を構成しない場合、SmartScreen フィルターがこのゾーンのページの悪意のあるコンテンツをスキャンするかどうかをユーザーが選択できます。 注:Internet Explorer 7 の場合、このポリシー設定では、フィッシング詐欺検出機能がこのゾーンのページの悪意のあるコンテンツをスキャンするかどうかを制御します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067092)

  **既定値**:Enabled

- **[Internet Explorer crash detection]\(Internet Explorer のクラッシュの検出\)** :  
  このポリシー設定を使用すると、アドオン管理のクラッシュ検出機能を管理できます。 このポリシー設定を有効にすると、Internet Explorer でクラッシュが起きた場合、Windows XP Professional Service Pack 1 またはそれ以前の場合と同様に、Windows エラー報告が起動されます。 Windows エラー報告のポリシー設定はすべて引き続き適用されます。 このポリシー設定を無効にするか、または構成しない場合は、アドオン管理のクラッシュ検出機能は動作します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067094)

  **既定値**:無効

- **[Internet Explorer internet zone java permissions]\(Internet Explorer のインターネット ゾーンでの Java のアクセス許可\)** :  
  このポリシー設定を使用すると、Java アプレットのアクセス許可を管理できます。 このポリシー設定を有効にすると、オプションをドロップダウン ボックスから選択できます。 アクセス許可の設定を個々に制御するには [カスタム] を選択します。 [安全性 - 低] を選択すると、アプレットはすべての操作を実行できます。 [安全性 - 中] を選択すると、アプレットはサンドボックス (メモリ内の領域で、その外側にはプログラムは呼び出しを実行できない) 内で実行されます。また、スクラッチ領域 (クライアント コンピューター内の安全でセキュリティで保護された記憶域) やユーザーによって制御されたファイル I/O などの機能が利用できます。 [安全性 - 高] を選択すると、アプレットはサンドボックス内で実行されます。 アプレットが実行されないようにするには、[Java を無効にする] を選択します。 このポリシー設定を無効にすると、Java アプレットは実行されません。 このポリシー設定を構成しない場合は、アクセス許可は [安全性 - 高] に設定されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067174)

  **既定値**:Java を無効にする

- **[Internet Explorer restricted zone active scripting]\(Internet Explorer の制限付きゾーンでのアクティブ スクリプティング\)** :  
  このポリシー設定を使用すると、ゾーン内のページ上のスクリプト コードを実行するかどうかを管理できます。 このポリシー設定を有効にすると、ゾーン内のページ上のスクリプト コードを自動的に実行できます。 ドロップダウン ボックスで [ダイアログを表示する] を選択すると、ゾーン内のページ上のスクリプト コードの実行を許可するかどうかをユーザーに確認するメッセージが表示されます。 このポリシー設定を無効にすると、ゾーン内のページ上のスクリプト コードは実行されません。 このポリシー設定を構成しない場合は、ゾーンのページ上のスクリプト コードは実行されません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067172)

  **既定値**:無効化

- **[Internet Explorer internet zone logon options]\(Internet Explorer のインターネット ゾーンのログオン オプション\)** :  
  このポリシー設定を使用すると、サインイン オプションの設定を管理できます。 このポリシー設定を有効にすると、次のサインイン オプションから選択できます。 HTTP 認証を無効にして、Common Internet File System (CIFS) プロトコル用にのみ guest アカウントを使用する場合は、[匿名ログオン] を選択してください。 ユーザーの ID とパスワードを照会するために、ユーザー名とパスワードの入力を求めるメッセージが表示されます。 ユーザーに入力を求めた後、これらの値は残りのセッションで確認なしに使用されます。 他のゾーンでユーザーの ID とパスワードを照会するには [イントラネット ゾーンでのみ自動ログオンを許可する] を選択してください。 ユーザーが照会された後に、これらの値は残りのセッションで警告なしに使用されます。 現在のユーザー名とパスワードで自動的にサインインし、Windows NT チャレンジ応答 (別名 NTLM 認証) を使用してログオンを試みます。 サーバーで Windows NT チャレンジ応答がサポートされている場合、サインインでは、ユーザーのログオン用のネットワーク ユーザー名とパスワードが使用されます。 サーバーで Windows NT チャレンジ応答がサポートされていない場合、ユーザーはユーザー名とパスワードを提供する必要があります。 このポリシー設定を無効にすると、サインインは [イントラネット ゾーンでのみ自動ログオンを許可する] に設定されます。 このポリシー設定を構成しない場合、サインインは [イントラネット ゾーンでのみ自動的にサインインする] に設定されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067194)

  **既定値**:ダイアログを表示する

- **[Internet Explorer の制限付きゾーンで VB スクリプトの実行を許可する]** :  
  このポリシー設定を使用すると、Internet Explorer 内の指定されたゾーンのページ上で VB スクリプトを実行できるかどうかを管理できます。 ドロップダウン ボックスで [有効にする] を選択すると、ユーザーによる手動操作を必要とすることなく、VB スクリプトを実行できます。 ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、ユーザーは VB スクリプトの実行を許可するかどうかをたずねられます。 ドロップダウン ボックスで [無効にする] を選択した場合、VB スクリプトは実行されません。 このポリシー設定を構成しなかった場合、または無効にした場合、VB スクリプトは実行されません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067173)

  **既定値**:無効化

- **[Internet Explorer internet zone drag content from different domains across windows]\(Internet Explorer のインターネット ゾーンでウィンドウを超えて異なるドメインからコンテンツをドラッグする\)** :  
  このポリシー設定を使用すると、移動元と移動先が異なるウィンドウにあるときに、あるドメインから別のドメインにコンテンツをドラッグするオプションを設定できます。 このポリシー設定を有効にして [有効にする] をクリックすると、ユーザーは移行元と移行先が異なるウィンドウにある場合、あるドメインから別のドメインにコンテンツをドラッグすることができます。 この設定はユーザーが変更できません。 このポリシー設定を有効にして [無効にする] をクリックすると、ユーザーは移行元と移行先が異なるウィンドウにある場合、あるドメインから別のドメインにコンテンツをドラッグできません。 この設定はユーザーが変更できません。 Internet Explorer 10 では、このポリシー設定を無効にする場合、または構成しない場合、[有効にする] をクリックすると、ユーザーは移行元と移行先が異なるウィンドウの場合、あるドメインから別のドメインにコンテンツをドラッグできません。 ユーザーは、[インターネット オプション] ダイアログでこの設定を変更できます。 Internet Explorer 9 以前のバージョンでは、このポリシーを無効にする場合、または構成しない場合は、ユーザーは移行元と移行先が異なるウィンドウの場合、あるドメインから別のドメインにコンテンツをドラッグすることができます。 この設定はユーザーが変更できません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067093)

  **既定値**:無効

- **[Internet Explorer intranet zone initialize and script Active X controls not marked as safe]\(Internet Explorer のイントラネット ゾーンで安全であるとマークされていない Active X コントロールを初期化およびスクリプト化する\)** :  
  このポリシー設定を使用すると、安全とマークされていない ActiveX コントロールを管理できます。 このポリシー設定を有効にすると、ActiveX コントロールがパラメーターを読み込んで実行され、また、信頼されていないデータまたはスクリプトに対するオブジェクトの安全性を設定することなくスクリプト化されます。 この設定は、安全でかつ管理されたゾーン以外では推奨しません。 この設定により、安全でないコントロールと安全なコントロールの両方が初期化されてスクリプト化され、スクリプト実行オプションで安全とマークされた Script ActiveX コントロールは無視されます。 このポリシー設定を有効にして、ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、コントロールにパラメーターを読み込んだりスクリプト化したりすることを許可するかどうかをユーザーにたずねます。 このポリシー設定を無効にすると、安全であるとマークできない ActiveX コントロールにパラメーターを読み込んだりスクリプト化したりすることはできません。 このポリシー設定を構成しなかった場合、安全であるとマークできない ActiveX コントロールにパラメーターを読み込んだりスクリプト化したりすることはできません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067175)

  **既定値**:無効化

- **[Internet Explorer download enclosures]\(Internet Explorer での添付ファイルのダウンロード\)** :  
  このポリシー設定では、ユーザーがエンクロージャ (添付ファイル) をフィードからユーザーのコンピューターにダウンロードできないようにします。 このポリシー設定を有効にすると、フィードのプロパティ ページで、フィード同期エンジンが添付ファイルをダウンロードするように設定できません。 開発者は、フィードの API を使用してダウンロード設定を変更できません。 このポリシー設定を無効にするか、構成しない場合、フィードのプロパティ ページで、フィード同期エンジンが添付ファイルをダウンロードするように設定できます。 開発者は、フィードの API を使用してダウンロードの設定を変更できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067245)

  **既定値**:無効

- **[Internet Explorer restricted zone download unsigned Active X controls]\(Internet Explorer の制限付きゾーンで署名されていない Active X コントロールをダウンロードする\)** :  
  このポリシー設定を使用すると、ユーザーがゾーンから署名されていない ActiveX コントロールをダウンロードできるかどうかを管理できます。 このようなコードは害を及ぼす危険があり、信頼されていないゾーンのものの場合は特にそうです。 このポリシー設定を有効にすると、ユーザーは、何もしなくても、署名されていないコントロールを実行できます。 ドロップダウン ボックスで [ダイアログを表示する] を選択すると、署名されていないコントロールの実行を許可するかどうかをユーザーに確認するメッセージが表示されます。 このポリシー設定を無効にすると、ユーザーは署名されていないコントロールを実行できません。 このポリシー設定を構成しない場合、ユーザーは署名されていないコントロールを実行できません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067177)

  **既定値**:無効化

- **[Internet Explorer internet zone drag content from different domains within windows]\(Internet Explorer のインターネット ゾーンでウィンドウ内の異なるドメインからコンテンツをドラッグする\)** :  
  このポリシー設定を使用すると、ユーザーがゾーンから署名されていない ActiveX コントロールをダウンロードできるかどうかを管理できます。 このようなコードは害を及ぼす危険があり、信頼されていないゾーンのものの場合は特にそうです。 このポリシー設定を有効にすると、ユーザーは、何もしなくても、署名されていないコントロールを実行できます。 ドロップダウン ボックスで [ダイアログを表示する] を選択すると、署名されていないコントロールの実行を許可するかどうかをユーザーに確認するメッセージが表示されます。 このポリシー設定を無効にすると、ユーザーは署名されていないコントロールを実行できません。 このポリシー設定を構成しない場合、ユーザーは署名されていないコントロールを実行できません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067095)

  **既定値**:無効

- **[Internet Explorer プロセスで Active X インストールを制限する]** :  
  このポリシー設定を使用すると、Web ブラウザー コントロールをホストしているアプリケーションで、ActiveX コントロール インストールの自動的な確認ダイアログをブロックできます。 このポリシー設定を有効にすると、ActiveX コントロール インストールの確認ダイアログの自動表示はすべてのプロセスにおいて Web ブラウザー コントロールによってブロックされます。 このポリシー設定を無効にするか、または構成しない場合は、ActiveX コントロール インストールの確認ダイアログの自動表示はすべてのプロセスにおいて Web ブラウザー コントロールによってブロックされません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067250)

  **既定値**:Enabled

- **[Internet Explorer インターネット ゾーンでのスクリプトレット]** :  
  このポリシー設定を使用すると、ユーザーがスクリプトレットを実行できるかどうかを管理できます。 このポリシー設定を有効にすると、ユーザーはスクリプトレットを実行できます。 このポリシー設定を無効にすると、ユーザーはスクリプトレットを実行できません。 このポリシー設定を構成しなかった場合、ユーザーはスクリプトレットを有効または無効にできます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067176)

  **既定値**:無効化

- **[Internet Explorer restricted zone drag and drop or copy and paste files]\(Internet Explorer の制限付きゾーンでファイルのドラッグ アンド ドロップまたはコピーと貼り付けを行う\)** :  
  このポリシー設定を使用すると、ユーザーがゾーン内のソースからファイルのドラッグまたはファイルのコピーと貼り付けを行うことができるかどうかを管理できます。 このポリシー設定を有効にすると、自動的に、ユーザーはこのゾーンからファイルをドラッグしたり、ファイルをコピーして貼り付けたりできます。 ドロップダウン ボックスで [ダイアログを表示する] を選択すると、ユーザーは、このゾーンからファイルをドラッグまたはコピーするかどうかの選択を求められます。 このポリシー設定を無効にすると、ユーザーはこのゾーンからファイルをドラッグしたり、ファイルをコピーして貼り付けたりできません。 このポリシー設定を構成しない場合は、このゾーンからファイルをドラッグまたはコピーするかどうかをユーザーにたずねます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067096)

  **既定値**:無効化

- **[Internet Explorer software when signature is invalid]\(Internet Explorer での署名が無効な場合のソフトウェア\)** :  
  このポリシー設定を使用すると、署名が無効な場合でもユーザーがソフトウェア (ActiveX コントロールやファイル ダウンロードなど) をインストールまたは実行できるかどうかを管理できます。 署名が無効である場合、そのファイルをだれかが改ざんした可能性があります。 このポリシー設定を有効にすると、ユーザーが無効な署名を持つファイルをインストールまたは実行するときにダイアログが表示されます。 このポリシー設定を無効にすると、ユーザーは無効な署名を持つファイルを実行したりインストールしたりすることはできません。 このポリシーを構成しなかった場合は、ユーザーは無効な署名を持つファイルを実行またはインストールするかどうかを選択できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067201)

  **既定値**:無効

- **[Internet Explorer restricted zone copy and paste via script]\(Internet Explorer の制限付きゾーンでのスクリプトによるコピーと貼り付け\)** :  
  このポリシー設定を使用すると、指定された領域でスクリプトがクリップボードの操作 (例: 切り取り、コピー、貼り付け) を実行できるかどうかを管理できます。 このポリシー設定を有効にすると、スクリプトによりクリップボードの操作を実行できます。 ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、クリップボードの操作を実行するかどうかがユーザーにたずねられます。 このポリシー設定を無効にすると、スクリプトによってクリップボードの操作は実行されません。 このポリシー設定を構成しなかった場合、スクリプトはクリップボードの操作を実行できません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067165)

  **既定値**:無効化

- **[Internet Explorer restricted zone drag content from different domains across windows]\(Internet Explorer の制限付きゾーンでウィンドウを超えて異なるドメインからコンテンツをドラッグする\)** :  
  このポリシー設定を使用すると、移動元と移動先が異なるウィンドウにあるときに、あるドメインから別のドメインにコンテンツをドラッグするオプションを設定できます。 このポリシー設定を有効にして [有効にする] をクリックすると、ユーザーは移行元と移行先が異なるウィンドウにある場合、あるドメインから別のドメインにコンテンツをドラッグすることができます。 この設定はユーザーが変更できません。 このポリシー設定を有効にして [無効にする] をクリックすると、ユーザーは移行元と移行先が異なるウィンドウにある場合、あるドメインから別のドメインにコンテンツをドラッグできません。 この設定はユーザーが変更できません。 Internet Explorer 10 では、このポリシー設定を無効にする場合、または構成しない場合、[有効にする] をクリックすると、ユーザーは移行元と移行先が異なるウィンドウの場合、あるドメインから別のドメインにコンテンツをドラッグできません。 ユーザーは、[インターネット オプション] ダイアログでこの設定を変更できます。 Internet Explorer 9 以前のバージョンでは、このポリシーを無効にする場合、または構成しない場合は、ユーザーは移行元と移行先が異なるウィンドウの場合、あるドメインから別のドメインにコンテンツをドラッグすることができます。 この設定はユーザーが変更できません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067166)

  **既定値**:無効

- **[Internet Explorer のユーザーによるサイトの追加]** :  
  ユーザーがセキュリティ ゾーンのサイトを追加または削除できないようにします。 セキュリティ ゾーンはセキュリティ レベルが同じ Web サイトのグループです。 このポリシーを有効にすると、セキュリティ ゾーンのサイト管理設定が無効になります。 (セキュリティ ゾーンのサイト管理設定を表示するには、[インターネット オプション] ダイアログ ボックスで、[セキュリティ] タブをクリックし、[サイト] ボタンをクリックします)。このポリシーを無効にするか、構成しない場合、ユーザーは [信頼済みサイト] および [制限付きサイト] ゾーンに対して Web サイトの追加と削除を行うことができます。また、[ローカル イントラネット] ゾーンの設定を変更できます。 このポリシーにより、管理者が設定したセキュリティ ゾーンのサイト管理設定をユーザーは変更できなくなります。 注:このポリシーよりも優先される [[セキュリティ] ページの使用を許可しない] ポリシー (場所: \ユーザーの構成\管理用テンプレート\Windows コンポーネント\Internet Explorer\インターネット コントロール パネル) を有効にすると、インターフェイスから [セキュリティ] タブが削除され、 それが有効になっている場合、このポリシーは無視されます。 "セキュリティ ゾーン: コンピューターの設定のみ使用する" ポリシーも参照してください。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067167)

  **既定値**:無効

- **[Internet Explorer のインターネット ゾーンのスクリプトによって開かれるウィンドウ]** :  
  このポリシー設定を使用すると、スクリプトによって開始されるポップアップ ウィンドウや、タイトルとステータス バーが含まれるウィンドウに対する制限を管理できます。 このポリシー設定を有効にすると、Windows Restrictions セキュリティはこのゾーンでは適用されません。 セキュリティ ゾーンは、この機能で提供されるセキュリティの追加レイヤーなしに実行されます。 このポリシー設定を無効にすると、スクリプトによって起動されたポップアップ ウィンドウや、タイトルとステータス バーを含むウィンドウに含まれる、危害を及ぼす可能性のある動作は実行されません。 この Internet Explorer のセキュリティ機能は、プロセスの [スクリプト化されたウィンドウのセキュリティ制限] 機能コントロール設定で指定されたように、このゾーンでオンになります。 このポリシー設定を構成しないと、スクリプトによって起動されたポップアップ ウィンドウや、タイトルとステータス バーを含むウィンドウに含まれる、危害を及ぼす可能性のある動作は実行されません。 この Internet Explorer のセキュリティ機能は、プロセスの [スクリプト化されたウィンドウのセキュリティ制限] 機能コントロール設定で指定されたように、このゾーンでオンになります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067088)

  **既定値**:無効

- **[Internet Explorer のセキュリティ ゾーンでコンピューターの設定のみ使用する]** :  
  同じコンピューターのすべてのユーザーに、セキュリティ ゾーン情報を適用します。 セキュリティ ゾーンはセキュリティ レベルが同じ Web サイトのグループです。 このポリシーを有効にすると、セキュリティ ゾーンに対してユーザーが行った変更は、そのコンピューターのすべてのユーザーに適用されます。 このポリシーを無効にしたり構成しない場合には、ユーザーは、独自のセキュリティ ゾーンを設定できます。 このポリシーを使用すると、セキュリティ ゾーンの設定が同じコンピューターに統一して適用され、ユーザーごとに設定を変えることはできません。 [セキュリティ ゾーン: ポリシーの変更を許可しない] ポリシーも参照してください。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067086)

  **既定値**:Enabled

- **[Internet Explorer のロックダウンされたローカル コンピューター ゾーンの Java アクセス許可]** :  
  このポリシー設定を使用すると、Java アプレットのアクセス許可を管理できます。 このポリシー設定を有効にすると、オプションをドロップダウン ボックスから選択できます。 アクセス許可の設定を個々に制御するには [カスタム] を選択します。 [安全性 - 低] を選択すると、アプレットはすべての操作を実行できます。 [安全性 - 中] を選択すると、アプレットはサンドボックス (メモリ内の領域で、その外側にはプログラムは呼び出しを実行できない) 内で実行されます。また、スクラッチ領域 (クライアント コンピューター内の安全でセキュリティで保護された記憶域) やユーザーによって制御されたファイル I/O などの機能が利用できます。 [安全性 - 高] を選択すると、アプレットはサンドボックス内で実行されます。 アプレットが実行されないようにするには、[Java を無効にする] を選択します。 このポリシー設定を無効にすると、Java アプレットは実行されません。 このポリシー設定を構成しなかった場合、Java アプレットは無効になります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067253)

  **既定値**:Java を無効にする

- **[Internet Explorer の制限付きゾーンで Active X コントロールに対してマルウェア対策を実行しない]** :  
  このポリシー設定では、Internet Explorer で ActiveX コントロールに対してマルウェア対策プログラムを実行し、ページを読み込んでも安全か確認するかどうかが決定されます。 このポリシー設定を有効にすると、Internet Explorer では、ActiveX コントロールのインスタンスを作成しても安全かどうかを確認するための、マルウェア対策プログラムでのチェックは行われません。 このポリシー設定を無効にすると、Internet Explorer では、ActiveX コントロールのインスタンスを作成しても安全かどうかを確認するための、マルウェア対策プログラムでのチェックが常に行われます。 このポリシー設定を構成しない場合、Internet Explorer では、ActiveX コントロールのインスタンスを作成しても安全かどうかを確認するための、マルウェア対策プログラムでのチェックが常に行われます。 ユーザーは、Internet Explorer の [セキュリティ] の設定を使用して、この動作を有効または無効に切り替えることができます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067089)

  **既定値**:無効

- **[Internet Explorer の制限付きゾーンで Authenticode 署名済みの .NET Framework 依存コンポーネントを実行する]** :  
  このポリシー設定を使用すると、Authenticode で署名されている .NET Framework コンポーネントを Internet Explorer から実行できるかどうかを管理できます。 これらのコンポーネントには、object タグから参照されたマネージド コントロールや、リンクから参照されたマネージド実行可能ファイルが含まれます。 このポリシー設定を有効にすると、Internet Explorer では署名されているマネージド コンポーネントが実行されます。 ドロップダウン ボックスで [ダイアログを表示する] を選択すると、Internet Explorer では、署名されているマネージド コンポーネントを実行するかどうかをユーザーに確認するメッセージが表示されます。 このポリシー設定を無効にすると、Internet Explorer は署名済みの管理されたコンポーネントを実行しません。 このポリシー設定を構成しない場合は、Internet Explorer は署名済みの管理されたコンポーネントを実行します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067169)

  **既定値**:無効化

- **[Internet Explorer の制限付きゾーンにあるデータ ソースへのアクセス]** :  
  このポリシー設定を使用すると、Internet Explorer が Microsoft XML パーサー (MSXML) または ActiveX Data Objects (ADO) を使用して別のセキュリティ ゾーンからデータにアクセスできるかどうかを管理できます。 このポリシー設定を有効にすると、ユーザーは、ゾーン内の別のサイトにあるデータに MSXML または ADO を使用してアクセスするゾーン内のページを読み込むことができます。 ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、ゾーン内の他のサイトにあるデータに MSXML または ADO を使用してアクセスするゾーン内のページを読み込むことを許可するかどうかをユーザーにたずねます。 このポリシー設定を無効にすると、ゾーン内の他のサイトにあるデータに MSXML または ADO を使用してアクセスするゾーン内のページを読み込むことはできません。 このポリシー設定を構成しないと、ゾーン内の他のサイトにあるデータに MSXML または ADO を使用してアクセスするゾーン内のページを読み込むことはできません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067161)

  **既定値**:無効化

- **[Internet Explorer internet zone don't run antimalware against ActiveX controls]\(Internet Explorer のインターネット ゾーンで Active X コントロールに対してマルウェア対策を実行しない\)** :  
  このポリシー設定では、Internet Explorer で ActiveX コントロールに対してマルウェア対策プログラムを実行し、ページを読み込んでも安全か確認するかどうかが決定されます。 このポリシー設定を有効にすると、Internet Explorer では、ActiveX コントロールのインスタンスを作成しても安全かどうかを確認するための、マルウェア対策プログラムでのチェックは行われません。 このポリシー設定を無効にすると、Internet Explorer では、ActiveX コントロールのインスタンスを作成しても安全かどうかを確認するための、マルウェア対策プログラムでのチェックが常に行われます。 このポリシー設定を構成しない場合、Internet Explorer では、ActiveX コントロールのインスタンスを作成しても安全かどうかを確認するための、マルウェア対策プログラムでのチェックが常に行われます。 ユーザーは、Internet Explorer の [セキュリティ] の設定を使用して、この動作を有効または無効に切り替えることができます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067162)

  **既定値**:無効

- **[Internet Explorer のインターネット ゾーンでのスクリプトによるコピーと貼り付け]** :  
  このポリシー設定を使用すると、指定された領域でスクリプトがクリップボードの操作 (例: 切り取り、コピー、貼り付け) を実行できるかどうかを管理できます。 このポリシー設定を有効にすると、スクリプトによりクリップボードの操作を実行できます。 ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、クリップボードの操作を実行するかどうかがユーザーにたずねられます。 このポリシー設定を無効にすると、スクリプトによってクリップボードの操作は実行されません。 このポリシー設定を構成しなかった場合、スクリプトはクリップボードの操作を実行できません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067084)

  **既定値**:無効化

- **[Internet Explorer での Activex インストーラー サービスの使用]** :  
  このポリシー設定を使用すると、ActiveX コントロールのインストール方法を指定できます。 このポリシー設定を有効にすると、ActiveX インストーラー サービスが存在し、ActiveX コントロールのインストールを許可するように構成されている場合にのみ、ActiveX コントロールがインストールされます。 このポリシー設定を無効にするか、または構成しない場合、ActiveX コントロール (ユーザーごとのコントロールを含む) は標準インストール プロセスを使用してインストールされます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067163)

  **既定値**:Enabled

- **[Internet Explorer でゾーン昇格からの保護を処理する]** :  
  Internet Explorer によって、開かれる各 Web ページに制限が適用されます。 制限は、Web ページの場所 (インターネット、イントラネット、ローカル コンピューター ゾーンなど) によって決まります。 たとえば、ローカル コンピューターにある Web ページはローカル コンピューター セキュリティ ゾーンにあり、最小限の制限を受けるため、ローカル コンピューター セキュリティ ゾーンは悪意のあるユーザーの一番のターゲットとなります。 このポリシー設定を有効にすると、すべてのゾーンを、すべてのプロセスのゾーン昇格から保護できます。 このポリシー設定を無効にするか、または構成しない場合は、Internet Explorer のプロセス以外のプロセス、またはプロセスの一覧にあるプロセス以外のプロセスは、このような保護を受けません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067160)

  **既定値**:Enabled

- **[Internet Explorer のインターネット ゾーンで署名なしの Active X コントロールをダウンロードする]** :  
  このポリシー設定を使用すると、ユーザーがゾーンから署名されていない ActiveX コントロールをダウンロードできるかどうかを管理できます。 このようなコードは害を及ぼす危険があり、信頼されていないゾーンのものの場合は特にそうです。 このポリシー設定を有効にすると、ユーザーは、何もしなくても、署名されていないコントロールを実行できます。 ドロップダウン ボックスで [ダイアログを表示する] を選択すると、署名されていないコントロールの実行を許可するかどうかをユーザーに確認するメッセージが表示されます。 このポリシー設定を無効にすると、ユーザーは署名されていないコントロールを実行できません。 このポリシー設定を構成しない場合、ユーザーは署名されていないコントロールを実行できません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067325)

  **既定値**:無効化

- **[Internet Explorer のインターネット ゾーンで異なるドメインとの間でウィンドウとフレームを移動する]** :  
  このポリシー設定を使用すると、異なるドメイン間でウィンドウとフレームを開くことや、アプリケーションにアクセスすることを管理できます。 このポリシー設定を有効にすると、ユーザーは他のドメインからウィンドウとフレームを開くことや、アプリケーションにアクセスすることができます。 ドロップダウン ボックスで [ダイアログを表示する] を選択すると、他のドメインからウィンドウやフレームを開いたりアプリケーションにアクセスしたりすることを許可するかどうかをユーザーに確認するメッセージが表示されます。 このポリシー設定を無効にすると、ユーザーは他のドメインからウィンドウとフレームを開けることや、アプリケーションにアクセスすることができません。 このポリシー設定を構成しない場合は、ユーザーは他のドメインからウィンドウとフレームを開くことや、アプリケーションにアクセスすることができます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067083)

  **既定値**:無効化

- **[Internet Explorer のインターネット ゾーンでスクリプトを介してステータス バーを更新する]** :  
  このポリシー設定を使用すると、スクリプトを介してゾーン内のステータス バーを更新できるかどうかを管理できます。 このポリシー設定を有効にすると、スクリプトを介してステータス バーを更新できます。 このポリシー設定を無効にした場合、または構成しなかった場合、スクリプトを介してステータス バーを更新できません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067087)

  **既定値**:無効

- **[Internet Explorer の制限付きゾーンでサーバーへのファイルのアップロード時にローカル パスを含める]** :  
  このポリシー設定では、ユーザーが HTML フォーム経由でファイルをアップロードするときに、ローカル パス情報が送信されるかどうかが制御されます。 ローカル パス情報が送信された場合、意図せずに、一部の情報がサーバーに公開されることがあります。 たとえば、ユーザーのデスクトップから送信されたファイルに、パスの一部としてユーザー名が含まれている可能性があります。 このポリシー設定を有効にすると、ユーザーが HTML フォーム経由でファイルをアップロードするときに、パス情報が送信されます。 このポリシー設定を無効にすると、ユーザーが HTML フォーム経由でファイルをアップロードするときに、パス情報が削除されます。 このポリシー設定を構成しなかった場合、ユーザーが HTML フォーム経由でファイルをアップロードするときに、パス情報を送信するかどうかをユーザーが選択できます。 既定では、パス情報は送信されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067085)

  **既定値**:無効

- **[Internet Explorer のプロセスでファイルのダウンロードを制限する]** :  
  このポリシー設定は、Web ブラウザー コントロールをホストしているアプリケーションで、ユーザーが開始していないファイル ダウンロードの確認ダイアログの自動表示をブロックすることを有効にします。 このポリシー設定を有効にすると、ユーザーによって開始されていないファイル ダウンロードの確認ダイアログの自動表示はすべてのプロセスにおいて Web ブラウザー コントロールによってブロックされます。 このポリシー設定を無効にすると、ユーザーによって開始されていないファイル ダウンロードの確認ダイアログの自動表示はすべてのプロセスにおいて Web ブラウザー コントロールによってブロックされません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067164)

  **既定値**:Enabled

- **[Internet Explorer の制限付きゾーンで承認済みドメインのみが Active X コントロールを使用できるようにする]** :  
  このポリシー設定では、ActiveX コントロールをインストールした Web サイト以外の Web サイトで ActiveX コントロールを実行する許可を求めるメッセージをユーザーに表示するかどうかを制御します。 このポリシー設定を有効にすると、このゾーン内の Web サイトから ActiveX コントロールが実行される前に、ユーザーにメッセージが表示されます。 ユーザーは、コントロールの実行を現在のサイトだけに許可するか、すべてのサイトに許可するかを選択できます。 このポリシー設定を無効にすると、ユーザーにはサイトごとの ActiveX 警告は表示されず、ActiveX コントロールはこのゾーン内のすべてのサイトから実行できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067233)

  **既定値**:Enabled

- **[Internet Explorer の制限付きゾーンで安全であるとマークされていない Active X コントロールを初期化およびスクリプト化する]** :  
  このポリシー設定を使用すると、安全とマークされていない ActiveX コントロールを管理できます。 このポリシー設定を有効にすると、ActiveX コントロールがパラメーターを読み込んで実行され、また、信頼されていないデータまたはスクリプトに対するオブジェクトの安全性を設定することなくスクリプト化されます。 この設定は、安全でかつ管理されたゾーン以外では推奨しません。 この設定により、安全でないコントロールと安全なコントロールの両方が初期化されてスクリプト化され、スクリプト実行オプションで安全とマークされた Script ActiveX コントロールは無視されます。 このポリシー設定を有効にして、ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、コントロールにパラメーターを読み込んだりスクリプト化したりすることを許可するかどうかをユーザーにたずねます。 このポリシー設定を無効にすると、安全であるとマークできない ActiveX コントロールにパラメーターを読み込んだりスクリプト化したりすることはできません。 このポリシー設定を構成しなかった場合、安全であるとマークできない ActiveX コントロールにパラメーターを読み込んだりスクリプト化したりすることはできません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067097)

  **既定値**:無効化

- **[Internet Explorer のユーザーによるポリシーの変更]** :  
  セキュリティ ゾーンの設定をユーザーが変更できないようにします。 セキュリティ ゾーンはセキュリティ レベルが同じ Web サイトのグループです。 このポリシーを有効にすると、[インターネット オプション] ダイアログ ボックスの [セキュリティ] タブの [レベルのカスタマイズ] ボタンとセキュリティ レベル スライダーが無効になります。 このポリシーを無効にするか、または構成しない場合は、セキュリティ ゾーンの設定を変更できます。 このポリシーにより、管理者が設定したセキュリティ ゾーンの設定をユーザーは変更できなくなります。 注:このポリシーよりも優先される [[セキュリティ] ページの使用を許可しない] ポリシー (場所: \ユーザーの構成\管理用テンプレート\Windows コンポーネント\Internet Explorer\インターネット コントロール パネル) を有効にすると、コントロール パネルのインターネット オプションから [セキュリティ] タブが削除され、 それが有効になっている場合、このポリシーは無視されます。 "セキュリティ ゾーン: コンピューターの設定のみ使用する" ポリシーも参照してください。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067155)

  **既定値**:無効

- **[Internet Explorer の制限付きゾーンでの保護モード]** :  
  このポリシー設定を使用すると、保護モードを有効にできます。 保護モードを使用すると、Internet Explorer が書き込むことができるレジストリやファイル システム内の場所を制限することで、脆弱性を悪用した攻撃から Internet Explorer を保護できます。 このポリシー設定を有効にすると、保護モードが有効になります。 ユーザーは保護モードを無効にできません。 このポリシー設定を無効にすると、保護モードが無効になります。 ユーザーは保護モードを有効にできません。 このポリシー設定を構成しなかった場合、ユーザーは保護モードを有効または無効にできます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067080)

  **既定値**:[ウェイクアップ時間 (デスクトップ コンピューター)] を有効にして、デスクトップ コンピューターが、スケジュールされた更新またはソフトウェアのインストールを実行するために、スリープ状態または休止状態から復帰する時刻を指定します。

- **[Internet Explorer のインターネット ゾーンでのユーザー データ永続化]** :  
  このポリシー設定を使用すると、ブラウザーの履歴、お気に入り、XML ストア、またはディスクに保存された Web ページ内に直接入っている情報の保管を管理できます。 このポリシー設定を正しく構成すると、ユーザーが固定されたページに戻ったときに、ページの状態を復元できます。 このポリシー設定を有効にすると、ユーザーはブラウザーの履歴、お気に入り、XML ストア、またはディスクに保存されている Web ページ内に直接、情報を保管できます。 このポリシー設定を無効にすると、ユーザーはブラウザーの履歴、お気に入り、XML ストア、またはディスクに保存されている Web ページ内に直接、情報を保管できません。 このポリシー設定を構成しなかった場合、ユーザーはブラウザーの履歴、お気に入り、XML ストア、またはディスクに保存されている Web ページ内に直接、情報を保管できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067156)

  **既定値**:無効

- **[Internet Explorer のインターネット ゾーンでの Web ブラウザー コントロールのスクリプト化]** :  
  このポリシー設定では、スクリプトによる埋め込み WebBrowser コントロールをページで制御できるかどうかが決定されます。 このポリシー設定を有効にすると、WebBrowser コントロールへのスクリプト アクセスが許可されます。 このポリシー設定を無効にすると、WebBrowser コントロールへのスクリプト アクセスは許可されません。 このポリシー設定を構成しなかった場合、ユーザーは WebBrowser コントロールへのスクリプト アクセスを有効または無効にできます。 既定では、WebBrowser コントロールへのスクリプト アクセスは、ローカル コンピューターとイントラネット ゾーンでのみ許可されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067157)

  **既定値**:無効

- **[Internet Explorer の制限付きゾーンでのユーザー データ永続化]** :  
  このポリシー設定を使用すると、ブラウザーの履歴、お気に入り、XML ストア、またはディスクに保存された Web ページ内に直接入っている情報の保管を管理できます。 このポリシー設定を正しく構成すると、ユーザーが固定されたページに戻ったときに、ページの状態を復元できます。 このポリシー設定を有効にすると、ユーザーはブラウザーの履歴、お気に入り、XML ストア、またはディスクに保存されている Web ページ内に直接、情報を保管できます。 このポリシー設定を無効にすると、ユーザーはブラウザーの履歴、お気に入り、XML ストア、またはディスクに保存されている Web ページ内に直接、情報を保管できません。 このポリシー設定を構成しなかった場合、ユーザーはブラウザーの履歴、お気に入り、XML ストア、またはディスクに保存されている Web ページ内に直接、情報を保管できません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067081)

  **既定値**:無効

- **[Internet Explorer のロックダウンされた信頼済みゾーンでの Java のアクセス許可]** :  
  このポリシー設定を使用すると、Java アプレットのアクセス許可を管理できます。 このポリシー設定を有効にすると、オプションをドロップダウン ボックスから選択できます。 アクセス許可の設定を個々に制御するには [カスタム] を選択します。 [安全性 - 低] を選択すると、アプレットはすべての操作を実行できます。 [安全性 - 中] を選択すると、アプレットはサンドボックス (メモリ内の領域で、その外側にはプログラムは呼び出しを実行できない) 内で実行されます。また、スクラッチ領域 (クライアント コンピューター内の安全でセキュリティで保護された記憶域) やユーザーによって制御されたファイル I/O などの機能が利用できます。 [安全性 - 高] を選択すると、アプレットはサンドボックス内で実行されます。 アプレットが実行されないようにするには、[Java を無効にする] を選択します。 このポリシー設定を無効にすると、Java アプレットは実行されません。 このポリシー設定を構成しなかった場合、Java アプレットは無効になります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067082)

  **既定値**:Java を無効にする

- **[Internet Explorer の拡張保護モード]** :  
  拡張保護モードでは、64 ビット版の Windows で 64 ビット プロセスを使用することにより、悪意のある Web サイトに対する保護が強化されます。 Windows 8 以降が実行されているコンピューターでは、拡張保護モードによって、Internet Explorer が読み取り元に設定できる、レジストリとファイル システム内の場所も制限されています。 このポリシー設定を有効にすると、拡張保護モードが有効になります。 保護モードが有効になっているすべてのゾーンで、拡張保護モードが使用されます。 ユーザーは拡張保護モードを無効にできません。 このポリシー設定を無効にすると、拡張保護モードが無効になります。 保護モードが有効になっているすべてのゾーンで、Windows Vista の Internet Explorer 7 で導入されたバージョンの保護モードが使用されます。 このポリシー設定を構成しない場合、ユーザーは、[インターネット オプション] ダイアログの [詳細設定] タブで拡張保護モードを有効または無効にできます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067158)

  **既定値**:Enabled

- **[Internet Explorer のスマート スクリーン警告のバイパス]** :  
  このポリシー設定では、ユーザーが SmartScreen フィルターからの警告をバイパスできるかどうかを決定します。 SmartScreen フィルター機能では、ダウンロードしたユーザー数が少ない実行可能ファイルについてユーザーに警告します。 このポリシー設定を有効にすると、ユーザーは SmartScreen フィルターの警告によってブロックされます。 このポリシー設定を無効にした場合、または構成しなかった場合、ユーザーは SmartScreen フィルター機能の警告をバイパスできます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067159)

  **既定値**:無効

- **[Internet Explorer の制限付きゾーンのメタ更新]** :  
  このポリシー設定を使用すると、Web ページの作成者がブラウザーを別の Web ページにリダイレクトするために Meta Refresh 設定 (タグ) を使用している場合に、ユーザーのブラウザーを別の Web ページにリダイレクトできるかどうかを管理できます。 このポリシー設定を有効にすると、アクティブな Meta Refresh 設定を含むページを読み込むブラウザーを他の Web ページにリダイレクトできます。 このポリシー設定を無効にすると、アクティブな Meta Refresh 設定を含むページを読み込むブラウザーを他の Web ページにリダイレクトできません。 このポリシー設定を構成しなかった場合、アクティブな Meta Refresh 設定を含むページを読み込むブラウザーを他の Web ページにリダイレクトできません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067154)

  **既定値**:無効

## <a name="local-policies-security-options"></a>ローカル ポリシーのセキュリティ オプション

詳細については、Windows のドキュメントの「[Policy CSP - LocalPoliciesSecurityOptions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions)」(ポリシー CSP - LocalPoliciesSecurityOptions) を参照してください。

- **[名前付きパイプと共有への匿名アクセスを制限する]** :  
  このセキュリティ設定を有効にすると、次の設定と一致する共有およびパイプへの匿名アクセスが制限されます: (1) 匿名でアクセスできる名前付きパイプ (2) 匿名でアクセスできる共有。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067212)

  **既定値**:はい

- **[NTLM SSP ベースのサーバー向け最小セッション セキュリティ]** :  
  このセキュリティ設定を使用すると、サーバーで 128 ビット暗号化および NTLMv2 セッション セキュリティのネゴシエーションが必要になるようにすることができます。 これらの値は、LAN Manager 認証レベルのセキュリティ設定値に依存します。 オプションは次のとおりです。NTLMv2 セッション セキュリティが必要: メッセージの整合性がネゴシエートされない場合、接続は失敗します。 128 ビット暗号化が必要: 強力な暗号化 (128 ビット) がネゴシエートされない場合、接続は失敗します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067246)

  **既定値**:NTLM V2 および 128 ビットの暗号化が必要

- **スクリーン セーバーがアクティブになるまでのロック画面の非アクティブ時間 (分)** :  
  Windows ではログオン セッションの非アクティブ状態が通知され、非アクティブ状態の時間が非アクティブ状態の上限を超えると、スクリーン セーバーが作動し、セッションがロックされます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067210)

  **既定値**:15

- **[クライアントの通信に常にデジタル署名を要求する]** :  
  このセキュリティ設定では、ドメインのメンバーによって開始された、セキュリティで保護されたチャネルのトラフィックすべてに対して署名または暗号化を行う必要があるかどうかを決定します。 コンピューターがドメインに参加すると、コンピューター アカウントが作成されます。 それ以降、システムでは起動時に、そのコンピューター アカウントのパスワードを使用して、そのドメイン用のドメイン コントローラーとの間でセキュリティで保護されたチャネルが確立されます。 このセキュリティで保護されたチャネルは、NTLM パススルー認証や LSA SID/名前の参照などの操作を実行するために使用されます。 この設定では、ドメインのメンバーによって開始された、セキュリティで保護されたチャネルのトラフィックすべてが最低限のセキュリティ要件を満たす必要があるかどうかを決定します。 具体的には、ドメインのメンバーによって開始された、セキュリティで保護されたチャネルのトラフィックすべてに対して署名または暗号化を行う必要があるかどうかを決定します。 このポリシーを有効にすると、セキュリティで保護されたチャネルのトラフィックすべてに対する署名または暗号化がネゴシエートされるまで、セキュリティで保護されたチャネルは確立されません。 このポリシーを無効にすると、セキュリティで保護されたチャネルのトラフィックすべてに対する署名または暗号化は、ドメイン コントローラーとネゴシエートされます。この場合、署名と暗号化のレベルは、ドメイン コントローラーのバージョンと次の 2 つのポリシーの設定によって決まります: ドメイン メンバー:  可能な場合、セキュリティで保護されたチャネルのデータをデジタル的に暗号化するドメイン メンバー: 可能な場合、セキュリティで保護されたチャネルのデータをデジタル的に署名する。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067187)

  **既定値**:はい

- **[認証レベル]** :  
  このセキュリティ設定では、ネットワーク ログオンに使用されるチャレンジ/レスポンス認証プロトコルが決定されます。 この選択は、以下に示すように、クライアントで使用する認証プロトコルのレベル、ネゴシエートされるセッション セキュリティのレベル、およびサーバーによって受け入れられる認証レベルに影響します:

  - "*LM と NTLM 応答を送信する*" - クライアントでは LM および NTLM 認証が使用され、NTLMv2 セッション セキュリティは使用されません。ドメイン コントローラーでは LM、NTLM、および NTLMv2 認証が受け入れられます。

  - "*LM と NTLM を送信する - ネゴシエートされた場合は NTLMv2*" - クライアントでは LM および NTLM 認証が使用され、サーバーでサポートされている場合は NTLMv2 セッション セキュリティも使用されます。 ドメイン コントローラーでは、LM、NTLM、および NTLMv2 認証が受け入れられます。

  - "*NTLM 応答のみ送信する*" - クライアントでは NTLM 認証のみが使用され、サーバーでサポートされている場合は NTLMv2 セッション セキュリティも使用されます。ドメイン コントローラーでは、LM、NTLM、および NTLMv2 認証が受け入れられます。

  - "*NTLMv2 応答のみ送信する*" - クライアントでは NTLMv2 認証のみが使用され、サーバーでサポートされている場合は NTLMv2 セッション セキュリティも使用されます。ドメイン コントローラーでは、LM、NTLM、および NTLMv2 認証が受け入れられます。

  - "*NTLMv2 応答のみ送信する。LM を拒否する*" - クライアントでは NTLMv2 認証のみが使用され、サーバーでサポートされている場合は NTLMv2 セッション セキュリティが使用されます。 ドメイン コントローラーでは、LM は拒否されます (NTLM と NTLMv2 認証のみが受け入れられます)。

  - "*NTLMv2 応答のみ送信する。LM と NTLM を拒否する*" - クライアントでは NTLMv2 認証のみが使用され、サーバーでサポートされている場合は NTLMv2 セッション セキュリティが使用されます。 ドメイン コントローラーでは、LM と NTLM は拒否されます (NTLMv2 認証のみが受け入れられます)。

  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067189)

  **既定値**:NTLMv2 応答のみ送信する。 LM と NTLM を拒否する

- **[暗号化されていないパスワードがクライアントからサード パーティの SMB サーバーに送信されるのを防ぐ]** :  
  このセキュリティ設定を有効にすると、サーバー メッセージ ブロック (SMB) リダイレクターは、認証時にパスワードの暗号化をサポートしていない Microsoft 以外の SMB サーバーにプレーンテキストのパスワードを送信することができます。 暗号化されていないパスワードを送信することには、セキュリティ上のリスクがあります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067235)

  **既定値**:はい

- **[サーバーが常に通信にデジタル署名を行うことを要求する]** :  
  このセキュリティ設定では、SMB クライアントによって SMB パケットの署名がネゴシエートされるかどうかが決定されます。 サーバー メッセージ ブロック (SMB) プロトコルは、Microsoft ファイルおよびプリンターの共有の基礎、さらにはリモート Windows 管理などのネットワーク操作の基礎となります。 転送中に SMB パケットを変更する中間者攻撃を防ぐために、SMB プロトコルでは SMB パケットのデジタル署名がサポートされています。 このポリシー設定では、SMB クライアント コンポーネントが SMB サーバーに接続するときに、その SMB クライアント コンポーネントによって SMB パケットの署名がネゴシエートされるかどうかが決定されます。 この設定を有効にすると、セッションのセットアップ時に SMB パケットの署名を実行するよう Microsoft ネットワーク クライアントからサーバーに要求が出されます。 サーバーでパケットの署名が有効になっている場合、パケットの署名がネゴシエートされます。 このポリシーを無効にすると、SMB クライアントによって SMB パケットの署名がネゴシエートされることはありません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067319)

  **既定値**:はい

- **[管理者に対する昇格時のプロンプトの動作]** :  
  このポリシー設定では、管理者に対する昇格時のプロンプトの動作が制御されます。 オプションは次のとおりです。

  - "*プロンプトを表示せずに昇格する*" - 昇格を必要とする操作を、同意または資格情報の必要なしに実行することを権限アカウントに許可します。 注:このオプションは非常に制限された環境内でのみ使用します。

  - "*セキュリティで保護されたデスクトップで資格情報を要求する*" - 操作で特権の昇格が必要になると、ユーザーはセキュリティで保護されたデスクトップ上で特権を持つユーザー名とパスワードを入力するように求められます。 ユーザーが有効な資格情報を入力すると、ユーザーが利用できる最も高い特権で操作が続行されます。

  - "*セキュリティで保護されたデスクトップで同意を要求する*" - 操作で特権の昇格が必要になると、ユーザーはセキュリティで保護されたデスクトップ上で許可または拒否のいずれかを選択するように求められます。 ユーザーが許可を選択すると、ユーザーが利用できる最も高い特権で操作が続行されます。

  - "*資格情報を要求する*" - 操作で特権の昇格が必要になると、ユーザーは管理者のユーザー名とパスワードを入力するように求められます。 ユーザーが有効な資格情報を入力すると、適用可能な特権で操作が続行されます。

  - "*同意を要求する*" - 操作で特権の昇格が必要になると、ユーザーは許可または拒否のいずれかを選択するように求められます。 ユーザーが許可を選択すると、ユーザーが利用できる最も高い特権で操作が続行されます。

  - "*非 Windows バイナリに対して同意を要求する*" - Microsoft 以外のアプリケーションの操作で特権の昇格が必要になると、ユーザーはセキュリティで保護されたデスクトップ上で許可または拒否のいずれかを選択するように求められます。 ユーザーが許可を選択すると、ユーザーが利用できる最も高い特権で操作が続行されます。

  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067215)

  **既定値**:セキュリティで保護されたデスクトップで同意を要求する

- **[Minimum session security for NTLM SSP based clients]\(NTLM SSP ベースのクライアント向け最小セッション セキュリティ\)** :  
  このセキュリティ設定を使用すると、クライアントで 128 ビット暗号化および NTLMv2 セッション セキュリティのネゴシエーションが必要になるようにすることができます。 これらの値は、LAN Manager 認証レベルのセキュリティ設定値に依存します。 オプションは次のとおりです。

  - "*NTLMv2 セッション セキュリティが必要*" - NTLMv2 プロトコルがネゴシエートされていない場合、接続は失敗します。

  - "*128 ビット暗号化が必要*" - 強力な暗号化 (128 ビット) がネゴシエートされない場合、接続は失敗します。

  - *NTLMv2 および 128 ビットの暗号化が必要*。

  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067324)

  **既定値**:NTLM V2 128 暗号化が要求

- **スマート カードを取り外したときの動作**:  
  このセキュリティ設定では、ログオンしているユーザーのスマート カードがスマート カード リーダーから取り出されたときの動作を決定します。 オプションは次のとおりです。

  - *操作の必要なし*。

  - *ワークステーションをロックする* - スマート カードが取り出されたときにワークステーションはロックされます。これにより、ユーザーはスマート カードを持って場所を離れ、なおかつ、保護されたセッションを維持できます。

  - "*ログオフを強制する*" - スマート カードが取り出されると、ユーザーは自動的にログオフされます。

  - "*リモート デスクトップ セッションを切断する*" - スマート カードを取り出すと、ユーザーをログオフさせずにセッションを切断します。 このため、ユーザーは後でスマート カードを挿入し、セッションを再開することも、スマート カード リーダーを装備した別のコンピューターにスマート カードを挿入し、セッションを再開することもできます。もう一度ログオンする必要はありません。 セッションがローカルの場合、このポリシーの機能は [ワークステーションをロックする] と同じになります。

  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067331)

  **既定値**:ワークステーションをロックする

- **[SAM アカウントと共有の匿名の列挙をブロックする]** :  
  このセキュリティ設定では、SAM アカウントと共有の匿名の列挙を許可するかどうかが決定されます。 Windows では匿名ユーザーがドメイン アカウントとネットワーク共有の名前の列挙など、特定の操作を行うことを許可しています。 これは、たとえば管理者が、相互信頼関係のない信頼される側のドメイン内のユーザーにアクセス許可を付与するのに便利です。 SAM アカウントおよび共有の匿名の列挙を許可しない場合は、このポリシーを "*はい*" に設定します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067191)

  **既定値**:はい

- **[空のパスワードを使用したリモート ログオンをブロックする]** :  
  このセキュリティ設定では、パスワードで保護されていないローカル アカウントを使用して物理的なコンピューター コンソール以外の場所からログオンできるようにするかどうかが決定されます。 有効にすると、パスワードで保護されていないローカル アカウントには、そのコンピューターのキーボードを使用してログオンする必要があります。

  *警告*: 物理的に安全な場所に置かれていないコンピューターでは、すべてのローカル ユーザー アカウントに対して常に強力なパスワード ポリシーが適用される必要があります。 そうしないと、パスワードのないユーザー アカウントを使用し、コンピューターに物理的にアクセスできるすべてのユーザーがコンピューターにログオンできてしまいます。 これは、持ち運びができるコンピューターの場合に特に重要です。

  Everyone グループにこのセキュリティ ポリシーを適用すると、すべてのユーザーがリモート デスクトップ サービスを使用してログオンできなくなります。 ドメイン アカウントを使用するログオンにはこの設定は影響しません。 リモートからの対話型ログオンを使用するアプリケーションでは、この設定を回避できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067219)

  **既定値**:はい

- **[Standard user elevation prompt behavior]\(標準ユーザーに対する昇格時のプロンプトの動作\)** :  
  このポリシー設定では、標準ユーザーに対する昇格時のプロンプトの動作を制御します。

  - "*昇格要求を自動的に拒否する*" - 操作で特権の昇格が必要な場合、構成可能なアクセス拒否エラー メッセージが表示されます。 デスクトップの実行を標準ユーザーが行う企業では、ヘルプ デスクへの問い合わせを減らすためにこの設定が選択される場合があります。

  - "*セキュリティで保護されたデスクトップで資格情報を要求する*" - 操作で特権の昇格が必要になると、ユーザーはセキュリティで保護されたデスクトップ上で別のユーザー名とパスワードを入力するように求められます。 ユーザーが有効な資格情報を入力すると、適用可能な特権で操作が続行されます。

  - "*資格情報を要求する*" - 操作で特権の昇格が必要になると、ユーザーは管理者のユーザー名とパスワードを入力するように求められます。 ユーザーが有効な資格情報を入力すると、適用可能な特権で操作が続行されます。

  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067183)

  **既定値**:昇格要求を自動的に拒否する

- **[Require admin approval mode for administrators]\(管理者に管理者承認モードを要求する\)** :  
  このポリシー設定は、コンピューターのすべてのユーザー アカウント制御 (UAC) ポリシー設定の動作を制御します。 このポリシー設定を変更した場合、コンピューターを再起動する必要があります。 オプションは次のとおりです。

  - "*未構成*" - 管理者承認モードと関連するすべての UAC ポリシー設定が無効になります。 注:このポリシー設定を無効にすると、オペレーティング システムのセキュリティが全体的に低下したという通知が Security Center からあります。

  - "*はい*" - 管理者承認モードが有効になります。 組み込まれている管理者アカウントや管理者グループのその他のすべてのユーザーが管理者承認モードで実行することを許可するには、このポリシーを有効にし、関連する UAC ポリシー設定を正しく設定する必要があります。

  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067184)

  **既定値**:はい

- **[Prevent anonymous enumeration of SAM accounts]\(SAM アカウントの匿名の列挙を防ぐ\)** :  
  このセキュリティ設定は、コンピューターに対する匿名接続にどのようなアクセス許可を追加付与するかを決定します。 Windows では匿名ユーザーがドメイン アカウントとネットワーク共有の名前の列挙など、特定の操作を行うことを許可しています。 これは、たとえば管理者が、相互信頼関係のない信頼される側のドメイン内のユーザーにアクセス許可を付与するのに便利です。 このセキュリティ オプションでは、次のような追加の制限が匿名接続に課せられます。

  - "*はい*" - SAM アカウントの列挙を許可しません。 このオプションでは、リソースに対するセキュリティのアクセス許可の Everyone を認証されたユーザーに置き換えます。

  - "*未構成*" - 追加の制限はありません。 既定のアクセス許可が使用されます。

  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067318)

  **既定値**:はい

- **[Allow remote calls to security accounts manager]\(セキュリティ アカウント マネージャーへのリモート呼び出しを許可する\)** :  
  このポリシー設定では、SAM へのリモート rpc 接続を制限することができます。 これを選択しない場合、既定のセキュリティ記述子が使用されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067209)

  **既定値**:*O:BAG:BAD:(A;;RC;;;BA)*

- **[Use admin approval mode]\(管理者承認モードを使用する)** :  
  このポリシー設定は、組み込みの管理者アカウントの管理者承認モードの動作を制御します。 オプションは次のとおりです。

  - "*はい*" - あらかじめ登録された Administrator アカウントでは、管理者承認モードが使用されます。 既定では、特権の昇格が必要な操作では、ユーザーにその操作の承認が求められます。

  - "*未構成*" - あらかじめ登録された Administrator アカウントでは、すべてのアプリケーションが完全な管理特権で実行されます。

  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067186)

  **既定値**:はい
  
- **[セキュリティで保護された場所の UI アクセス アプリケーションのみを許可する]** :  
  このポリシー設定は、標準ユーザーに対して昇格がプロンプトされたときにセキュリティで保護されたデスクトップを、ユーザー インターフェイス アクセシビリティ (UIAccess または UIA) プログラムが自動的に無効にできるかどうかを制御します。

  - "*はい*" - Windows リモート アシスタンスなどの UIA プログラムは、昇格時のプロンプトに対してセキュリティで保護されたデスクトップを自動的に無効にします。 "ユーザー アカウント制御: 昇格のプロンプト時にセキュリティで保護されたデスクトップに切り替える" ポリシー設定を無効にしない場合、セキュリティで保護されたデスクトップではなく、対話ユーザーのデスクトップにプロンプトが表示されます。

  - "*未構成*" - セキュリティで保護されたデスクトップを無効にするには、対話型のデスクトップのユーザーが無効にするか、"ユーザー アカウント制御: 昇格のプロンプト時にセキュリティで保護されたデスクトップに切り替える" ポリシー設定を無効にする必要があります。

  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067185)

  **既定値**:はい

- **[アプリケーションのインストールを検出し、昇格をプロンプトする]** :  
  このポリシー設定は、コンピューターへのアプリケーションのインストールの検出動作を制御します。 オプションは次のとおりです。

  - "*有効*" - 特権の昇格を必要とするアプリケーション インストール パッケージが検出されると、ユーザーは管理ユーザー名とパスワードを入力するように求められます。 ユーザーが有効な資格情報を入力すると、適用可能な特権で操作が続行されます。

  - "*無効*" - アプリケーション インストール パッケージは検出されず、昇格は求められません。 グループ ポリシー ソフトウェア インストールや Systems Management Server (SMS) などの委任されたインストール技術を活用している、標準ユーザー デスクトップを実行する企業では、この機能を無効にします。 この場合、インストーラーの検出は不要です。

  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067208)

  **既定値**:はい

- **[Prevent storing LAN manager hash value on next password change]\(次のパスワードの変更で LAN Manager のハッシュ値を保存しない\)** :  
  このセキュリティ設定は、次のパスワードの変更で、新しいパスワードの LAN Manager (LM) のハッシュ値を保存するかどうかを決定します。 LM ハッシュは、暗号化強度の高い Windows NT ハッシュと比べて比較的弱く、攻撃されやすいです。 LM ハッシュはセキュリティ データベースのローカル コンピューターに保存されるので、セキュリティ データベースが攻撃された場合、パスワードが漏えいすることがあります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067213)

  **既定値**:はい

- **[ファイルおよびレジストリの書き込みエラーをユーザーごとの場所に仮想化する]** :  
  このポリシー設定は、アプリケーションの書き込みエラーを、定義されているレジストリおよびファイル システムの場所にリダイレクトするかどうかを制御します。 このポリシー設定は、管理者として実行されるアプリケーションが、実行時のアプリケーション データを *%ProgramFiles%* 、 *%Windir%* 、 *%Windir%\system32*、または *HKLM\Software* に書き込むよう緩和します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067321)

  **既定値**:はい

## <a name="microsoft-defender"></a>Microsoft Defender

詳細については、Windows ドキュメントの「[Policy CSP - Defender](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender)」(ポリシー CSP - Defender) を参照してください。

::: zone-end
::: zone pivot="mdm-may-2019"

- **[Adobe Reader による子プロセスの作成をブロックする]** :  
このルールでは、Adobe Reader による追加のプロセス作成をブロックすることで攻撃を防ぎます。 マルウェアは、ソーシャル エンジニアリングまたは悪用によって、追加のペイロードをダウンロードして起動し、Adobe Reader から抜け出すことができます。 Adobe Reader による子プロセスの生成をブロックすることで、それをベクトルとして使用しようとしているマルウェアの拡散を防ぎます。
[詳細情報](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)

  **既定値**:[ウェイクアップ時間 (デスクトップ コンピューター)] を有効にして、デスクトップ コンピューターが、スケジュールされた更新またはソフトウェアのインストールを実行するために、スリープ状態または休止状態から復帰する時刻を指定します。

- **[子プロセスでの Office 通信アプリの起動]** :  
  [悪用からデバイスを保護する](https://go.microsoft.com/fwlink/?linkid=874499)

  **既定値**:[ウェイクアップ時間 (デスクトップ コンピューター)] を有効にして、デスクトップ コンピューターが、スケジュールされた更新またはソフトウェアのインストールを実行するために、スリープ状態または休止状態から復帰する時刻を指定します。

- **Enter how often (0-24 hours) to check for security intelligence updates (セキュリティ インテリジェンスの更新を確認する頻度 (0-24 時間) の入力)**  
  CSP: [Defender/SignatureUpdateInterval](https://go.microsoft.com/fwlink/?linkid=2113936)
  
  新しい署名を確認する頻度を指定します。 値 1 は 1 時間、2 は 2 時間です。

  **既定値**:4

::: zone-end
::: zone pivot="mdm-preview,mdm-may-2019"

- **[Defender schedule scan day]\(Defender のスキャン日スケジュール\)** :  
  Defender のスキャン日スケジュール。

  **既定値**:毎日

- **[Turn on cloud-delivered protection]\(クラウドによる保護を有効にする\)** :  
  CSP:[Defender/AllowCloudProtection](https://go.microsoft.com/fwlink/?linkid=2113937)
  
  [はい] に設定すると、Defender によって検出された問題に関する情報が Microsoft に送信されます。 [未構成] に設定すると、クライアントは既定値に戻されます。これにより、この機能が有効になりますが、ユーザーはこの機能を無効にすることができます。

  **既定値**:はい  

- **リアルタイム保護を有効にする**  
  CSP: [Defender/AllowRealtimeMonitoring](https://go.microsoft.com/fwlink/?linkid=2114050)

  この設定を [はい] に設定すると、リアルタイム監視が強制され、ユーザーがこの設定を無効にすることはできません。 [未構成] に設定すると、クライアントの既定値 (有効) に戻されますが、ユーザーはこの設定を変更できます。 リアルタイム監視を無効にするには、カスタム URI を使用します。

  **既定値**:はい  

- **[アーカイブ ファイルをスキャンする]** :  
  CSP: [Defender/AllowArchiveScanning](https://go.microsoft.com/fwlink/?linkid=2114047)
  
  [はい] に設定すると、ZIP ファイルや CAB ファイルのスキャンなどのアーカイブ ファイルが強制されます。 [未構成] に設定すると、設定はクライアントの既定値 (アーカイブされたファイルをスキャン) に戻されますが、ユーザーはこの設定を無効にすることができます。

  **既定値**:はい

- **[動作の監視を有効にする]** :  
  CSP: [Defender/AllowBehaviorMonitoring](https://go.microsoft.com/fwlink/?linkid=2114048)

  この設定を [はい] に設定すると、動作の監視が強制され、ユーザーはこの設定を無効にできなくなります。 [未構成] に設定すると、クライアントの既定値 (有効) に戻されますが、ユーザーはこの設定を変更できます。 リアルタイム監視を無効にするには、カスタム URI を使用します。

  **既定値**:はい

- **[受信メール メッセージをスキャンする]** :  
  CSP: [Defender/AllowEmailScanning](https://go.microsoft.com/fwlink/?linkid=2114052)

  [はい] に設定すると、メールボックスとメール ファイル (PST、DBX、MNX、MIME、BINHEX など) がスキャンされます。 [未構成] に設定すると、設定はクライアントの既定値に戻され、メール ファイルはスキャンされません。

  **既定値**:はい

- **[フル スキャン中に、リムーバブル ドライブをスキャンする]** :  
  CSP: [Defender/AllowFullScanRemovableDriveScanning](https://go.microsoft.com/fwlink/?linkid=2113946)

  [はい] に設定すると、フル スキャン中に、リムーバブル ドライブ (USB フラッシュ ドライブなど) がスキャンされます。 [未構成] に設定すると、クライアントの既定値 (リムーバブル ドライブをスキャン) に戻されますが、ユーザーはこの設定を無効にすることができます。
  **既定値**:はい  

- **[Office アプリケーションによる他のプロセスへのコード挿入をブロックする]** :  
  [悪用からデバイスを保護する](https://go.microsoft.com/fwlink/?linkid=872974)

  [はい] に設定すると、Office アプリケーションは、その他のプロセスへのコードの挿入をブロックされます。 [監査のみ] に設定すると、ブロックではなく Windows イベントが発生します。 [未構成] に設定すると、設定は Windows の既定値 (無効) に戻されます。 この ASR 規則は、次の GUID を使用して制御されます。75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84

  **既定値**:ブロックする

- **Office アプリケーションによる実行可能なコンテンツの作成をブロックする**  
  [悪用からデバイスを保護する](https://go.microsoft.com/fwlink/?linkid=872975)

  [はい] に設定すると、Office アプリケーションは実行可能なコンテンツの作成を許可されません。 [監査のみ] に設定すると、ブロックではなく Windows イベントが発生します。 [未構成] に設定すると、設定は Windows の既定値 (無効) に戻されます。 この ASR 規則は、次の GUID を使用して制御されます。3B576869-A4EC-4529-8536-B80A7769E899

  **既定値**:ブロックする

- **すべての Office アプリケーションによる子プロセスの作成をブロックする**  
  [悪用からデバイスを保護する](https://go.microsoft.com/fwlink/?linkid=872976)

  [監査モード] に設定すると、ブロックではなく Windows イベントが発生します。 [未構成] に設定すると、設定は Windows の既定値 (無効) に戻されます。 この ASR 規則は、次の GUID を使用して制御されます。D4F940AB-401B-4EFC-AADC-AD5F3C50688A

  **既定値**:ブロックする

- **[Office マクロからの Win32 API 呼び出しをブロックする]** :  
  [悪用からデバイスを保護する](https://go.microsoft.com/fwlink/?linkid=872977)

  [はい] に設定すると、Office マクロの Win32 API 呼び出しの使用がブロックされます。 [監査のみ] に設定すると、ブロックではなく Windows イベントが発生します。 [未構成] に設定すると、設定は Windows の既定値 (無効) に戻されます。 この ASR 規則は、次の GUID を使用して制御されます。92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B
  
  **既定値**:ブロックする

- **[難読化されている可能性のあるスクリプト (js/vbs/ps) の実行をブロックする]** :  
  [悪用からデバイスを保護する](https://go.microsoft.com/fwlink/?linkid=872978)

  [はい] に設定すると、難読化されたスクリプトの実行が Defender によってブロックされます。 [監査のみ] に設定すると、ブロックではなく Windows イベントが発生します。 [未構成] に設定すると、設定は Windows の既定値 (無効) に戻されます。 この ASR 規則は、次の GUID を使用して制御されます。5BEB7EFE-FD9A-4556-801D-275E5FFC04CC
  
  **既定値**:ブロックする

- **[Email content execution type]\(電子メール コンテンツ実行タイプ\)** :    
  [電子メールおよび Web メールのクライアントからの実行可能なコンテンツをブロックする](https://go.microsoft.com/fwlink/?linkid=872980)

  [はい] に設定すると、電子メール クライアントおよび Web メール クライアントからダウンロードされた実行可能コンテンツがブロックされます。 [監査のみ] に設定すると、ブロックではなく Windows イベントが発生します。 [未構成] に設定すると、設定は Windows の既定値 (無効) に戻されます。

  **既定値**:ブロックする

- **[Prevent credential stealing type]\(資格情報盗難防止タイプ\)** :  
  [悪用からデバイスを保護する](https://go.microsoft.com/fwlink/?linkid=874499)
  
  [はい] に設定すると、lsass.exe を使介して資格情報を盗もうとする試みがブロックされます。 [監査のみ] に設定すると、ブロックではなく Windows イベントが発生します。 [未構成] に設定すると、設定は Windows の既定値 (無効) に戻されます。 この ASR 規則は、次の GUID を使用して制御されます。9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2

  **既定値**:[ウェイクアップ時間 (デスクトップ コンピューター)] を有効にして、デスクトップ コンピューターが、スケジュールされた更新またはソフトウェアのインストールを実行するために、スリープ状態または休止状態から復帰する時刻を指定します。

- **[Defender potentially unwanted app action]\(Defender の望ましくないアプリに対するアクション\)** :  
  CSP:[Defender/PUAProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-puaprotection)+

  Microsoft Defender ウイルス対策に備わっている望ましくない可能性があるアプリケーション (PUA) 保護機能では、PUA を特定して、ご使用のネットワーク内のエンドポイントへのダウンロードやインストールをブロックできます。 これらのアプリケーションはウイルス、マルウェア、または他の種類の脅威とは見なされませんが、パフォーマンスや使用に悪影響を与えるアクションをエンドポイントで実行する可能性があります。 PUA は、評価が低いと考えられるアプリケーションを指すこともあります。 一般的な PUA の動作は次のとおりです。さまざまな種類のソフトウェア バンドル。Web ブラウザーへの広告挿入。問題を検出し、エラーの修正に対して支払いを要求するが、エンドポイント上に残っていて変更や最適化を何も行わないドライバーやレジストリのオプティマイザー ("偽装ウイルス対策" プログラムとも呼ばれます)。 これらのアプリケーションは、ネットワークがマルウェアに感染するリスクを高め、識別困難なマルウェア感染を引き起こし、アプリケーションのクリーンアップで IT リソースを浪費させる可能性があります。

  **既定値**:ブロックする

- **[USB から実行される信頼されていないプロセスまたは署名されていないプロセスをブロックする]** :  
  [悪用からデバイスを保護する](https://go.microsoft.com/fwlink/?linkid=874502)
  
  [はい] に設定すると、USB ドライブから実行されている信頼できないプロセスまたは署名のないプロセスがブロックされます。 [監査のみ] に設定すると、ブロックではなく Windows イベントが発生します。 [未構成] に設定すると、設定は Windows の既定値 (無効) に戻されます。 この ASR 規則は、次の GUID を使用して制御されます: b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4

  **既定値**:ブロックする

- **[ネットワークの保護]** :  
  [Defender/EnableNetworkProtection](https://go.microsoft.com/fwlink/?linkid=872618)

  [はい] に設定すると、システム上のすべてのユーザーに対してネットワーク保護が有効になります。 ネットワーク保護により、従業員はインターネット上のフィッシング詐欺や悪意のあるコンテンツにアクセスできません。 これには、サードパーティのブラウザーが含まれます。 [監査のみ] に設定すると、ユーザーは危険なドメインからブロックされなくなりますが、代わりに Windows イベントが発生します。 [未構成] に設定すると、設定は Windows の既定値 (無効) に戻されます。

  **既定値**:[ウェイクアップ時間 (デスクトップ コンピューター)] を有効にして、デスクトップ コンピューターが、スケジュールされた更新またはソフトウェアのインストールを実行するために、スリープ状態または休止状態から復帰する時刻を指定します。

- **[Defender sample submission consent type]\(Defender のサンプル送信の同意の種類\)** :  
  [Defender/SubmitSamplesConsent](https://go.microsoft.com/fwlink/?linkid=2067131)

  Microsoft Defender でデータを送信するためのユーザーの同意レベルを確認します。 必要な同意が既に与えられている場合、Microsoft Defender からそれらが送信されます。 それ以外の場合 (かつユーザーが "確認しない" を指定した場合)、(Defender/AllowCloudProtection が許可されている場合は) データを送信する前にユーザーの同意を求める UI が起動します。

  **既定値**:安全なサンプルを自動的に送信します。

::: zone-end
::: zone pivot="mdm-may-2019"

- **ネットワーク ファイルをスキャンする**  
  [Defender/AllowScanningNetworkFiles](https://go.microsoft.com/fwlink/?linkid=2114049)

  - **既定値**:はい

- **JavaScript または VBScript による、ダウンロードされた実行可能なコンテンツの起動をブロックする**  
  [悪用からデバイスを保護する](https://go.microsoft.com/fwlink/?linkid=872979)

  [はい] に設定すると、インターネットからダウンロードされた JavaScript ファイルまたは VBScript ファイルの実行が Defender によってブロックされます。 [監査のみ] に設定すると、ブロックではなく Windows イベントが発生します。 [未構成] に設定すると、設定は Windows の既定値 (無効) に戻されます。 この ASR 規則は、次の GUID を使用して制御されます。D3E037E1-3EB8-44C8-A917-57927947596D

::: zone-end
::: zone pivot="mdm-may-2019,mdm-preview"

## <a name="ms-security-guide"></a>MS Security Guide (MS セキュリティ ガイド)

詳細については、Windows の「[Policy CSP - MSSecurityGuide](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mssecurityguide)」(ポリシー CSP - MSSecurityGuide) を参照してください。

- **[Apply UAC restrictions to local accounts on network logon]\(ネットワーク ログオン時にローカル アカウントに UAC 制限を適用する\)** :  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067188)

  **既定値**:Enabled

- **[SMB v1 client driver start configuration]\(SMB v1 クライアント ドライバーの開始時の構成\)** :  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067214)

  **既定値**:Disabled driver (無効なドライバー)

- **[SMB v1 server]\(SMB v1 サーバー\)** :  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067190)

  **既定値**:無効

- **[Digest authentication]\(ダイジェスト認証\)** :  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067193)

  **既定値**:無効

- **[Structured exception handling overwrite protection]\(構造化例外処理の上書き保護)\** :  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067217)

  **既定値**:Enabled

## <a name="mss-legacy"></a>MSS Legacy (MSS レガシ)

詳細については、Windows の「[Policy CSP - MSSLegacy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-msslegacy)」(ポリシー CSP - MSSLegacy) を参照してください。

- **[Network IP source routing protection level]\(ネットワーク IP ソース ルーティングの保護レベル\)** :  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067220)

  **既定値**:Highest protection (最高の保護)  

- **[Network ignore NetBIOS name release requests except from WINS servers]\(ネットワークが WINS サーバーからのを除く NetBIOS 名のリリース要求を無視する\)** :  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067218)

  **既定値**:Enabled

- **[Network IPv6 source routing protection level]\(ネットワーク IPv6 ソース ルーティングの保護レベル\)** :  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067216)

  **既定値**:Highest protection (最高の保護)

- **[Network ICMP redirects override OSPF generated routes]\(ネットワーク ICMP が生成されたオーバーライド OSPF ルートをリダイレクトする\)** :  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067326)

  **既定値**:無効

## <a name="power"></a>電源

詳細については、Windows の「[Policy CSP - Power](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power)」(ポリシー CSP - Power) を参照してください。

- **[Require password on wake while plugged in]\(電源接続中のスリープ解除時にパスワードを要求する\)** :  
  このポリシー設定では、システムのスリープ状態を解除するときに、ユーザーにパスワードを要求するかどうかを指定します。 このポリシー設定を有効にした場合、または構成しなかった場合、ユーザーはシステムのスリープ状態を解除するときにパスワードを要求されます。 このポリシー設定を無効にすると、ユーザーはシステムのスリープ状態を解除するときにパスワードを要求されません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067221)

  **既定値**:Enabled

- **[Standby states when sleeping while on battery]\(バッテリ使用中のスリープ状態時のスタンバイ状態\)** :  
  このポリシー設定では、コンピューターをスリープ状態にするときに Windows でスタンバイ状態を使用できるかどうかを管理します。 このポリシー設定を有効にしたり、構成しない場合、Windows はスタンバイ状態を使用してコンピューターをスリープ状態にします。 このポリシー設定を無効にすると、スタンバイ状態 (S1-S3) は許可されなくなります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067195)

  **既定値**:無効

- **[Standby states when sleeping while plugged in]\(電源接続中のスリープ状態時のスタンバイ状態\)** :  
  このポリシー設定では、コンピューターをスリープ状態にするときに Windows でスタンバイ状態を使用できるかどうかを管理します。 このポリシー設定を有効にしたり、構成しない場合、Windows はスタンバイ状態を使用してコンピューターをスリープ状態にします。 このポリシー設定を無効にすると、スタンバイ状態 (S1-S3) は許可されなくなります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067196)

  **既定値**:無効

- **[Require password on wake while on battery]\(バッテリ使用中のスリープ解除時にパスワードを要求する\)** :  
  このポリシー設定では、システムのスリープ状態を解除するときに、ユーザーにパスワードを要求するかどうかを指定します。 このポリシー設定を有効にした場合、または構成しなかった場合、ユーザーはシステムのスリープ状態を解除するときにパスワードを要求されます。 このポリシー設定を無効にすると、ユーザーはシステムのスリープ状態を解除するときにパスワードを要求されません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067322)

  **既定値**:Enabled

::: zone-end
::: zone pivot="mdm-may-2019"

## <a name="remote-assistance"></a>リモート アシスタンス

詳細については、Windows ドキュメントの[ポリシー CSP - RemoteAssistance](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remoteassistance#remoteassistance-solicitedremoteassistance) に関するページをご覧ください。

- **[要請されたリモート アシスタンス]** :  
  このポリシー設定を使用すると、このコンピューター上で要請されたリモート アシスタンスを有効または無効に設定することができます。
  
  - "*このポリシー設定を有効にすると*"、このコンピューターのユーザーは電子メールやファイル転送を使用して他のユーザーに支援を求めることができます。 また、ユーザーは、インスタント メッセージング プログラムを使用してこのコンピューターへの接続を許可したり、追加のリモート アシスタンスの設定を構成したりすることができます。

  - "*このポリシー設定を無効にすると*"、このコンピューターのユーザーは電子メールやファイル転送を使用して他のユーザーに支援を求めることができません。 また、ユーザーは、インスタント メッセージング プログラムを使用してこのコンピューターへの接続を許可することができなくなります。

  - "*このポリシー設定を構成しない場合*" は、コントロール パネルの [システムのプロパティ] からユーザーが自分で、要請されたリモート アシスタンスを有効または無効に設定することができます。 ユーザーは、リモート アシスタンスの設定を構成することもできます。

  このポリシー設定を有効にした場合、ヘルパーがリモート アシスタンスを提供できるようにするには、2 つの方法があります。"ヘルパーにコンピューターの閲覧のみを許可する" または "ヘルパーにコンピューターのリモート制御を許可する" です。 [チケットの最大有効時間] ポリシー設定によって、電子メールまたはファイル転送を使用して作成されたリモート アシスタンスの招待の有効時間の制限を設定することができます。 [Select the method for sending email invitations]\(電子メールの招待の送信方法を選択する\) 設定によって、リモート アシスタンスの招待の送信に使用する電子メール規格を指定できます。 お使いの電子メールのプログラムによって、*Mailto* 規格 (招待を受信する側がインターネット リンク経由で接続) か、または SMAPI (簡易 MAPI) 規格 (招待を電子メールのメッセージに添付) を使用できます。 Windows Vista では SMAPI だけがサポートされている方法であるため、このポリシー設定は使用できません。 このポリシー設定を有効にした場合は、リモート アシスタンスが通信できるように、適切なファイアウォールの例外を有効にする必要もあります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067198)

  **既定値**:リモート アシスタンスを無効にする

<!-- These settings are not available: 
  When set to *Enable Remote Assistance*, configure the following additional settings:

  - **Remote Assistance solicited permission**:  
    **Default**: View

  - **Maximum ticket time value**:  
    **Default**: *Not configured*

  - **Maximum ticket time period**:  
    **Default**: Minutes

  - **E-Mail invitation method**:  
    **Default**: Simple MAPI
-->

::: zone-end
::: zone pivot="mdm-preview,mdm-may-2019"

## <a name="remote-desktop-services"></a>リモート デスクトップ サービス

詳細については、Windows ドキュメントの「[Policy CSP - RemoteDesktopServices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remotedesktopservices)」(ポリシー CSP - RemoteDesktopServices) を参照してください。

- **[Block password saving]\(パスワードの保存をブロックする\)** :  
  リモート デスクトップ接続からこのコンピューターにパスワードを保存できるかどうかを制御します。 この設定を有効にすると、リモート デスクトップ接続のパスワードを保存するためのチェック ボックスが使用できなくなり、以降、ユーザーはパスワードを保存できなくなります。 ユーザーがリモート デスクトップ接続で RDP ファイルを開いて設定を保存した場合、RDP ファイルに以前から存在していたパスワードはすべて削除されます。 この設定を無効または未構成にする場合、ユーザーはリモート デスクトップ接続でパスワードを保存できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067301)

   **既定値**:Enabled

- **[Secure RPC communication]\(セキュリティで保護された RPC 通信\)** :  
  リモート デスクトップ セッション ホスト サーバーで、すべてのクライアントとセキュリティで保護された RPC 通信を必要にするか、またはセキュリティで保護されていない通信を許可するかを指定します。 この設定を使用して、認証されて暗号化された要求のみを許可することにより、クライアントとの RPC 通信のセキュリティを強化できます。 状態が有効に設定されている場合、リモート デスクトップ サービスは、セキュリティで保護された要求をサポートする RPC クライアントからの要求を受け入れて、信用されていないクライアントとのセキュリティで保護されていない通信を許可しません。 状態が無効に設定されている場合は、リモート デスクトップ サービスではすべての RPC トラフィックに対してセキュリティが常に要求されます。 しかし、要求に応答しない RPC クライアントにはセキュリティで保護されていない通信が許可されます。 状態が未構成に設定されている場合は、セキュリティで保護されていない通信が許可されます。 注:RPC インターフェイスがリモート デスクトップ サービスの管理または構成に使用されています。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067248)

  **既定値**:Enabled

- **[Block drive redirection]\(ドライブのリダイレクトをブロックする\)** :  
  このポリシー設定では、リモート デスクトップ サービス セッションで、クライアント ドライブのマッピングをしないようにするかどうかを指定します (ドライブ リダイレクト)。 既定の RD セッション ホスト サーバーでは、接続時に自動的にクライアント ドライブがマップされます。 マップされたドライブは、エクスプローラーまたは [コンピューター] のセッション フォルダー ツリーに、 *\<computername>* の *\<driveletter>* という形式で表示されます。 このポリシー設定を使用して、この動作をオーバーライドできます。 このポリシー設定を有効にすると、クライアント ドライブのリダイレクトはリモート デスクトップ サービス セッションでは許可されません。また、クリップボードでのファイル コピーのリダイレクトは、Windows Server 2003、Windows 8、および Windows XP を実行しているコンピューターでは許可されません。 このポリシー設定を無効にすると、クライアント ドライブのリダイレクトは常に許可されます。 また、クリップボードのリダイレクトを許可すると、クリップボードでのファイル コピーのリダイレクトは常に許可されます。 このポリシー設定を構成しなかった場合、クライアント ドライブのリダイレクトおよびクリップボードでのファイル コピーのリダイレクトはグループ ポリシー レベルでは指定されません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067197)

  **既定値**:Enabled

- **[Prompt for password upon connection]\(接続するときにパスワードを要求する\)** :  
  このポリシー設定では、リモート デスクトップ サービスに接続するたびにクライアントにパスワードを要求するかどうかを指定します。 この設定を使用すると、ユーザーがリモート デスクトップ接続クライアントで既にパスワードを入力している場合でも、リモート デスクトップ サービスにログオンするときにパスワードの入力を強制的に要求できます。 既定では、ユーザーはリモート デスクトップ接続クライアントにパスワードを入力すれば、リモート デスクトップ サービスに自動的にログオンできます。 このポリシー設定を有効にすると、ユーザーはリモート デスクトップ接続のクライアントでパスワードを供給しても、リモート デスクトップ サービスに自動的にログオンできません。 ユーザーは、ログオンするためにパスワードを要求されます。 このポリシー設定を無効にすると、ユーザーはリモート デスクトップ接続クライアントにパスワードを入力することで、リモート デスクトップ サービスに常に自動的にログオンできます。 このポリシー設定を構成しなかった場合、自動ログオンはグループ ポリシー レベルでは指定されません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067328)

  **既定値**:Enabled

- **[Remote desktop services client connection encryption level]\(リモート デスクトップ サービス クライアント接続の暗号化レベル\)** :  
  リモート デスクトップ プロトコル (RDP) 接続時に、クライアント コンピューターと RD セッション ホスト サーバー間の通信をセキュリティで保護するために、特定の暗号化レベルの使用を必要とするかどうかを指定します。 このポリシーは、ネイティブの RDP 暗号化を使用しているときにのみ適用されます。 ただし (SSL 暗号化と異なり) ネイティブ RDP 暗号化は推奨されません。 SSL 暗号化にこのポリシーは適用されません。 このポリシー設定を有効にすると、リモート接続時のクライアントと RD セッション ホスト サーバー間のすべての通信で、この設定で指定された暗号化方式を使用する必要があります。 既定では、暗号化レベルは高に設定されます。 次の暗号化方法を利用できます。

  - "*高*" - [高] 設定では、強力な 128 ビット暗号化を使ってクライアントとサーバー間で送受信されるデータを暗号化します。 この暗号化レベルは、128 ビットのクライアントのみが含まれる環境で使用します (たとえば、リモート デスクトップ接続を実行しているクライアント)。 この暗号化レベルをサポートしていないクライアントは RD セッション ホスト サーバーに接続できません。

  - "*クライアント互換*" - [クライアント互換] 設定では、クライアントとサーバーの間で送信されるすべてのデータは、クライアントでサポートされている最高のキー強度で暗号化されます。 この暗号化レベルは、128 ビット暗号化をサポートしていないクライアントが含まれる環境で使用します。

  - "*低*" - [低] 設定では、56 ビット暗号化を使ってクライアントからサーバーへ送信されるデータのみを暗号化します。  
  
  この設定を無効にするか、または構成しない場合は、RD セッション ホスト サーバーへのリモート接続に使用される暗号化レベルは、グループ ポリシーを通じて強制されません。 重要 FIPS 準拠は、システム暗号化を通じて構成できます。 グループ ポリシーの [暗号化、ハッシュ、署名のための FIPS 準拠アルゴリズムを使う] 設定 (場所: "コンピューターの構成\Windows の設定\セキュリティの設定\ローカル ポリシー\セキュリティ オプション")。[FIPS 準拠] 設定では、Microsoft 暗号化モジュールを使用して、Federal Information Processing Standard (FIPS) 140 暗号化アルゴリズムによって、クライアントとサーバー間で送受信されるデータを暗号化および暗号化解除します。 クライアントと RD セッション ホスト サーバーとの間の通信に最高レベルの暗号化が必要な場合、この暗号化レベルを使用します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067222)

  **既定値**:高

## <a name="remote-management"></a>リモート管理

詳細については、Windows ドキュメントの「[Policy CSP - RemoteManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remotemanagement)」(ポリシー CSP - RemoteManagement) を参照してください。

- **[Block storing run as credentials]\(実行アカウントの資格情報の保存をブロックする\)** :  
  クライアントの基本認証。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067300)

  **既定値**:Enabled

- **[基本認証]** :  
  このポリシー設定を使用すると、Windows リモート管理 (WinRM) サービスでリモート クライアントからの基本認証を受け付けるかどうかを管理できます。 このポリシー設定を有効にすると、WinRM サービスではリモート クライアントからの基本認証が受け付けられます。 このポリシー設定を無効にした場合、または構成しなかった場合は、WinRM サービスはリモート クライアントからの基本認証を受け付けません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067223)

  **既定値**:無効

- **[Block client digest authentication]\(クライアントのダイジェスト認証をブロックする\)** :  
  このポリシー設定を使用すると、Windows リモート管理 (WinRM) クライアントでダイジェスト認証を使用するかどうかを管理できます。 このポリシー設定を有効にすると、WinRM クライアントでダイジェスト認証は使用されません。 このポリシー設定を無効にした場合、または構成しなかった場合は、WinRM クライアントでダイジェスト認証が使用されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067302)

  **既定値**:Enabled

- **[暗号化されていないトラフィック]** :  
  このポリシー設定を使用すると、Windows リモート管理 (WinRM) サービスで、暗号化されていないメッセージをネットワーク経由で送受信するかどうかを管理できます。 このポリシー設定を有効にすると、WinRM クライアントでは暗号化されていないメッセージがネットワーク経由で送受信されます。 このポリシー設定を無効にした場合、または構成しなかった場合は、WinRM クライアントは、暗号化されたメッセージのみをネットワーク経由で送受信します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067226)

  **既定値**:無効

- **[クライアントが暗号化されていないトラフィック]** :  
  このポリシー設定を使用すると、Windows リモート管理 (WinRM) クライアントで、暗号化されていないメッセージをネットワーク経由で送受信するかどうかを管理できます。 このポリシー設定を有効にすると、WinRM クライアントでは暗号化されていないメッセージがネットワーク経由で送受信されます。 このポリシー設定を無効にした場合、または構成しなかった場合は、WinRM クライアントは、暗号化されたメッセージのみをネットワーク経由で送受信します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067304)

  **既定値**:無効

- **[クライアントの基本認証]** :  
  このポリシー設定を使用すると、Windows リモート管理 (WinRM) クライアントで基本認証を使用するかどうかを管理できます。 このポリシー設定を有効にすると、WinRM クライアントでは基本認証が使用されます。 WinRM が HTTP トランスポートを使用するように構成されている場合、ユーザー名とパスワードがクリア テキストとしてネットワーク経由で送信されます。 このポリシー設定を無効にした場合、または構成しなかった場合は、WinRM クライアントで基本認証は使用されません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067252)

  **既定値**:無効

## <a name="remote-procedure-call"></a>リモート プロシージャ コール

詳細については、Windows ドキュメントの「[Policy CSP - RemoteProcedureCall](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remoteprocedurecall)」(ポリシー CSP - RemoteProcedureCall) を参照してください。

- **[RPC unauthenticated client options]\(RPC の認証されていないクライアント オプション\)** :  
  このポリシー設定では、RPC サーバーに接続する認証されていない RPC クライアントを RPC サーバー ランタイムが処理する方法を制御します。 このポリシー設定は、すべての RPC アプリケーションに影響します。 ドメイン環境では、このポリシー設定はグループ ポリシーの処理自体を含む広範な機能に影響する可能性があるため、注意して使用する必要があります。 このポリシー設定の変更を元に戻すには、影響を受けた各コンピューターでの手動操作が必要になることがあります。 このポリシー設定をドメイン コントローラーに適用しないでください。 このポリシー設定を無効にすると、RPC サーバー ランタイムでは、Windows クライアントに対しては "認証済み" の値が使用され、このポリシー設定をサポートする Windows Server バージョンに対しては "なし" の値が使用されます。 このポリシー設定を構成しない場合、設定は無効のままになります。 RPC サーバー ランタイムは、Windows クライアントでは [認証済み] の値の使用が、このポリシー設定をサポートする Server SKU では [なし] の値の使用が有効にされた場合と同じように動作します。 このポリシー設定を有効にすると、コンピューター上で実行されている RPC サーバーに接続する、認証されていない RPC クライアントを制限するよう、RPC サーバー ランタイムに指示されます。 サーバーとの通信時に名前付きパイプを使用している場合、または RPC セキュリティを使用している場合に、クライアントは認証済みとして認識されます。 このポリシー設定で選択した値によっては、未認証のクライアントがアクセスできるよう明示的に要求した RPC インターフェイスが、この制限から除外される場合があります。

  - *[なし]* では、このポリシー設定が適用されるコンピューター上で実行されている RPC サーバーへの、すべての RPC クライアントの接続を許可します。

  - *[認証済み]* では、このポリシー設定が適用されるコンピューター上で実行されている RPC サーバーへの、認証済み (前の定義による) の RPC クライアントのみの接続を許可します。 例外を要求したインターフェイスは除外されます。

  - *[認証済み (例外なし)]* では、このポリシー設定が適用されるコンピューター上で実行されている RPC サーバーへの、認証済み (前の定義による) の RPC クライアントのみの接続を許可します。 例外は許可されません。 注:このポリシー設定は、システムが再起動されるまで適用されません。

  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067225)

  **既定値**:認証済み

## <a name="search"></a>検索

詳細については、Windows ドキュメントの「[Policy CSP - Search](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-search)」(ポリシー CSP - Search) を参照してください。

- **[Disable indexing encrypted items]\(暗号化されたアイテムのインデックス作成を無効にする\)** :  
  アイテムのインデックス作成を許可または禁止します。 これは Windows Search Indexer 用のスイッチです。Windows 情報保護 (WIP) で保護されたファイルなど、暗号化されたアイテムにインデックスを付けるかどうかを制御します。 このポリシーが有効な場合、WIP で保護されたアイテムにインデックスが付けられ、それらのメタデータは暗号化されていない場所に保存されます。 メタデータには、ファイル パスや変更日などがあります。 このポリシーが無効な場合、WIP で保護されたアイテムにはインデックスが付けられず、Cortana またはエクスプローラーの結果に表示されません。 また、デバイスに WIP で保護されたメディア ファイルが多数ある場合は、写真や Groove アプリのパフォーマンスにも影響が出る可能性があります。  
  [詳細情報]( https://go.microsoft.com/fwlink/?linkid=2067303)

  **既定値**:はい

## <a name="smart-screen"></a>スマート スクリーン

詳細については、Windows ドキュメントの「[Policy CSP - SmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-smartscreen)」 (ポリシー CSP - SmartScreen) を参照してください。

::: zone-end
::: zone pivot="mdm-preview"

- **[Block execution of unverified files]\(確認されていないファイルの実行をブロックする\)** :  
  確認されていないファイルをユーザーが実行しないようにします。

  - "*未構成*" - 従業員は SmartScreen の警告を無視し、悪意のあるファイルを実行できます。

  - "*はい*" - 従業員は SmartScreen の警告を無視して、悪意のあるファイルを実行することはできません。

  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067228)

  **既定値**:はい

- **[Require SmartScreen for apps and files]\(アプリとファイルに SmartScreen を要求する\)** :  
  IT 管理者が Windows 用の SmartScreen を構成することを許可します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067168)

  **既定値**:はい

::: zone-end
::: zone pivot="mdm-may-2019"

- **Windows SmartScreen を有効にする**  
  CSP:[SmartScreen/EnableSmartScreenInShell](https://go.microsoft.com/fwlink/?linkid=872784)

  [はい] に設定すると、すべてのユーザーに対して SmartScreen の使用が強制されます。 [はい] に設定すると、設定は Windows の既定値に戻されます。これにより、SmartScreen は有効にされますが、ユーザーはこの設定を変更できます。 SmartScreen を無効にするには、カスタム URI を使用します。

  **既定値**:はい

- **ユーザーが SmartScreen 警告を無視できないようにする**  
  CSP:[SmartScreen/PreventOverrideForFilesInShell](https://go.microsoft.com/fwlink/?linkid=872783)

  [はい] に設定されていると、SmartScreen は有効となり、ファイルや悪意のあるアプリに関する警告をユーザーは無視できません。 [未構成] に設定されていると、ユーザーはファイルや悪意のあるアプリに関する SmartScreen の警告を無視できます。  

  この設定では、[Windows SmartScreen の有効化] 設定を [はい] にする必要があります。

  **既定値**:はい

::: zone-end
::: zone pivot="mdm-preview,mdm-may-2019"

## <a name="system"></a>System (システム)

詳細については、Windows ドキュメントの「[Policy CSP - System ](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system)」(ポリシー CSP - System) を参照してください。

- **[System boot start driver initialization]\(システム ブート開始ドライバーの初期化\)** :  
  このポリシー設定を使用すると、起動時マルウェア対策のブート開始ドライバーによって決まる分類に基づいて、どのブート開始ドライバーを初期化するかを指定できます。 起動時マルウェア対策のブート開始ドライバーは、各ブート開始ドライバーに次のような分類を返します。

  - "*良好*" - ドライバーが署名されていて、改ざんされていません。

  - *不良* - ドライバーがマルウェアとして認識されました。 既知の不良のドライバーの初期化を許可しないことをお勧めします。

  - "*不良 (ブートに不可欠)* " - ドライバーはマルウェアとして認識されましたが、このドライバーを読み込まなければコンピューターを正常に起動できません。

  - "*不明*" - このドライバーは、マルウェアの検出アプリケーションで証明されていないため、起動時マルウェア対策のブート開始ドライバーによって分類されていません。

  このポリシー設定を有効にした場合、次にコンピューターを起動したときに初期化するブート開始ドライバーを選択できます。 このポリシー設定を無効にした場合、または構成しなかった場合、良好、不明、または不良 (ブートに不可欠) と判定されたブート開始ドライバーは初期化され、不良と判定されたドライバーの初期化はスキップされます。 お使いのマルウェアの検出アプリケーションに起動時マルウェア対策のブート開始ドライバーが含まれない場合、または起動時マルウェア対策のブート開始ドライバーが無効になっている場合、この設定は影響せず、すべてのブート開始ドライバーが初期化されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067307)

  **既定値**:良好、不明、および不良 (ブートに不可欠)

## <a name="wi-fi"></a>Wi-Fi

詳細については、Windows ドキュメントの「[Policy CSP - Wifi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi)」(ポリシー CSP - Wifi) を参照してください。

- **[インターネット共有をブロックする]** :  
  インターネット共有がデバイスで可能かどうかを指定します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067327)

  **既定値**:はい

- **[Block Automatically connecting to Wi-Fi hotspots]\(Wi-Fi ホットスポットへの自動接続をブロックする\)** :  
  デバイスが Wi-Fi ホットスポットに自動的に接続するのを許可または禁止します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067320)

  **既定値**:はい

## <a name="windows-connection-manager"></a>Windows 接続マネージャー

詳細については、Windows ドキュメントの「[Policy CSP - WindowsConnectionManager](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsconnectionmanager)」(ポリシー CSP - WindowsConnectionManager) を参照してください。

- **[Block connection to non-domain networks]\(非ドメイン ネットワークへの接続をブロックする\)** :  
  このポリシー設定は、コンピューターがドメイン ベースのネットワークと非ドメイン ベースのネットワークに同時に接続することを禁止します。 このポリシー設定を有効にした場合、コンピューターは次の状況で自動または手動のネットワーク接続試行に応答します。

  - *[自動接続試行]* - コンピューターがドメイン ベースのネットワークに既に接続している場合は、非ドメイン ネットワークへの自動接続試行がすべてブロックされます。 コンピューターが非ドメイン ベースのネットワークに既に接続している場合は、ドメイン ネットワークへの自動接続試行がブロックされます。

  - *[手動接続試行]* - コンピューターがイーサネット以外のメディアを介して非ドメイン ベースのネットワークまたはドメイン ベースのネットワークに接続しているときに、ユーザーがこのポリシー設定に違反して他のネットワークへの手動接続を作成しようとした場合は、既存のネットワーク接続が切断され、手動接続が許可されます。 コンピューターがイーサネットを介して非ドメイン ベースのネットワークまたはドメイン ベースのネットワークに接続しているときに、ユーザーがこのポリシー設定に違反して他のネットワークへの手動接続を作成しようとした場合は、既存のイーサネット接続が保持され、手動接続試行がブロックされます。

  このポリシー設定を構成しなかった場合、または無効にした場合、コンピューターはドメイン ネットワークと非ドメイン ネットワークの両方に同時に接続できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067323)

  **既定値**:Enabled

::: zone-end
::: zone pivot="mdm-may-2019"

## <a name="windows-hello-for-business"></a>Windows Hello for Business

- **Windows Hello for Business をブロックする**  
  Windows Hello for Business は、パスワード、スマート カード、および仮想スマート カードを置き換えることで Windows にサインインする代替方法です。 このポリシー設定を無効にした場合、または構成しなかった場合、デバイスでは Windows Hello for Business がプロビジョニングされます。 このポリシー設定を有効にした場合、デバイスではどのユーザーに対しても Windows Hello for Business をプロビジョニングが行われません。

  **既定値**:Enabled
  
  *[無効]* に設定すると、次の設定を構成できます。

  - **PIN の長さの最小値**  
    PIN の長さの最小値は 4 から 127 文字にする必要があります。

    **既定値**:*未構成*

  - **可能な場合、高度なスプーフィング対策の使用を有効にする**  
    [スプーフィング対策保護](https://go.microsoft.com/fwlink/?linkid=2067192)

    有効にした場合、デバイスでは拡張スプーフィング対策が使用されます (使用可能な場合)。 構成しない場合、スプーフィング対策のクライアント構成が受け入れられます。

    **既定値**:未構成

  - **[PIN での小文字の使用]** :  
    必須にした場合、ユーザーの PIN には少なくとも 1 文字の小文字が含まれる必要があります。

    **既定値**:許可しない

  - **[PIN での特殊文字の使用]** :  
    必須にした場合、ユーザーの PIN には少なくとも 1 文字の特殊文字が含まれる必要があります。

    **既定値**:許可しない
 

  - **PIN での大文字の使用**:  
    必須にした場合、ユーザーの PIN には少なくとも 1 文字の大文字が含まれる必要があります。

    **既定値**:許可しない

::: zone-end
::: zone pivot="mdm-preview,mdm-may-2019"

## <a name="windows-ink-workspace"></a>Windows Ink ワークスペース

詳細については、Windows ドキュメントの「[Policy CSP - WindowsInkWorkspace](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsinkworkspace)」(ポリシー CSP - WindowsInkWorkspace) を参照してください。

- **[Ink Workspace]\(Ink ワークスペース\)** :  
  ユーザーに Ink ワークスペースへのアクセスを許可するかどうかを指定します。

  - "*無効*" - Ink ワークスペースへのアクセスは無効にされます。 機能はオフになります。

  - "*有効*" - Ink ワークスペース機能はオンですが、ユーザーはロック画面上ではそれにアクセスできません。

  - *未構成* - Ink ワークスペース機能がオンにされ、ユーザーはロック画面上でそれを使用できるようになります。

  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067241)

  **既定値**:Enabled

## <a name="windows-powershell"></a>Windows PowerShell

詳細については、Windows ドキュメントの「[Policy CSP - WindowsPowerShell](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowspowershell)」 (ポリシー CSP - WindowsPowerShell) を参照してください。

- **[PowerShell script block logging]\(PowerShell スクリプト ブロックのログ記録\)** :  
  このポリシー設定は、Microsoft-Windows-PowerShell/Operational イベント ログへのすべての PowerShell スクリプト入力のログ記録を有効にします。 このポリシー設定を有効にした場合、Windows PowerShell は対話的に、またはオートメーションを介して呼び出された、コマンド、スクリプト ブロック、関数、およびスクリプトの処理をログに記録します。 このポリシー設定を無効にすると、PowerShell スクリプトの入力のログ記録は無効になります。 スクリプト ブロックの呼び出しのログ記録を有効にすると、PowerShell はさらに、コマンド、スクリプト ブロック、関数、またはスクリプトの呼び出しの開始時または停止時にイベントを記録します。 呼び出しのログ記録を有効にすると、大量のイベント ログが生成されます。 注:このポリシー設定は、グループ ポリシー エディターの [コンピューターの構成] と [ユーザーの構成] の両方の下にあります。 [コンピューターの構成] のポリシー設定は、[ユーザーの構成] のポリシー設定よりも優先されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067330)

  **既定値**:Enabled

::: zone-end
::: zone pivot="mdm-may-2019"

## <a name="whats-changed-in-the-new-template"></a>新しいテンプレートでの変更点

"*2019 年 5 月の MDM セキュリティ ベースライン*" テンプレートでは、"*プレビュー*" テンプレートから次の点が変更されています。

### <a name="changes-to-the-baseline-settings"></a>ベースラインの設定に対する変更

以下の設定は、次のいずれかになります。

- "*新規*": この最新バージョンのベースラインでの新しい設定。
- "*削除*": 以前のバージョンに存在していたが、この最新のベースライン バージョンで削除された設定。
- "*変更*": 以前のバージョンから何らかの変更が行われた設定。

*[新規]* [**上でロック**](#above-lock):

- **ロック画面から音声でアプリをアクティブ化する**

*[新規]* [**アプリケーション管理**](#application-management):

- **インストールに対するユーザー制御をブロックする**
- **昇格された特権による MSI アプリのインストールをブロックする**

*[削除]* [**BitLocker**](#bitlocker):

- BitLocker のリムーバブル ドライブのポリシー > **暗号化方法**
- **BitLocker の固定ドライブのポリシー** *(すべての設定)*
- **BitLocker のシステム ドライブのポリシー** *(すべての設定)*

*[新規]* [**接続**](#connectivity):

- **UNC パスへのセキュリティで保護されたアクセスを構成**

*[新規]* [**Device Guard**](#device-guard):

- **仮想化ベースのセキュリティ**

*[新規]* [**DMA ガード**](#dma-guard):

- **Kernel DMA Protection と互換性のない外部デバイスの列挙**

*[新規]* [**Internet Explorer**](#internet-explorer):

- **Internet Explorer のインターネット ゾーンでスクリプトを介してステータス バーを更新する**
- **Internet Explorer のインターネット ゾーンでのファイルのドラッグ アンド ドロップまたはコピーと貼り付け**
- **Internet Explorer の制限付きゾーンでの .NET Framework 依存コンポーネント**
- **Internet Explorer のローカル コンピューター ゾーンで Active X コントロールに対してマルウェア対策を実行しない**
- **Internet Explorer の暗号化サポート**

*[変更]* [**Internet Explorer**](#internet-explorer):

- **Internet Explorer のインターネット ゾーンでのファイルのダウンロードに対する自動プロンプト** > 既定値が**無効**になりました。 プレビューでは、この設定は有効に設定されていました。

*[新規]* [**リモート アシスタンス**](#remote-assistance):

- **要請されたリモート アシスタンス**
  - **要請されたリモート アシスタンスのアクセス許可**
  - **チケットの最大有効時間値**
  - **チケットの最大有効期間**
  - **メール招待方法**

*[新規]* [**Microsoft Defender**](#microsoft-defender):

- **子プロセスでの Adobe Reader の起動**
- **子プロセスでの Office 通信アプリの起動**

*[新規]* [**ファイアウォール**](#firewall)

- **ファイアウォール プロファイル ドメイン**
  - **受信接続をブロック**
  - **送信接続が必要**
  - **着信通知をブロック**
  - **ファイアウォールの有効化**
- **ファイアウォール プロファイル パブリック**
  - **受信接続をブロック**
  - **送信接続が必要**
  - **着信通知をブロック**
  - **ファイアウォールの有効化**
  - **グループ ポリシーからの接続セキュリティ ルールをマージしない**
  - **グループ ポリシーからのポリシー ルールをマージしない**
- **ファイアウォール プロファイル プライベート**
  - **受信接続をブロック**
  - **送信接続が必要**
  - **着信通知をブロック**
  - **ファイアウォールの有効化**

*[新規]* [**Windows Hello for Business**](#windows-hello-for-business):

- **使用可能な場合は、高度なスプーフィング対策を要求する**
- **Windows Hello for Business の構成**
- **PIN に小文字が必要**
- **PIN に特殊文字が必要**
- **PIN の長さの最小値**
- **PIN に大文字が必要**

::: zone-end

## <a name="next-steps"></a>次のステップ

- [セキュリティ ベースラインに関する詳細](security-baselines.md)
- [競合を回避する](security-baselines.md#avoid-conflicts)
- [Intune でのポリシーとプロファイルのトラブルシューティング](../configuration/troubleshoot-policies-in-microsoft-intune.md)
