---
title: 클라우드 네이티브 응용 프로그램에서 캐싱
description: 클라우드 네이티브 응용 프로그램의 캐싱 전략에 대해 알아봅니다.
author: robvet
ms.date: 01/22/2020
ms.openlocfilehash: 2da61a01fc53233d1934df813fcba3b91a495c43
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76795118"
---
# <a name="caching-in-a-cloud-native-app"></a>클라우드 네이티브 앱에서 캐싱

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

캐싱의 이점은 잘 이해 됩니다. 이 기법은 백 엔드 데이터 저장소에서 자주 액세스 하는 데이터를 응용 프로그램에 더 가까이 있는 *빠른 저장소* 로 임시로 복사 하는 방식으로 작동 합니다. 캐싱은 종종 구현 되는 위치입니다.

- 데이터는 상대적으로 정적 상태로 유지 됩니다.
- 특히 캐시 속도와 비교 하 여 데이터 액세스가 느립니다.
- 데이터는 높은 수준의 경합이 적용 됩니다.

## <a name="why"></a>이유는 무엇입니까?

[Microsoft 캐싱 지침](https://docs.microsoft.com/azure/architecture/best-practices/caching)에 설명 된 대로 캐싱은 개별 마이크로 서비스 및 시스템 전체에 대 한 성능, 확장성 및 가용성을 향상 시킬 수 있습니다. 데이터 저장소에 대 한 대량의 동시 요청 처리의 대기 시간과 경합을 줄입니다. 데이터 볼륨 및 사용자 수가 늘어나면 캐싱의 이점이 커집니다.

캐싱은 클라이언트가 변경 불가능 하거나 자주 변경 되지 않는 데이터를 반복 해 서 읽을 때 가장 효과적입니다. 예를 들어 제품 및 가격 정보와 같은 참조 정보나 구성에 비용이 많이 드는 공유 정적 리소스가 있습니다.

마이크로 서비스는 상태 비저장 이어야 하지만, 분산 캐시는 절대적으로 필요한 경우 세션 상태 데이터에 대 한 동시 액세스를 지원할 수 있습니다.

반복 계산을 방지 하기 위해 캐싱도 고려 합니다. 작업에서 데이터를 변환 하거나 복잡 한 계산을 수행 하는 경우 후속 요청에 대 한 결과를 캐시 합니다.

## <a name="caching-architecture"></a>캐싱 아키텍처

클라우드 네이티브 응용 프로그램은 일반적으로 분산 캐싱 아키텍처를 구현 합니다. 캐시는 마이크로 서비스와는 별도로 클라우드 기반 [지원 서비스로](./definition.md#backing-services)호스팅됩니다. 그림 5-20은 아키텍처를 보여 줍니다.

![클라우드 네이티브 앱에서 캐싱](media/caching-in-a-cloud-native-app.png)

**그림 5-19**: 클라우드 네이티브 앱에서 캐싱

위의 그림에서 캐시는 마이크로 서비스에 독립적이 고 공유 되는 방식을 확인 합니다. 이 시나리오에서는 [API 게이트웨이에서](./front-end-communication.md)캐시가 호출 됩니다. 4 장에서 설명한 대로 게이트웨이는 들어오는 모든 요청에 대 한 프런트 엔드 역할을 합니다. 분산 캐시는 가능한 경우 캐시 된 데이터를 반환 하 여 시스템 응답성을 높입니다. 또한 캐시를 서비스와 분리 하 여 증가 된 트래픽 수요를 충족 하기 위해 캐시를 독립적으로 확장 또는 축소할 수 있습니다.

이 그림에서는 [캐시 배제 패턴](https://docs.microsoft.com/azure/architecture/patterns/cache-aside)이라고 하는 일반적인 캐싱 패턴을 보여 줍니다. 들어오는 요청의 경우 먼저 캐시 (단계 \#1)에서 응답을 쿼리 합니다. 데이터를 찾았으면 즉시 반환 됩니다. 데이터가 캐시에 없으면 ( [캐시 누락](https://www.techopedia.com/definition/6308/cache-miss)이라고 함) 다운스트림 서비스의 로컬 데이터베이스에서 검색 됩니다 (step \#2). 그런 다음 나중에 요청 (단계 \#3)에 대 한 캐시에 기록 되 고 호출자에 게 반환 됩니다. 시스템이 시기 적절 하 고 일관 되 게 유지 되도록 캐시 된 데이터를 정기적으로 제거 해야 합니다.

공유 캐시가 증가 함에 따라 여러 노드 간에 데이터를 분할 하는 것이 유용할 수 있습니다. 이렇게 하면 경합을 최소화 하 고 확장성을 향상 시킬 수 있습니다. 많은 캐싱 서비스는 노드를 동적으로 추가 및 제거 하 고 파티션 간에 데이터의 균형을 다시 조정 하는 기능을 지원 합니다. 이 방법은 일반적으로 클러스터링을 포함 합니다. 클러스터링은 페더레이션 노드의 컬렉션을 원활한 단일 캐시로 노출 합니다. 그러나 내부적으로 데이터는 부하를 균등 하 게 분산 하는 미리 정의 된 배포 전략에 따라 노드 간에 분산 됩니다.

## <a name="azure-cache-for-redis"></a>Azure Cache for Redis

[Redis 용 Azure Cache](https://azure.microsoft.com/services/cache/) 는 Microsoft에서 완벽 하 게 관리 하는 안전한 데이터 캐싱 및 메시징 브로커 서비스입니다. PaaS (Platform as a Service) 제품으로 사용 되는 데이터에 대 한 높은 처리량 및 대기 시간이 짧은 액세스를 제공 합니다. 서비스는 Azure 내부 또는 외부의 모든 응용 프로그램에서 액세스할 수 있습니다.

Azure Cache for Redis 서비스는 Azure 데이터 센터에서 호스트 되는 오픈 소스 Redis 서버에 대 한 액세스를 관리 합니다. 서비스는 관리, 액세스 제어 및 보안을 제공 하는 외관 역할을 합니다. 서비스는 기본적으로 문자열, 해시, 목록 및 집합을 비롯 한 다양 한 데이터 구조 집합을 지원 합니다. 응용 프로그램에서 이미 Redis를 사용 하는 경우 Redis 용 Azure Cache와 동일 하 게 작동 합니다.

Redis에 대 한 Azure Cache는 단순 캐시 서버입니다. 마이크로 서비스 아키텍처를 개선 하는 여러 가지 시나리오를 지원할 수 있습니다.

- 메모리 내 데이터 저장소
- 분산형 비관계형 데이터베이스
- 메시지 브로커
- 구성 또는 검색 서버
  
고급 시나리오의 경우 캐시 된 데이터의 복사본을 [디스크에 유지할](https://docs.microsoft.com/azure/azure-cache-for-redis/cache-how-to-premium-persistence)수 있습니다. 치명적 이벤트에서 주 캐시와 복제본 캐시를 모두 사용 하지 않도록 설정 하면 가장 최근 스냅숏에서 캐시가 재구성 됩니다.

Azure Redis Cache는 미리 정의 된 여러 구성 및 가격 책정 계층에서 사용할 수 있습니다.  [프리미엄 계층](https://docs.microsoft.com/azure/azure-cache-for-redis/cache-premium-tier-intro) 에는 클러스터링, 데이터 지 속성, 지역에서 복제 및 가상 네트워크 격리와 같은 많은 엔터프라이즈 수준 기능이 있습니다.

>[!div class="step-by-step"]
>[이전](relational-vs-nosql-data.md)
>[다음](elastic-search-in-azure.md)
