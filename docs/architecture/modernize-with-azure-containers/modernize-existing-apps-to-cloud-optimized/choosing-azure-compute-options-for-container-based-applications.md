---
title: 컨테이너 기반 애플리케이션의 Azure 컴퓨팅 플랫폼 선택
description: Azure 클라우드 및 Windows 컨테이너를 사용 하 여 기존 .NET 응용 프로그램 현대화 | 컨테이너 기반 응용 프로그램을 위한 Azure compute 플랫폼 선택
ms.date: 05/04/2018
ms.openlocfilehash: 079c9c5ca02b6dc75214d63cb59afdead03d3190
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73737007"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a>컨테이너 기반 애플리케이션의 Azure 컴퓨팅 플랫폼 선택

이전 섹션을 읽은 후에도 Azure는 여러 선택 항목을 제공 하는 오픈 클라우드입니다. 사용자 요구에 가장 적합 한 기능을 사용할 수 있지만 컨테이너 화 된 응용 프로그램에 사용 해야 하는 제품/기술에 대 한 질문도 표시 합니다.

*기본* 권장 사항으로, 다음은이 지침에서 권장 하는 기본 조건입니다.

- **단일 모놀리식 앱:** Azure App Service 선택
- **N 계층 앱:** AKS (Azure Kubernetes Service)와 같은 orchestrator를 선택 하거나, 하나 이상의 백 엔드 서비스가 있는 경우 App Service를 선택 합니다.
- **마이크로 서비스:** 컨테이너에 대해 AKS 또는 Azure Web Apps 선택
- **서버를 사용 하지 않는 함수 & 이벤트 처리기:** Azure Functions 선택
- **대규모 일괄 처리:** Azure Batch 선택

그러나 제품의 선택은 특정 응용 프로그램의 요구 사항 및 특성에 따라 달라 지므로 이러한 권장 사항은 솔트를 사용 하 여 수행 해야 합니다. 처음에는 유사한 형식을 사용할 경우에도 모든 응용 프로그램이 동일 하지는 않습니다.

응용 프로그램의 요구 사항을 심층적으로 분석 한 후에는 선택한 제품이 다를 수 있습니다. 하지만 시작 지점으로, 특정 우선 순위에 따라 평가 및 테스트를 시작할 수 있는 초기 지침을 제공 하는 것이 좋습니다.

그림 1에서 다양 한 종류의 앱과 이상적인 Azure 호스팅 시나리오에 대 한 분석을 볼 수 있습니다.

![여러 앱에 가장 적합 한 Azure 호스팅 시나리오 표](./media/choosing-azure-compute-options-for-container-based-applications/azure-hosting-scenarios-for-apps.png)

> [!div class="step-by-step"]
> [이전](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [다음](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
