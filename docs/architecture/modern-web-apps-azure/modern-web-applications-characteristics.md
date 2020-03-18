---
title: 최신 웹 애플리케이션의 특징
description: ASP.NET Core 및 Azure를 사용하여 최신 웹 애플리케이션 설계 | 최신 웹 애플리케이션의 특징
author: ardalis
ms.author: wiwagn
ms.date: 12/04/2019
ms.openlocfilehash: d70fa54adeb505fd37807399402281dfda67cf52
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "77451566"
---
# <a name="characteristics-of-modern-web-applications"></a>최신 웹 애플리케이션의 특징

> "… 적절한 설계를 사용하면 기능을 저렴하게 구현할 수 있습니다. 이 접근 방법은 힘들지만 계속 성공하고 있습니다."  
> _\- Dennis Ritchie_

최신 웹 애플리케이션은 사용자의 기대치와 요구 사항이 이전보다 더 높습니다. 오늘날의 웹앱은 전 세계 어느 곳에서나 연중무휴 24시간 이용할 수 있으며, 디바이스 또는 화면 크기에 거의 상관없이 사용할 수 있습니다. 웹 애플리케이션은 안전하고 유연하며 수요 급증에 맞추어 확장 가능해야 합니다. 점점 더 복잡해지는 시나리오는 JavaScript를 사용하며 웹 API를 통해 효율적으로 통신하는 클라이언트에 빌드된 풍부한 사용자 경험으로 처리되어야 합니다.

ASP.NET Core는 최신 웹 애플리케이션 및 클라우드 기반 호스팅 시나리오에 대해 최적화되어 있습니다. 모듈형 설계는 애플리케이션이 실제 사용하는 기능에만 의존하도록 하여 애플리케이션 보안 및 성능을 향상시키면서 호스팅 리소스 요구사항을 줄입니다.

## <a name="reference-application-eshoponweb"></a>참조 애플리케이션: eShopOnWeb

이 지침에는 몇 가지 원칙과 권장 사항을 설명하는 참조 애플리케이션인 _eShopOnWeb_이 포함되어 있습니다. 이 애플리케이션은 셔츠, 커피 머그잔 및 기타 마케팅 항목의 카탈로그 검색을 지원하는 간단한 온라인 상점입니다. 이 참조 애플리케이션은 이해를 돕기 위한 의도로 간단하게 제작되었습니다.

![eShopOnWeb](./media/image2-1.png)

**그림 2-1.** eShopOnWeb

> ### <a name="reference-application"></a>참조 애플리케이션
>
> - **eShopOnWeb**  
>   <https://github.com/dotnet/eShopOnWeb>

## <a name="cloud-hosted-and-scalable"></a>클라우드 호스팅 및 확장 가능

ASP.NET Core는 메모리가 적고 처리량이 높기 때문에 클라우드(퍼블릭 클라우드, 프라이빗 클라우드, 모든 클라우드)에 최적화되어 있습니다. ASP.NET Core 애플리케이션은 사용 공간을 더 적게 차지하므로 동일한 하드웨어에서 더 많이 호스팅할 수 있으며, 선불 클라우드 호스팅 서비스 요금을 사용할 경우 더 적은 리소스 요금을 지불합니다. 또한 처리량이 더 높으므로 하드웨어가 동일할 경우 특정 애플리케이션에서 더 많은 고객에게 서비스를 제공할 수 있으며, 서버와 호스팅 인프라에 투자할 필요성을 줄여줍니다.

## <a name="cross-platform"></a>플랫폼 간

ASP.NET Core는 플랫폼 간 구현이며 Linux, macOS 및 Windows에서 실행할 수 있습니다. 이는 ASP.NET Core로 빌드된 앱의 개발 및 배포를 위한 많은 새 옵션을 제공합니다. Docker 컨테이너(Linux 및 Windows 모두)는 ASP.NET Core 애플리케이션을 호스팅하여 [컨테이너 및 마이크로 서비스](../microservices/index.md)의 이점을 활용할 수 있습니다.

## <a name="modular-and-loosely-coupled"></a>모듈형 및 느슨하게 결합

NuGet 패키지는 .NET Core에서 완벽하게 통합되며, ASP.NET Core 앱은 NuGet을 통해 많은 라이브러리로 구성됩니다. 이러한 기능의 세분성은 앱이 실제 필요한 기능만 의존하고 배포하도록 보장하여 사용 공간 및 보안 취약성 노출 영역을 줄여줍니다.

또한 ASP.NET Core는 내부 및 애플리케이션 수준 모두에서 [종속성 주입](https://deviq.com/dependency-injection/)을 완전히 지원합니다. 인터페이스는 다양하게 구현될 수 있으며, 필요에 따라 바꿀 수 있습니다. 종속성 주입을 사용하면 앱이 특정 구현이 아닌 해당하는 인터페이스에 느슨하게 결합되도록 하여 더 용이하게 확장하고, 유지 관리하고, 테스트할 수 있습니다.

## <a name="easily-tested-with-automated-tests"></a>자동화된 테스트를 사용하여 쉽게 테스트

ASP.NET Core 애플리케이션은 단위 테스트를 지원하며, 느슨한 결합 및 종속성 주입 지원을 통해 테스트 목적으로 모조 구현과 인프라 문제를 쉽게 교체할 수 있게 해줍니다. ASP.NET Core에는 메모리에서 앱을 호스트하는 데 사용할 수 있는 TestServer도 함께 제공됩니다. 기능 테스트는 이 메모리 내 서버에 대한 요청을 수행하여 전체 애플리케이션 스택(미들웨어, 라우팅, 모델 바인딩, 필터 등 포함)을 실행하고 응답을 수신하는데, 실제 서버에서 앱을 호스팅하고 네트워크 계층을 통해 요청하는 데 걸리는 시간을 몇 분의 일로 단축합니다. 이러한 테스트는 특히 최신 웹 애플리케이션에서 점차 중요해지는 API의 경우 쓰기 쉽고 유용합니다.

## <a name="traditional-and-spa-behaviors-supported"></a>기존 및 SPA 동작 지원

기존 웹 애플리케이션은 클라이언트 쪽 동작을 거의 포함하지 않았지만, 대신 앱이 필요로 하는 모든 탐색, 쿼리 및 업데이트를 서버에 의존합니다. 사용자가 수행한 각각의 새 작업은 웹 요청으로 변환되어 최종 사용자의 브라우저에서 전체 페이지가 다시 로드됩니다. MVC(Classic Model-View-Controller) 프레임워크는 일반적으로 이 방법을 따르며, 각각의 새 요청은 다른 컨트롤러 작업에 해당하며 모델과 함께 작동하고 뷰를 반환합니다. 지정된 페이지의 일부 개별 작업은 AJAX(Asynchronous JavaScript and XML) 기능으로 향상될 수 있지만 앱의 전체 아키텍처는 다양한 MVC 뷰와 URL 엔드포인트를 사용합니다. 또한 ASP.NET Core MVC는 MVC 스타일 페이지를 구성하는 간단한 방법인 Razor Pages를 지원합니다.

반대로, SPA(Single Page Applications)에는 동적으로 생성된 서버 쪽 페이지 로드(있는 경우)가 거의 없습니다. 앱을 시작하고 실행하는 데 필요한 JavaScript 라이브러리를 로드하는 정적 HTML 파일 내에서 많은 SPA가 초기화됩니다. 이러한 앱은 데이터 요구 사항에 따라 웹 API를 많이 사용하며 훨씬 풍부한 사용자 환경을 제공할 수 있습니다.

많은 웹 애플리케이션에는 기존 웹 애플리케이션 동작(일반적으로 콘텐츠용)과 SPA(대화형 작업용)가 결합되어 있습니다. ASP.NET Core는 동일한 도구 집합 및 기본 프레임워크 라이브러리를 사용하여 동일한 애플리케이션에서 MVC(보기 또는 페이지 기반) 및 웹 API를 모두 지원합니다.

## <a name="simple-development-and-deployment"></a>간단한 개발 및 배포

ASP.NET Core 애플리케이션은 간단한 텍스트 편집기 및 명령줄 인터페이스 또는 Visual Studio와 같은 모든 기능을 갖춘 개발 환경을 사용하여 작성할 수 있습니다. 모놀리식 애플리케이션은 일반적으로 단일 엔드포인트에 배포됩니다. 배포는 CI(연속 통합) 및 CD(지속적인 업데이트) 파이프라인의 일부로 쉽게 자동화될 수 있습니다. Microsoft Azure는 기존 CI/CD 도구 외에도 통합 git 리포지토리에 대한 지원을 통합했으며, 지정된 git 분기 또는 태그에 자동으로 업데이트를 배포할 수 있습니다. Azure DevOps는 모든 기능을 갖춘 CI/CD 빌드 및 배포 파이프라인을 제공하고 GitHub Actions는 그곳에서 호스트되는 프로젝트에 대해 또 다른 옵션을 제공합니다.

## <a name="traditional-aspnet-and-web-forms"></a>기존 ASP.NET 및 Web Forms

ASP.NET Core 외에도, 기존 ASP.NET 4.x는 웹 애플리케이션을 빌드하기 위한 견고하고 안정적인 플랫폼으로 계속 유지됩니다. ASP.NET은 풍부한 페이지 기반 애플리케이션 개발에 적합하고 풍부한 타사 구성 요소 에코시스템을 지원하는 Web Forms뿐만 아니라 MVC 및 웹 API 개발 모델도 지원합니다. Microsoft Azure는 ASP.NET 4.x 애플리케이션을 매우 오랫동안 지원해 왔으며 많은 개발자가 이 플랫폼에 익숙합니다.

## <a name="blazor"></a>Blazor

Blazor는 ASP.NET Core 3.0 이상에 포함되어 있습니다. Razor, C# 및 ASP.NET Core를 사용하여 풍부한 대화형 웹 클라이언트 애플리케이션을 빌드하기 위한 새로운 메커니즘을 제공합니다. 최신 웹 애플리케이션을 개발할 때 고려할 다른 솔루션을 제공합니다. 고려할 두 가지 버전의 Blazor는 서버 쪽과 클라이언트 쪽입니다.

서버 쪽 Blazor는 2019년 ASP.NET Core 3.0으로 출시되었습니다. 이름에서 알 수 있듯이 이는 서버에서 실행되고 클라이언트 문서 변경 내용을 네트워크를 통해 브라우저에 다시 렌더링합니다. 서버 쪽 Blazor는 클라이언트 쪽 JavaScript를 요구하거나 각 클라이언트 페이지 상호 작용에 대해 별도의 페이지 로드를 요구하지 않고 풍부한 클라이언트 환경을 제공합니다. 로드된 페이지의 변경 내용은 서버에서 요청되고 처리된 후 SignalR을 사용하여 다시 클라이언트로 전송됩니다.

클라이언트 쪽 Blazor는 2020년에 출시되며 서버에서 변경 사항을 렌더링할 필요가 없습니다. 대신, 클라이언트에서 .NET 코드를 실행하는 데 WebAssembly를 활용합니다. 클라이언트는 데이터를 요청하는 데 필요한 경우 서버에 대한 API 호출을 수행할 수 있지만 모든 클라이언트 쪽 동작은 이미 모든 주요 브라우저에서 지원되고 단지 Javascript 라이브러리인 WebAssembly를 통해 클라이언트에서 실행됩니다.

> ### <a name="references--modern-web-applications"></a>참조 - 최신 웹 애플리케이션
>
> - **ASP.NET Core 소개**  
>   <https://docs.microsoft.com/aspnet/core/>
> - **ASP.NET Core에서 테스트**  
>   <https://docs.microsoft.com/aspnet/core/testing/>
> - **Blazor - 시작하기**  
>   <https://blazor.net/docs/get-started.html>

>[!div class="step-by-step"]
>[이전](index.md)
>[다음](choose-between-traditional-web-and-single-page-apps.md)
