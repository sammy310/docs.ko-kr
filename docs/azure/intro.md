---
title: Azure 및 .NET 시작
description: Azure 및.NET에 대해 알아야 할 기본 사항을 알아봅니다.
ms.date: 06/20/2020
ms.topic: conceptual
ms.custom: devx-track-dotnet
ms.author: daberry
author: daberry
ms.openlocfilehash: b5766012b77da88ae9a696939b6e498ebc421522
ms.sourcegitcommit: 5d9cee27d9ffe8f5670e5f663434511e81b8ac38
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2021
ms.locfileid: "98025044"
---
# <a name="introduction-to-azure-and-net"></a>Azure 및 .NET 소개

## <a name="what-is-azure"></a>Azure란?

Azure는 최신 애플리케이션을 빌드하는 프로세스를 간소화하도록 설계된 클라우드 플랫폼입니다.  애플리케이션을 Azure에서 완전히 호스트하든, Azure 서비스를 통해 온-프레미스 애플리케이션을 확장하든 Azure를 사용하면 스케일링 가능하고 안정적이며 유지 관리 가능한 애플리케이션을 만들 수 있습니다.  Visual Studio, Visual Studio Code와 같이 이미 사용하는 도구와 포괄적인 SDK 라이브러리를 광범위하게 지원하는 Azure는 .NET 개발자가 처음부터 생산성을 발휘하도록 지원하기 위해 설계되었습니다.

## <a name="application-development-scenarios-on-azure"></a>Azure의 애플리케이션 개발 시나리오

요구에 따라 다양한 방법으로 Azure를 애플리케이션에 통합할 수 있습니다.

- **Azure에서 호스트하는 애플리케이션 -** Azure에서 웹 애플리케이션에서 API, 데이터베이스, 스토리지 서비스에 이르는 전체 애플리케이션 스택을 호스트할 수 있습니다. Azure는 완전 관리형 서비스, 컨테이너, 가상 머신 등 다양한 호스팅 모델을 지원합니다. 완전 관리형 Azure 서비스를 사용하는 경우 애플리케이션에서 Azure에 기본 제공되는 스케일링 성능, 고가용성, 보안을 활용할 수 있습니다.

- **애플리케이션에서 클라우드 서비스 사용 -** 기존 앱에서 Azure 서비스를 통합하여 기능을 확장할 수 있습니다.  [Azure Cognitive Search](/azure/search/search-what-is-azure-search)를 사용한 전체 텍스트 검색 기능 추가, [Azure Key Vault](/azure/key-vault/)에 애플리케이션 비밀을 안전하게 저장, [Azure Cognitive Services](/azure/cognitive-services/)를 사용하여 비전, 음성, 언어 이해 기능 추가 등을 예로 들 수 있습니다.  이러한 서비스는 Azure에서 완전히 관리되며 현재 애플리케이션 아키텍처나 배포 모델을 변경하지 않고 애플리케이션에 쉽게 추가할 수 있습니다.

- **최신 서버리스 아키텍처 -** Azure Functions는 HTTP 요청에 응답, Blob 스토리지에서 파일 업로드 처리, 큐의 이벤트 처리 등의 이벤트 기반 워크플로를 처리하는 솔루션의 빌드를 간소화합니다.  서버 또는 프레임워크 코드는 신경 쓰지 않고 이벤트 처리에 필요한 코드만 작성하면 됩니다.  또한 기타 Azure 및 타사 서비스에 대한 250개 넘는 커넥터를 활용하여 가장 까다로운 통합 문제를 해결할 수 있습니다.

## <a name="access-azure-services-from-net-applications"></a>.NET 애플리케이션에서 Azure 서비스 액세스

앱이 Azure나 온-프레미스 어디에 호스트되어 있든 관계없이 **.NET용 Azure SDK** 를 통해 대부분의 Azure 서비스 액세스에 액세스할 수 있습니다.  .NET용 Azure SDK는 일련의 NuGet 패키지로 제공되며 .NET Core(2.1 이상)와 .NET Framework(4.6.1 이상) 애플리케이션 모두에서 사용할 수 있습니다. .NET용 Azure SDK를 사용하면 적합한 NuGet 패키지를 설치하고 클라이언트 개체를 인스턴스화하고 적절한 메서드를 호출하는 것만큼 쉽게 Azure 서비스를 애플리케이션에 통합할 수 있습니다. .NET용 Azure SDK에 대한 자세한 내용은 [.NET용 Azure SDK 개요](./sdk/azure-sdk-for-dotnet.md)에서 찾을 수 있습니다.

![.NET 애플리케이션에서 Azure SDK를 사용하여 Azure 서비스에 액세스하는 방법을 보여 주는 다이어그램](./media/azure-sdk-for-dotnet-overview.png)

## <a name="next-steps"></a>다음 단계

다음으로 .NET 개발을 위해 [일반적으로 사용되는 Azure 서비스](./key-azure-services.md)에 대해 알아봅니다.
