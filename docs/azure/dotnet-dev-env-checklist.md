---
title: Azure의 .NET 개발 구성 검사 목록
description: Azure를 사용하여 .NET 개발을 수행하기 위해 설치해야 하는 모든 도구의 간략한 요약을 제공합니다.
ms.date: 1/1/2021
ms.topic: conceptual
ms.custom: devx-track-dotnet
ms.author: daberry
author: daberry
ms.openlocfilehash: 2f22f69ec99baf192d1cbdd28f884b7f47867389
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257982"
---
# <a name="net-on-azure-development-environment-checklist"></a>Azure의 .NET 개발 환경 검사 목록

이 검사 목록은 Azure에서의 .NET 개발을 위해 개발 환경이 올바르게 구성되었는지 확인하는 데 도움이 됩니다.

## <a name="create-an-azure-account"></a>Azure 계정 만들기

Azure 서비스에 액세스하거나 Azure에서 애플리케이션을 실행하려면 Azure 계정이 필요합니다.

* Visual Studio 구독자인 경우 매월 제공되는 [무료 Azure 크레딧](https://azure.microsoft.com/pricing/member-offers/credit-for-visual-studio-subscribers/)이 있습니다.
* [Azure 체험 계정을 만들고](https://azure.microsoft.com/free/dotnet/) $200 크레딧을 받고 12개월 동안의 별도의 비용이 없는 서비스를 선택합니다.
* 회사의 Azure 관리자가 할당해준 계정을 사용합니다.

## <a name="configure-your-ide"></a>IDE 구성

Visual Studio 및 Visual Studio Code와 같은 널리 사용되는 도구에는 IDE에서 바로 Azure로 작업하도록 해주는 확장이 포함되어 있습니다.

* Azure를 사용한 .NET 개발을 위한 [Visual Studio 구성](./configure-visual-studio.md)
* Azure를 사용한 .NET 개발을 위한 [Visual Studio Code 구성](./configure-vs-code.md)

## <a name="install-the-azure-cli"></a>Azure CLI 설치

Azure Portal을 사용하는 것 외에도 Azure CLI를 설치하여 Azure 리소스를 만들고 관리할 수 있습니다.

* [Windows용 Azure CLI 설치](/cli/azure/install-azure-cli-windows?tabs=azure-cli)
* [macOS용 Azure CLI 설치](/cli/azure/install-azure-cli-macos)
* [Linux용 Azure CLI 설치](/cli/azure/install-azure-cli-linux)

## <a name="install-additional-tools-and-utilities"></a>추가 도구 및 유틸리티 설치

이러한 추가 도구는 Azure로 작업할 때 생산성을 높일 수 있도록 설계되었습니다.

* PowerShell 스크립트를 사용하여 Azure 리소스를 만들고 관리하려는 경우 [Azure PowerShell 설치](/powershell/azure/install-az-ps)
* BLOB, 큐, 테이블, CosmosDB를 비롯한 Azure 스토리지 리소스의 데이터를 업로드, 다운로드, 관리하려면 [Azure Storage Explorer 설치](https://azure.microsoft.com/features/storage-explorer/)
* Azure SQL로 작업하는 경우 [Azure Data Studio 설치](/sql/azure-data-studio/download-azure-data-studio)

## <a name="bookmark-the-following-sites"></a>다음 사이트를 책갈피에 추가

Azure 개발 중에는 이러한 사이트를 자주 사용하게 됩니다.  빠른 참조를 위해 책갈피에 추가하세요.

* Azure Portal - [https://portal.azure.com/](https://portal.azure.com/)
* Azure Cloud Shell - [https://shell.azure.com/](https://shell.azure.com/)
