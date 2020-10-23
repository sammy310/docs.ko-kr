---
title: .NET 용어
description: .NET 설명서에서 사용되는 선택한 용어의 의미를 알아봅니다.
ms.date: 10/13/2020
ms.technology: dotnet-standard
ms.openlocfilehash: 1d9330b68f80da934777cb3aee6d2b3cb52c8256
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050346"
---
# <a name="net-glossary"></a>.NET 용어

이 용어집의 주 용도는 .NET 설명서에서 정의 없이 자주 나타나는 선택한 용어 및 머리글자어의 의미를 명확히 나타내는 것입니다.

## <a name="aot"></a>AOT

Ahead-Of-Time 컴파일러입니다.

[JIT](#jit)와 비슷하게 이 컴파일러도 [IL](#il)을 기계어 코드로 변환합니다. JIT 컴파일과는 달리 AOT 컴파일은 애플리케이션이 실행되기 전에 수행되며 일반적으로 다른 컴퓨터에서 수행됩니다. AOT 툴 체인은 런타임에 컴파일되지 않으므로 컴파일 시간을 최소화할 필요가 없습니다. 즉, 더 많은 시간을 최적화하는 데 사용할 수 있습니다. AOT의 컨텍스트는 전체 애플리케이션이므로 AOT 컴파일러는 모듈 간 연결 및 전체 프로그램 분석도 수행합니다. 즉, 모든 참조가 수행되고 단일 실행 파일이 생성된다는 의미입니다.

[CoreRT](#corert)와 [.NET 네이티브](#net-native)를 참조하세요.

## <a name="app-model"></a>앱 모델

[워크로드](#workload)별 API. 몇 가지 예제는 다음과 같습니다.

* ASP.NET
* ASP.NET Web API
* EF(Entity Framework)
* WPF(Windows Presentation Foundation)
* WCF(Windows Communication Foundation)
* Windows WF(Workflow Foundation)
* Windows Forms(WinForms)

## <a name="aspnet"></a>ASP.NET

.NET Framework와 함께 제공되는 원래 ASP.NET 구현체입니다.

경우에 따라 ASP.NET은 ASP.NET Core를 포함한 두가지 ASP.NET 구현체를 나타내는 포괄적인 용어입니다. 지정된 인스턴스에서 이 용어가 전달하는 의미는 컨텍스트에 의해 결정됩니다. ASP.NET을 사용하여 두 구현체를 모두 의미하는 것이 아님을 분명히 하려는 경우 ASP.NET 4.x를 참조하세요.

[ASP.NET 설명서](/aspnet/#pivot=aspnet)를 참조하세요.

## <a name="aspnet-core"></a>ASP.NET Core

다양한 ASP.NET 플랫폼에서 사용할 수 있는 고성능 오픈 소스 구현입니다.

[ASP.NET Core 설명서](/aspnet/#pivot=core)를 참조하세요.

## <a name="assembly"></a>어셈블리

애플리케이션이나 다른 어셈블리에서 호출할 수 있는 API 컬렉션을 포함할 수 있는 *.dll*/ *.exe* 파일입니다.

어셈블리에는 인터페이스와 클래스, 구조체, 열거형, 대리자와 같은 형식이 포함될 수 있습니다. 프로젝트의 *bin* 폴더에 있는 어셈블리를 *바이너리*라고도 합니다. [라이브러리](#library)를 참조하세요.

## <a name="bcl"></a>BCL

기본 클래스 라이브러리입니다. ‘프레임워크 라이브러리’라고도 합니다.

System.\*(및 제한된 범위의 Microsoft.\*) 네임스페이스를 구성하는 라이브러리 집합입니다. BCL은 ASP.NET Core 같은 상위 수준 애플리케이션 프레임워크의 기반이 되는 하위 수준의 범용 프레임워크입니다.

[.NET 5(및 .NET Core) 이상 버전](#net-5-and-later-versions)의 BCL 소스 코드는 [.NET 런타임 리포지토리](https://github.com/dotnet/runtime)에 포함됩니다. 이 .NET 최신 구현의 대다수 BCL API는 .NET Framework에서도 사용할 수 있으므로 해당 소스 코드를 .NET Framework BCL 소스 코드의 포크로 간주할 수 있습니다.

## <a name="clr"></a>CLR

공용 언어 런타임입니다.

정확한 의미는 컨텍스트에 따라 달라집니다. 공용 언어 런타임은 일반적으로 [.NET Framework](#net-framework) 또는 [.NET 5(및 .NET Core) 이상 버전](#net-5-and-later-versions)의 런타임을 나타냅니다.

CLR은 메모리 할당 및 관리를 처리합니다. 또한 CLR은 앱을 실행할 뿐만 아니라 [JIT](#jit) 컴파일러를 사용하여 즉시 코드를 생성하고 컴파일하는 가상 머신입니다.

.NET Framework의 CLR 구현은 Windows 전용입니다.

.NET 5 이상 버전의 CLR 구현(Core CLR이라고도 함)은 .NET Framework CLR과 동일한 코드베이스에서 빌드됩니다. 원래 Core CLR은 Silverlight의 런타임이고 여러 플랫폼, 특히 Windows 및 OS X에서 실행되도록 디자인되었습니다. 지금도 많은 Linux 배포 지원을 포함하는 [플랫폼 간](#cross-platform) 런타임입니다.

[런타임](#runtime)도 참조하세요.

## <a name="core-clr"></a>Core CLR

[.NET 5(및 .NET Core) 이상 버전](#net-5-and-later-versions)의 공용 언어 런타임입니다.

[CLR](#clr)을 참조하세요.

## <a name="corert"></a>CoreRT

[CLR](#clr)과 달리 CoreRT는 가상 머신이 아닙니다. 즉, [JIT](#jit)를 포함하지 않으므로 즉시 코드를 생성하고 실행하는 기능을 포함하지 않습니다. 그러나 [GC](#gc)와 RTTI(런타임 형식 식별) 및 리플렉션에 대한 기능은 포함합니다. 그러나 해당 형식 시스템은 리플렉션에 대한 메타데이터가 필요하지 않도록 설계되었습니다. 메타데이터가 필요하지 않으면 불필요한 메타데이터를 분리하고 더 중요하게는 앱이 사용하지 않는 코드를 식별할 수 있는 [AOT](#aot) 도구 체인을 사용할 수 있습니다. CoreRT는 개발 중입니다.

[.NET 네이티브와 CoreRT 소개](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)를 참조하세요.

## <a name="cross-platform"></a>크로스 플랫폼

각 운영 체제에 맞게 다시 작성할 필요 없이 Linux, Windows 및 iOS와 같은 다양한 운영 체제에서 사용할 수 있는 애플리케이션을 개발하고 실행하는 기능입니다. 이를 통해 다양한 플랫폼에서 애플리케이션 간에 코드를 다시 사용하고 일관성을 유지할 수 있습니다.

## <a name="ecosystem"></a>에코시스템

특정 기술에 대한 애플리케이션을 빌드하고 실행하는 데 사용되는 모든 런타임 소프트웨어, 개발 도구 및 커뮤니티 리소스입니다.

“.NET 에코시스템”이라는 용어는 타사 앱 및 라이브러리를 포함한다는 점에서 “.NET 스택”과 같은 유사한 용어와 다릅니다. 다음은 문장에서의 예제입니다.

- “[.NET Standard](#net-standard)는 .NET 에코시스템의 통일성을 높이기 위한 것입니다.”

## <a name="framework"></a>프레임워크

일반적으로 특정 기술을 기반으로 하는 애플리케이션의 개발 및 배포를 용이하게 하는 포괄적인 API 컬렉션입니다. 이 일반적인 의미에서 ASP.NET Core 및 Windows Forms는 애플리케이션 프레임워크의 예입니다. [라이브러리](#library)를 참조하세요.

“프레임워크”라는 단어는 다음 용어에서 다른 의미가 있습니다.

- [.NET Framework](#net-framework)
- [대상 프레임워크](#target-framework)
- [TFM(대상 프레임워크 모니커)](#tfm)
- [프레임워크 종속 앱](../core/deploying/index.md#publish-framework-dependent)

레거시 .NET 설명서에서 “프레임워크”는 경우에 따라 [.NET의 구현](#implementation-of-net)을 나타냅니다. 예를 들어 문서에서는 .NET 5를 프레임워크라고 할 수 있습니다.

## <a name="gc"></a>GC

가비지 수집기입니다.

가비지 수집기는 자동 메모리 관리의 구현체입니다.  GC는 개체가 사용한 메모리에서 더 이상 사용되지 않는 메모리를 해제합니다.

[가비지 수집](garbage-collection/index.md)을 참조하세요.

## <a name="il"></a>IL

중간 언어입니다.

C#과 같은 상위 수준 .NET 언어가 IL(중간 언어)이라는 하드웨어 독립 명령 집합으로 컴파일됩니다. IL은 MSIL(Microsoft IL) 또는 CIL(공통 IL)이라고도 합니다.

## <a name="jit"></a>JIT

Just-In-Time 컴파일러입니다.

[AOT](#aot)와 유사한 이 컴파일러는 [IL](#il)을 프로세서에서 이해하는 기계어 코드로 변환합니다. AOT와 달리 JIT 컴파일은 요청 시 수행되며 코드가 실행되어야 하는 것과 동일한 컴퓨터에서 수행됩니다. JIT 컴파일은 애플리케이션이 실행되는 동안 수행되므로 컴파일 시간이 실행 시간의 일부입니다. 따라서 JIT 컴파일러는 결과 코드가 생성할 수 있는 시간 단축과 코드 최적화에 소요된 시간의 균형을 맞춰야 합니다. 그러나 JIT는 실제 하드웨어를 인식하므로 개발자가 다른 구현을 제공할 필요가 없도록 합니다.

## <a name="implementation-of-net"></a>.NET의 구현체

.NET의 구현체에는 다음이 포함됩니다.

- 하나 이상의 런타임. 예: [CLR](#clr), [CoreRT](#corert).
- .NET Standard의 버전을 구현하고 추가 API를 포함할 수 있는 클래스 라이브러리. 예: [.NET Framework](#net-framework) 및 [.NET 5(및 .NET Core) 이상 버전](#net-5-and-later-versions)의 [BCL](#bcl).
- 필요에 따라 하나 이상의 애플리케이션 프레임워크. 예: [ASP.NET](#aspnet), Windows Forms 및 WPF는 .NET Framework 및 .NET 5에 포함됩니다.
- 필요에 따라 개발 도구. 일부 개발 도구는 여러 구현체에서 공통적으로 사용할 수 있음.

.NET 구현체의 예:

- [.NET Framework](#net-framework)
- [.NET 5 이상 버전(.NET Core 2.1~3.1 포함)](#net-5-and-later-versions)
- [UWP(유니버설 Windows 플랫폼)](#uwp)
- [Mono](#mono)

## <a name="library"></a>라이브러리

앱이나 다른 라이브러리에서 호출할 수 있는 API 컬렉션입니다. .NET 라이브러리는 하나 이상의 [어셈블리](#assembly)로 구성됩니다.

라이브러리 및 [프레임워크](#framework)라는 단어는 종종 같은 뜻으로 사용됩니다.

## <a name="mono"></a>Mono

Mono는 작은 런타임이 필요할 때 주로 사용되는 오픈 소스 [크로스 플랫폼](#cross-platform) .NET 구현체입니다. 이는 Android, Mac, iOS, tvOS 및 watchOS에서 Xamarin 애플리케이션의 성능을 향상하는 런타임으로, 주로 작은 사용 공간이 필요한 앱에 초점을 맞춥니다.

Mono는 현재 게시된 .NET Standard 버전을 모두 지원합니다.

지금까지 Mono는 .NET Framework의 방대한 API를 구현하고 Unix에서 가장 인기 있는 기능의 일부를 따라서 만들었습니다. 경우에 따라 Unix에서 해당 기능을 사용하는 .NET 애플리케이션을 실행하는 데도 사용됩니다.

일반적으로 Mono는 [Just-In-Time 컴파일러](#jit)에서 사용되지만 iOS 같은 플랫폼에 사용되는 전체 [정적 컴파일러(Ahead-Of-Time 컴파일)](#aot) 기능도 제공합니다.

[Mono 설명서](https://www.mono-project.com/docs/)를 참조하세요.

## <a name="net"></a>.NET

[.NET Standard](#net-standard) 및 모든 [.NET 구현체](#implementation-of-net)와 워크로드에 대한 포괄적인 용어입니다. 항상 전체를 대문자로 표기하며 절대로 ".Net"을 사용하지 않습니다.

[.NET 5](#net-5-and-later-versions)(현재 미리 보기 상태)가 릴리스되면 모든 새로운 .NET 개발에 권장되는 .NET 구현이 되므로 일부 컨텍스트에서 “.NET”은 “.NET 5 이상 버전”을 의미합니다.

[.NET 기본 사항](../fundamentals/index.yml)을 참조하세요.

## <a name="net-5-and-later-versions"></a>.NET 5 이상 버전

다양한 .NET 플랫폼에서 사용할 수 있는 고성능 오픈 소스 구현체입니다. [CLR](#clr)(공용 언어 런타임), [AOT](#aot) 런타임(개발 시 [CoreRT](#corert)), [BCL](#bcl)(기본 클래스 라이브러리) 및 [.NET SDK](#net-sdk)를 포함합니다.

이 .NET 구현의 초기 버전을 .NET Core라고 합니다. .Net 5.0은 .NET Core 3.1 다음 버전입니다. [.NET Framework](#net-framework)라고 알려진 이전 구현과 최신 .NET 구현을 혼동하지 않도록 버전 4를 건너뛰었습니다. 현재 버전의 .NET Framework는 4.8입니다.

[.NET 기본 사항](../fundamentals/index.yml)을 참조하세요.

## <a name="net-cli"></a>.NET CLI

[.NET 5(및 .NET Core) 이상 버전](#net-5-and-later-versions)용 애플리케이션 및 라이브러리를 개발하기 위한 플랫폼 간 도구 체인입니다. .NET Core CLI라고도 합니다.

[.NET CLI](../core/tools/index.md)를 참조하세요.

## <a name="net-core"></a>.NET Core

[.NET 5 이상 버전](#net-5-and-later-versions)을 참조하세요.

## <a name="net-framework"></a>.NET Framework

Windows에서만 실행되는 .NET의 구현체입니다. [CLR](#clr)(공용 언어 런타임), [BCL](#bcl)(기본 클래스 라이브러리) 및 [ASP.NET](#aspnet), Windows Forms, WPF 등의 애플리케이션 프레임워크 라이브러리를 포함합니다.

[.NET Framework 가이드](../framework/index.yml)를 참조하세요.

## <a name="net-native"></a>.NET 네이티브

[JIT](#jit)(Just-In-Time)와 반대로 네이티브 코드 [AOT](#aot)(Ahead-Of-Time)를 생성하는 컴파일러 툴 체인입니다.

컴파일은 C++ 컴파일러 및 링커가 작동하는 방식과 유사하게 개발자의 컴퓨터에서 수행되며, 사용되지 않는 코드를 제거하고 더 많은 시간을 최적화에 사용합니다. 라이브러리에서 코드를 추출하여 실행 파일에 병합합니다. 결과는 전체 앱을 나타내는 단일 모듈입니다.

UWP는 .NET 네이티브에서 지원하는 첫 번째 애플리케이션 프레임워크였습니다. 이제 Windows와 macOS, Linux용 네이티브 콘솔 앱 작성을 지원합니다.

[.NET 네이티브와 CoreRT 소개](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)를 참조하세요.

## <a name="net-sdk"></a>.NET SDK

개발자가 [.NET 5(및 .NET Core) 이상 버전](#net-5-and-later-versions)용 .NET 애플리케이션과 라이브러리를 만드는 데 사용할 수 있는 라이브러리 및 도구 집합입니다. .NET Core SDK라고도 합니다.

앱을 빌드하기 위한 [.NET CLI](#net-cli), 앱을 빌드하고 실행하기 위한 .NET 라이브러리 및 런타임, CLI 명령을 실행하고 애플리케이션을 실행하는 dotnet 실행 파일(*dotnet.exe*)을 포함합니다.

[.NET SDK 개요](../core/sdk.md)를 참조하세요.

## <a name="net-standard"></a>.NET Standard

모든 .NET 구현체에서 사용할 수 있는 .NET API의 공식 규격입니다.

.NET Standard 규격은 설명서에서 라이브러리라고도 합니다. 라이브러리는 API 구현체를 포함하므로 규격(인터페이스)뿐만 아니라 .NET Standard를 “라이브러리”라고 잘못 부르기도 합니다.

[.NET Standard](net-standard.md)를 참조하세요.

## <a name="ngen"></a>NGEN

네이티브(이미지) 생성입니다.

해당 기술을 영구 [JIT](#jit) 컴파일러로 생각할 수 있습니다. 일반적으로 코드가 실행되는 컴퓨터에서 코드를 컴파일하지만 컴파일은 대개 설치 시에 수행됩니다.

## <a name="package"></a>패키지

NuGet 패키지(또는 줄여서 패키지)는 작성자 이름과 같은 추가 메타데이터와 함께 동일한 이름의 어셈블리가 하나 이상 있는 .zip 파일입니다.

*.zip* 파일은 *.nupkg* 확장명을 사용하며 *.dll* 파일 및 *.xml* 파일과 같이 여러 대상 프레임워크 및 버전에서 사용할 자산을 포함합니다. 앱 또는 라이브러리에 설치된 경우 앱 또는 라이브러리에서 지정한 대상 프레임워크에 따라 적절한 자산이 선택됩니다. 인터페이스를 정의하는 자산은 *ref* 폴더에 있으며 구현을 정의하는 자산은 *lib* 폴더에 있습니다.

## <a name="platform"></a>platform

Windows와 macOS, Linux, iOS, Android 같은 운영 체제와 해당 운영 체제가 실행되는 하드웨어입니다.

다음은 문장에서의 사용 예입니다.

- “.NET Core는 다양한 플랫폼에서 사용할 수 있는 .NET의 구현체입니다.”
- “PCL 프로필은 Microsoft 플랫폼을 나타내지만 .NET Standard는 플랫폼에 독립적입니다.”

레거시 .NET 설명서에서는 [.NET 구현](#implementation-of-net) 또는 모든 구현을 포함하는 .NET [스택](#stack)을 의미하는 용어로 “.NET 플랫폼”을 사용하기도 합니다. 해당 용어는 둘 다 기본적인(OS/하드웨어) 의미와 혼동되므로 여기서는 해당 용어를 사용하지 않습니다.

“플랫폼”은 앱 빌드 및 실행을 위한 도구 및 라이브러리를 제공하는 소프트웨어를 나타내는 “개발자 플랫폼”이라는 관용구에서 다른 의미를 가집니다. .NET은 다양한 유형의 애플리케이션을 빌드하기 위한 플랫폼 간 오픈 소스 개발자 플랫폼입니다.

## <a name="runtime"></a>런타임

일반적으로 관리형 프로그램의 실행 환경입니다. OS는 런타임 환경의 일부이지만 .NET 런타임의 일부는 아닙니다. 해당 단어의 뜻 그대로 .NET 런타임의 몇 가지 예는 다음과 같습니다.

- [CLR](#clr)(공용 언어 런타임)
- .NET 네이티브(UWP)
- Mono 런타임

“런타임”이라는 단어는 다음 컨텍스트에서 다른 의미가 있습니다.

* [.NET 다운로드 페이지](https://dotnet.microsoft.com/download).

  여기에서 “런타임”은 머신에서 [프레임워크 종속](../core/deploying/index.md#publish-framework-dependent) 앱을 실행할 수 있도록 머신에 다운로드하고 설치할 수 있는 [BCL](#bcl)(프레임워크 라이브러리)과 함께 [CLR](#clr)을 함께 의미합니다.

* [.NET 5(및 .NET Core) 이상 버전](#net-5-and-later-versions)의 [RID(런타임 식별자)](../core/rid-catalog.md).

  여기에서 “런타임”은 .NET 앱이 실행되는 OS 플랫폼 및 CPU 아키텍처를 의미합니다(예: `linux-x64`).

레거시 .NET 설명서에서는 다음 예제와 같이 [.NET 구현](#implementation-of-net)의 뜻 그대로 “런타임”을 사용하기도 합니다.

- “다양한 .NET 런타임에서 특정 버전의 .NET Standard를 구현합니다.”
- “여러 런타임에서 실행되도록 만들어진 라이브러리는 이 프레임워크를 대상으로 해야 합니다.” (.NET Standard를 참조)
- “다양한 .NET 런타임에서 특정 버전의 .NET Standard를 구현합니다. … 각 .NET 런타임 버전은 지원하는 최신 .NET Standard 버전을 보급합니다.”

## <a name="stack"></a>스택

애플리케이션을 만들고 실행하는 데 사용되는 프로그래밍 기술 집합입니다.

“.NET 스택”은 .NET Standard 및 모든 .NET 구현체를 나타냅니다. “.NET 스택”이라는 문구는 하나의 .NET 구현체를 나타냅니다.

## <a name="target-framework"></a>대상 프레임워크(target framework)

.NET 앱이나 라이브러리에서 사용하는 API 컬렉션입니다.

앱이나 라이브러리는 모든.NET 구현에서 표준화된 API 세트의 사양인 .NET Standard의 버전(예: .NET Standard 2.0)을 대상으로 할 수 있습니다. 또한 앱이나는 라이브러리는 특정 .NET 구현체의 버전을 대상으로 할 수 있으며, 이 경우 구현체 관련 API에 액세스할 수 있습니다. 예를 들어 Xamarin.iOS를 대상으로 하는 앱은 Xamarin 제공 iOS API 래퍼에 액세스할 수 있습니다.

일부 대상 프레임워크(예: .NET Framework)에서 사용 가능한 API는 .NET 구현체에서 시스템에 설치하는 어셈블리에 의해 정의되고 애플리케이션 프레임워크 API(예: ASP.NET, WinForms)를 포함할 수 있습니다. 패키지 기반 대상 프레임워크(예: .NET Standard 및 .NET Core)에서 프레임워크 API는 앱이나 라이브러리에 설치된 패키지에 의해 정의됩니다. 이 경우 대상 프레임워크는 프레임워크를 구성하는 모든 패키지를 참조하는 패키지를 암시적으로 지정합니다.

[대상 프레임워크](frameworks.md)를 참조하세요.

## <a name="tfm"></a>TFM

대상 프레임워크 모니커입니다.

.NET 앱이나 라이브러리의 대상 프레임워크를 지정하기 위한 표준화된 토큰 형식입니다. 대상 프레임워크는 일반적으로 `net462` 같은 짧은 이름으로 참조합니다. 긴 형식의 TFM(예: .NETFramework,Version=4.6.2)이 있지만 일반적으로 대상 프레임워크를 지정하는 데 사용하지 않습니다.

[대상 프레임워크](frameworks.md)를 참조하세요.

## <a name="uwp"></a>UWP

유니버설 Windows 플랫폼입니다.

IoT(사물 인터넷)에 대한 최신의 터치 가능 Windows 애플리케이션 및 소프트웨어를 작성하는 데 사용되는 .NET의 구현체입니다. PC, 태블릿, 휴대폰, Xbox와 같은 대상으로 지정할 수 있는 다양한 종류의 디바이스를 통합하도록 설계되었습니다. UWP는 중앙 집중식 앱 스토어, 실행 환경(AppContainer), Win32를 대체할 Windows API(WinRT) 등 많은 서비스를 제공합니다. 앱은 C++과 C#, Visual Basic, JavaScript로 작성할 수 있습니다. C#과 Visual Basic을 사용할 경우 .NET API는 .NET 5(및 .NET Core) 이상 버전에서 제공됩니다.

## <a name="workload"></a>workload

다른 사람이 빌드 중인 앱의 유형. [앱 모델](#app-model)보다 일반적입니다. 예를 들어 이 문서를 포함하여 모든 .NET 문서 페이지의 맨 위에는 **워크로드**에 대한 드롭다운 목록이 있습니다. 이를 통해 **웹**, **모바일**, **클라우드**, **데스크톱**, **기계 학습 \& 데이터**에 대한 문서로 전환할 수 있습니다.

일부 컨텍스트에서 *워크로드*는 특정 유형의 앱을 지원하기 위해 설치할 수 있는 Visual Studio 기능 컬렉션을 참조합니다. 예를 들어 [워크로드 선택](../core/install/windows.md#select-a-workload)을 참조하세요.

## <a name="see-also"></a>참조

- [.NET 기본 사항](../fundamentals/index.yml)
- [.NET Framework 가이드](../framework/index.yml)
- [ASP.NET 개요](/aspnet/index#pivot=aspnet)
- [ASP.NET Core 개요](/aspnet/index#pivot=core)
