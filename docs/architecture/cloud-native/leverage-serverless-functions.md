---
title: 서버리스 기능 활용
description: 클라우드 네이티브 응용 프로그램에서 서버 리스 및 Azure Functions 활용
ms.date: 06/30/2019
ms.openlocfilehash: 77ddef0eb8844ea1b55cd2fc5ec8aa12593c8631
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841746"
---
# <a name="leveraging-serverless-functions"></a>서버리스 기능 활용

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

클라우드 기능을 활용 하기 위해 전체 컴퓨터 및 운영 체제를 관리 하는 스펙트럼에서는 서버를 사용 하지 않는 것이 사용자의 코드 일 뿐 이며 코드가 실행 될 때만 지불 하면 됩니다. Azure Functions는 응용 프로그램에 서버 리스 기능을 빌드하는 방법을 제공 합니다.

## <a name="what-is-serverless"></a>서버를 사용 하지 않는 항목

서버를 사용 하지 않는 컴퓨팅은 응용 프로그램을 실행 하는 데 관련 된 서버가 없다는 것을 의미 하지 않습니다. 코드는 여전히 서버에서 실행 됩니다. 이러한 차이는 응용 프로그램 개발 팀이 서버 인프라를 관리 하는 데 더 이상 신경 쓸 필요가 없다는 것입니다. Azure Functions와 같은 서버를 사용 하지 않는 컴퓨팅 솔루션은 팀에서 생산성을 높이고 조직에서 리소스를 최적화 하 고 솔루션 제공에 집중할 수 있도록 지원 합니다.

서버를 사용 하지 않는 컴퓨팅은 이벤트 트리거 상태 비저장 컨테이너를 사용 하 여 응용 프로그램 또는 응용 프로그램의 일부를 호스팅합니다. 서버를 사용 하지 않는 플랫폼을 확장 하 고 필요에 따라 수요를 충족 시킬 수 있습니다. Azure Functions와 같은 플랫폼은 큐, 이벤트 및 저장소와 같은 다른 Azure 서비스에 쉽게 액세스할 수 있습니다.

## <a name="what-challenges-are-solved-by-serverless"></a>서버 리스에서 해결 되는 문제는 무엇 인가요?

서버를 사용 하지 않는 최종 추상화는 사용자 고유의 하드웨어를 실행 하는 것입니다. 개발자는 자체 서버를 호스팅할 때 필요한 다음 작업을 고려 하지 않고 비즈니스 문제를 해결 하기 위해 코드를 작성 하는 것에만 집중할 수 있습니다.

- 컴퓨터 및 소프트웨어 라이선스 구매
- 컴퓨터와 네트워킹, 전원 및 A/C 요구 사항 하우징, 보안, 구성 및 유지 관리
- 운영 체제 및 소프트웨어 패치 및 업그레이드
- 응용 프로그램 소프트웨어를 호스팅하도록 웹 서버 또는 컴퓨터 서비스 구성
- 플랫폼 내에서 응용 프로그램 소프트웨어 구성

많은 회사에서 수십 개의 직원 구성원을 사용 하 고 이러한 하드웨어 인프라 문제를 지원 하기 위해 많은 예산을 할당 합니다. 클라우드로 전환 하면 이러한 문제 중 일부가 제거 됩니다. 응용 프로그램을 서버를 사용 하지 않는 방식으로 이동 하면 나머지는 제거 됩니다.

## <a name="what-scenarios-are-appropriate-for-serverless"></a>서버 리스에 적합 한 시나리오는 무엇입니까?

서버를 사용 하지 않는 경우 일부 트리거에 대 한 응답으로 호출 되는 개별 단기 실행 함수를 사용 합니다. 이렇게 하면 백그라운드 작업을 처리 하는 데 적합 합니다.

예를 들어 응용 프로그램에서 요청 처리의 일부로 전자 메일을 보내야 할 수 있습니다. 웹 요청 처리의 일부로 전자 메일을 보내는 대신, 전자 메일의 세부 정보를 큐에 배치 하 고 Azure 함수를 사용 하 여 메시지를 선택 하 고 전자 메일을 보낼 수 있습니다. 응용 프로그램의 다양 한 부분이 나 심지어 많은 응용 프로그램에서이 동일한 Azure 함수를 활용 하 여 응용 프로그램에 대 한 향상 된 성능 및 확장성을 제공 하 고 [큐 기반 부하 평준화](https://docs.microsoft.com/azure/architecture/patterns/queue-based-load-leveling) 를 사용 하 여 전자 메일 전송과 관련 된 병목 현상을 방지할 수 있습니다.

응용 프로그램과 Azure Functions 간의 [게시자/구독자 패턴이](https://docs.microsoft.com/azure/architecture/patterns/publisher-subscriber) 가장 일반적인 패턴 이지만 다른 패턴을 사용할 수 있습니다. Azure Blob Storage에 대 한 변경 내용과 같은 다른 이벤트에 의해 Azure Functions 트리거될 수 있습니다. 이미지 업로드를 지 원하는 응용 프로그램에는 미리 보기 이미지 만들기, 업로드 된 이미지를 일관 된 차원으로 크기 조정 또는 이미지 크기 최적화를 담당 하는 Azure 함수가 있을 수 있습니다. 이러한 모든 기능은 Azure Blob Storage에 삽입 하 여 직접 트리거할 수 있으므로 응용 프로그램 자체에서 복잡성과 워크 로드를 모두 제외 시킬 수 있습니다.

많은 응용 프로그램에는 워크플로의 일부로 장기 실행 프로세스가 있습니다. 이러한 작업은 사용자가 응용 프로그램과의 상호 작용을 수행 하 여 사용자의 경험에 부정적인 영향을 줄 수 있도록 하는 경우가 많습니다. 서버를 사용 하지 않는 컴퓨팅은 사용자 상호 작용 루프 외부에서 더 느린 작업을 수행할 수 있는 좋은 방법을 제공 하며 이러한 작업은 전체 응용 프로그램의 크기를 조정할 필요 없이 필요에 따라 쉽게 확장할 수 있습니다.

## <a name="when-should-you-avoid-serverless"></a>서버를 사용 하지 않는 경우는 언제 인가요?

서버를 사용 하지 않는 컴퓨팅은 사용자 인터페이스를 차단 하지 않는 작업에 가장 적합 합니다. 즉, 웹 응용 프로그램 또는 web Api를 직접 호스트 하는 데 적합 하지 않습니다. 주된 이유는 서버를 사용 하지 않는 솔루션은 요청 시 프로 비전 되 고 확장 되기 때문입니다. 새 함수 인스턴스가 필요한 경우 *콜드 시작*이라고 하며 프로 비전 하는 데 시간이 걸립니다. 이 시간은 일반적으로 몇 초 이지만 다양 한 요소에 따라 더 길어질 수 있습니다. 단일 인스턴스를 정기적으로 연결 하는 경우 (예를 들어 정기적으로 요청을 수행 하는 경우), 인스턴스 수를 확장 해야 하는 경우 콜드 시작 문제가 남아 있습니다.

![콜드 및 웜 시작](./media/cold-start-warm-start.png)
**그림 3-10**. 콜드 시작과 웜 시작 비교

콜드 시작을 완전히 방지 해야 하는 경우 [소비 계획에서 전용 계획으로](https://azure.microsoft.com/blog/understanding-serverless-cold-start/)전환 하도록 선택할 수 있습니다. 프리미엄 요금제를 사용 하 여 [준비 인스턴스를 하나 이상 구성](https://docs.microsoft.com/azure/azure-functions/functions-premium-plan#pre-warmed-instances) 하 여 다른 인스턴스를 추가 해야 하는 경우 이미 실행 되 고 준비를 할 수도 있습니다. 이러한 옵션은 서버를 사용 하지 않는 컴퓨팅과 관련 된 주요 문제 중 하나를 완화할 수 있습니다.

또한 장기 실행 작업의 경우 일반적으로 서버 리스를 사용 하지 않아야 합니다. 이러한 작업은 신속 하 게 완료할 수 있는 작은 작업에 가장 적합 합니다. 서버를 사용 하지 않는 대부분의 플랫폼에서는 몇 분 내에 개별 함수를 완료 해야 합니다. 기본값은 5 분의 시간 제한 기간 (최대 10 분으로 구성 될 수 있음)을 Azure Functions 합니다. Azure Functions premium 요금제는이 문제를 완화 하 고, 시간을 30 분으로 제한 하 고 제한 없는 더 높은 제한을 구성할 수 있도록 허용 합니다.

마지막으로 응용 프로그램 내의 특정 작업에 대해 서버 리스를 활용 하면 복잡성이 증가 합니다. 먼저 모듈화 된 느슨하게 연결 된 방식으로 응용 프로그램을 설계 하는 것이 가장 좋습니다. 그런 다음 서버를 사용 하지 않는 이점이 있으면 추가 복잡성을 제공 하는지 확인 하는 것이 좋습니다. 서버를 사용 하지 않는 컴퓨팅에는 분산 응용 프로그램 아키텍처를 사용 하지 않고도 단일 모놀리식 배포에서 더 작은 응용 프로그램을 완벽 하 게 실행할 수 있습니다.

## <a name="references"></a>참조 항목

- [서버 리스 콜드 시작 이해](https://azure.microsoft.com/blog/understanding-serverless-cold-start/)
- [사전 준비 Azure Functions 인스턴스](https://docs.microsoft.com/azure/azure-functions/functions-premium-plan#pre-warmed-instances)
- [사용자 지정 이미지를 사용 하 여 Linux에서 함수 만들기](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image)

>[!div class="step-by-step"]
>[이전](leverage-containers-orchestrators.md)
>[다음](combine-containers-serverless-approaches.md)
