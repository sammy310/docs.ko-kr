---
title: .NET Core 소개 및 개요
description: .NET Core는 Windows, Linux, macOS 앱을 만들기 위한 모듈식 고성능 .NET 구현입니다. 시작하려면 .NET Core에 관해 알아봅니다.
author: richlander
ms.date: 03/26/2020
ms.custom: updateeachrelease
ms.openlocfilehash: 350fd50bee3403a05d1c19c9a692535613b17498
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538278"
---
# <a name="introduction-to-net-core"></a>.NET Core 소개

[.NET Core](about.md)는 [오픈 소스](https://github.com/dotnet/runtime/blob/master/LICENSE.TXT) 범용 개발 플랫폼입니다. 여러 프로그래밍 언어를 사용하여 x64, x86, ARM32, ARM64 프로세서의 Windows, macOS 및 Linux용 .NET Core 앱을 만들 수 있습니다. [클라우드](/aspnet/core/), [IoT](/archive/msdn-magazine/2019/august/net-core-cross-platform-iot-programming-with-net-core-3-0), [클라이언트 UI](../desktop-wpf/overview/index.md) 및 [기계 학습](../machine-learning/index.yml)용 프레임워크 및 API가 제공됩니다.

[.NET Core SDK를 다운로드](https://dotnet.microsoft.com/download)하여 머신에서 .NET Core를 사용해 보세요. 최신 버전은 [.NET Core 3.1](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/)입니다.

## <a name="download-net-core"></a>.NET Core 다운로드

다음 방법으로 .NET Core를 가져올 수 있습니다.

* [Windows 및 macOS용 설치 프로그램](https://dotnet.microsoft.com/download)
* [Linux 패키지](./install/linux.md)
* [Docker 컨테이너](https://hub.docker.com/_/microsoft-dotnet-core/)
* [Zip 및 tarball](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* [스크립트 설치](https://dotnet.microsoft.com/download/dotnet-core/scripts)
* [릴리스 정보](https://github.com/dotnet/core/tree/master/release-notes)

## <a name="create-your-first-application"></a>첫 애플리케이션 만들기

.NET Core SDK를 설치한 후 명령 프롬프트를 엽니다. 다음 명령을 사용하여 애플리케이션을 만들고 실행합니다.

```dotnetcli
dotnet new console
dotnet run
```

다음과 같은 내용이 출력됩니다.

```output
Hello World!
```

## <a name="contribute"></a>참가

.NET Core는 개방형 플랫폼입니다. 누구나 참여할 수 있습니다.

* [개발자 커뮤니티](https://developercommunity.visualstudio.com/spaces/61/index.html)에서 제품 문제 및 질문을 게시하세요.
* 제품 기여는 [dotnet/runtime](https://github.com/dotnet/runtime), [dotnet/sdk](https://github.com/dotnet/sdk), [dotnet/rosyln](https://github.com/dotnet/roslyn) 또는 [aspnetcore](https://github.com/dotnet/aspnetcore)와 같은 프로젝트 리포지토리 중 하나에서 만들어야 합니다. 자세한 내용은 [.NET Core 리포지토리](https://github.com/dotnet/core/blob/master/Documentation/core-repos.md)를 참조하세요.

## <a name="support"></a>고객 지원팀

.NET Core는 Windows, macOS 및 Linux의 경우 Microsoft에서 지원하며 Red Hat Enterprise Linux의 경우 Red Hat에서 지원합니다.

## <a name="next-steps"></a>다음 단계

> [!div class="nextstepaction"]
> [.NET Core 자습서](tutorials/index.md)

> [!div class="nextstepaction"]
> [브라우저에서 .NET Core 사용해 보기](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml)
