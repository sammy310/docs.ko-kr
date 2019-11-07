---
title: 클라우드에 대해 준비 된 복원 서비스를 빌드합니다. 클라우드의 일시적 오류 포용
description: Azure 클라우드 및 Windows 컨테이너를 사용 하 여 기존 .NET 응용 프로그램 현대화 | 클라우드에 대해 준비 된 복원 서비스를 빌드합니다. 클라우드의 일시적 오류 포용
ms.date: 04/30/2018
ms.openlocfilehash: e6fae8140b55cb0308dca9f4b77e961501b41f8f
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739406"
---
# <a name="build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud"></a>클라우드에 대 한 복원 력 서비스 빌드: 클라우드의 일시적 오류 수용

복원력은 오류를 복구하고 계속 작업을 진행하는 기능입니다. 복원 력은 오류를 방지 하는 것이 아니라 오류가 발생 한다는 사실을 감안 하 여 가동 중지 시간 또는 데이터 손실을 방지 하는 방식으로 응답 합니다. 복원력의 목표는 오류 발생 후 애플리케이션을 완전히 작동 중인 상태로 되돌리는 것입니다.

응용 프로그램은 최소한 하드웨어 기반 모델이 아닌 소프트웨어 기반 복원 력 모델을 구현 하는 경우 클라우드에 사용할 준비가 된 것입니다. 클라우드 응용 프로그램은 발생 하는 부분 오류를 수용 해야 합니다. 예상 되는 부분 오류로 인해 복원 력을 얻으려면 응용 프로그램을 디자인 하거나 부분적으로 리팩터링할 수 있습니다. 일시적인 네트워크 중단 및 노드 또는 클라우드에서 충돌 하는 Vm과 같은 부분 오류를 처리 하도록 설계 해야 합니다. 컨테이너가 orchestrator 클러스터 내의 다른 노드로 이동 하는 경우에도 응용 프로그램 내에서 일시적인 오류가 발생할 수 있습니다.

## <a name="handling-partial-failure"></a>부분 실패 처리

클라우드 기반 응용 프로그램의 경우 부분 오류의 위험이 있습니다. 예를 들어, 단일 웹 사이트 인스턴스 또는 컨테이너가 실패할 수도 있고, 짧은 시간 동안 사용할 수 없거나 응답 하지 않을 수도 있습니다. 또는 단일 VM 또는 서버에서 충돌이 발생할 수 있습니다.

클라이언트와 서비스는 별도의 프로세스 이기 때문에 서비스가 클라이언트의 요청에 시기 적절 하 게 응답 하지 못할 수 있습니다. 서비스가 오버 로드 되어 요청에 느리게 응답 하거나 네트워크 문제로 인해 짧은 시간 동안 액세스 하지 못할 수 있습니다.

예를 들어 Azure SQL Database에서 데이터베이스에 액세스 하는 모놀리식 .NET 응용 프로그램이 있다고 가정 합니다. Azure SQL database 또는 기타 타사 서비스가 잠깐 동안 응답 하지 않는 경우 (Azure SQL database는 다른 노드나 서버로 이동 하 고 몇 초 동안 응답 하지 않을 수 있음) 사용자가 작업을 수행 하려고 하면 응용 프로그램이 충돌 하 고 표시 수 있습니다. 같은 순간에 예외가 발생 합니다.

HTTP 서비스를 사용 하는 앱에서 유사한 시나리오가 발생할 수 있습니다. 단기 일시적 오류 중에는 클라우드에서 네트워크 또는 서비스 자체를 사용 하지 못할 수 있습니다.

그림 4-9에 표시 된 것과 같은 탄력적 응용 프로그램은 응용 프로그램에 리소스의 일시적인 오류를 처리할 수 있는 기회를 제공 하기 위해 "지 수 백오프를 통해 다시 시도"와 같은 기술을 구현 해야 합니다. 또한 응용 프로그램에서 "회로 차단기"를 사용 해야 합니다. 회로 차단기는 실제로 장기 오류일 때 응용 프로그램이 리소스에 액세스 하는 것을 중지 합니다. 응용 프로그램은 회로 차단기를 사용 하 여 서비스 거부 흥미로운 방지 합니다.

![지 수 백오프를 사용 하 여 다시 시도로 처리 되는 부분 실패의 다이어그램입니다.](./media/build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud/retry-partial-failures.png)

**그림 4-9.** 지 수 백오프를 사용 하 여 재시도로 처리 되는 부분 오류

HTTP 리소스와 데이터베이스 리소스에서 이러한 기술을 모두 사용할 수 있습니다. 그림 4-9에서 응용 프로그램은 3 계층 아키텍처를 기반으로 하므로 서비스 수준 (HTTP) 및 데이터 계층 수준 (TCP)에서 이러한 기술이 필요 합니다. 데이터베이스 외에도 단일 앱 계층만 사용 하는 모놀리식 응용 프로그램 (추가 서비스 또는 마이크로 서비스 없음)에서 데이터베이스 연결 수준에서 일시적인 오류를 처리 하는 것으로 충분할 수 있습니다. 이 시나리오에서는 데이터베이스 연결의 특정 구성만 필요 합니다.

사용 중인 .NET 버전에 따라 데이터베이스에 액세스 하는 복원 력 있는 통신을 구현 하는 경우, 예를 들어 [Entity Framework 6 이상인](/ef/ef6/fundamentals/connection-resiliency/retry-logic)경우에는 간단 하 게 사용할 수 있습니다. 데이터베이스 연결을 구성 하는 것이 중요 합니다. 또는 [임시 오류 처리 응용 프로그램 블록](https://docs.microsoft.com/previous-versions/msp-n-p/hh680934(v=pandp.50)) (이전 버전의 .net의 경우)과 같은 추가 라이브러리를 사용 하거나 사용자 고유의 라이브러리를 구현 해야 할 수도 있습니다.

HTTP 재시도 및 회로 차단기를 구현할 때 .NET의 권장 사항은 .NET Core 지원을 포함 하는 .NET Framework 4.0, .NET Framework 4.5 및 .NET Standard 1.1를 대상으로 하는 [기능 라이브러리를](https://github.com/App-vNext/Polly) 사용 하는 것입니다.

클라우드의 부분 실패를 처리 하기 위한 전략을 구현 하는 방법을 알아보려면 다음 참조를 참조 하세요.

### <a name="additional-resources"></a>추가 자료

- **부분 오류를 처리 하기 위한 복원 력 통신 구현**

    [https://docs.microsoft.com/dotnet/architecture/microservices/implement-resilient-applications/partial-failure-strategies](../../microservices/implement-resilient-applications/partial-failure-strategies.md)

- **Entity Framework 연결 복원 력 및 재시도 논리 (버전 6 이상)**

    [https://docs.microsoft.com/ef/ef6/fundamentals/connection-resiliency/retry-logic](/ef/ef6/fundamentals/connection-resiliency/retry-logic)

- **일시적인 오류 처리 응용 프로그램 블록**

- <https://docs.microsoft.com/previous-versions/msp-n-p/hh680934(v=pandp.50)>

- **복원 력 있는 HTTP 통신용 정책**

    https://github.com/App-vNext/Polly

>[!div class="step-by-step"]
>[이전](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
>[다음](modernize-your-apps-with-monitoring-and-telemetry.md)
