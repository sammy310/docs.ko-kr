---
title: Azure 플랫폼 복원 력
description: Azure 용 클라우드 네이티브 .NET 앱 설계 | Azure를 사용 하는 클라우드 인프라 복원 력
ms.date: 06/30/2019
ms.openlocfilehash: 8b33c1cec1633c9fb25ae2b02e51f8be01c22941
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337383"
---
# <a name="azure-platform-resiliency"></a>Azure 플랫폼 복원 력

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

클라우드에서 신뢰할 수 있는 응용 프로그램을 구축 하는 것은 기존 온-프레미스 응용 프로그램 개발과 다릅니다. 지금까지 강화 하기 위해 고급 하드웨어를 구입 했지만, 클라우드 환경에서는 규모를 확장 합니다. 목표는 오류를 방지 하는 것이 아니라 영향을 최소화 하 고 시스템을 안정적으로 유지 하는 것입니다.

즉, 신뢰할 수 있는 클라우드 응용 프로그램은 다음과 같은 고유한 특성을 표시 합니다.

- 복원 력을 유지 하 고 문제를 해결 하며 계속 해 서 작동 합니다.
- HA (고가용성) 이며 상당한 가동 중지 시간 없이 정상 상태에서 설계 된 대로 실행 됩니다.

이러한 특징이 함께 작동 하는 방식과 비용에 미치는 영향을 이해 하는 것은 안정적인 클라우드 네이티브 응용 프로그램을 구축 하는 데 필수적입니다. 다음으로 Azure 클라우드의 기능을 활용 하 여 클라우드 네이티브 응용 프로그램에 복원 력 및 가용성을 구축할 수 있는 방법을 살펴보겠습니다.

## <a name="design-with-redundancy"></a>중복성으로 디자인

오류는 영향 범위에 따라 다릅니다. 하드웨어 오류 (예: 실패 한 디스크)는 클러스터의 단일 노드에 영향을 줄 수 있습니다. 실패 한 네트워크 스위치는 전체 서버 랙에 영향을 줄 수 있습니다. 전력 손실과 같이 일반적이 지 않은 오류는 전체 데이터 센터에 방해가 될 수 있습니다. 드물게 전체 지역을 사용할 수 없게 됩니다.

[중복성](https://docs.microsoft.com/azure/architecture/guide/design-principles/redundancy) 은 응용 프로그램 복원 력을 제공 하는 한 가지 방법입니다. 필요한 정확한 중복성 수준은 비즈니스 요구 사항에 따라 다르며 시스템의 비용과 복잡도에 영향을 줍니다. 예를 들어 다중 지역 배포는 단일 지역 배포 보다 더 비용이 많이 들고 관리가 복잡 합니다. 장애 조치 (failover) 및 장애 복구를 관리 하려면 운영 절차가 필요 합니다. 추가적인 비용 및 복잡성이 타당한 비즈니스 시나리오도 있고 그렇지 않은 경우도 있습니다.

중복성을 설계 하려면 응용 프로그램에서 중요 한 경로를 확인 한 다음 경로의 각 지점에서 중복성이 있는지 확인 해야 합니다. 하위 시스템이 실패 하는 경우 응용 프로그램이 다른 작업으로 장애 조치 (failover) 되나요? 마지막으로, 중복성 요구 사항을 충족 하기 위해 활용할 수 있는 Azure 클라우드 플랫폼에 기본 제공 되는 기능을 명확 하 게 이해 해야 합니다. 중복성 설계에 대 한 권장 사항은 다음과 같습니다.

- *서비스의 여러 인스턴스를 배포합니다.* 애플리케이션이 서비스의 단일 인스턴스에 종속된 경우 단일 실패 지점이 생깁니다. 여러 인스턴스를 프로비전하면 복원력 및 확장성이 모두 개선됩니다. Azure Kubernetes Service에서 호스트 하는 경우 Kubernetes 매니페스트 파일에서 중복 인스턴스 (복제본 집합)를 선언적으로 구성할 수 있습니다. 복제본 수 값은 포털에서 프로그래밍 방식으로 관리 하거나 자동 크기 조정 기능을 통해 관리할 수 있습니다 .이에 대해서는 뒷부분에서 설명 합니다.

- *부하 분산 장치 활용* 부하 분산은 응용 프로그램의 요청을 정상적인 서비스 인스턴스에 배포 하 고 자동으로 비정상 인스턴스를 회전에서 제거 합니다. Kubernetes에 배포 하는 경우 Kubernetes manifest 파일의 서비스 섹션에서 부하 분산을 지정할 수 있습니다.

- *다중 지역 배포를 계획 합니다.* 응용 프로그램이 단일 지역에 배포 되 고 해당 지역을 사용할 수 없게 되 면 응용 프로그램도 사용할 수 없게 됩니다. 이는 응용 프로그램의 서비스 수준 계약의 조건에서 허용 되지 않을 수 있습니다. 대신 여러 지역에 응용 프로그램 및 서비스를 배포 하는 것이 좋습니다. 예를 들어 AKS (Azure Kubernetes Service) 클러스터는 단일 지역에 배포 됩니다. 지역 장애 로부터 시스템을 보호 하기 위해 응용 프로그램을 여러 지역의 여러 AKS 클러스터에 배포 하 고 [쌍을 이루는 지역](https://buildazure.com/2017/01/06/azure-region-pairs-explained/) 기능을 사용 하 여 플랫폼 업데이트를 조정 하 고 복구 작업의 우선 순위를 정할 수 있습니다.

- *[지역에서 복제](https://docs.microsoft.com/azure/sql-database/sql-database-active-geo-replication)를 사용 하도록 설정 합니다.* Azure SQL Database, Cosmos DB 등의 서비스에 대 한 지역에서 복제는 여러 지역에 걸쳐 데이터의 보조 복제본을 만듭니다. 두 서비스 모두 동일한 지역 내에서 데이터를 자동으로 복제 하지만 지역에서 복제는 보조 지역으로 장애 조치 (failover) 할 수 있도록 하 여 지역 가동 중단 으로부터 사용자를 보호 합니다. 컨테이너 이미지를 저장 하는 방법에 대 한 지리적 복제 센터의 또 다른 모범 사례입니다. AKS에 서비스를 배포 하려면 리포지토리에서 이미지를 저장 하 고 가져와야 합니다. Azure Container Registry AKS와 통합 되며 컨테이너 이미지를 안전 하 게 저장할 수 있습니다. 성능 및 가용성을 향상 시키려면 이미지를 AKS 클러스터가 있는 각 지역의 레지스트리에 지리적으로 복제 하는 것이 좋습니다. 그런 다음 그림 6-6에 표시 된 것 처럼 각 AKS 클러스터는 해당 지역의 로컬 컨테이너 레지스트리에서 컨테이너 이미지를 끌어옵니다.

![지역 간 복제 된 리소스](./media/replicated-resources.png)

**그림 6-6** 지역 간 복제 된 리소스

- *DNS 트래픽 부하 분산 장치를 구현 합니다.* [Azure Traffic Manager](https://docs.microsoft.com/azure/traffic-manager/traffic-manager-overview) 는 DNS 수준에서 부하 분산을 통해 중요 한 응용 프로그램에 대 한 고가용성을 제공 합니다. 지리적 위치, 클러스터 응답 시간 및 심지어 응용 프로그램 끝점 상태에 따라 다른 지역으로 트래픽을 라우팅할 수 있습니다. 예를 들어 Azure Traffic Manager는 고객에 게 가장 가까운 AKS 클러스터 및 응용 프로그램 인스턴스로 지시할 수 있습니다. 서로 다른 지역에 여러 AKS 클러스터가 있는 경우 Traffic Manager를 사용 하 여 각 클러스터에서 실행 되는 응용 프로그램에 대 한 트래픽 흐름 방식을 제어 합니다. 그림 6-7에서는이 시나리오를 보여 줍니다.

![AKS 및 Azure Traffic Manager](./media/aks-traffic-manager.png)

**그림 6-7** AKS 및 Azure Traffic Manager

## <a name="design-for-scalability"></a>확장성을 위한 디자인

클라우드는 크기를 thrives. 시스템 리소스를 늘리거나 줄여 시스템 부하를 해결 하는 기능은 Azure 클라우드의 주요 개념입니다. 그러나 응용 프로그램을 효과적으로 확장 하려면 응용 프로그램에 포함 하는 각 Azure 서비스의 크기 조정 기능을 이해 해야 합니다.  시스템에서 크기 조정을 효과적으로 구현 하기 위한 권장 사항은 다음과 같습니다.

- *크기 조정을 위한 디자인.* 응용 프로그램은 크기 조정을 위해 디자인 되어야 합니다. 시작 하려면 요청을 임의의 인스턴스로 라우팅할 수 있도록 서비스의 상태를 지정 해야 합니다. 상태 비저장 서비스가 있으면 인스턴스를 추가 하거나 제거 해도 현재 사용자에 게 부정적인 영향을 주지 않습니다.

- *작업을 분할*합니다. 독립적인 자체 포함 마이크로 서비스로 도메인을 분해 각 서비스를 다른 서비스와 독립적으로 확장할 수 있습니다. 일반적으로 서비스에는 서로 다른 확장성 요구 사항과 요구 사항이 있습니다. 분할을 사용 하면 전체 응용 프로그램의 크기를 조정 하는 데 불필요 한 비용 없이 크기를 조정 해야 하는 내용만 확장할 수 있습니다.

- *규모 확장을 선호 합니다.* 클라우드 기반 응용 프로그램은 확장이 아니라 리소스를 확장 하는 것을 선호 합니다. 규모 확장 (수평 크기 조정이 라고도 함)은 원하는 수준의 성능을 충족 하 고 공유 하기 위해 기존 시스템에 서비스 리소스를 더 추가 하는 작업을 포함 합니다. 수직 확장 (수직 확장이 라고도 함)은 기존 리소스를 더 강력한 하드웨어 (더 많은 디스크, 메모리 및 처리 코어)로 교체 하는 과정을 포함 합니다. 일부 Azure 클라우드 리소스에서 사용할 수 있는 자동 크기 조정 기능을 사용 하 여 확장을 자동으로 호출할 수 있습니다. 여러 리소스에 걸쳐 확장 하면 전체 시스템에 중복성도 추가 됩니다. 마지막으로, 단일 리소스를 확장 하는 작업은 일반적으로 더 작은 리소스에서 확장 하는 것 보다 더 비쌉니다. 그림 6-8에서는 두 가지 방법을 보여 줍니다.

![규모 확장 및 규모 확장](./media/scale-up-scale-out.png)

**그림 6-8.** 규모 확장 및 규모 확장

- *비례적으로 크기 조정* 서비스 크기를 조정 하는 경우 *리소스 집합*을 고려 합니다. 특정 서비스를 크게 확장 하는 경우 백 엔드 데이터 저장소, 캐시 및 종속 서비스에 미치는 영향은 무엇 인가요? Cosmos DB와 같은 일부 리소스는 비례적으로 확장 될 수 있지만 다른 많은 리소스는 사용할 수 없습니다. 리소스를 다른 연결 된 리소스를 소모 하는 지점으로 확장 하지 않도록 하려고 합니다.

- *선호도를 피합니다.* 노드가 로컬 선호도를 필요로 하지 않도록 하는 것이 가장 좋은 방법입니다. 일반적으로 *고정 세션이*라고도 합니다. 요청은 임의의 인스턴스로 라우팅할 수 있어야 합니다. 상태를 유지 해야 하는 경우 [Azure Redis cache](https://azure.microsoft.com/services/cache/)와 같은 분산 캐시에 저장 해야 합니다.

- *플랫폼 자동 크기 조정 기능을 활용 합니다.* 사용자 지정 또는 타사 메커니즘이 아닌 가능한 경우 기본 제공 자동 크기 조정 기능을 사용 합니다. 가능 하면 예약 된 크기 조정 규칙을 사용 하 여 시작 지연 없이 리소스를 사용할 수 있도록 하 고, 필요에 따라 규칙에 반응 형 자동 크기 조정을 추가 하 여 예기치 않은 수요 변화를 처리할 수 있습니다. 자세한 내용은 자동 크기 조정 [지침](https://docs.microsoft.com/azure/architecture/best-practices/auto-scaling)을 참조 하세요.

- *적극적으로 확장 합니다.* 최종 방법은 비즈니스를 잃지 않고 트래픽의 즉각적인 급증을 신속 하 게 충족할 수 있도록 적극적으로 규모를 확장 하는 것입니다. 그리고 시스템을 안정적으로 유지 하기 위해 (즉, 불필요 한 인스턴스 제거)를 확장 합니다. 이를 구현 하는 간단한 방법은 크기 조정 작업 사이에 대기 하는 시간, 리소스를 추가 하는 데 5 분, 인스턴스를 제거 하는 데 최대 15 분이 되는 쿨 다운 기간을 설정 하는 것입니다.

## <a name="built-in-retry-in-services"></a>서비스의 기본 제공 다시 시도

이전 섹션에서 프로그래밍 방식으로 다시 시도 하는 작업을 구현 하는 것이 좋습니다. 많은 Azure 서비스와 해당 클라이언트 Sdk에도 다시 시도 메커니즘이 포함 되어 있습니다. 다음 목록에서는이 책에서 설명 하는 대부분의 Azure 서비스에 대 한 다시 시도 기능을 요약 합니다.

- *Azure Cosmos DB.* 클라이언트 API의 <xref:Microsoft.Azure.Documents.Client.DocumentClient> 클래스는 실패 한 시도를 자동으로 받아볼 합니다. The number of retries and maximum wait time are configurable. Exceptions thrown by the client API are either requests that exceed the retry policy or non-transient errors.

- *Azure Redis Cache.* The Redis StackExchange client uses a connection manager class that includes retries on failed attempts. The number of retries, specific retry policy and wait time are all configurable.

- *Azure Service Bus.* The Service Bus client exposes a [RetryPolicy class](xref:Microsoft.ServiceBus.RetryPolicy) that can be configured with a back-off interval, retry count, and <xref:Microsoft.ServiceBus.RetryExponential.TerminationTimeBuffer%2A>, which specifies the maximum time an operation can take. The default policy is nine maximum retry attempts with a 30-second backoff period between attempts.

- *Azure SQL Database.* Retry support is provided when using the [Entity Framework Core](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency) library.

- *Azure Storage.* The storage client library support retry operations. The strategies vary across Azure storage tables, blobs, and queues. As well, alternate retries switch between primary and secondary storage services locations when the geo-redundancy feature is enabled.

- *Azure Event Hubs.* The Event Hub client library features a RetryPolicy property, which includes a configurable exponential backoff feature.

>[!div class="step-by-step"]
>[이전](application-resiliency-patterns.md)
>[다음](resilient-communications.md)
