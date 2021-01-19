---
title: .NET용 Azure SDK 개요
description: .NET용 Azure SDK가 무엇인지와 .NET 애플리케이션에서 SDK를 사용하는 기본 단계를 간략하게 살펴봅니다.
ms.date: 11/30/2020
ms.custom: devx-track-dotnet
ms.author: daberry
author: daberry
ms.openlocfilehash: b547e105b13d380ffae049ab55e76aa25abe8cc3
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2021
ms.locfileid: "98189202"
---
# <a name="azure-sdk-for-net-overview"></a>.NET용 Azure SDK 개요

## <a name="what-is-the-azure-sdk-for-net"></a>.NET용 Azure SDK란?

**.NET용 Azure SDK** 는 .NET 애플리케이션에서 Azure 서비스를 쉽게 사용할 수 있도록 설계되었습니다.  Blob Storage에 파일을 업로드하고 다운로드하거나, Azure Key Vault에서 애플리케이션 비밀을 검색하거나, Azure Event Hubs의 알림을 처리하는 등 .NET용 Azure SDK를 사용하면 일관되고 익숙한 인터페이스를 통해 Azure 서비스에 액세스할 수 있습니다.  

.NET용 Azure SDK는 .NET Core(2.1 이상)와 .NET Framework(4.6.1 이상) 애플리케이션 모두에서 사용할 수 있는 일련의 NuGet 패키지로 제공됩니다.

![.NET 애플리케이션에서 Azure SDK를 사용하여 Azure 서비스에 액세스하는 방법을 보여 주는 다이어그램](./media/azure-sdk-for-dotnet-overview.png)

## <a name="use-the-azure-sdk-for-net-in-your-applications"></a>애플리케이션에서 .NET용 Azure SDK 사용

.NET 애플리케이션 중 하나에서 Azure SDK 패키지를 사용하려면 다음 단계를 수행합니다.

1. **적절한 SDK 패키지 찾기 -** [패키지 목록](../packages.md)을 사용하여 사용 중인 Azure 서비스에 적합한 패키지를 찾습니다.  대부분의 서비스에는 서비스를 사용하기 위한 클라이언트 패키지와 서비스 인스턴스를 만들고 관리하기 위한 관리 패키지가 있습니다.  대부분의 경우 클라이언트 패키지가 필요합니다.  NuGet을 사용하여 애플리케이션에 해당 패키지를 설치합니다.

2. **애플리케이션의 인증 설정 -** Azure 리소스에 액세스하려면 Azure에서 애플리케이션에 적절한 자격 증명과 액세스 권한을 할당해야 합니다.  [Azure에 .NET 애플리케이션 인증](../authentication.md)에서 인증을 구성하는 방법을 알아보세요.

3. **애플리케이션에서 SDK를 사용하여 코드 작성 -** Azure 서비스를 사용할 때 코드에서는 먼저 서비스에 사용할 클라이언트 개체를 만든 다음 해당 클라이언트 개체에 대해 메서드를 호출하여 서비스와 상호 작용합니다.  동기 메서드와 비동기 메서드가 모두 제공됩니다.  개별 SDK 패키지를 사용하는 예는 Azure 설명서 전반에 제공되어 있습니다.

4. **SDK에 대한 로깅 구성(선택 사항) -** 애플리케이션과 Azure 간의 문제를 진단해야 하는 경우 [.NET용 Azure SDK에서 로깅을 사용하도록 설정](../logging.md)할 수 있습니다.
