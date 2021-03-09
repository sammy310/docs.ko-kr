---
title: .NET 아키텍처 구성 요소
description: .NET Standard, .NET 구현, .NET 런타임 및 도구와 같은 .NET 아키텍처 구성 요소에 대해 설명합니다.
author: cartermp
ms.date: 10/05/2020
ms.openlocfilehash: 884deb61ab5cda5054fb54134c3338b4d05599ca
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102106399"
---
# <a name="net-architectural-components"></a>.NET 아키텍처 구성 요소

.NET 앱은 하나 이상의 *.NET 구현체* 로 개발하고 이 구현체에서 동작합니다. .NET 구현에는 .NET Framework와 .NET 5(및 .NET Core), Mono가 있습니다. .NET Standard라는 .NET의 여러 구현에는 공통적인 API 사양이 있습니다. 이 문서에서는 이러한 개념들을 간략하게 소개합니다.

## <a name="net-standard"></a>.NET Standard

.NET Standard는 .NET 구현체의 기본 클래스 라이브러리(Base Class Library)로 구현한 API 집합입니다. 보다 공식적으로는, 코드를 컴파일할 수 있는 일정한 약속을 구성하는 .NET API 규격입니다. 이러한 계약은 여러 .NET 구현에서 구현됩니다.

.NET Standard는 [대상 프레임워크](glossary.md#target-framework)입니다. .NET Standard 버전을 대상으로 하는 코드는 해당 .NET Standard 버전을 지원하는 모든 .NET 구현체에서 실행할 수 있습니다.

.NET Standard는 여러 .NET 구현에서 이식성을 가능하게 하기 위해 만들어졌지만, 이제 .NET 5는 여러 플랫폼과 워크로드에서 코드를 공유하는 더 나은 방법을 제공합니다. 자세한 내용은 [.NET 5 및 .NET Standard](net-standard.md#net-5-and-net-standard)를 참조하세요.

## <a name="net-implementations"></a>.NET 구현체

.NET의 각 구현체에는 다음 구성 요소가 포함됩니다.

- 하나 이상의 런타임. 예: .NET Framework CLR, .NET 5 CLR
- 클래스 라이브러리. 예: .NET Framework 기본 클래스 라이브러리, .NET 5 기본 클래스 라이브러리.
- 필요에 따라 하나 이상의 애플리케이션 프레임워크. 예: [ASP.NET](https://www.asp.net/), [Windows Forms](/dotnet/desktop/winforms/windows-forms-overview) 및 [WPF(Windows Presentation Foundation)](/dotnet/desktop/wpf/)가 .NET Framework 및 .NET 5에 포함됩니다.
- 필요에 따라 개발 도구. 일부 개발 도구는 여러 구현체에서 공통적으로 사용할 수 있음.

Microsoft가 지원하는 네 가지 .NET 구현이 있습니다.

- .NET 5(및 .NET Core) 이상
- .NET Framework
- Mono
- UWP

.NET 5는 이제 지속적인 개발의 초점이 되는 주요 구현입니다. .NET 5는 Windows 데스크톱 앱 및 크로스 플랫폼 콘솔 앱, 클라우드 서비스 및 웹 사이트와 같은 여러 플랫폼과 많은 워크로드를 지원하는 단일 코드 기반에 구축되었습니다.

### <a name="net-5"></a>.NET 5

.NET 5는 대규모 서버 및 클라우드 워크로드를 처리하도록 설계된 .NET의 교차 플랫폼 구현입니다. 또한 데스크톱 앱을 포함한 다른 워크로드도 지원합니다. Windows와 macOS, Linux에서 실행됩니다. 이는 .NET Standard를 구현하므로 .NET Standard를 대상으로 하는 코드는 .NET 5에서 실행할 수 있습니다. [ASP.NET Core](https://dotnet.microsoft.com/learn/aspnet/what-is-aspnet-core), [Windows Forms](/dotnet/desktop/winforms/windows-forms-overview) 및 [WPF(Windows Presentation Foundation)](/dotnet/desktop/wpf/)는 모두 .NET 5에서 실행됩니다.

자세한 내용은 다음 자료를 참조하세요.

- [.NET 소개](../core/introduction.md)
- [서버 앱에 대해 .NET 5와 .NET Framework 중에서 선택](choosing-core-framework-server.md)
- [.NET 5 및 .NET Standard](net-standard.md#net-5-and-net-standard)

### <a name="net-framework"></a>.NET Framework

.NET Framework는 2002년부터 있었던 원래 .NET 구현입니다. 버전 4.5 이상은 .NET Standard를 구현하므로 .NET Standard를 대상으로 하는 코드는 .NET Framework의 해당 버전에서 실행할 수 있습니다. Windows Forms 및 WPF를 사용하는 Windows 데스크톱 개발용 API와 같이 Windows 관련 추가 API가 포함되어 있습니다. .NET Framework는 Windows 데스크톱 애플리케이션을 구축을 위해 최적화되어 있습니다.

자세한 내용은 [.NET Framework 가이드](../framework/index.yml)를 참조하세요.

### <a name="mono"></a>Mono

Mono는 작은 런타임이 필요할 때 주로 사용되는 .NET 구현체입니다. 이는 Android, macOS, iOS, tvOS 및 watchOS에서 Xamarin 애플리케이션의 성능을 향상하는 런타임으로, 주로 작은 사용 공간에 초점을 맞춥니다. 또한 Mono에서는 Unity 엔진으로 만든 게임이 동작합니다.

Mono는 현재 게시된 .NET Standard 버전을 모두 지원합니다.

지금까지 Mono는 .NET Framework의 방대한 API를 구현하고 Unix에서 가장 인기 있는 기능의 일부를 따라서 만들었습니다. 경우에 따라 Unix에서 해당 기능을 사용하는 .NET 애플리케이션을 실행하는 데도 사용됩니다.

일반적으로 Mono는 Just-In-Time 컴파일러에서 사용되지만 iOS 같은 플랫폼에 사용되는 전체 정적 컴파일러(Ahead-Of-Time 컴파일) 기능도 제공합니다.

자세한 내용은 [Mono 설명서](https://www.mono-project.com/docs/)를 참조하세요.

### <a name="universal-windows-platform-uwp"></a>UWP(유니버설 Windows 플랫폼)

UWP는 IoT(사물 인터넷)에 대한 최신 터치 가능 Windows 애플리케이션 및 소프트웨어를 작성하는 데 사용되는 .NET의 구현입니다. PC, 태블릿, 휴대폰, Xbox와 같은 대상으로 지정할 수 있는 다양한 종류의 디바이스를 통합하도록 설계되었습니다. UWP는 중앙 집중식 앱 스토어, 실행 환경(AppContainer), Win32를 대체할 Windows API(WinRT) 등 많은 서비스를 제공합니다. 앱은 C++과 C#, Visual Basic, JavaScript로 작성할 수 있습니다.

자세한 내용은 [유니버설 Windows 플랫폼 소개](/windows/uwp/get-started/universal-application-platform-guide)를 참조하세요.

## <a name="net-runtimes"></a>.NET 런타임

런타임은 관리되는 프로그램에 대한 실행 환경입니다. OS는 런타임 환경의 일부이지만 .NET 런타임의 일부는 아닙니다. 다음은 .NET 런타임의 몇 가지 예입니다.

- .NET Framework에 대한 CLR(공용 언어 런타임)
- .NET 5에 대한 CLR(공용 언어 런타임)
- 유니버설 Windows 플랫폼용 .NET 네이티브
- Xamarin.iOS와 Xamarin.Android, Xamarin.Mac, Mono 데스크톱 프레임워크에 대한 Mono 런타임

## <a name="net-tooling-and-common-infrastructure"></a>.NET 도구 및 공통 인프라

모든 .NET 구현체에서 동작하는 다양한 도구와 인프라 구성 요소를 사용할 수 있습니다. 이러한 도구 및 구성 요소는 다음과 같습니다.

- .NET 언어 및 해당 컴파일러
- .NET 프로젝트 시스템( *.csproj*, *.vbproj* 및 *.fsproj* 파일 기반)
- 프로젝트를 빌드하는 데 사용하는 빌드 엔진 [MSBuild](/visualstudio/msbuild/msbuild)
- .NET에 대한 Microsoft의 패키지 관리자 [NuGet](/nuget/)
- [CAKE](https://cakebuild.net/) 및 [FAKE](https://fake.build/) 등의 오픈 소스 빌드 오케스트레이션 도구

자세한 내용은 [도구 및 생산성](../core/introduction.md#tools-and-productivity)을 참조하세요.

## <a name="applicable-standards"></a>적용 가능한 표준

C# 언어 및 CLI(공용 언어 인프라) 사양은 [Ecma International&reg;](https://www.ecma-international.org/)을 통해 표준화됩니다. 이러한 표준의 첫 번째 버전은 2001년 12월에 Ecma에서 게시했습니다.

표준에 대한 후속 수정 사항은 프로그래밍 언어 기술 위원회([TC49](https://www.ecma-international.org/technical-committees/tc49/)) 내에서 TC49-TG2(C#) 및 TC49-TG3(CLI) 작업 그룹을 통해 개발되었고 이후에는 Ecma General Assembly가, 그 이후에는 ISO/IEC JTC 1이 ISO Fast-Track 프로세스를 통해 도입했습니다.

### <a name="latest-standards"></a>최신 표준

다음과 같은 공식 Ecma 문서는 [C#](https://www.ecma-international.org/publications-and-standards/standards/ecma-334/) 및 [CLI](https://www.ecma-international.org/publications-and-standards/standards/ecma-335/)([TR-84](https://www.ecma-international.org/publications-and-standards/technical-reports/ecma-tr-84/))에서 사용할 수 있습니다.

- **C# 언어 표준(버전 5.0)** : [ECMA-334.pdf](https://www.ecma-international.org/wp-content/uploads/ECMA-334_5th_edition_december_2017.pdf)
- **CLI(공용 언어 인프라)** : [ECMA-335.pdf](hhttps://www.ecma-international.org/wp-content/uploads/ECMA-335_6th_edition_june_2012.pdf).
- **파티션 IV XML 파일에서 파생된 정보**: [ECMA-084.pdf](https://www.ecma-international.org/publications/files/ECMA-TR/ECMA%20TR-084.pdf) format.

공식 ISO/IEC 문서는 ISO/IEC [공개적으로 사용할 수 있는 표준](https://standards.iso.org/ittf/PubliclyAvailableStandards/) 페이지에서 사용할 수 있습니다. 이러한 링크는 해당 페이지에서 직접 제공됩니다.

- **정보 기술 - 프로그래밍 언어- C#** : [ISO/IEC 23270:2018](https://standards.iso.org/ittf/PubliclyAvailableStandards/c075178_ISO_IEC_23270_2018.zip)
- **정보 기술 - CLI(공용 언어 인프라) 파티션 I ~ VI**: [ISO/IEC 23271:2012](https://standards.iso.org/ittf/PubliclyAvailableStandards/c058046_ISO_IEC_23271_2012(E).zip)
- **정보 기술 - CLI (공용 언어 인프라) - 파티션 IV XML 파일에서 파생된 정보에 대한 기술 보고서**: [ISO/IEC TR 23272:2011](https://www.ecma-international.org/wp-content/uploads/ECMA_TR-84_6th_edition_june_2012.pdf)

## <a name="see-also"></a>참조

- [.NET 소개](../core/introduction.md)
- [.NET Standard 소개](net-standard.md)
- [서버 앱에 대해 .NET 5와 .NET Framework 중에서 선택](choosing-core-framework-server.md)
- [.NET Framework 가이드](../framework/index.yml)
- [C# 가이드](../csharp/index.yml)
- [F# 가이드](../fsharp/index.yml)
- [Visual Basic 가이드](../visual-basic/index.yml)
