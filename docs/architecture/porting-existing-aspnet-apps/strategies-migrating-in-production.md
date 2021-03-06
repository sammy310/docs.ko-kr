---
title: 프로덕션 환경에서 실행하는 동안 마이그레이션하기 위한 전략
description: ASP.NET MVC에서 한 번에 ASP.NET Core 큼 앱을 마이그레이션하는 데 사용할 수 없습니다. 앱을 기존 사용자를 위해 실행 하는 동시에 ASP.NET Core으로 마이그레이션하기 위한 몇 가지 전략에 대해 알아봅니다.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 4910984cb281139493aa5424809ba3eedab776e9
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401693"
---
# <a name="strategies-for-migrating-while-running-in-production"></a>프로덕션 환경에서 실행하는 동안 마이그레이션하기 위한 전략

많은 팀은 .NET Core로 마이그레이션할 계획인 앱을 .NET Framework 하지만, 마이그레이션을 완료 하는 데 상당한 시간이 소요 되는 앱이 너무 큽니다. 원래 앱은 마이그레이션을 수행 하는 동안 실시간으로 수행 되어야 합니다. 이전 버전 및 새 버전의 앱이 함께 작동 하는 방법이 필요 하거나, 이전 버전을 업그레이드 하는 것이 중요 하지 않은 상태에서 최신 버전으로 마이그레이션 하는 방법이 있어야 합니다. 팀은 다양 한 전략을 사용 하 여 이러한 목표를 지원할 수 있습니다.

## <a name="refactor-the-net-framework-solution"></a>.NET Framework 솔루션 리팩터링

.NET Framework 앱을 .NET Core로 이식 하려는 경우 .NET Core를 사용 하 여 더 잘 작동 하도록 리팩터링 하는 것이 좋습니다. 즉, .NET Standard 대상으로 하는 개별 클래스 라이브러리를 업데이트 하 고 ASP.NET MVC 프로젝트와 이러한 클래스 라이브러리로 많은 논리를 이동 합니다. .NET Standard 라이브러리에 있는 코드는 .NET Framework에서 .NET Core로 비교적 쉽게 이동 해야 합니다.

리팩터링을 수행 하는 경우에는 적절 한 리팩터링 기본 사항을 사용 해야 합니다. 예를 들어, 리팩터링을 시작 하기 전에 시스템이 수행 하는 작업을 확인 하는 테스트를 만듭니다. 시스템의 동작을 변경 하지 않았는지 확인 하는 작업이 완료 되 면 이러한 테스트를 실행 합니다. 사용할 수 있는 자동화 된 테스트 집합이 아직 없는 경우 시스템에 특성화 테스트를 추가 해야 할 수 있습니다.

## <a name="extract-front-end-assets-to-a-cdn"></a>CDN에 대 한 프런트 엔드 자산 추출

.NET Framework 앱에 스크립트, CSS 파일 또는 이미지와 같은 많은 정적 자산이 포함 된 경우이를 별도의 CDN으로 마이그레이션할 수 있습니다. 그런 다음, 기존 앱을 업데이트 하 여 이러한 자산에 대 한 CDN 링크를 참조 합니다. 앱을 .NET Core로 이식할 때 이러한 정적 파일은 마이그레이션의 일부가 아니며 ASP.NET Core 앱의 CDN에서 계속 참조 합니다.

## <a name="extract-and-migrate-individual-microservices"></a>개별 마이크로 서비스 추출 및 마이그레이션

대량 .NET Framework 앱은 개별적으로 마이그레이션할 수 있는 별도의 프런트 엔드 시스템으로 구성 되어 있을 수 있습니다. 또는 기존 ASP.NET MVC 앱의 일부를 새로운 ASP.NET Core 마이크로 서비스 구현으로 가져오는 마이크로 서비스 아키텍처로 마이그레이션하기 위한 후보가 될 수 있습니다. 관련 전자책 [.Net 마이크로 서비스: 컨테이너 화 된 .Net 응용 프로그램용 아키텍처](https://aka.ms/microservicesebook)에서 마이크로 서비스에 대해 자세히 알아볼 수 있습니다.

예를 들어 기존 앱은 사용자 로그인 및 등록과 관련 하 여 사용 하는 기능 집합을 포함할 수 있습니다. 이러한 마이크로 서비스를 사용 ASP.NET Core 하 여 빌드 및 배포 하 고 레거시 .NET Framework 앱에 통합할 수 있는 별도의로 마이그레이션할 수 있습니다. 그런 다음 앱에 개별 사용자의 쇼핑 카트를 추적 하는 데 사용 되는 몇 개의 페이지가 있을 수 있습니다. 이러한 페이지를 고유한 별도의 마이크로 서비스로 끌어 기존 앱에 다시 통합할 수도 있습니다. 이러한 방식으로 원래 .NET Framework 앱은 프로덕션 환경에서 계속 실행 되지만 현대화 .NET Core 마이크로 서비스에서 제공 되는 기능을 더 많이 사용 합니다.

## <a name="deploy-multiple-versions-of-the-app-side-by-side-in-iis"></a>IIS에서 여러 버전의 앱을 함께 배포

호스트 헤더와 리디렉션의 조합을 사용 하 여 기존 ASP.NET MVC 앱을 동일한 IIS 서버의 ASP.NET Core 앱과 나란히 실행 하도록 구성할 수 있습니다. 개별 컨트롤러와 같은 기능을 ASP.NET Core으로 이식 하 여 ASP.NET Core 웹 사이트 또는 하위 응용 프로그램을 대상으로 하는 IIS 내에서 해당 경로 및 Url을 매핑합니다 (IIS 가상 디렉터리는 ASP.NET Core 앱에서 지원 되지 않음). ASP.NET Core 앱은 IIS 하위 애플리케이션(하위 앱)으로 호스팅될 수 있습니다. 하위 앱의 경로는 루트 앱 URL의 일부가 됩니다.

## <a name="apply-the-strangler-pattern"></a>스트랭글러 패턴 적용

큰 ASP.NET MVC 앱은 기능을 증분 방식으로 마이그레이션하여 새로운 ASP.NET Core 앱으로 점진적으로 바꿀 수 있습니다. 이에 대 한 한 가지 방법을 [스트랭글러 패턴](/azure/architecture/patterns/strangler)이라고 하며,이 패턴은 strangle이 고 궁극적으로 트리를 분리 하는 스트랭글러 vines에 대해 이름이 지정 되었습니다. 이 방법은 먼저 기존 솔루션의 위에 외관 계층을 구현 하는 것에 의존 합니다. 이 외관은 문제에 대 한 새로운 접근 방식 또는 API 게이트웨이와 같은 기본 솔루션을 사용 하 여 구축 해야 합니다.

외관이 준비 되 면 그 일부를 새 ASP.NET Core 앱으로 라우팅할 수 있습니다. 원래 .NET Framework 앱을 .NET Core로 이식할 때 계속 외관 계층을 업데이트 하 여 새 시스템에 façade's 전체 기능을 더 많이 보냅니다. 그림 3-5에서는 시간에 따른 스트랭글러 패턴의 진행을 보여 줍니다.

## <a name="multi-targeting-approaches"></a>다중 대상 지정 방법

.NET Framework를 대상으로 하는 규모가 많은 앱은 각 프레임 워크에 대해 다중 대상 지정 및 별도의 코드 경로를 사용 하 여 시간에 따라 ASP.NET Core 마이그레이션할 수 있습니다. 예를 들어 두 환경에서 실행 해야 하는 코드는 다른 기능을 구현 하거나 .NET Framework .NET Core에서 실행 하는 경우 다른 종속성을 사용 하도록 [전처리기 `#if` ](../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) 지시문을 사용 하 여 수정할 수 있습니다. 또 다른 옵션은 대상으로 지정 되는 프레임 워크에 따라 서로 다른 파일 집합을 포함 하도록 프로젝트 파일을 수정 하는 것입니다. 프로젝트 파일은와 같은 서로 다른 와일드 카드 사용 패턴을 사용 하 여 대상으로 지정 `*.core.cs` 되는 프레임 워크에 따라 서로 다른 소스 파일 집합을 포함할 수 있습니다.

이러한 기술을 통해 단일 공통 코드 베이스를 유지 관리할 수 있으며, 새로운 기능이 추가 되 고 (의 일부) 앱이 .NET Core를 사용 하도록 포팅 됩니다.

![그림 3-5](media/Figure3-5.png)

**그림 3-5.** 시간에 따른 스트랭글러 패턴입니다.

결국 전체 외관 계층은 최신의 새 구현에 해당 합니다. 이 시점에서는 레거시 시스템과 얼굴 계층이 모두 사용 중지 될 수 있습니다.

## <a name="summary"></a>요약

ASP.NET MVC 및 Web API apps는 동시에 한 번에 ASP.NET Core 이식할 수 없으며 시간이 지남에 따라 점진적으로 마이그레이션됩니다. 이 섹션에서는이 증분 마이그레이션을 수행 하기 위한 몇 가지 전략을 제공 합니다. 조직 및 앱에 가장 적합 한 것을 선택 합니다.

## <a name="references"></a>참조

- [.NET 마이크로 서비스: 컨테이너 화 된 .NET 응용 프로그램에 대 한 아키텍처](https://aka.ms/microservicesebook)
- [eShopOnContainers Reference 마이크로 서비스 응용 프로그램](https://github.com/dotnet-architecture/eShopOnContainers)
- [IIS가 있는 Windows에서 ASP.NET Core 호스팅](/aspnet/core/host-and-deploy/iis/)
- [스트랭글러 패턴](/azure/architecture/patterns/strangler)

>[!div class="step-by-step"]
>[이전](understand-update-dependencies.md)
>[다음](example-migration-eshop.md)
