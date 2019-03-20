---
title: 컨테이너 기반 응용 프로그램에 대 한 Azure 계산 플랫폼 선택
description: Azure 클라우드 및 Windows 컨테이너를 사용 하 여 기존.NET 응용 프로그램 현대화 | 컨테이너 기반 응용 프로그램에 대 한 Azure 계산 플랫폼 선택
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/04/2018
ms.openlocfilehash: f251aecfeaf2421a5cecf218577369963bc736fb
ms.sourcegitcommit: 462dc41a13942e467984e48f4018d1f79ae67346
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58186106"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a>컨테이너 기반 응용 프로그램에 대 한 Azure 계산 플랫폼 선택

이전 섹션을 읽은 후 확인 했을 때 Azure는 여러 선택 항목을 제공 하는 개방형 클라우드입니다. 그러나 컨테이너 화 된 응용 프로그램에 사용 해야 하는 제품/기술에 대 한 질문 수도 표시, 요구 사항에 맞게 가장 적합 한를 사용할 수 있습니다.

로 *기본적으로* 권장 사항, 다음은이 설명서에 권장 되는 기본 조건:

- **단일 모놀리식 앱:** Azure App Service를 선택 합니다.
- **N 계층 앱:** 단일 또는 몇 백 엔드 서비스에 있는 경우 Azure Kubernetes Service (AKS), Service Fabric (SF) 또는 App Service와 같은 오 케 스트레이 터를 선택 합니다.
- **Linux 마이크로 서비스:** AKS/Kubernetes를 선택 합니다.
- **Windows 마이크로 서비스:** Service Fabric을 선택
- **서버 리스 functions 및 이벤트 처리기:** Azure 함수 선택
- **대규모 일괄 처리:** Azure Batch를 선택 합니다.

그러나이 권장 사항은 제품의 선택은 특정 응용 프로그램의 요구 사항 및 특징에 따라 달라 집니다으로 약간의 솔트를 사용 하 여 수행 해야 합니다. 일부 응용 프로그램은 처음에 비슷한 형식이 계실 경우에 동일 합니다.

응용 프로그램의 요구를 심층적으로 분석 한 후 선택한 제품 다를 수 있습니다. 그러나 시작 지점으로 개의 평가 시작 하는 데 수의 초기 지침 이며 특정 우선 순위에 따라 테스트 합니다.

다음 그림에서는 자세한 의사 결정 테이블 하는 동안 더 전역을 분석할 수 있습니다.

![](./media/image8.5.png)

알림 방법 (Windows 및 OS 기본 일부 오 케 스트레이 터는 더 Linux 컨테이너에 대 한 완성 및 Windows 컨테이너에 대 한 기타 Linux)는 의사 결정 요소를 수도 있습니다. 예를 들어 Linux 컨테이너는 Service Fabric에서 더 새롭고 완성도 낮음 하지만 Kubernetes (AKS azure에서)에서 매우 완성도 높은입니다. 반면에 Windows 컨테이너는 Service Fabric (2017 년 5 월에에서 릴리스됨)에 더 성숙 하 고 AKS에서 더 새롭고 완성도 낮음.

그러나 OS 완성에서 이러한 차이 나중에 페이드 및 여러 플랫폼에는 비교할 수 있는 OS의 완성도 있고 결정 응용 프로그램에 필요할 수 또는 각 플랫폼의 에코 시스템에 따라 특정 기능을 기반으로 하는 기본 설정에 대 한 자세한 내용은 이었으며 이유입니다.

> [!div class="step-by-step"]
> [이전](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [다음](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
