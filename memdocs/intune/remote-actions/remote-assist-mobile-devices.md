---
title: Intune によって管理されるモバイル デバイスをリモートで支援する
description: モバイル デバイスを使用するユーザーをリモートで支援するには、4 つの異なるオプションを使用できます。
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/20/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 548f63dcbd1635c106573fda40f8cc7bf312866e
ms.sourcegitcommit: 7f17d6eb9dd41b031a6af4148863d2ffc4f49551
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "80086651"
---
# <a name="remotely-assist-mobile-devices-managed-by-microsoft-endpoint-manager"></a>Microsoft Endpoint Manager によって管理されるモバイル デバイスをリモートで支援する

Microsoft Endpoint Manager によって管理されるデバイスをリモートで管理する場合、使用できるオプションは 4 つあります。

- [Microsoft Teams](https://products.office.com/microsoft-teams/) は、どこにいてもチャット、会議、共同作業を行うことができるチーム作業のハブです。
- [クイック アシスト](https://support.microsoft.com/help/4027243/windows-10-solve-pc-problems-with-quick-assist)は、2 人でリモート接続を介してデバイスを共有できる Windows 10 アプリケーションです。
- [TeamViewer](https://www.teamviewer.com/) は、個別に購入するサード パーティ プログラムです。 包括的な一連のリモート アクセス機能とサポート機能を備えています。 Intune と [TeamViewer の統合](teamviewer-support.md)により、TeamViewer を使用したリモート サポートが可能になり、コネクタは Intune で直接管理されるようになりました。
- [リモート制御](https://docs.microsoft.com/configmgr/core/clients/manage/remote-control/introduction-to-remote-control)は、Microsoft Endpoint Configuration Manager に含まれています。 ワークグループ コンピューターとドメインに参加しているコンピューターのリモートでの管理、支援、または表示に使用されます。

| 機能、プラットフォーム、ライセンス | **Teams** | クイック アシスト | TeamViewer (Intune) | リモート制御 (ConfigMgr) |
|:---:|:---:|:---:|:---:|:---:|
| リモートの表示と制御 |![チェックマーク](../enrollment/media/enrollment-method-capab/checkmark.png)|![チェックマーク](../enrollment/media/enrollment-method-capab/checkmark.png)|![チェックマーク](../enrollment/media/enrollment-method-capab/checkmark.png)|![チェックマーク](../enrollment/media/enrollment-method-capab/checkmark.png)|
| チャット |![チェックマーク](../enrollment/media/enrollment-method-capab/checkmark.png)||![チェックマーク](../enrollment/media/enrollment-method-capab/checkmark.png)||
| ファイルの転送 |![チェックマーク](../enrollment/media/enrollment-method-capab/checkmark.png)|![チェックマーク](../enrollment/media/enrollment-method-capab/checkmark.png)|![チェックマーク](../enrollment/media/enrollment-method-capab/checkmark.png)|![チェックマーク](../enrollment/media/enrollment-method-capab/checkmark.png)|
| 管理者特権でのアクセス |||![チェックマーク](../enrollment/media/enrollment-method-capab/checkmark.png)|![チェックマーク](../enrollment/media/enrollment-method-capab/checkmark.png)|
| 自動アクセス |||![チェックマーク](../enrollment/media/enrollment-method-capab/checkmark.png)|![チェックマーク](../enrollment/media/enrollment-method-capab/checkmark.png)|
| 同時リモート制御 |![チェックマーク](../enrollment/media/enrollment-method-capab/checkmark.png)|![チェックマーク](../enrollment/media/enrollment-method-capab/checkmark.png)|||
| マルチ ユーザー サポート |||![チェックマーク](../enrollment/media/enrollment-method-capab/checkmark.png)|![チェックマーク](../enrollment/media/enrollment-method-capab/checkmark.png)|
| リモート操作 ||![チェックマーク](../enrollment/media/enrollment-method-capab/checkmark.png)|![チェックマーク](../enrollment/media/enrollment-method-capab/checkmark.png)|![チェックマーク](../enrollment/media/enrollment-method-capab/checkmark.png)|
| インターネット経由のサポート |![チェックマーク](../enrollment/media/enrollment-method-capab/checkmark.png)|![チェックマーク](../enrollment/media/enrollment-method-capab/checkmark.png)|![チェックマーク](../enrollment/media/enrollment-method-capab/checkmark.png)||
| 監査レポート |![チェックマーク](../enrollment/media/enrollment-method-capab/checkmark.png)||![チェックマーク](../enrollment/media/enrollment-method-capab/checkmark.png)|![チェックマーク](../enrollment/media/enrollment-method-capab/checkmark.png)|
| すべてのプラットフォーム (Windows、iOS、Android、macOS) のサポート |![チェックマーク](../enrollment/media/enrollment-method-capab/checkmark.png)||![チェックマーク](../enrollment/media/enrollment-method-capab/checkmark.png)||
| Windows 10 との統合 - 追加のアプリは不要 ||![チェックマーク](../enrollment/media/enrollment-method-capab/checkmark.png)|||
| デバイスを Configuration Manager と Intune で共同管理する必要があります ||||![チェックマーク](../enrollment/media/enrollment-method-capab/checkmark.png)|
| 追加のライセンスが必要です\* |![チェックマーク](../enrollment/media/enrollment-method-capab/checkmark.png)||![チェックマーク](../enrollment/media/enrollment-method-capab/checkmark.png)|![チェックマーク](../enrollment/media/enrollment-method-capab/checkmark.png)|

\* Teams には O365 または M365 のライセンスが必要です。 TeamViewer と Intune を使用するには、TeamViewer と Intune の両方のライセンスが必要です。 リモート制御は Configuration Manager の機能であり、Configuration Manager ライセンスが必要です。
