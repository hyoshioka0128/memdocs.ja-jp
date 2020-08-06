---
title: Microsoft Intune を使用して Windows デバイスの登録をセットアップする
titleSuffix: ''
description: Windows デバイスの登録をセットアップします。
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/22/2020
ms.topic: how-to
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f94dbc2e-a855-487e-af6e-8d08fabe6c3d
ms.reviewer: spshumwa
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9104716c469168a5ab2c5c1b49caf14071150db1
ms.sourcegitcommit: 302556d3b03f1a4eb9a5a9ce6138b8119d901575
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "83988913"
---
# <a name="set-up-enrollment-for-windows-devices"></a>Windows デバイスの登録をセットアップする

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

この記事は、IT 管理者がそのユーザーの Windows の登録を簡略化する場合に役立ちます。 [Intune が設定](../fundamentals/setup-steps.md)されたら、ユーザーは職場または学校のアカウントで[サインイン](https://docs.microsoft.com/mem/intune/user-help/windows-enrollment-company-portal)し、Windows デバイスを登録します。  

Intune 管理者は次の方法で登録を簡略化できます。

- [自動登録を有効にする](#enable-windows-10-automatic-enrollment) (Azure AD Premium が必須)
- [CNAME の登録](#simplify-windows-enrollment-without-azure-ad-premium)
- [一括登録を有効にする](windows-bulk-enroll.md) (Azure AD Premium と Windows Configuration Designer が必須)

Windows デバイスの登録を簡単にする方法は次の 2 つの要素で決まります。

- **Azure Active Directory Premium を使用していますか?** <br>[Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) は、Enterprise Mobility + Security およびその他のライセンス プランに付属します。
- **ユーザーはどのバージョンの Windows クライアントを登録しますか?** <br>Windows 10 デバイスは、職場または学校のアカウントを追加すると自動的に登録できます。 以前のバージョンでは、会社ポータル アプリを使用して登録する必要があります。

||**Azure AD Premium**|**その他の AD**|
|----------|---------------|---------------|  
|**Windows 10**|[自動登録](#enable-windows-10-automatic-enrollment) |ユーザー登録|
|**以前の Windows バージョン**|ユーザー登録|ユーザー登録|

自動登録を利用できる組織は、Windows 構成デザイナー アプリを利用し、[デバイスの一括登録](windows-bulk-enroll.md)を構成することもできます。

## <a name="device-enrollment-prerequisites"></a>デバイス登録の前提条件

管理者がデバイスを Intune に登録して管理する前に、管理者のアカウントにライセンスが既に割り当てられている必要があります。 [デバイスを登録するためのライセンス割り当ての詳細](../fundamentals/licenses-assign.md)

## <a name="multi-user-support"></a>マルチ ユーザー サポート

Intune では、次の両方のデバイスで、複数のユーザーがサポートされます。

- Windows 10 Creator の更新プログラムを実行する
- Azure Active Directory ドメインに参加している

標準ユーザーが自分の Azure AD 資格情報でサインインするとき、自分のユーザー名に割り当てられているアプリとポリシーが与えられます。 デバイスの[プライマリ ユーザー](../remote-actions/find-primary-user.md)だけが、アプリのインストールやデバイス操作 (削除、リセット) の実行などのセルフサービス シナリオのためにポータル サイトを使用できます。 プライマリ ユーザーが割り当てられていない共有 Windows 10 デバイスでも、ポータル サイトを使用して、使用可能なアプリをインストールできます。

[!INCLUDE [AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="simplify-windows-enrollment-without-azure-ad-premium"></a>Azure AD Premium なしで Windows 登録を簡略化する
Intune サーバーに登録要求をリダイレクトする、ドメイン ネーム サーバー (DNS) エイリアス (CNAME レコード タイプ) を作成することで、登録を簡略化できます。 それ以外の場合、Intune に接続を試行するユーザーは、登録時に Intune のサーバー名を入力する必要があります。

**手順 1:CNAME を作成する** (省略可能)<br>
会社のドメインの CNAME DNS リソース レコードを作成します。 たとえば、会社の Web サイトが contoso.com の場合、EnterpriseEnrollment.contoso.com を enterpriseenrollment-s.manage.microsoft.com にリダイレクトする CNAME を DNS に作成します。

CNAME DNS エントリの作成は省略可能ですが、CNAME レコードにより、ユーザーによる登録が簡単になります。 CNAME レコードの登録が見つからない場合、ユーザーは手動で MDM サーバー名 enrollment.manage.microsoft.com を入力するように求められます。

|Type|ホスト名|指定先|TTL|
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 時間|
|CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 時間|

企業に複数の UPN サフィックスがある場合は、ドメイン名ごとに 1 つ CNAME を作成し、それぞれで EnterpriseEnrollment-s.manage.microsoft.com をポイントする必要があります。 たとえば、Contoso のユーザーは電子メール/UPN として、次の形式を使用します。

- name@contoso.com
- name@us.contoso.com
- name@eu.contoso.com

Contoso DNS の管理者は、次の CNAME を作成する必要があります。

|Type|ホスト名|指定先|TTL|  
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 時間|
|CNAME|EnterpriseEnrollment.us.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 時間|
|CNAME|EnterpriseEnrollment.eu.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 時間|

`EnterpriseEnrollment-s.manage.microsoft.com` – Intune サービスへのリダイレクトとメールのドメイン名によるドメイン認識がサポートされます。

DNS レコードの変更が反映されるまでには、最大で 72 時間かかります。 DNS レコードの変更が反映されるまで、Intune で DNS の変更を確認することはできません。

## <a name="additional-endpoints-are-used-but-no-longer-supported"></a>追加のエンドポイントが使用されているが、サポートされなくなった
EnterpriseEnrollment-s.manage.microsoft.com が、登録において推奨される完全修飾ドメイン名です。 過去にお客様が使用していて、引き続き機能するその他のエンドポイントが 2 つありますが、サポートされなくなりました。 EnterpriseEnrollment.manage.microsoft.com (-s がない) と manage.microsoft.com は、両方とも自動検出サーバーのターゲットとして使用できますが、ユーザーは確認メッセージで [OK] をタッチする必要があります。 EnterpriseEnrollment-s.manage.microsoft.com をポイントすると、ユーザーが追加の確認ステップを実行する必要がないため、これは推奨される構成です。

## <a name="alternate-methods-of-redirection-are-not-supported"></a>リダイレクトの別の方法はサポートされていない
CNAME の構成以外の方法を使用することは、サポートされていません。 たとえば、プロキシ サーバーを使用して enterpriseenrollment.contoso.com/EnrollmentServer/Discovery.svc を enterpriseenrollment-s.manage.microsoft.com/EnrollmentServer/Discovery.svc または manage.microsoft.com/EnrollmentServer/Discovery.svc のいずれかにリダイレクトすることは、サポートされていません。

**手順 2: CNAME を確認する** (省略可能)<br>
1. [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) で、 **[デバイス]**  >  **[Windows]**  >  **[Windows の登録]**  >  **[CNAME 検証]** を選択します。
2. **[ドメイン]** ボックスに、企業の Web サイトを入力し、 **[テスト]** を選択します。

## <a name="tell-users-how-to-enroll-windows-devices"></a>Windows デバイスの登録方法をユーザーに通知する
ユーザーに、Windows デバイスを登録する方法とデバイスが管理されるとどうなるかを伝えます。

> [!NOTE]
> 特定のバージョンの Windows で割り当てられた Windows アプリを表示するためには、エンド ユーザーは Microsoft Edge を介してポータル サイト Web サイトにアクセスする必要があります。 Google Chrome、Mozilla Firefox、Internet Explorer などの他のブラウザーでは、この種のフィルタリングはサポートされていません。

エンドユーザー用の登録手順については、「[Intune に Windows デバイスを登録する](../user-help/windows-enrollment-company-portal.md)」を参照してください。 また、ユーザーには、[IT 管理者がユーザーのデバイスに関して確認できる情報](../user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md)に関するページも案内してください。

>[!IMPORTANT]
> MDM 自動登録を有効にしていなくても、Azure AD に参加している Windows 10 デバイスを持っている場合は、登録後に Intune コンソールに 2 つのレコードが表示されます。 これを停止するには、Azure AD に参加しているデバイスを持っているユーザーが、 **[アカウント]**  >  **[職場または学校にアクセスする]** に移動し、同じアカウントを使用して**接続**するようにします。 

エンドユーザー タスクの詳細については、「[Microsoft Intune を使用したエンドユーザー エクスペリエンスに関するリソース](../fundamentals/end-user-educate.md)」を参照してください。

## <a name="registration-and-enrollment-cnames"></a>登録の CNAME
Azure Active Directory には、iOS/iPadOS、Android、および Windows デバイスのデバイス登録用に使用される、異なった CNAME があります。 Intune の条件付きアクセスを使用するためには、デバイスを登録する ("ワークプレースに参加させる" とも呼ばれます) 必要があります。 条件付きアクセスを使用する予定の場合は、使用する会社名ごとに EnterpriseRegistration CNAME を構成する必要もあります。

| Type | ホスト名 | 指定先 | TTL |
| --- | --- | --- | --- |
| 名前 | EnterpriseRegistration。 company_domain.com | EnterpriseRegistration.windows.net | 1 時間|

デバイス登録の詳細については、「[Azure Portal を使用してデバイス ID を管理する](https://docs.microsoft.com/azure/active-directory/devices/device-management-azure-portal)」をご覧ください

## <a name="windows-10-auto-enrollment-and-device-registration"></a>Windows 10 の自動登録とデバイス登録

このセクションは、米国政府機関向けクラウドのお客様に適用されます。

CNAME DNS エントリの作成は省略可能ですが、CNAME レコードにより、ユーザーによる登録が簡単になります。 CNAME レコードの登録が見つからない場合、ユーザーは手動で MDM サーバー名 enrollment.manage.microsoft.us を入力するように求められます。

| Type | ホスト名 | 指定先 | TTL |
| --- | --- | --- | --- |
| CNAME | EnterpriseEnrollment.company_domain.com | EnterpriseEnrollment-s.manage.microsoft.us | 1 時間|
|CNAME | EnterpriseRegistration.company_domain.com | EnterpriseRegistration.windows.net | 1 時間 |


## <a name="next-steps"></a>次のステップ

- [Azure で Intune を使用して Windows デバイスを管理する際の考慮事項](../fundamentals/intune-legacy-pc-client.md)
