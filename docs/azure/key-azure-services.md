---
title: .NET 개발자를 위한 주요 Azure 서비스
description: Azure에는 100개 이상의 서비스가 있지만 이 문서에서는 .NET 개발자가 자주 사용하는 8개 정도의 서비스를 주로 다룹니다.
ms.date: 11/30/2020
ms.topic: conceptual
ms.custom: devx-track-dotnet
ms.author: daberry
author: daberry
ms.openlocfilehash: 452f09aa93760b21fdb56583025cc421b8d86e44
ms.sourcegitcommit: 3d6d6595a03915f617349781f455f838a44b0f44
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2020
ms.locfileid: "97700967"
---
# <a name="key-azure-services-for-net-developers"></a>.NET 개발자를 위한 주요 Azure 서비스

Azure에 100가지 이상의 서비스가 있지만 .NET 개발자가 자주 사용하는 Azure 서비스는 다음과 같습니다.

| **서비스** |         | **설명**      |
| :--:|:------|:------------|
| ![App Service 아이콘](./media/app-services.svg) | **Azure App Service** | Azure App Service는 Azure에서 웹 애플리케이션과 API를 호스트하기 위한 완전 관리형 플랫폼입니다.  고가용성 환경에서 자동 부하 분산과 자동 스케일링 기능을 제공합니다.  사용하는 컴퓨팅 리소스에 대해서만 비용을 지불하며 무료 계층을 사용할 수 있습니다. |
| ![Azure Functions 아이콘](./media/azure-functions.svg) | **Azure Functions** | Azure Functions는 서버나 런타임을 관리하지 않고 코드를 작성하고 실행할 수 있는 서버리스 컴퓨팅 서비스입니다.  Functions는 다양한 이벤트로 트리거될 수 있으며 이벤트를 처리하는 데 필요한 코드만 작성하면 됩니다.        |
| ![Azure SQL 아이콘](./media/azure-sql.svg) | **Azure SQL**            | Azure SQL은 SQL Server의 완전 관리형 클라우드 기반 버전입니다. Azure는 패치, 백업 등과 같은 일반 관리 작업을 자동으로 수행하고 고가용성을 기본적으로 제공합니다.  |
| ![Cosmos DB 아이콘](./media/cosmos-db.svg) | **Azure Cosmos DB**      | Azure Cosmos DB는 한 자릿수 응답 시간, 자동 스케일링, MongoDB 호환 API 등을 제공하는 완전 관리형 NoSQL 데이터베이스입니다.                    |
| ![Azure Storage Blob 아이콘](./media/storage-blobs.svg) | **Azure Blob Storage**   | Azure Blob Storage를 사용하면 애플리케이션에서 파일을 클라우드에 저장하고 검색할 수 있습니다.  Azure Storage는 스케일링 성능이 뛰어나 방대한 양의 데이터를 저장할 수 있고 데이터를 중복 저장하여 고가용성을 보장합니다. |
| ![Azure Service Bus 아이콘](./media/service-bus.svg) | **Azure Service Bus**   | Azure Service Bus는 지점 간 통합과 게시-구독 통합을 모두 지원하는 완전 관리형 엔터프라이즈 메시지 브로커입니다.  분리된 애플리케이션 빌드, 큐 기반 부하 평준화, 마이크로 서비스 간 원활한 통신 등에 적합합니다.   |
| ![Azure Key Vault 아이콘](./media/azure-key-vault.svg) | **Azure Key Vault**   | 모든 애플리케이션에는 연결 문자열, API 키 등의 애플리케이션 비밀을 저장해야 합니다.  Azure Key Vault를 사용하면 액세스가 제한된 암호화된 자격 증명 모음에 해당 비밀을 안전하게 저장하고 액세스하여 비밀과 애플리케이션 손상을 방지할 수 있습니다.   |
| ![Cognitive Services 아이콘](./media/cognitive-services.svg) | **Cognitive Services**   | Azure Cognitive Services는 애플리케이션에 AI 기반 기능을 추가할 수 있는 클라우드 기반 서비스 모음입니다.  컴퓨터 비전, 음성 인식, 언어 이해, 변칙 검색 등을 예로 들 수 있습니다. |

Azure 제품 및 서비스의 전체 목록은 [Azure 설명서 홈페이지](/azure/?product=all)를 참조하세요.

### <a name="next-steps"></a>다음 단계

[Azure 계정을 만들어](create-azure-account.md) Azure 개발 환경 구성 시작
