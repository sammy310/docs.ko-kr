---
title: 요약 및 진행 방향
description: 핵심 핵심 결론을 요약 하 고 앞으로 이동 하는 방법을 살펴봅니다.
ms.date: 02/17/2021
author: robvet
ms.openlocfilehash: fdbb92d067c29db56aa7449b8fe3c974c8c132b8
ms.sourcegitcommit: d623f686701b94bef905ec5e93d8b55d031c5d6f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2021
ms.locfileid: "103624073"
---
# <a name="summary-and-the-road-ahead"></a>요약 및 진행 방향

Microsoft는이에 대 한 microsoft의 고객을 위한 것입니다. [2 장](dapr-at-20000-feet.md) 에서 2만 피트로의 제트 비행기 비행은 최종 접근 방식으로 진행 됩니다.

비행기가 게이트에서 택시 면이 가이드의 몇 가지 중요 한 결론을 검토해 보겠습니다.

- D **4** -d 4는 분산 응용 프로그램을 빌드하는 방법을 간소화 하는 *배포 응용 프로그램 런타임* 입니다. 구성 요소 및 플러그형 구성 요소의 아키텍처를 노출 합니다. 6apr는 응용 프로그램을 Eapr 런타임에 존재 하는 인프라 기능에 바인딩하는 **동적 붙이기를** 제공 합니다. 인프라를 구축 하는 대신 사용자와 팀이 비즈니스 기능을 고객에 게 제공 하는 데 주력 합니다.

- **오픈 소스 및 플랫폼 간** -기본 EAPR API는 HTTP 또는 grpc를 지 원하는 *모든 플랫폼* 에서 사용 될 수 있습니다. 또한 d 4는 인기 있는 개발 플랫폼용 언어 관련 Sdk를 제공 합니다. Eapr v 1.0은 Go, Python, .NET, Java, PHP 및 JavaScript를 지원 합니다.

- **빌딩 블록** -4 월 빌딩 블록은 배포 응용 프로그램 기능을 캡슐화 합니다. 이 문서를 작성할 당시에는 그림 11-1에 표시 된 7 개의 빌딩 블록을 지원 합니다.

![4apr 빌딩 블록](./media/dapr-at-20000-feet/building-blocks.png)

**그림 11-1**. 4apr 빌딩 블록입니다.

- **구성 요소** -4apr 구성 요소는 각 6apr 빌딩 블록 기능에 대 한 구체적인 구현을 제공 합니다. 개발자가 응용 프로그램 코드를 변경 하지 않고 구성 요소 구현을 교환할 수 있도록 하는 공용 인터페이스를 노출 합니다. 그림 11-2에서는 구성 요소, 구성 요소 및 서비스 간의 관계를 보여 줍니다.

![4apr 빌딩 블록 통합](./media/dapr-at-20000-feet/building-blocks-integration.png)

**그림 11-2**. 4apr 빌딩 블록 통합.

- **사이드카** -사이드카 아키텍처의 응용 프로그램과 함께 별도의 컨테이너 프로세스로 실행 됩니다. 응용 프로그램은 HTTP 및 gRPC를 통해 Eapr Api와 통신 합니다. 사이드카는 서비스에 포함 되지 않고 연결 된 격리 및 캡슐화를 제공 합니다. 그림 11-3은 사이드카 아키텍처를 보여 줍니다.

![사이드카 아키텍처](./media/dapr-at-20000-feet/sidecar-generic.png)

**그림 11-3**. 사이드카 아키텍처.

- **호스팅 환경** 6apr는 플랫폼 간 지원을 제공 하며 여러 환경에서 실행할 수 있습니다. 이 문서를 작성할 당시에는 자체 호스트 된 로컬 모드와 Kubernetes 환경을 포함 합니다.

- **eShopOnDapr** -이 책에는 [eShopOnDapr](https://github.com/dotnet-architecture/eShopOnDapr)이라는 참조 응용 프로그램이 포함 되어 있습니다. 참조 응용 프로그램은 인기 있는 전자 상거래 응용 프로그램 도메인을 사용 하 여 각 구성 요소를 사용 하는 방법을 보여 줍니다. 몇 년 전에 릴리스되는 널리 사용 되는 [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers)의 진화입니다.

## <a name="the-road-ahead"></a>앞으로 이동

향후에는 배포 응용 프로그램 개발에 매우 큰 영향을 줄 수 있습니다. Eapr 팀과 오픈 소스 기여자에서 무엇을 받을 수 있나요?

작성 당시에는 다음과 같은 추가 기능을 제공 합니다.

- 기존 구성 요소에 대 한 향상 된 기능:
  - 상태 관리의 쿼리 기능을 사용 하 여 여러 값을 검색할 수 있습니다.
  - Pub/sub에서 필터링 항목을 사용 하 여 콘텐츠를 기준으로 항목을 필터링 할 수 있습니다.
  - 관찰성의 응용 프로그램 추적 API는 특정 라이브러리에 바인딩하지 않고도 응용 프로그램에서 직접 추적 기능을 제공 합니다.
  - 행위자 프로그래밍 모델에 이벤트 구동 기능을 제공 하는 행위자에 대 한 바인딩 및 pub/sub 지원. 바인딩된 구성 요소는 이벤트 및 메시지를 트리거하고 행위자의 메서드를 호출 합니다.

- 새 구성 요소:
  - 구성 데이터를 읽고 쓰기 위한 구성 API 빌딩 블록입니다. 이 블록은 Azure Configuration Manager 또는 GCP 구성 관리를 포함 하는 공급자에 바인딩됩니다.
  - 0에서 시작 하는 Http 크기 자동 크기 조정.
  - 단일 인스턴스 및 잠금 의미 체계 기능을 제공 하는 리더 선거 빌딩 블록입니다.
  - 서비스 호출에 대 한 투명 프록시 구성 요소를 사용 하 여 네트워크 수준에서 Url 또는 DNS 주소를 기반으로 메시지를 라우팅할 수 있습니다.
  - 복원 력 빌딩 블록 (회로 차단기, 대량 헤드 & 시간 제한).

- 프레임 워크 및 클라우드 기본 기술과 통합. 일부 사례:
  - Django
  - Nodejs
  - 고속
  - Kyma
  - 미드웨이

- 새 언어 Sdk:
  - JavaScript
  - RUST
  - C++

- 새 호스팅 플랫폼:
  - VM
  - Azure IoT Edge
  - Azure Stack Edge
  - Azure Service Fabric

- 개발자 및 운영자 생산성 도구:
  - VS Code 확장입니다.
  - DevOps 파이프라인 개발을 위한 로컬 디버깅을 위한 원격 개발 컨테이너
  - Eapr 응용 프로그램 관리의 운영 문제를 심층적으로 파악할 수 있게 해 주는 4 차 운영 대시보드 향상 기능입니다.

D 4 월 버전 1.0은 개발자에 게 배포 응용 프로그램을 빌드하기 위한 훌륭한 도구 상자를 제공 합니다. 제안 된 향상 된 기능 목록에서 볼 수 있듯이, 많은 새로운 기능을 사용 하 여 Capr가 활성 개발 중입니다. 이후 업데이트를 위해 [eapr 사이트](https://dapr.io/) 및 [eapr 알림 블로그](https://cloudblogs.microsoft.com/opensource/2019/10/16/announcing-dapr-open-source-project-build-microservice-applications/) 를 계속 조정 합니다.

>[!div class="step-by-step"]
>[이전](secrets.md)
