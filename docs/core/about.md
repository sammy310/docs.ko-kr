---
title: .NET Core 개요
description: .NET Core의 특성 및 구성을 알아보고 다른 .NET 구현과 비교합니다.
ms.date: 03/26/2020
ms.openlocfilehash: d5ef79fe5a8fbb56beae77edd01830fe6561fa51
ms.sourcegitcommit: 4ad2f8920251f3744240c3b42a443ffbe0a46577
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/08/2020
ms.locfileid: "86100732"
---
# <a name="net-core-overview"></a>.NET Core 개요

> [!div class="button"]
> [.NET Core 다운로드](https://dotnet.microsoft.com/download)

.NET Core에는 다음과 같은 특징이 있습니다.

- **플랫폼 간:** Windows, macOS 및 Linux [운영 체제](https://github.com/dotnet/core/blob/master/os-lifecycle-policy.md)에서 실행됩니다.
- **오픈 소스:** .NET Core 프레임워크는 MIT 및 Apache 2 라이선스를 사용하는 [오픈 소스](https://github.com/dotnet/core)입니다. .NET Core는 [.NET Foundation](https://dotnetfoundation.org/) 프로젝트입니다.
- **최신:** 비동기 프로그래밍, 구조체를 사용하는 복사 없는 패턴, 컨테이너에 대한 리소스 거버넌스와 같은 최신 패러다임을 구현합니다.
- **성능:**  [하드웨어 내장 함수](https://devblogs.microsoft.com/dotnet/hardware-intrinsics-in-net-core/), [계층화된 컴파일](https://github.com/dotnet/coreclr/blob/master/Documentation/design-docs/tiered-compilation.md) 및 [Span\<T>](../standard/memory-and-spans/index.md) 같은 기능을 사용해 [고성능](https://devblogs.microsoft.com/dotnet/performance-improvements-in-net-core-3-0/)을 제공합니다.
- **환경 전체에서 일관성:** x64, x86 및 ARM을 비롯한 여러 운영 체제 및 아키텍처에서 동일한 동작을 사용하여 코드를 실행합니다.
- **명령줄 도구:**  로컬 개발 및 연속 통합에서 사용할 수 있는 편리한 명령줄 도구가 포함되어 있습니다.
- **유연한 배포:** .NET Core를 앱에 포함하거나 병렬로 설치(사용자 또는 시스템 수준 설치)할 수 있습니다. [Docker 컨테이너](docker/introduction.md)에서 사용될 수 있습니다.

## <a name="languages"></a>언어

[C#](../csharp/index.yml), [Visual Basic](../visual-basic/index.yml) 및 [F#](../fsharp/index.yml) 언어를 사용하여 .NET Core에 대한 애플리케이션 및 라이브러리를 작성할 수 있습니다. 이러한 언어는 즐겨 찾는 텍스트 편집기나 다음과 같은 IDE(통합 개발 환경)에서 사용할 수 있습니다.

- [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)
- [Visual Studio Code](https://code.visualstudio.com/download)

편집기 통합은 부분적으로 [OmniSharp](https://www.omnisharp.net/) 및 [Ionide](https://ionide.io) 프로젝트의 참가자가 제공합니다.

## <a name="apis"></a>API

.NET Core는 모든 종류의 앱을 빌드하기 위한 프레임워크를 제공합니다.

* [ASP.NET Core](/aspnet/core/)를 사용한 클라우드 앱
* [Xamarin](/xamarin)을 사용한 모바일 앱
* [System.Device.GPIO](https://docs.microsoft.com/archive/msdn-magazine/2019/august/net-core-cross-platform-iot-programming-with-net-core-3-0)를 사용한 IoT 앱
* [WPF](../desktop-wpf/overview/index.md) 및 Windows Forms를 사용한 Windows 클라이언트 앱
* 기계 학습 [ML.NET](../machine-learning/index.yml)

다음과 같은 일반적인 요구를 충족하는 많은 API가 포함되어 있습니다.

- 기본 형식(예: <xref:System.Boolean?displayProperty=nameWithType> 및 <xref:System.Int32?displayProperty=nameWithType>).
- <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> 및 <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType>과 같은 컬렉션
- <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> 및 <xref:System.IO.FileStream?displayProperty=nameWithType>과 같은 유틸리티 형식
- <xref:System.Data.DataSet?displayProperty=nameWithType> 및 <xref:System.Data.Entity.DbSet?displayProperty=nameWithType>와 같은 데이터 형식
- <xref:System.Span%601?displayProperty=nameWithType>, <xref:System.Numerics.Vector?displayProperty=nameWithType> 및 [Pipelines](../standard/io/pipelines.md)와 같은 고성능 형식

.NET Core는 [.NET Standard](../standard/net-standard.md) 사양을 구현하여 .NET Framework 및 Mono API에서 호환성을 제공합니다.

## <a name="composition"></a>컴퍼지션

.NET Core는 다음과 같은 부분으로 구성됩니다.

- [.NET Core 런타임](https://github.com/dotnet/runtime/tree/master/src/coreclr)은 형식 시스템, 어셈블리 로드, 가비지 수집기, 네이티브 interop, 기타 기본 서비스를 제공합니다. [.NET Core 프레임워크 라이브러리](https://github.com/dotnet/runtime/tree/master/src/libraries)는 기본 데이터 형식, 앱 컴퍼지션 형식, 기본 유틸리티를 제공합니다.
- [ASP.NET Core 런타임](https://github.com/dotnet/aspnetcore)은 웹앱, IoT 앱, 모바일 백 엔드 등의 최신 클라우드 기반 인터넷 연결 앱을 빌드하기 위한 프레임워크를 제공합니다.
- .NET Core 개발자 환경을 사용할 수 있도록 하는 [.NET Core SDK](https://github.com/dotnet/sdk) 및 언어 컴파일러([Roslyn](https://github.com/dotnet/roslyn) 및 [F#](https://github.com/microsoft/visualfsharp))입니다.
- [dotnet 명령](./tools/dotnet.md)은 .NET Core 앱 및 CLI 명령을 시작하는 데 사용됩니다. 런타임을 선택 및 호스트하고, 어셈블리 로드 정책을 제공하며, 앱과 도구를 시작합니다.

### <a name="open-source"></a>오픈 소스

[.NET Core](about.md)는 [오픈 소스](https://github.com/dotnet/runtime/blob/master/LICENSE.TXT) 범용 개발 플랫폼입니다. x64, x86, ARM32, ARM64 프로세서의 Windows, macOS 및 Linux용 .NET Core 앱을 만들 수 있습니다. [클라우드](/aspnet/core/), [IoT](https://docs.microsoft.com/archive/msdn-magazine/2019/august/net-core-cross-platform-iot-programming-with-net-core-3-0), [클라이언트 UI](../desktop-wpf/overview/index.md) 및 [기계 학습](../machine-learning/index.yml)용 프레임워크 및 API가 제공됩니다.

## <a name="support"></a>고객 지원팀

.NET Core는 [Microsoft에 의해](https://dotnet.microsoft.com/platform/support/policy) Windows, macOS 및 Linux에서 지원됩니다. 정기적으로 보안 및 품질이 업데이트됩니다(매월 두 번째 화요일).

Microsoft에서 제공하는 .NET Core 이진 배포는 Azure의 Microsoft가 유지 관리하는 서버에서 빌드되고 테스트 되며 Microsoft 엔지니어링 및 보안 관행을 따릅니다.

RHEL(Red Hat Enterprise Linux)에서 [Red Hat이 .NET Core를 지원](https://developers.redhat.com/topics/dotnet/)합니다. Red Hat은 소스에서 .NET Core를 빌드하여 [Red Hat 소프트웨어 컬렉션](https://developers.redhat.com/products/softwarecollections/overview/)에서 사용할 수 있게 합니다. Red Hat 및 Microsoft는 협력하여 RHEL에서 .NET Core가 잘 작동하도록 합니다.

[Tizen은 Tizen 플랫폼에서 .NET Core을 지원](https://developer.tizen.org/development/training/.net-application)합니다.
