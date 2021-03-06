---
title: 1606 の診断データ
titleSuffix: Configuration Manager
description: Configuration Manager バージョン 1606 で収集される診断結果および使用状況データの各種レベルについて説明します。
ms.date: 12/29/2016
ms.prod: configuration-manager
ms.technology: configmgr-core
ms.topic: conceptual
ms.assetid: f7350d03-f440-4744-82d4-75f8c6c25028
author: aczechowski
ms.author: aaroncz
manager: dougeby
ROBOTS: NOINDEX
ms.openlocfilehash: cd58fb2ad105d3fb94fcc1d2fe56f0ae64f766f1
ms.sourcegitcommit: bbf820c35414bf2cba356f30fe047c1a34c5384d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "81697070"
---
# <a name="levels-of-diagnostic-usage-data-collection-for-version-1606-of-configuration-manager"></a>Configuration Manager バージョン 1606 で収集される診断結果および使用状況データのレベル

*適用対象:Configuration Manager (Current Branch)*

Configuration Manager バージョン 1606 では、**基本**、**エンハンス**、**フル**の 3 つのレベルの診断結果と使用状況データが収集されます。 既定では、この機能は、エンハンス レベルに設定されます。 以降のセクションでは、各レベルで収集されるデータについて詳しく説明します。

以前のバージョンからの変更は、***[新規]***、***[更新]***、***[削除]***、または ***[移動]*** で示されます。


> [!IMPORTANT]
>  Configuration Manager は、基本レベルとエンハンス レベルでは、サイト コードまたはサイト名、IP アドレス、ユーザー名またはコンピューター名、物理アドレス、電子メール アドレスを収集しません。 フル レベルで収集したこの情報 (ログ ファイルやメモリのスナップショットなどの詳細な診断情報に含まれる可能性があります) に特別な目的はありません。 Microsoft が個人の特定、連絡、広告作成の目的でこの情報を使用することはありません。

##  <a name="how-to-change-the-level"></a><a name="bkmk_change"></a> レベルを変更する方法
 管理者に指定された役割に基づいた管理スコープに、**サイト** オブジェクト クラスにおける**変更**アクセス許可が含まれる場合、その管理者は、Configuration Manager コンソールの診断結果と使用状況データの設定で収集されるデータ レベルを変更できます。

   そのためには、コンソールで Backstage タブ (ドロップダウン矢印の付いた左上のタブ) に移動し、 **[使用状況データ]** を選んで、使うデータ レベルを選びます。  

##  <a name="level-1---basic"></a><a name="bkmk_level1"></a> レベル 1 - 基本
 基本レベルには階層に関するデータが含まれています。これには、インストールまたはアップグレードのエクスペリエンスを向上させるために必要なデータや、階層に適用できる Configuration Manager 更新プログラムを判断するために役立つデータが含まれます。

 Configuration Manager バージョン 1606 以降、このレベルには次のデータが含まれます。


-   セットアップ情報:
      - ビルド、インストールの種類、言語パック、有効にされた機能  

      -   更新プログラム パックの展開の状態とエラー、ダウンロードの進行状況、前提条件エラー 

      -  アップグレード後のスクリプトのバージョン

      -  更新プログラムの高速リングの使用

-   データベースのパフォーマンス指標 (レプリケーション処理情報、プロセッサおよびディスク使用率が上位の SQL Server ストアド プロシージャ)

-   基本的なデータベース構成 (プロセッサ、クラスターの構成、分散ビューの構成)

-   Configuration Manager データベース スキーマ (すべてのオブジェクト定義のハッシュ)

-   Configuration Manager クライアント バージョンとオペレーティング システム バージョンの数

-   マネージド デバイスのオペレーティング システムおよび Exchange Connector によって設定されたポリシーの数

-   クライアントの言語とロケールの数

-   Windows 10 デバイスの数 (ブランチおよびビルド別)

-   Configuration Manager サイト階層の基本データ (サイトの一覧、種類、バージョン、状態、クライアントの数、およびタイム ゾーン)

-   サイト システム サーバーの基本情報 (使用されるサイト システムの役割、インターネットと SSL ステータス、オペレーティング システム、プロセッサ、物理または仮想マシン)

-   ユーザー探索に関する基本統計情報 (ユーザー探索の数、グループ サイズの最小/最大/平均値)

-   エンドポイント保護の基本情報 (マルウェア対策クライアントのバージョン)

-   アプリケーションと展開の種類の数に関する基本情報 (アプリの合計、複数の展開の種類を持つアプリの合計、依存関係を持つアプリの合計、置き換えられたアプリの合計、使用中の展開テクノロジの数)

-   基本的なオペレーティング システム展開 (OSD) 数 (イメージ)

-   配布ポイントと管理ポイントの種類、構成の基本情報 (保護済み、事前設定済み、PXE、マルチキャスト、SSL の状態、プル/ピア配布ポイント、MDM 対応、SSL 対応など)

-   製品利用統計情報 (実行時、ランタイム、エラー)

-  構成された製品利用統計情報のレベル、モード (オンラインまたはオフライン)、更新プログラムの高速構成

-  ネットワーク探索の使用 (有効または無効)
-  管理コンソール:

    -  コンソール接続に関する統計情報 (オペレーティング システムのバージョン、言語、SKU、アーキテクチャに加えて、システム メモリ、論理プロセッサの数、接続サイト ID、インストールされてた .NET のバージョン、コンソールの言語パック)    


- ***[新規]*** SQL のバージョン、Service Pack レベル、エディション、照合順序 ID、文字セット


##  <a name="level-2---enhanced"></a><a name="bkmk_level2"></a> レベル 2 - エンハンス
エンハンス レベルはセットアップ終了後の既定値です。 このレベルには、基本レベルで収集されたデータと機能固有のデータ (頻度と使用期間)、Configuration Manager クライアントの設定 (コンポーネント名、状態、ポーリング間隔などの特定の設定)、およびソフトウェアの更新に関する基本情報が含まれます。

これが推奨レベルです。このレベルでは、製品やサービスを今後適切に改善するために最小限必要なデータを Microsoft に提供します。 このレベルでは、オブジェクト名 (サイト、ユーザー、コンピューター、またはオブジェクト)、セキュリティ関連のオブジェクトの詳細、またはソフトウェア更新プログラムを必要とするシステムの数などの脆弱性が収集されます。

Configuration Manager バージョン 1606 以降、このレベルには次のデータが含まれます。

-   **アプリケーション管理:**  

    -    組織内で使用される展開の種類の使用状況/ターゲットに関する基本情報 (対象となるユーザー/デバイス、必須/使用可能、ユニバーサル アプリ)  

    -   アプリケーションの展開情報 (インストール/アンインストール、承認が必要、ユーザーの介入が有効/無効、依存関係、置き換え)  

    -   使用可能なアプリケーション要求の統計  

    -   パッケージの数 (種類別)  

    -   アプリケーションへの適用の数 (オペレーティング システム別)  

    -   パッケージ/プログラムの展開の数  

    -   App-V 環境と展開のプロパティの数  

    -   Windows 10 ライセンスが供与されたアプリケーションのライセンスの数  

    -   時間帯あたりのユーザーまたはデバイスあたりのアプリケーション展開数の最小/最大/平均値

    -   メンテナンス期間の種類と期間  

    -  アプリケーション ポリシーのサイズと複雑さの統計情報

    - ***[新規]*** ビジネス向け Windows ストア アプリの数と同期の統計情報 (アプリの種類の集計を含む)  

    - ***[新規]*** 境界グループの統計情報 (高速の数、低速の数、グループあたりの数)

    - ***[新規]*** MSI 構成オプションとカウント

    - ***[新規]*** アプリの要件 (組み込み条件の数を参照する展開テクノロジ)

    - ***[新規]*** アプリの置き換え、チェーンの最大深度

    - ***[新規]*** Universal Data Access (UDA) の使用状況、作成方法



-   **クライアント:**  

    -   有効なクライアント エージェントの一覧/数  

    -   クライアント インストールの数 (ソースの場所の種類別)  

    -   クライアント インストール エラーの数  

    -  ***[新規]*** クライアントの自動アップグレード展開構成 (クライアントの試験稼働など)

    -  ***[新規]*** クライアントの正常性の統計情報と主要な問題のまとめ

    - ***[新規]*** BIOS の動作時間 (年単位)

    - ***[新規]*** オペレーティング システムの動作時間 (月単位)

    - ***[新規]*** ソフトウェア センターのアクションの数

    - ***[新規]*** Active Management Technology (AMT) クライアント バージョン

    - ***[新規]*** クライアント展開のダウンロード エラー

    - ***[新規]*** クライアント通知操作の動作状態 (各々の実行回数、対象となるクライアントの最大数、平均の成功率)

    - ***[新規]*** クライアントで使用される展開方法、展開方法ごとのクライアントの数

    - ***[新規]*** クライアントのキャッシュ サイズ構成



- "***[新規]***" **Cloud Services:**

  - ***[新規]*** Operations Management Suite に同期されているコレクションの数

  - ***[新規]*** Operations Management Suite クラウド コネクタが有効になっているかどうか



- ***[新規] コレクション:***

    -  ***[移動]*** コレクションの評価統計情報 (クエリ時間、割り当て数/未割り当て数、種類別のカウント、ID のロール オーバー、規則の使用状況)

    - ***[新規]*** 展開なしのコレクション

    - ***[新規]*** コレクション ID の使用状況 (ID が不足していない)



-   **コンプライアンス設定:**  

    -   構成アイテムの数 (種類別)  

    -   構成基準の基本情報 (数、展開数、参照数)  

    -   ***[更新]*** 組み込み設定を参照する展開の数 (修復設定をキャプチャするようになりました)  

    -   ***[更新]*** カスタム設定に対して作成された規則および展開の数 (修復設定をキャプチャするようになりました)  
    -   展開された Simple Certificate Enrollment Protocol (SCEP)、VPN、Wi-Fi、証明書 (.pfx)、コンプライアンス ポリシー テンプレートの数

    -  SCEP 証明書、VPN、Wi-Fi、証明書 (.pfx)、プラットフォーム別のコンプライアンス ポリシー展開の数

    - ***[新規]*** Passport for Work のポリシー (作成済み、展開済み)



-   **コンテンツ:**  

    -   境界の数 (種類別)  

    -   境界グループの情報 (各境界グループに割り当てられた境界とサイト システムの数)  

    -   配布ポイント グループの情報 (配布ポイント グループに割り当てられたパッケージと配布ポイントの数)  

    -   配布ポイントの構成情報 (ブランチ キャッシュの使用、配布ポイントの監視)  

    -   配布マネージャーの構成情報 (スレッド、再試行の待ち時間、再試行回数、プル配布ポイントの設定)  


-   **エンドポイント保護:**  

    -   Endpoint Protection のマルウェア対策および Windows ファイアウォール ポリシーの使用状況 (グループに割り当てられている固有のポリシーの数)<br /><br /> これには、ポリシーに含まれている設定に関する情報は含まれません。  

    -   エンドポイント保護の展開エラー (エンドポイント保護ポリシーの展開エラー コードの数)  

    -   エンドポイント保護ダッシュボードに表示するように選択されたコレクションの数  

    -   エンドポイント保護機能用に構成されたアラートの数  

    - ***[新規]*** Advanced Threat Protection (ATP) ポリシー (ポリシーの数、ポリシーが展開されているかどうか)


-   "***[削除]***" **モバイル アプリケーション管理 (MAM):**  

    -   ***[削除]*** MAM 対応 Office アプリケーションおよび基幹業務アプリケーションとポリシーの数 (オペレーティング システム別)  

    -   ***[削除]*** MAM アプリケーション/ポリシーの展開の数  

    -   ***[削除]*** MAM 設定ごとに作成された規則の数  


- "***[新規]***" **移行:**

  -  ***[新規]*** 移行されたオブジェクト (移行ウィザードを使用) の数



-   **モバイル デバイス管理 (MDM):**  

    -   発行されたモバイル デバイス アクション (ロック、ピン留め、ワイプ、インベントリからの削除) コマンドの数  

    -   Configuration Manager および Microsoft Intune によって管理されるモバイル デバイスの数と、そのデバイスの登録方法 (一括、ユーザー ベース)  

    -   モバイル デバイスのポーリング スケジュールと統計情報、モバイル デバイスのチェックイン期間  

    -   モバイル デバイス ポリシーの数  

    -   複数の登録済みモバイル デバイスを持つユーザーの数  

-   **Microsoft Intune のトラブルシューティング:**

    -   状態、ステータス、インベントリ、RDR、DDR、UDX、テナントの状態、POL、LOG、証明書、CRP、再同期、CFD、RDO、BEX、ISM、および Microsoft Intune からダウンロードされたコンプライアンス メッセージの数とサイズ

    -   Microsoft Intune にレプリケートされたデバイス アクション (ワイプ、インベントリからの削除、ロック)、製品利用統計情報、およびデータ メッセージの数とサイズ

    -   Microsoft Intune のユーザー同期に関する完全な統計とデルタ統計


-   **オンプレミス モバイル デバイス管理 (MDM):**  

    -   オンプレミス MDM アプリケーション展開に関する展開成功/失敗の統計情報  

    -   Windows 10 一括登録パッケージおよびプロファイルの数  



-   **オペレーティング システムの展開:**  

    -   ブート イメージ、ドライバー、ドライバー パッケージ、マルチキャスト対応の配布ポイント、PXE 対応の配布ポイント、およびタスク シーケンスの数  

    -   ***[新規]*** タスク シーケンス ステップの使用数



-   **サイトの更新プログラム:**

    - インストールされた Configuration Manager 修正プログラムのバージョン




-   **ソフトウェア更新プログラム:**  

    -   ソフトウェア更新プログラムの展開が含まれるコレクション数の合計/平均値、および展開された更新プログラム数の最大/平均値  

    -   同期に関連付けられた自動展開規則の数  

    -   新しく作成する、または更新プログラムを既存のグループに追加する自動展開規則の数  

    -   自動展開規則で使用される使用可能なデルタと期限デルタ  

    -   更新プログラムあたりの割り当て数の平均/最大値  

    -   System Center Update Publisher で作成および展開された更新プログラムの数  

    -   更新プログラムのグループと割り当ての数  

    -   更新プログラム パッケージの数と、パッケージの対象配布ポイント数の最大/最小/平均値  

    -   更新プログラム グループの数と、グループあたりの更新プログラム数の最小/最大/平均値  

    -   更新プログラムの数と、展開済み、期限切れ、置き換え済み、ダウンロード済み、および EULA を含む更新プログラムの割合  

    -   更新スキャン エラー コードとマシンの数  

    -   クライアント更新の評価とスキャンのスケジュール  

    -   ソフトウェアの更新ポイントの同期スケジュール  

    -   複数の展開を含む自動展開規則の数  

    -   アクティブな Windows 10 サービス プランに使用される構成  

    -   Windows 10 ダッシュボードのコンテンツ バージョン  

    -   Windows Update for Business を使用している Windows 10 クライアントの数  

    -   クラスターの修正プログラム適用の統計情報  

    -   展開された Office 365 更新プログラムの数  

    -   ソフトウェアの更新ポイントで同期される分類

    -   ***[新規]*** ソフトウェア更新ポイントの負荷分散の統計情報



-   **SQL/パフォーマンス データ:**  

    -   最大データベース テーブルの数  

    -   SQL Always-On レプリカ情報  

    -  SQL の変更の追跡の保有期間

    - ***[新規]*** 探索の種類、有効化、スケジュール (完全、増分)

    - ***[新規]*** 探索の運用統計 (見つかったオブジェクトの数)

    - ***[新規]*** SQL 変更の追跡のパフォーマンスの問題、保有期間、自動クリーンアップの状態



- "***[新規]***" **その他**

    - ***[新規]*** Wake On Lan (WOL) サイトの数



##  <a name="level-3---full"></a><a name="bkmk_level3"></a> レベル 3 - フル
フル レベルには、基本レベルとエンハンス レベルのすべてのデータが含まれます。 また、Endpoint Protection の詳細情報、更新プログラムの対応率、およびソフトウェア更新プログラム情報も含まれています。 このレベルには、キャプチャ時にメモリやログ ファイルに存在していた、個人情報が含まれる可能性があるシステム ファイルやメモリ スナップショットなどの詳細な診断情報を含めることもできます。

Configuration Manager バージョン 1606 以降、このレベルには次のデータが含まれます。

-   コレクションの評価および更新の統計情報

-   Endpoint Protection の正常性の概要 (保護済み、危険、不明、未サポート クライアントの数を含む)

-   Endpoint Protection ポリシーの構成

-   ソフトウェア更新プログラムの展開情報 (クライアントとUTC 時刻の対象となっている展開の割合、必須/オプション/サイレント、再起動抑制)

-   ソフトウェア更新プログラムの展開の全体的なコンプライアンス対応状況

-   自動展開規則の評価スケジュールの情報

-   ***[削除]*** ネットワーク アクセス保護ポリシーを持つクライアントの数

-   ソフトウェア更新プログラムの展開のエラー コードと数

-   ソフトウェア更新プログラムの展開コレクションの非アクティブなクライアント数の最小/最大/平均値

-   期限切れのソフトウェア更新プログラムが含まれるグループの数

-   パッケージあたりのソフトウェア更新プログラム数の最小/最大/平均値

-   ソフトウェア更新プログラムのスキャン成功の割合

-   最後のソフトウェア更新プログラムのスキャンが実行されてからの経過時間の最小/最大/平均値

-    ソフトウェアの更新ポイントで同期されるソフトウェア更新プログラムの製品
-    コンプライアンス設定: SCEP、VPN、Wi-Fi、コンプライアンス ポリシー テンプレートの構成の詳細

-    Intune で管理されるデバイス向けの EAS 条件付きアクセス ポリシーの種類 (ブロックまたは検疫)

-   ***[新規]*** 環境内の上位 50 の CPU

-   "***[新規]***" Configuration Manager の DCM 構成パックの使用状況

-   ***[新規]*** MSI 製品コード (顧客が展開する一般的なアプリ)

-   ***[新規]*** ATP の正常性の概要

-   ***[新規]*** クライアント展開のインストール エラーの詳細
