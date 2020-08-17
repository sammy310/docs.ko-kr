---
title: BlazorASP.NET Web Forms 개발자를 위한 소개
description: Blazor.Net을 사용한 전체 스택 웹 앱 소개 및 작성
author: danroth27
ms.author: daroth
no-loc:
- Blazor
- WebAssembly
ms.date: 09/11/2019
ms.openlocfilehash: a5aae6cf02ccec84ac8642b6ce8d9c919755e868
ms.sourcegitcommit: 0100be20fcf23f61dab672deced70059ed71bb2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88267570"
---
# <a name="an-introduction-to-no-locblazor-for-aspnet-web-forms-developers"></a>BlazorASP.NET Web Forms 개발자를 위한 소개

ASP.NET Web Forms 프레임 워크는 .NET Framework 먼저 2002로 제공 되므로 .NET 웹 개발의 스테이플링을 받았습니다. 웹이 아직 infancy 된 경우에도 ASP.NET Web Forms 데스크톱 개발에 사용 된 많은 패턴을 도입 하 여 웹 앱을 간단 하 고 생산적으로 빌드 했습니다. ASP.NET Web Forms에서는 다시 사용할 수 있는 UI 컨트롤에서 웹 페이지를 신속 하 게 구성할 수 있습니다. 사용자 상호 작용은 자연스럽 게 이벤트로 처리 됩니다. Microsoft 및 제어 공급 업체에서 제공 하는 Web Forms UI 컨트롤의 다양 한 에코 시스템을 제공 합니다. 컨트롤을 통해 데이터 원본에 연결 하 고 다양 한 데이터 시각화를 표시할 수 있습니다. 시각적으로 쉬운데 Web Forms 디자이너는 컨트롤을 관리 하기 위한 간단한 끌어서 놓기 인터페이스를 제공 합니다.

몇 년 동안 Microsoft는 웹 개발 추세를 해결 하기 위한 새로운 ASP.NET 기반 웹 프레임 워크를 도입 했습니다. 이러한 웹 프레임 워크에는 ASP.NET MVC, ASP.NET 웹 페이지 및 최근 ASP.NET Core 포함 됩니다. 각각의 새로운 프레임 워크를 사용 하 여 ASP.NET Web Forms에 대 한 곧 거부를 예측 하 고 오래 된 outmoded 웹 프레임 워크로 criticized 했습니다. 이러한 예측에도 불구 하 고, 많은 .NET 웹 개발자가 작업을 완료 하는 간단 하 고 안정적이 고 생산적인 방법으로 ASP.NET Web Forms를 계속 찾을 수 있습니다.

이 문서를 작성할 당시에는 수백만 명의 웹 개발자가 매월 ASP.NET Web Forms를 사용 합니다. ASP.NET Web Forms 프레임 워크는 문서, 샘플, 책 및 블로그 게시물이 10 년 전에 유용 하 고 관련성을 유지 하는 시점까지 안정적입니다. 대부분의 .NET 웹 개발자를 위해 "ASP.NET"는 .NET이 처음 구상한 목적이 때와 마찬가지로 "ASP.NET Web Forms"와 같은 동의어를 가집니다. Web Forms ASP.NET의 장점 및 단점에 대 한 인수는 다른 새로운 .NET 웹 프레임 워크와 비교 하 여 r 수 있습니다. ASP.NET Web Forms는 웹 앱을 만드는 데 널리 사용 되는 프레임 워크를 유지 합니다.

이러한 경우에도 소프트웨어 개발의 혁신은 저하 되지 않습니다. 모든 소프트웨어 개발자는 새로운 기술과 경향을 모음은 해야 합니다. 특히 다음 두 가지 추세를 고려 하는 것이 좋습니다.

1. 오픈 소스 및 플랫폼 간 전환
2. 응용 프로그램 논리를 클라이언트로 이동

## <a name="an-open-source-and-cross-platform-net"></a>오픈 소스 및 플랫폼 간 .NET

.NET 및 ASP.NET Web Forms 처음 제공 되는 경우 플랫폼 에코 시스템은 현재와 크게 다른 것으로 보았습니다. 데스크톱과 서버 시장에는 Windows가 있습니다. MacOS 및 Linux와 같은 대체 플랫폼은 여전히 traction을 얻기 위해 노력 하 고 있습니다. ASP.NET Web Forms는 windows 전용 구성 요소로 .NET Framework와 함께 제공 됩니다. 즉, Web Forms ASP.NET 앱은 Windows Server 컴퓨터 에서만 실행할 수 있습니다. 이제 대부분의 최신 환경에서 서버 및 개발 컴퓨터에 대해 다양 한 종류의 플랫폼을 사용 하 여 많은 사용자에 대 한 플랫폼 간 지원이 절대 요구 사항입니다.

최신 웹 프레임 워크는 이제 많은 이점을 제공 하는 오픈 소스 이기도 합니다. 사용자는 버그를 수정 하 고 기능을 추가 하기 위해 단일 프로젝트 소유자에 게 제공 되지 않습니다. 오픈 소스 프로젝트는 개발 진행률과 예정 된 변경 내용에 대해 향상 된 투명도를 제공 합니다. 오픈 소스 프로젝트는 전체 커뮤니티의 기여를 즐기고 협력적인 오픈 소스 에코 시스템을 촉진 합니다. 오픈 소스 위험에도 불구 하 고, 많은 소비자와 참가자가 안전 하 고 합리적인 방식으로 오픈 소스 에코 시스템의 이점을 누릴 수 있는 적절 한 완화 방법을 찾았습니다. 이러한 완화의 예로는 참가자 사용권 계약, 친숙 한 라이선스, 계통 검색, 지원 토대 등이 있습니다.

.NET 커뮤니티는 플랫폼 간 지원과 오픈 소스를 모두 받아들이고 했습니다. .NET Core는 Windows, macOS 및 다양 한 Linux 배포를 비롯 하 여 다양 한 플랫폼에서 실행 되는 .NET의 오픈 소스 및 플랫폼 간 구현입니다. Xamarin은 .NET의 오픈 소스 버전인 Mono를 제공 합니다. Mono는 Android, iOS 및 감시 및 스마트 Tv를 비롯 한 다양 한 다른 폼 팩터를 실행 합니다. Microsoft는 [.net 5](https://devblogs.microsoft.com/dotnet/introducing-net-5/) 가 .net Core 및 Mono를 "모든 곳에서 사용 하 고 일관 된 런타임 동작 및 개발자 환경을 사용 하는 단일 .net 런타임 및 프레임 워크"로 조정 한다는 것을 발표 했습니다.

는 오픈 소스 및 플랫폼 간 지원으로 이동 하 여 Web Forms 혜택을 ASP.NET? 불행 하 게 대답 한 것은 아닙니다. 또는 적어도 나머지 플랫폼과 동일한 익스텐트가 아닙니다. .NET 팀은 [최근에](https://devblogs.microsoft.com/dotnet/net-core-is-the-future-of-net/) ASP.NET Web Forms .net Core 또는 .net 5로 이식할 수 없다는 것을 명확 하 게 만들었습니다. 왜 그럴까요?

ASP.NET Web Forms에 대 한 .NET Core의 초기 일에 노력 했습니다. 필요한 주요 변경 수를 너무 많이 찾았습니다. 여기서는 Microsoft의 경우에도 동시에 지원할 수 있는 웹 프레임 워크 수에 제한이 있습니다. 커뮤니티의 누군가가 ASP.NET Web Forms의 오픈 소스 및 플랫폼 간 버전을 만드는 이유를 발생 시킬 수 있습니다. [ASP.NET Web Forms에 대 한 소스 코드](https://github.com/microsoft/referencesource) 는 참조 형태로 공개적으로 사용할 수 있게 되었습니다. 그러나이 경우에는 ASP.NET이 Windows 전용으로 유지 되 고 오픈 소스 기여 모델 없이는 Web Forms 것 처럼 보입니다. 시나리오에 대 한 플랫폼 간 지원 또는 오픈 소스가 중요할 경우에는 새로운 항목을 확인 해야 합니다.

이는 ASP.NET Web Forms 고 더 이상 사용 되지 않는 *것을 의미* 하나요? 물론 아니에요! .NET Framework Windows의 일부로 제공 되는 한 ASP.NET Web Forms은 지원 되는 프레임 워크입니다. 많은 Web Forms 개발자를 위한 플랫폼 간 및 오픈 소스 지원 부족은 문제가 되지 않습니다. 플랫폼 간 지원, 오픈 소스 또는 .NET Core 또는 .NET 5의 다른 새로운 기능에 대 한 요구 사항이 없는 경우 Windows에서 ASP.NET Web Forms를 사용 하는 것이 좋습니다. ASP.NET Web Forms는 수많은 웹 앱을 작성할 수 있는 생산적인 방법으로 계속 제공 됩니다.

그러나 다른 추세를 고려 하 고 있으며이는 클라이언트에 대 한 이동입니다.

## <a name="client-side-web-development"></a>클라이언트 쪽 웹 개발

모든입니다. ASP.NET Web Forms를 비롯 한 네트워크 기반 웹 프레임 워크는 일반적으로 *서버에서 렌더링*됩니다. 서버에서 렌더링 된 웹 앱에서 브라우저는 서버에 대 한 요청을 수행 하 여 응답을 생성 하는 일부 코드 (ASP.NET apps의 .NET 코드)를 실행 합니다. 이 응답은 처리를 위해 브라우저에 다시 전송 됩니다. 이 모델에서는 브라우저가 씬 렌더링 엔진으로 사용 됩니다. UI를 생성 하 고 비즈니스 논리를 실행 하며 상태를 관리 하는 작업은 서버에서 수행 됩니다.

그러나 브라우저는 다양 한 플랫폼으로 사용할 수 있습니다. 사용자 컴퓨터의 기능에 액세스 권한을 부여 하는 개방 된 웹 표준의 수를 지속적으로 구현 합니다. 클라이언트 장치의 계산 능력, 저장소, 메모리 및 기타 리소스를 활용 하지 않는 이유는 무엇 인가요? 특히 UI 상호 작용은 최소한 부분적으로 또는 완전히 클라이언트 쪽에서 처리 될 때 보다 풍부 하 고 대화형 느낌을 누릴 수 있습니다. 서버에서 처리 되어야 하는 논리와 데이터는 여전히 서버 쪽에서 처리 될 수 있습니다. 웹 API 호출 또는 Websocket과 같은 실시간 프로토콜도 사용할 수 있습니다. 이러한 혜택은 JavaScript를 작성 하려는 웹 개발자에 게 무료로 제공 됩니다. 클라이언트 쪽 UI 프레임 워크 (예: 각도, 반응 및 Vue)는 클라이언트 쪽 웹 개발을 간소화 하 고 널리 성장 하 고 있습니다. ASP.NET Web Forms 개발자는 클라이언트를 활용 하는 것도 도움이 될 수 있으며 ASP.NET AJAX와 같은 통합 JavaScript 프레임 워크를 사용 하 여 몇 가지 기본 지원을 제공 합니다.

하지만 서로 다른 두 플랫폼과 에코 시스템 (.NET 및 JavaScript)를 브리징 하는 것은 비용이 듭니다. 다른 언어, 프레임 워크 및 도구를 사용 하는 두 병렬 환경에서 전문 지식이 필요 합니다. 클라이언트와 서버 간에 코드 및 논리를 쉽게 공유할 수 없어 중복 및 엔지니어링 오버 헤드가 발생 합니다. 또한 변화 하는 속도에서 진화 하는 기록을 포함 하는 JavaScript 에코 시스템을 유지 하기 어려울 수 있습니다. 프런트 엔드 프레임 워크 및 빌드 도구 기본 설정은 빠르게 변경 됩니다. 업계에서는 Grunt에서 Gulp로의 진행을 관찰 했습니다. JQuery, 녹아웃, 각도, 반응, Vue 등의 프런트 엔드 프레임 워크에서 동일한 restless 변동 (code churn)이 발생 했습니다. 그러나 JavaScript의 browser monopoly 지정 된 경우에는 거의 선택 하지 않았습니다. 즉, 웹 커뮤니티를 함께 연결 하 여 *miracle* 발생 시킬 수 있습니다.

## <a name="no-locwebassembly-fulfills-a-need"></a>WebAssembly 요구를 충족 합니다.

2015에서 주요 브라우저 공급 업체는 W3C 커뮤니티 그룹을 강제로 실행 하 여 라는 새 개방형 웹 표준을 만듭니다 WebAssembly . WebAssembly 는 웹의 바이트 코드입니다. 코드를로 컴파일할 수 있는 경우에 WebAssembly 는 모든 플랫폼의 모든 브라우저에서 거의 기본 속도로 실행할 수 있습니다. C/c + +에 초점을 맞춘 초기 노력. 그 결과, 플러그 인을 사용 하지 않고 브라우저에서 직접 기본 3D 그래픽 엔진을 실행 하는 것이 크게 데모 였습니다. WebAssembly 는 모든 주요 브라우저에서 표준화 되 고 구현 되었습니다.

에서 .NET을 실행 하 WebAssembly 는 작업은 2017 년대 이후 발표 되었으며, .net 5의 지원을 포함 하 여 2020에서 제공 될 예정입니다. 브라우저에서 직접 .NET 코드를 실행 하는 기능을 통해 .NET을 통한 전체 스택 웹 개발을 수행할 수 있습니다.

## <a name="no-locblazor-full-stack-web-development-with-net"></a>Blazor: .NET을 사용 하 여 전체 스택 웹 개발

브라우저에서 .NET 코드를 실행 하는 기능은 클라이언트 쪽 웹 앱을 만들기 위한 종단 간 환경을 제공 하지 않습니다. 여기서가 Blazor 제공 됩니다. Blazor는 JavaScript 대신 C#을 기반으로 하는 클라이언트 쪽 웹 UI 프레임워크입니다. Blazor 는를 통해 브라우저에서 직접 실행할 수 있습니다 WebAssembly . 브라우저 플러그 인은 필요 하지 않습니다. 또는 Blazor 앱이 .Net Core에서 서버 쪽을 실행 하 고 브라우저를 사용 하 여 실시간 연결을 통해 모든 사용자 상호 작용을 처리할 수 있습니다.

Blazor 에는 Visual Studio 및 Visual Studio Code에서 뛰어난 도구가 지원 됩니다. 프레임 워크는 전체 UI 구성 요소 모델을 포함 하 고에 대 한 기본 제공 기능을 포함 합니다.

- 양식 및 유효성 검사
- 종속성 주입
- 클라이언트 쪽 라우팅
- 레이아웃
- 브라우저 내 디버깅
- JavaScript interop

Blazor ASP.NET Web Forms와 공통적으로 많이 사용 됩니다. 두 프레임 워크는 모두 구성 요소 기반의 이벤트 구동 상태 저장 UI 프로그래밍 모델을 제공 합니다. 주요 아키텍처 차이점은 ASP.NET Web Forms 서버 에서만 실행 된다는 것입니다. Blazor 브라우저에서 클라이언트를 실행할 수 있습니다. 그러나 ASP.NET Web Forms 백그라운드에서 제공 되는 경우에는 많은 부분이 있습니다 Blazor . Blazor 는 클라이언트 쪽 개발과 .NET의 오픈 소스 플랫폼 간 미래를 활용 하는 방법을 찾는 ASP.NET Web Forms 개발자를 위한 자연 스러운 솔루션입니다.

이 책에서는 Web Forms 개발자에 게 특히 ASP.NET에 대 한 소개를 제공 Blazor 합니다. 각 Blazor 개념은 유사한 ASP.NET Web Forms 기능 및 관행의 맥락에서 제공 됩니다. 이 설명서의 끝 부분에서는 다음을 이해 하 게 됩니다.

- 앱을 빌드하는 방법 Blazor
- 가 Blazor 작동 합니다.
- 는 Blazor .Net Core와 관련 됩니다.
- 기존 ASP.NET Web Forms 앱을 적절 한 위치로 마이그레이션하기 위한 적절 한 전략 Blazor

## <a name="get-started-with-no-locblazor"></a>Blazor 시작

시작 하기 Blazor 는 쉽습니다. 로 이동 하 여 <https://blazor.net> 링크를 따라 적절 한 .NET Core SDK 및 Blazor 프로젝트 템플릿을 설치 합니다. 또한 Blazor Visual Studio 또는 Visual Studio Code에서 도구를 설정 하는 방법에 대 한 지침을 찾을 수 있습니다.

>[!div class="step-by-step"]
>[이전](index.md)
>[다음](architecture-comparison.md)
