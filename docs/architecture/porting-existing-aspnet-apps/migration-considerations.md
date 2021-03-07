---
title: 마이그레이션 고려 사항
description: ASP.NET MVC에서 .NET Core로 마이그레이션해야 하는지 여부와 적절 한 결정을 내릴 수 있도록 팀에서 알아야 할 사항은 무엇 인가요?
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: efa1efc99cbe46ef289cfd6b53ba83b3bc1b56b1
ms.sourcegitcommit: bdbf6472de867a0a11aaa5b9384a2506c24f27d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2021
ms.locfileid: "102401915"
---
# <a name="migration-considerations"></a>마이그레이션 고려 사항

가장 기본적인 질문 팀은 앱을 .NET Core로 이식 하는 것과 관련 하 여 무엇을 이식 해야 하나요? ASP.NET MVC 및/또는 Web API를 사용 하 여 .NET Framework에 가장 적합 한 경로를 유지 하는 경우도 있습니다. 이 장에서는 .NET Core로 이동 하는 것이 적합 한 이유를 고려 합니다. 이 장에서는 .NET Framework을 유지 하기 위한 시나리오와 counterpoints도 고려 합니다.

## <a name="is-migration-to-net-core-appropriate"></a>.NET Core로의 마이그레이션이 적절 합니까?

.NET Core 또는 .NET 5로 이동 해야 하는 이유 중 몇 가지를 살펴보겠습니다. 매우 많은 사항이 있으므로이 목록을 철저 하 게 고려 하지 마십시오.

### <a name="cross-platform-support"></a>플랫폼 간 지원

.NET Core를 기반으로 하는 앱은 실제로 플랫폼 간 이며 Windows, Linux 및 macOS에서 실행할 수 있습니다. 개발자가 원하는 하드웨어를 사용할 수 있을 뿐만 아니라 어디에서 나 앱을 호스팅할 수도 있습니다. 예제는 로컬 IIS부터 클라우드의 Azure 또는 Linux Docker 컨테이너에서 IoT 장치로의 범위입니다.

### <a name="performance-and-scalability"></a>성능 및 확장성

.NET Core로 빌드된 앱은 어디에서 [나 사용할 수 있는 가장 빠른 기술 스택 중 하나](https://www.techempower.com/benchmarks/#hw=ph&test=plaintext)에서 실행 됩니다. ASP.NET MVC 앱은 특히 .NET Core에서 사용할 수 있는 몇 가지 새로운 기능을 활용 하도록 업데이트 되는 경우 ASP.NET Core의 성능 향상을 표시 합니다.

### <a name="cloud-native"></a>클라우드 네이티브

위의 이유와 기타 이유로 .NET Core 앱은 클라우드 호스팅 환경에서 실행 하기에 적합 합니다. 간단한 시스템 수요를 충족 하기 위해 필요에 따라 간단 하 고 빠른 .NET Core 앱을 Azure 앱 서비스 또는 컨테이너에 배포 하 고 수평으로 확장할 수 있습니다.

### <a name="maintainable"></a>가능한

많은 앱에서 고객 및 비즈니스 요구를 충족 하는 동안 계속 해 서 고객 및 비즈니스 요구를 충족 하는 동안 기술 부채를 누적 하 고 유지 관리 하는 데 많은 비용이 듭니다. ASP.NET Core 앱은 ASP.NET MVC 앱 보다 쉽게 테스트할 수 있으므로 쉽게 리팩터링 하 고 쉽게 확장할 수 있습니다.

### <a name="modular"></a>모듈식

ASP.NET Core는 클래스 프레임 워크의 최고 수준의 일부로 NuGet 패키지를 사용 하는 모듈식입니다. .NET Core 용으로 빌드된 앱은 모두 종속성 주입을 지원 하 여 지정 된 환경에 필요한 모든 구현에서 솔루션을 쉽게 작성할 수 있도록 합니다. .NET Core를 사용 하 여 마이크로 서비스를 구축 하는 작업은 IIS에 대 한 종속성이 있는 ASP.NET MVC를 사용 하는 것 보다 더 간단 합니다. 그러면 작은 앱을 작은 모듈로 분할 하는 추가 옵션이

### <a name="modern"></a>최신

적극적으로 개발 된 최신 기술 스택에는 장점 호스트가 있습니다. 새 기능 및 c # 언어 기능은 .NET Core에만 추가 됩니다. .NET Framework 버전 4.8의 마지막 릴리스를 사용 하 고 8 개 이상의 c # 버전이 .NET Framework 대상으로 하지 않습니다. ASP.NET MVC는 Microsoft에서 여러 해 동안 지원 되는 상태로 유지 되지만, 최고의 .net 소프트웨어 개발자는 제공 하는 모든 이점 (위에 요약 되어 있는 일부)으로 최신 .NET Core 프레임 워크를 사용 하는 것을 볼 수 있습니다. ASP.NET MVC 앱을 유지 관리 하는 기술을 가진 개발자를 찾는 것은 온라인 교육 및 문제 해결에 도움이 되는 특정 시점에 문제가 되기 시작 합니다. 예를 들어, .NET 5.0에 대 한 많은 정보를 작성 하는 반면, ASP.NET MVC 5에 대 한 새로운 블로그 게시물을 작성 하는 것이 아닙니다.

.NET Core로 마이그레이션하는 것을 고려해 야 하는 많은 이유가 있습니다 .이는이 책을 읽는 이유입니다. 하지만 .NET Framework에 유지 하는 것이 더 적합할 수 있는 몇 가지 단점 및 이유를 살펴보겠습니다.

## <a name="when-is-net-framework-appropriate"></a>.NET Framework 적절 한 경우

.NET Framework을 유지 하는 가장 큰 이유는 앱이 활성 개발 중이 아니며 위에 나열 된 이점에 비해 크게 향상 되지 않는 경우입니다. 이 경우 앱을 이식 하는 비용을 초래 하는 좋은 비즈니스 사례가 없을 수 있습니다. 앱이 .NET Core 혜택 혜택을 활용할 수 있는 경우 .NET Core에서 사용할 수 없는 특정 기술이 필요한 경우에도 .NET Framework을 유지 해야 할 수 있습니다. Appdomain, Remoting, CAS (코드 액세스 보안), 보안 투명성 및를 포함 하 여 [.Net Core에서 사용할 수](../../core/porting/net-framework-tech-unavailable.md)없는 몇 가지 .net 기술이 있습니다 `System.EnterpriseServices` . 이러한 기술에 대 한 간략 한 요약 및 해당 대안이 여기에 포함 되어 있습니다. 자세한 지침은 설명서를 참조 하세요.

### <a name="application-domains"></a>애플리케이션 도메인

애플리케이션 도메인(AppDomains)은 앱을 서로 분리합니다. Appdomain에는 런타임 지원이 필요 하 고 비용이 많이 들 수 있습니다. 추가 앱 도메인을 만드는 것은 지원 되지 않으며 나중에 .NET Core에이 기능을 추가할 계획이 없습니다. 코드 격리의 경우 별도의 프로세스 또는 컨테이너를 대신 사용하세요.

### <a name="wcf"></a>WCF

서버 쪽 WCF는 .NET Core에서 지원 되지 않습니다. .NET Core는 wcf 클라이언트는 지원 하지만 WCF 호스트는 지원 하지 않습니다. 이 기능을 필요로 하는 앱은 마이그레이션의 일부로 다른 통신 기술 (예: gRPC 또는 REST)로 업그레이드 해야 합니다.

[.Net Foundation에서 사용할 수 있는 WCF 클라이언트 포트가](../../core/dotnet-five.md#windows-communication-foundation)있습니다. 완전히 오픈 소스, 플랫폼 간 및 Microsoft에서 지원 됩니다. Microsoft에서 공식적으로 지원 *하지* 않는 커뮤니티 지원 [CoreWCF 프로젝트](https://github.com/CoreWCF/CoreWCF) 도 있습니다.

### <a name="remoting"></a>원격 통신

.NET Remoting은 문제가 있는 아키텍처로 확인되었으며 더 이상 지원되지 않는 AppDomain 간 통신에 사용됩니다. 또한 원격 통신에는 유지 관리 비용이 많이 드는 런타임 지원이 필요합니다. 이러한 이유로 .net Remoting은 .NET Core에서 지원 되지 않으며 제품 팀은 향후 지원 추가에 대해 계획 하지 않습니다. .NET Core 앱에서 원격 기능을 대체 하는 데 사용할 수 있는 몇 가지 대체 메시징 전략 및 구현이 있습니다.

### <a name="code-access-security-cas-and-security-transparency"></a>CAS (코드 액세스 보안) 및 보안 투명성

이러한 기술은 .NET Core에서 지원 되지 않습니다. 대신, 운영 체제에서 제공 하는 보안 경계를 사용 하는 것이 좋습니다. 예를 들어 가상화, 컨테이너 또는 사용자 계정이 있습니다. 필요한 최소한의 권한 집합으로 프로세스를 실행 합니다.

## <a name="references"></a>참조

[.NET Core에서 사용할 수 없는 .NET Framework 기술](../../core/porting/net-framework-tech-unavailable.md)

>[!div class="step-by-step"]
>[이전](introduction.md)
>[다음](migrate-aspnet-core-2-1.md)
