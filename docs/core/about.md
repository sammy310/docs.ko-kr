---
title: .NET Core 정보
description: .NET Core에 대한 자세히 알아봅니다.
author: richlander
ms.date: 08/01/2018
ms.openlocfilehash: 6c76d5e80cba6947eb5a91fb31fc3e511970d165
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675968"
---
# <a name="about-net-core"></a>.NET Core 정보

.NET Core에는 다음과 같은 특징이 있습니다.

- **플랫폼 간:** Windows, macOS 및 Linux [운영 체제](https://github.com/dotnet/core/blob/master/os-lifecycle-policy.md)에서 실행됩니다.
- **아키텍처 간에 일관됨:** x64, x86 및 ARM을 비롯한 여러 아키텍처에서 동일한 동작을 사용하여 코드를 실행합니다.
- **명령줄 도구:**  로컬 개발 및 연속 통합 시나리오에서 사용할 수 있는 편리한 명령줄 도구를 포함합니다.
- **유연한 배포:** 앱이나 설치된 side-by-side 사용자 또는 머신 수준에 포함할 수 있습니다. [Docker 컨테이너](docker/index.md)에서 사용될 수 있습니다.
- **호환 가능:** .NET Core는 [.NET Standard](../standard/net-standard.md)를 통해 .NET Framework, Xamarin 및 Mono와 호환됩니다.
- **오픈 소스:** .NET Core 플랫폼은 MIT 및 Apache 2 라이선스를 사용하는 오픈 소스입니다. .NET Core는 [.NET Foundation](https://dotnetfoundation.org/) 프로젝트입니다.
- **Microsoft에서 지원됨:** .NET Core는 [.NET Core 지원](https://www.microsoft.com/net/core/support/)에 따라 Microsoft에서 지원됩니다.

## <a name="languages"></a>언어

C#, Visual Basic 및 F# 언어를 사용하여 .NET Core에 대한 애플리케이션 및 라이브러리를 작성할 수 있습니다. 이러한 언어는 [Visual Studio](https://visualstudio.microsoft.com/vs/), [Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp), Sublime Text 및 Vim을 비롯한 즐겨찾는 텍스트 편집기 및 IDE에 통합될 수 있습니다. 이 통합은 [OmniSharp](https://www.omnisharp.net/) 및 [Ionide](http://ionide.io) 프로젝트의 적합한 담당자에 의해 부분적으로 제공됩니다.

## <a name="apis"></a>API

.NET Core는 다음과 같은 여러 시나리오에서 API를 노출합니다.

- [bool](../csharp/language-reference/keywords/bool.md) 및 [int](../csharp/language-reference/keywords/int.md)와 같은 기본 형식
- <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> 및 <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType>과 같은 컬렉션
- <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> 및 <xref:System.IO.FileStream?displayProperty=nameWithType>과 같은 유틸리티 형식
- <xref:System.Data.DataSet?displayProperty=nameWithType> 및 [DbSet](https://www.nuget.org/packages/Microsoft.EntityFrameworkCore/)과 같은 데이터 형식
- <xref:System.Numerics.Vector?displayProperty=nameWithType> 및 [파이프라인](https://devblogs.microsoft.com/dotnet/system-io-pipelines-high-performance-io-in-net/)과 같은 고성능 형식

.NET Core는 [.NET Standard](../standard/net-standard.md) 사양을 구현하여 .NET Framework 및 Mono API에서 호환성을 제공합니다.

## <a name="frameworks"></a>프레임워크

여러 프레임워크가 .NET Core를 기반으로 빌드되었습니다.

- [ASP.NET Core](/aspnet/core/)
- [Windows 10 UWP(유니버설 Windows 플랫폼)](https://developer.microsoft.com/windows)
- [Tizen](https://developer.tizen.org/development/training/.net-application)

## <a name="composition"></a>컴퍼지션

.NET Core는 다음과 같은 부분으로 구성됩니다.

- [.NET Core 런타임](https://github.com/dotnet/coreclr)은 형식 시스템, 어셈블리 로드, 가비지 수집기, 네이티브 interop 및 기타 기본 서비스를 제공합니다. [.NET Core 프레임워크 라이브러리](https://github.com/dotnet/corefx)는 기본 데이터 형식, 앱 구성 형식 및 기본 유틸리티를 제공합니다.
- [ASP.NET 런타임](https://github.com/aspnet/home)은 웹앱, IoT 앱 및 모바일 백 엔드와 같이 최신 클라우드 기반 인터넷 연결 애플리케이션을 빌드하는 프레임워크를 제공합니다.
- .NET Core 개발자 환경을 사용할 수 있도록 하는 [.NET Core CLI 도구](https://github.com/dotnet/cli) 및 언어 컴파일러([Roslyn](https://github.com/dotnet/roslyn) 및 [F#](https://github.com/microsoft/visualfsharp))입니다.
- [dotnet 도구](https://github.com/dotnet/core-setup)는 .NET Core 앱 및 CLI 도구를 시작하는 데 사용됩니다. 이 호스트는 런타임을 선택하고 런타임을 호스트하며 어셈블리 로드 정책을 제공하고 앱 및 도구를 시작합니다.

이러한 구성 요소는 다음과 같은 방법으로 배포됩니다.

- [.NET Core 런타임](https://www.microsoft.com/net/download/dotnet-core/2.1) - .NET Core 런타임 및 프레임워크 라이브러리가 포함되어 있습니다.
- [ASP.NET Core 런타임](https://www.microsoft.com/net/download/dotnet-core/2.1) - ASP.NET Core 및 .NET Core 런타임 및 프레임워크 라이브러리가 포함되어 있습니다.
- [.NET Core SDK](https://www.microsoft.com/net/download/dotnet-core/2.1) - .NET CLI 도구, ASP.NET Core 런타임 및 .NET Core 런타임 및 프레임워크가 포함되어 있습니다.

### <a name="open-source"></a>오픈 소스

[.NET Core](https://github.com/dotnet/core)는 오픈 소스([MIT 라이선스](https://github.com/dotnet/core/blob/master/LICENSE.TXT))이며 2014년 Microsoft에 의해 [.NET Foundation](https://dotnetfoundation.org)에 제공되었습니다. 이제 가장 많이 사용되는 .NET Foundation 프로젝트 중의 하나입니다. 이 프로젝트는 개인, 교육 또는 상업용으로 개인 및 회사에서 자유롭게 채택할 수 있습니다. 여러 회사에서 앱, 도구, 새 플랫폼 및 호스팅 서비스의 일부로 .NET Core를 사용합니다. 이러한 회사 중 일부는 GitHub에서 .NET Core에 대한 중요한 정보를 제공하고 [.NET Foundation Technical Steering Group(.NET Foundation 기술 방향 설정 그룹)](https://dotnetfoundation.org/blog/tsg-welcome)의 일부로 제품 판매에 대한 지침을 제공합니다.

### <a name="designed-for-adaptability"></a>뛰어난 적응성

.NET Core는 다른 .NET 제품에 비해 매우 유사하지만 고유한 제품으로 구축되었습니다. .NET Core는 새 플랫폼 및 워크로드에 광범위하게 적응되도록 설계되었습니다. 여러 개의 OS 및 CPU 포트가 지원되며 훨씬 더 많은 포트로 이식할 수 있습니다.

제품은 여러 조각으로 구분되어 다양한 시점에 다양한 부품을 새 플랫폼에 적용할 수 있습니다. 런타임 및 플랫폼별 기본 라이브러리는 하나의 단위로 이식해야 합니다. 플랫폼 제약 없는 라이브러리는 구성에 따라 모든 플랫폼에서 있는 그대로 작동합니다. 플랫폼별 구현을 줄여 개발자 효율성을 향상시키거나, 알고리즘이나 API를 전체 또는 일부로 구현할 수 있을 때마다 플랫폼 중립적인 C# 코드를 선호한다는 등 프로젝트에 대한 편견이 있습니다.

일반적으로 사용자는 여러 운영 체제를 지원하기 위해 .NET Core를 구현하는 방법을 질문합니다. 또한 별도의 구현이 있는지 또는 [조건부 컴파일](https://en.wikipedia.org/wiki/Conditional_compilation)이 사용되는지에 대해서도 질문합니다. 둘 다 조건부 컴파일에 대한 강력한 편견이 있습니다.

대부분의 [CoreFX](https://github.com/dotnet/corefx)가 모든 플랫폼에서 공유되는 플랫폼 중립 코드임을 다음 차트에서 확인할 수 있습니다. 플랫폼 중립 코드는 모든 플랫폼에서 사용할 수 있는 이식 가능한 단일 어셈블리로 구현할 수 있습니다.

![CoreFX: 플랫폼별 코드 줄](../images/corefx-platforms-loc.png)

Windows 및 Unix 구현은 크기가 비슷합니다. CoreFX는 [Microsoft.Win32.Registry](https://github.com/dotnet/corefx/tree/master/src/Microsoft.Win32.Registry)와 같은 일부 Windows 전용 기능을 구현하지만 여러 Unix 전용 개념은 구현하지 않기 때문에 Windows 구현이 더 큽니다. 또한 대부분의 Linux 및 macOS 구현이 Unix 구현에서 공유되는데 Linux 및 macOS 관련 구현의 크기가 거의 비슷함을 확인할 수 있습니다.

.NET Core에는 플랫폼별 라이브러리와 플랫폼 중립 라이브러리가 혼합되어 있습니다. 몇 가지 예제에서 패턴을 확인할 수 있습니다.

- [CoreCLR](https://github.com/dotnet/coreclr)는 플랫폼별이며, 메모리 관리자 및 스레드 스케줄러와 같은 OS 하위 시스템을 기반으로 빌드합니다.
- 스토리지 및 암호화 API가 각 OS에서 다르기 때문에 [System.IO](https://github.com/dotnet/corefx/tree/master/src/System.IO) 및 [System.Security.Cryptography.Algorithms](https://github.com/dotnet/corefx/tree/master/src/System.Security.Cryptography.Algorithms)는 플랫폼별입니다.
- [System.Collections](https://github.com/dotnet/corefx/tree/master/src/System.Collections) 및 [System.Linq](https://github.com/dotnet/corefx/tree/master/src/System.Linq)는 데이터 구조를 통해 만들고 작동하기 때문에 플랫폼 중립입니다.

## <a name="comparisons-to-other-net-implementations"></a>다른 .NET 구현과 비교

기존 .NET 구현과 비교하여 .NET Core의 크기 및 모양을 이해하는 것이 가장 쉽습니다.

### <a name="comparison-with-net-framework"></a>.NET Framework와 비교

.NET은 Microsoft가 2000년에 처음 발표한 후 발전해 왔습니다. .NET Framework는 Microsoft에서 거의 20년 가까이 만들어낸 기본 .NET 구현입니다.

.NET Core와 .NET Framework 간의 주요 차이점은 다음과 같습니다.

- **앱 모델** - .NET Core는 일부 .NET Framework 앱 모델을 지원하지 않습니다. 특히, ASP.NET Web Forms 및 ASP.NET MVC는 지원하지 않지만 ASP.NET Core MVC는 지원합니다. [.NET Core 3이 WPF 및 Windows Forms를 지원한다](https://devblogs.microsoft.com/dotnet/net-core-3-and-support-for-windows-desktop-applications/)고 발표했습니다.
- **API** - .NET Core에는 팩터링이 다른 .NET Framework 기본 클래스 라이브러리의 대량 하위 집합이 포함됩니다(핵심 사례에서 어셈블리 이름이 다르고, 형식에서 노출된 멤버가 다름). 이러한 차이로 인해 어떤 경우 .NET Core에 대한 포트 원본을 변경해야 합니다([microsoft/dotnet-apiport](https://github.com/microsoft/dotnet-apiport) 참조). .NET Core는 [.NET Standard](../standard/net-standard.md) API 사양을 구현합니다.
- **하위 시스템** -- .Net Core는 더 간단한 구현 및 프로그래밍 모델 구축을 위해 .NET Framework에 하위 시스템의 하위 집합을 구현합니다. 예를 들어 CAS(코드 액세스 보안)는 지원되지 않지만 리플렉션은 지원됩니다.
- **플랫폼** -- .NET Framework는 Windows와 Windows Server를 지원하는 반면 .NET Core는 macOS 및 Linux도 지원합니다.
- **오픈 소스** -- .NET Core는 오픈 소스이며, [.NET Framework의 읽기 전용 하위 집합](https://github.com/microsoft/referencesource)은 오픈 소스입니다.

.NET Core는 고유하며, .NET Framework 및 기타 .NET 구현과 현저한 차이가 있지만, 원본 또는 이진 공유 기술을 사용하여 이러한 구현 간에 간단하게 코드를 공유할 수 있습니다.

### <a name="comparison-with-mono"></a>Mono와 비교

[Mono](https://www.mono-project.com/)는 원래 플랫폼 간 [오픈 소스](https://github.com/mono/mono) .NET 구현으로, 2004년에 처음 제공되었습니다. .NET Framework의 커뮤니티 복제본으로 생각할 수 있습니다. Mono 프로젝트 팀은 호환되는 구현을 제공하기 위해 Microsoft에서 게시한 오픈 [.NET 표준](https://github.com/dotnet/coreclr/blob/master/Documentation/project-docs/dotnet-standards.md)(특히 ECMA 335)을 사용했습니다.

.NET Core와 Mono 간의 주요 차이점은 다음과 같습니다.

- **앱 모델** -- Mono는 Xamarin 제품을 통해 .NET Framework 앱 모델의 하위 집합(예: Windows Forms) 및 몇 가지 추가 모델(예: [Xamarin.iOS](https://www.xamarin.com/platform))을 지원합니다. .NET Core는 이러한 모델을 지원하지 않습니다.
- **API** -- Mono는 .NET Framework API의 [큰 하위 집합](http://docs.go-mono.com/?link=root%3a%2fclasslib)을 지원하며, 동일한 어셈블리 이름 및 팩터링을 사용합니다.
- **플랫폼** -- Mono는 여러 플랫폼 및 CPU를 지원합니다.
- **오픈 소스** -- Mono와 .NET Core 둘 다 MIT 라이선스를 사용하며 .NET Foundation 프로젝트입니다.
- **포커스** -- 최근 몇 년 간 Mono의 주요 포커스는 모바일 플랫폼인 반면, .NET Core의 포커스는 클라우드 및 데스크톱 워크로드입니다.
