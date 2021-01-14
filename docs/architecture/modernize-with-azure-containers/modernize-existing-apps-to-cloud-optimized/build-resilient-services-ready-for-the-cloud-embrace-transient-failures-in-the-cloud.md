---
title: 클라우드를 위한 복원력 있는 서비스 빌드 클라우드의 일시적 오류 포용
description: Azure Cloud 및 Windows 컨테이너를 사용하여 기존 .NET 애플리케이션 현대화 | 클라우드를 위한 복원력 있는 서비스 빌드 클라우드의 일시적 오류 포용
ms.date: 12/21/2020
ms.openlocfilehash: 4d592a5761cdf696f3e57516d747cbd770512053
ms.sourcegitcommit: 5d9cee27d9ffe8f5670e5f663434511e81b8ac38
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2021
ms.locfileid: "98025331"
---
# <a name="build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud"></a>클라우드를 위한 탄력적인 서비스 빌드: 클라우드의 일시적 오류 포용

복원력은 오류를 복구하고 계속 작업을 진행하는 기능입니다. 복원력은 실패를 방지하는 기능이 아닌 실패가 발생할 수 있다는 사실을 받아들이고 가동 중지 시간 또는 데이터 손실을 방지할 수 있도록 해당 실패에 응답하는 기능입니다. 복원력의 목표는 오류 발생 후 애플리케이션을 완전히 작동 중인 상태로 되돌리는 것입니다.

애플리케이션은 최소한 하드웨어 기반 모델이 아닌 소프트웨어 기반 모델의 복원력을 구현하는 경우 클라우드에 사용할 준비가 된 것입니다. 클라우드 애플리케이션은 결국 발생하게 되는 부분 실패를 수용해야 합니다. 애플리케이션을 디자인하거나 부분적으로 리팩터링하여 예상되는 부분 실패에 대한 복원력을 구현합니다. 애플리케이션은 클라우드에서의 일시적 네트워크 중단과 노드 또는 VM 충돌과 같은 부분 실패에 대처할 수 있도록 디자인되어야 합니다. 오케스트레이터 클러스터 내에서 다른 노드로 이동한 컨테이너도 애플리케이션에서 일시적 단기 실패를 유발할 수 있습니다.

## <a name="handling-partial-failure"></a>부분 실패 처리

클라우드 기반 애플리케이션의 경우 부분 실패의 위험이 있습니다. 예를 들어, 단일 웹 사이트 인스턴스 또는 컨테이너가 실패할 수도 있고, 단기간 동안 사용할 수 없거나 응답하지 않을 수도 있습니다. 또는 단일 VM 또는 서버에서 충돌이 발생할 수 있습니다.

클라이언트와 서비스는 별도의 프로세스이기 때문에 서비스가 클라이언트의 요청에 적시에 응답하지 못할 수 있습니다. 서비스가 오버로드되고 요청에 느리게 응답하거나, 네트워크 문제로 인해 짧은 시간 동안 액세스하지 못할 수도 있습니다.

예를 들어 Azure SQL Database에서 데이터베이스에 액세스하는 모놀리식 .NET 애플리케이션이 있다고 가정해 보겠습니다. Azure SQL 데이터베이스 또는 다른 타사 서비스가 잠시 동안 응답하지 않는 경우(Azure SQL 데이터베이스는 다른 노드 또는 서버로 이동하고 몇 초 동안 응답하지 않을 수 있음) 사용자가 작업을 수행하려고 하면 애플리케이션에 충돌이 발생하고 이와 동시에 예외가 표시될 수 있습니다.

HTTP 서비스를 사용하는 앱에서도 비슷한 시나리오가 발생할 수 있습니다. 단기간의 일시적 실패 동안 클라우드에서 네트워크 또는 서비스 자체를 사용하지 못할 수 있습니다.

그림 4-9에 표시된 것과 같은 복원력 있는 애플리케이션은 "지수 백오프를 사용하여 다시 시도"와 같은 기술을 구현하여 애플리케이션에서 리소스의 일시적 실패를 처리할 수 있는 기회가 있어야 합니다. 또한 애플리케이션에서 "회로 차단기"를 사용해야 합니다. 회로 차단기는 실제로 장기 오류일 때 애플리케이션이 리소스에 액세스를 시도하는 것을 차단합니다. 애플리케이션은 회로 차단기를 사용하여 자신에 대한 서비스 거부를 방지합니다.

![지수 백오프를 사용하여 다시 시도에 의해 처리되는 부분 실패의 다이어그램](./media/retry-partial-failures.png)

**그림 4-9.** 지수 백오프를 사용하여 다시 시도에 의해 처리되는 부분 실패

HTTP 리소스와 데이터베이스 리소스 모두에서 이러한 기술을 사용할 수 있습니다. 그림 4-9에서는 애플리케이션이 3계층 아키텍처를 기반으로 하므로 서비스 수준(HTTP) 및 데이터 계층 수준(TCP)에서 이러한 기술이 필요합니다. 데이터베이스 이외에 단일 앱 계층만 사용하는 모놀리식 애플리케이션(추가 서비스 또는 마이크로 서비스가 없음)에서는 데이터베이스 연결 수준에서 일시적 실패를 처리하는 것으로 충분할 수 있습니다. 이 시나리오에서는 특정한 데이터베이스 연결 구성만 필요합니다.

데이터베이스에 액세스하는 복원력 있는 통신을 구현하는 경우 이는 사용 중인 .NET 버전에 따라 간단할 수 있습니다. (예를 들어 [Entity Framework 6 이상](/ef/ef6/fundamentals/connection-resiliency/retry-logic)에서는 데이터베이스 연결을 구성하는 문제일 뿐입니다.) 또는 [일시적 실패 처리 애플리케이션 블록](/previous-versions/msp-n-p/hh680934(v=pandp.50))과 같은 추가 라이브러를 사용하거나(이전 버전의 .NET) 심지어 사용자 고유 라이브러리를 구현해야 할 수도 있습니다.

HTTP 재시도 및 회로 차단기를 구현할 때 .NET에 대한 권장 사항은 .NET Standard 1.1(범위: .NET Core 1.0, Mono, Xamarin, UWP, WP8.1 이상) 및 .NET Standard 2.0 이상(범위: .NET Core 2.0 이상, .NET Core 3.0, 이후 Mono, Xamarin 및 UWP 대상)을 대상으로 하는 [Polly](https://github.com/App-vNext/Polly) 라이브러리를 사용하는 것입니다. NuGet 패키지에는 .NET Framework 4.6.1 및 4.7.2에 대한 직접 대상도 포함됩니다.

클라우드에서 부분 실패를 처리하기 위한 전략을 구현하는 방법을 알아보려면 다음 참조를 참조하세요.

### <a name="additional-resources"></a>추가 리소스

- **부분 실패를 처리하기 위한 복원력 있는 통신 구현**

    [https://docs.microsoft.com/dotnet/architecture/microservices/implement-resilient-applications/partial-failure-strategies](../../microservices/implement-resilient-applications/partial-failure-strategies.md)

- **Entity Framework 연결 복원력 및 다시 시도 논리(버전 6 이상)**

    [https://docs.microsoft.com/ef/ef6/fundamentals/connection-resiliency/retry-logic](/ef/ef6/fundamentals/connection-resiliency/retry-logic)

- **일시적인 오류 처리 애플리케이션 블록**

- <https://docs.microsoft.com/previous-versions/msp-n-p/hh680934(v=pandp.50)>

- **복원력 있는 HTTP 통신용 Polly 라이브러리**

    <https://github.com/App-vNext/Polly>

>[!div class="step-by-step"]
>[이전](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
>[다음](modernize-your-apps-with-monitoring-and-telemetry.md)
