---
title: EShopOnDapr 참조 응용 프로그램 소개
description: EShopOnDapr reference 응용 프로그램 및 해당 기록의 개요입니다.
author: amolenk
ms.date: 02/07/2021
ms.openlocfilehash: d05d47399b9be539597778a4f7856e06d3b16a6c
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401862"
---
# <a name="dapr-reference-application"></a>Eapr 참조 응용 프로그램

이 책의 이전 단계에서는 Aapr의 기본 혜택에 대해 알아보았습니다. 아키텍처 및 운영 복잡성을 줄이면서 팀이 분산 응용 프로그램을 구성 하는 데는 어떻게 도움이 될 수 있는지 확인 했습니다. 이 과정에서 몇 가지 작은 앱을 빌드할 수 있습니다. 이제는 마이크로 서비스 구성 요소 및 구성 요소를 보여 주는 종단 간 응용 프로그램을 살펴볼 차례입니다.

그러나 먼저 약간의 기록이 필요 합니다.

## <a name="eshop-on-containers"></a>컨테이너의 eShop

몇 년 전에 Microsoft는 업계 최고의 커뮤니티 전문가와 협력 하 여 널리 사용 되는 [컨테이너 화 된 .Net 응용 프로그램에 대 한 .Net 마이크로 서비스](https://dotnet.microsoft.com/download/e-book/microservices-architecture/pdf)를 제공 합니다. 그림 3-1에서는 책을 보여 줍니다.

![컨테이너 화 된 마이크로 서비스 .NET 응용 프로그램 설계.](./media/reference-application/architecting-microservices-book.png)

**그림 3-1**. .NET 마이크로 서비스: 컨테이너 화 된 .NET 응용 프로그램에 대 한 아키텍처입니다.

이 책에서는 배포 응용 프로그램을 빌드하기 위한 원칙, 패턴 및 모범 사례에 대해 자세히 dove. 여기에는 아키텍처 개념을 전시 하는 완전 한 기능을 갖춘 마이크로 서비스 참조 응용 프로그램이 포함 되어 있습니다. 응용 프로그램은 [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers), 커피숍 및 커피 머그잔를 비롯 한 다양 한 .net 항목을 판매 하는 전자 상거래 storefront를 보여 줍니다.  .NET Core를 기반으로 하는 응용 프로그램은 플랫폼 간 이며 Linux 또는 Windows 컨테이너에서 실행할 수 있습니다. 그림 3-2에서는 원래 eShop 아키텍처를 보여 줍니다.

![eShopOnContainers reference 응용 프로그램 아키텍처.](./media/reference-application/eshop-on-containers.png)

**그림 3-2**. 원래 `ShopOnContainers` 참조 응용 프로그램입니다.

여기에서 볼 수 있듯이 eShopOnContainers에는 많은 이동 파트가 포함 됩니다.

1. 3 개의 다른 프런트 엔드 클라이언트
1. 프런트 엔드에서 백 엔드를 추상화 하는 응용 프로그램 게이트웨이입니다.
1. 여러 백 엔드 코어 마이크로 서비스.
1. 비동기 pub/sub 메시징을 사용 하도록 설정 하는 이벤트 버스 구성 요소입니다.

EShopOnContainers reference 응용 프로그램은 .NET 커뮤니티 전체에서 널리 승인 되었으며 많은 큰 상업적 마이크로 서비스 응용 프로그램을 모델링 하는 데 사용 됩니다.

## <a name="eshop-on-dapr"></a>Eapr의 eShop

이 책에는 다른 버전의 eShop 응용 프로그램이 함께 제공 됩니다. 이를 [eShopOnDapr](https://github.com/dotnet-architecture/eShopOnDapr)라고 합니다. 업데이트 된 버전은 eShopOnContainers 구성 요소 및 구성 요소를 통합 하 여 이전 버전의 응용 프로그램을 발전 합니다. 그림 3-3은 간소화 된 새 솔루션 아키텍처를 보여 줍니다.  

![eShopOnDapr reference 응용 프로그램 아키텍처.](./media/reference-application/eshop-on-dapr.png)

**그림 3-3**. eShopOnDapr reference 응용 프로그램 아키텍처.

EShopOnDapr reference 응용 프로그램에 중점을 두고 있으므로 원래 응용 프로그램이 업데이트 되었습니다. 아키텍처는 다음으로 구성 됩니다.

1. 인기 각도의 SPA 프레임 워크로 작성 된 [단일 페이지 응용 프로그램](/archive/msdn-magazine/2013/november/asp-net-single-page-applications-build-modern-responsive-web-apps-with-asp-net) 프런트 엔드입니다. API 게이트웨이 마이크로 서비스 사용자 요청을 보냅니다.

1. API 게이트웨이는 프런트 엔드 클라이언트에서 백 엔드 핵심 마이크로 서비스를 추상화 합니다. 고성능 오픈 소스 서비스 프록시로 [엔보이](https://www.envoyproxy.io/)를 사용 하 여 구현 됩니다. 엔보이는 들어오는 요청을 다양 한 백 엔드 마이크로 서비스로 라우팅합니다. 대부분의 요청은 간단한 CRUD 작업으로, 예를 들어 카탈로그에서 브랜드 목록을 가져오고 백 엔드 마이크로 서비스에 대 한 직접 호출을 통해 처리 됩니다.

1. 다른 요청은 논리적으로 좀 더 복잡 하며 여러 마이크로 서비스가 함께 작동 해야 합니다. 이러한 경우 eShopOnDapr는 작업을 완료 하는 데 필요한 마이크로 서비스에 걸쳐 워크플로를 오케스트레이션 하는 [집계 마이크로 서비스](../cloud-native/service-to-service-communication.md#service-aggregator-pattern) 를 구현 합니다.

1. 핵심 백 엔드 마이크로 서비스 집합에는 전자 상거래 저장소에 필요한 기능이 포함 되어 있습니다. 각는 자체 포함 되며 다른 항목에 독립적입니다. 널리 허용 된 도메인 분해 패턴에 따라 각 마이크로 서비스는 특정 *비즈니스 기능* 을 격리 합니다.

   - 바구니 서비스는 고객의 시장 바구니 환경을 관리 합니다.
   - 카탈로그 서비스는 판매에 사용할 수 있는 제품 항목을 관리 합니다.
   - Id 서비스는 인증 및 id를 관리 합니다.
   - 주문 서비스는 주문 배치 및 관리의 모든 측면을 처리 합니다.
   - 지불 서비스는 고객의 지불을 엔터티입니다 합니다.

   각 서비스에는 자체 영구 저장소가 있습니다. 마이크로 서비스 [모범 사례](../cloud-native/distributed-data.md#database-per-microservice-why)를 준수 하는 경우 모든 서비스가 상호 작용 하는 공유 데이터 저장소는 없습니다.

   각 마이크로 서비스의 디자인은 개별 요구 사항에 따라 달라 집니다. 단순 서비스는 기본 CRUD 작업을 사용 하 여 기본 데이터 저장소에 액세스 합니다. 순서와 같은 고급 서비스는 Domain-Driven 디자인 방법을 사용 하 여 비즈니스 복잡성을 관리 합니다. 필요한 경우 .NET Core, Java, Go, NodeJS 등과 같은 다양 한 기술 스택에서 서비스를 빌드할 수 있습니다.

1. 마지막으로, 이벤트 버스는 Eapr 게시/구독 구성 요소를 래핑합니다. 마이크로 서비스에서 비동기 게시/구독 메시징을 사용할 수 있습니다. 개발자는 모든 4 월 지원 메시지 broker를 연결할 수 있습니다.

### <a name="application-of-dapr-building-blocks"></a>4Apr 빌딩 블록의 응용 프로그램

EShopOnDapr codebase는 eShopOnContainers codebase 보다 더 효율적입니다. 매우 많은 양의 오류가 발생 하기 쉬운 코드를 대체 합니다.

그림 3-4은 eShop 참조 응용 프로그램의 Capr 통합을 보여 줍니다.

![eShopOnDapr reference 응용 프로그램 아키텍처](./media/reference-application/eshop-on-dapr-buildingblocks.png)

**그림 3-4**. EShopOnDapr에서의 4apr 통합.

위의 그림에서 어떤 서비스에 어떤 서비스를 사용 하는지 확인할 수 있습니다.

1. 원래 eShopOnContainers 응용 프로그램은 순서 지정 서비스의 DDD 개념과 패턴을 보여 줍니다. 업데이트 된 eShopOnDapr의 주문 서비스는 대체 구현으로 *행위자 빌딩 블록* 을 사용 합니다. 행위자의 턴 기반 액세스 모델을 사용 하면 취소를 지 원하는 상태 저장 주문 프로세스를 쉽게 구현할 수 있습니다.
1. 주문 서비스는 [바인딩 구성](bindings.md)요소를 사용 하 여 주문 확인 전자 메일을 보냅니다.
1. 백 엔드 서비스는 [게시 & 구독 구성 블록](publish-subscribe.md)을 사용 하 여 비동기적으로 통신 합니다.
1. 비밀 관리는 비밀 [구성](secrets.md)요소에 의해 수행 됩니다.
1. API 게이트웨이 및 웹 쇼핑 집계 서비스는 백 엔드 서비스에서 메서드를 호출 하는 [서비스 호출 빌딩 블록](service-invocation.md) 을 사용 합니다.
1. 바구니 서비스는 [상태 관리 빌딩 블록](state-management.md) 을 사용 하 여 고객의 시장 바구니 상태를 저장 합니다.

### <a name="benefits-of-applying-dapr-to-eshop"></a>D 4를 eShop에 적용할 경우의 이점

일반적으로 다음과 같은 경우에는 Eapr 빌딩 블록을 사용 하 여 관찰성 및 유연성을 응용 프로그램에 추가 합니다.

1. 관찰성: Eapr 빌딩 블록을 사용 하 여 코드를 작성 하지 않고도 서비스 간 및 구성 요소 간 호출에 대 한 풍부한 분산 추적을 얻을 수 있습니다. EShopOnContainers에서는 많은 양의 사용자 지정 로깅을 사용 하 여 통찰력을 제공 합니다.
1. 유연성: 이제 구성 요소 구성 파일을 변경 하 여 인프라를 간단히 *교환할* 수 있습니다. 코드를 변경할 필요가 없습니다.

특정 구성 요소에서 제공 하는 이점에 대 한 몇 가지 추가 예는 다음과 같습니다.

- **서비스 호출**
  - D 4의 [mTLS](https://blog.cloudflare.com/introducing-tls-client-auth/)지원 기능을 통해 서비스는 이제 암호화 된 채널을 통해 통신 합니다.
  - 일시적인 오류가 발생 하면 서비스 호출이 자동으로 다시 시도 됩니다.
  - 자동 서비스 검색은 서비스에서 서로를 찾는 데 필요한 구성의 양을 줄여 줍니다.

- **게시/구독**
  - eShopOnContainer에는 Azure Service Bus 및 RabbitMQ를 모두 지 원하는 많은 양의 사용자 지정 코드가 포함 되어 있습니다. 개발자는 로컬 개발 및 테스트를 위해 프로덕션 및 RabbitMQ에 Azure Service Bus을 사용 했습니다. `IEventBus`이러한 메시지 브로커 간에 스와핑을 사용할 수 있도록 추상화 계층이 생성 되었습니다. 이 계층은 *오류가 발생 하기 쉬운 코드의 약 700 줄* 로 이루어져 있습니다. 업데이트 된 구현이 필요한 경우에는 *35 줄의 코드만* 필요 합니다. 이것은 원래 코드 줄의 **5%** 입니다. 무엇 보다도 구현은 간단 하 고 이해 하기 쉽습니다.
  - eShopOnDapr는 Eapr의 다양 한 ASP.NET Core 통합을 사용 하 여 pub/sub를 사용 합니다. `Topic`ASP.NET Core 컨트롤러 메서드에 특성을 추가 하 여 메시지를 구독할 수 있습니다. 따라서 각 메시지 브로커에 대해 별도의 메시지 처리기 루프를 작성할 필요가 없습니다.
  - HTTP 호출로 서비스에 라우팅되는 메시지는 새 개념 또는 Sdk를 도입 하지 않고도 ASP.NET Core 미들웨어를 사용 하 여 기능을 추가할 수 있습니다.

- **바인딩**
  - EShopOnContainers 솔루션에는 주문 확인을 고객에 게 전자 메일로 보내는 할 *일* 항목이 포함 되어 있습니다. 궁극적으로 SendGrid와 같은 타사 메일 API를 구현 하는 것으로 생각 합니다. D 4에서 전자 메일 알림을 구현 하는 것은 리소스 바인딩을 구성 하는 것 만큼 쉽습니다. 외부 Api 또는 Sdk를 학습할 필요가 없습니다.

> [!NOTE]
> 행위자 빌딩 블록은이 책의 첫 번째 버전에서 다루지 않습니다. 행위자 빌딩 블록의 광범위 한 장과 eShopOnDapr와의 통합이 1.1 업데이트에 포함 됩니다.

## <a name="summary"></a>요약

이 장에서는 eShopOnDapr reference 응용 프로그램에 대해 소개 합니다. 널리 사용 되는 eShopOnContainers 마이크로 서비스 reference 응용 프로그램의 진화입니다. eShopOnDapr은 많은 양의 사용자 지정 기능을 매우 많은 수의 구성 요소와 구성 요소로 대체 하 여 마이크로 서비스 응용 프로그램을 빌드하는 데 필요한 복잡성을 대폭 간소화 합니다.

### <a name="references"></a>참조

- [eShopOnDapr](https://github.com/dotnet-architecture/eShopOnDapr)

- [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers)

- [컨테이너 화 된 .NET 응용 프로그램용 .NET 마이크로 서비스](https://dotnet.microsoft.com/download/e-book/microservices-architecture/pdf)

- [Azure 용 Cloud-Native .NET 앱 설계](https://dotnet.microsoft.com/download/e-book/cloud-native-azure/pdf)

> [!div class="step-by-step"]
> [이전](getting-started.md)
> [다음](state-management.md)
