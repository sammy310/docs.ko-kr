---
title: 복원력 있는 애플리케이션 구현
description: 마이크로 서비스 아키텍처의 핵심 개념인 복원력에 대해 알아봅니다. 일시적 오류가 발생하면 해당 오류를 적절하게 처리하는 방법을 알아야 합니다.
ms.date: 01/30/2020
ms.openlocfilehash: 3ed4474eaa1225e80f05db86965e4ba53b5d2301
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100429327"
---
# <a name="implement-resilient-applications"></a>복원력 있는 애플리케이션 구현

*마이크로 서비스와 클라우드 기반 애플리케이션에서는 결국 발생하게 되는 부분 오류를 수용해야 합니다. 부분 오류에 탄력적으로 대처할 수 있도록 애플리케이션을 디자인해야 합니다.*

복원력은 오류를 복구하고 계속 작업을 진행하는 기능입니다. 이는 오류를 방지하는 기능이 아닌 오류가 발생할 수 있다는 사실을 받아들이고 가동 중지 시간 또는 데이터 손실을 방지할 수 있도록 해당 오류에 응답하는 기능입니다. 복원력의 목표는 오류 발생 후 애플리케이션을 완전히 작동 중인 상태로 되돌리는 것입니다.

마이크로 서비스 기반 애플리케이션을 디자인하고 배포하기는 쉽지 않습니다. 그러나 일부 오류가 명확히 발생하는 환경에서 애플리케이션을 계속 실행하는 작업도 필요합니다. 따라서 애플리케이션에 복원력이 있어야 합니다. 응용 프로그램은 클라우드에서의 네트워크 중단 또는 노드 또는 VM 충돌과 같은 부분 오류에 대처할 수 있도록 디자인되어야 합니다. 클러스터 내에서 다른 노드로 이동한 마이크로 서비스(컨테이너)도 애플리케이션에서 일시적 단기 오류를 유발할 수 있습니다.

애플리케이션의 여러 개별 구성 요소도 상태 모니터링 기능과 통합해야 합니다. 이 장의 지침을 따라 가동 중지 시간 또는 복잡한 클라우드 기반 배포의 일반적인 문제가 발생하는 환경에서도 원활하게 작동하는 애플리케이션을 만들 수 있습니다.

>[!IMPORTANT]
> eShopOnContainer는 릴리스 3.0.0까지 [Polly 라이브러리](https://thepollyproject.azurewebsites.net/)를 사용하여 [형식화된 클라이언트](./use-httpclientfactory-to-implement-resilient-http-requests.md)로 복원력을 구현해 왔습니다.
>
> 릴리스 3.0.0부터는 Kubernetes 클러스터 내에서 투명하고 구성 가능한 방식으로 재시도를 처리하기 때문에 코드에서 문제를 처리할 필요가 없는 [Linkerd 메시](https://linkerd.io/)를 사용하여 HTTP 호출 복원력이 구현됩니다.
>
> Polly 라이브러리는 특히 서비스를 시작하는 동안 데이터베이스 연결에 복원력을 더하는 데 여전히 사용됩니다.

>[!WARNING]
> 이 섹션의 모든 코드 샘플은 Linkerd를 사용하기 전에 유효했으며 현재 실제 코드를 반영하도록 업데이트되지 않습니다. 따라서 이 섹션의 맥락에서만 의미가 있습니다.

>[!div class="step-by-step"]
>[이전](../microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md)
>[다음](handle-partial-failure.md)
