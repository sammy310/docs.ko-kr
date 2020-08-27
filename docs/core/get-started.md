---
title: .NET Core 시작
description: Windows, Linux 및 macOS에서 .NET Core 애플리케이션을 빌드하는 방법을 알아볼 수 있는 리소스를 찾아보세요.
author: adegeo
ms.author: adegeo
ms.date: 12/03/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 56eebc0fc5bad6f57d93358cbbef389d6355d66b
ms.sourcegitcommit: c4a15c6c4ecbb8a46ad4e67d9b3ab9b8b031d849
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "88656692"
---
# <a name="get-started-with-net-core"></a>.NET Core 시작

이 문서에서는 .NET Core로 시작하는 데 필요한 정보를 제공합니다. Windows, Linux 및 macOS에서 .NET Core를 설치할 수 있습니다. 원하는 텍스트 편집기에서 코딩하고 플랫폼 간 라이브러리 및 애플리케이션을 생성할 수 있습니다.

.NET Core가 무엇인지 또는 다른 .NET 기술과 어떻게 연결되는지를 잘 모르겠으면 [.NET이란?](https://dotnet.microsoft.com/learn/dotnet/what-is-dotnet) 개요부터 시작하세요. 간단히 말해 .NET Core는 오픈 소스의 플랫폼 간 .NET의 구현입니다.

## <a name="create-an-application"></a>애플리케이션 만들기

먼저 사용자의 컴퓨터에 [.NET Core SDK](https://dotnet.microsoft.com/download)를 다운로드하여 설치합니다.

다음으로 **PowerShell**, **명령 프롬프트** 또는 **Bash**와 같은 터미널을 엽니다. 다음 `dotnet` 명령을 입력하여 C# 애플리케이션을 만들고 실행합니다.

```dotnetcli
dotnet new console --output sample1
dotnet run --project sample1
```

다음과 같은 내용이 출력됩니다.

```console
Hello World!
```

지금까지 간단한 .NET Core 애플리케이션을 만들었습니다. 또한 [Visual Studio Code](./tutorials/with-visual-studio-code.md), [Visual Studio](./tutorials/with-visual-studio.md)(Windows만 해당) 또는 [Mac용 Visual Studio](tutorials/with-visual-studio-mac.md)(macOS만 해당)를 사용하여 .NET Core 애플리케이션을 만들 수도 있습니다.

## <a name="tutorials"></a>자습서

다음 단계별 자습서에 따라 .NET Core 애플리케이션 개발을 시작합니다.

<!-- markdownlint-disable MD025 -->

# <a name="windows"></a>[Windows](#tab/windows)

- [Visual Studio 2019에서 첫 번째 .NET Core 콘솔 애플리케이션 만들기](./tutorials/with-visual-studio.md)
- [Visual Studio에서 .NET Standard를 사용하여 클래스 라이브러리 빌드](./tutorials/library-with-visual-studio.md)
- [자습서: Visual Studio Code를 사용하여 .NET Core 콘솔 앱 만들기](tutorials/with-visual-studio-code.md)

|   |   |
|---|---|
| ![동영상에 대한 비디오 카메라 아이콘](./media/video-icon.png "비디오 시청") | Channel 9에서 [Visual Studio Code 및 .NET Core 설치 방법](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/)을 시청하세요. |
| ![동영상에 대한 비디오 카메라 아이콘](./media/video-icon.png "비디오 시청") | YouTube에서 [.NET Core 101](https://www.youtube.com/playlist?list=PLdo4fOcmZ0oWoazjhXQzBKMrFuArxpW80) 동영상을 시청하세요. |

지원되는 Windows 버전 목록은 [.NET Core 종속성 및 요구 사항](install/dependencies.md?pivots=os-windows) 문서를 참조하세요.

# <a name="linux"></a>[Linux](#tab/linux)

다음 단계별 자습서에 따라 .NET Core 애플리케이션 개발을 시작합니다.

- [자습서: Visual Studio Code를 사용하여 .NET Core 콘솔 앱 만들기](tutorials/with-visual-studio-code.md)

|   |   |
|---|---|
| ![동영상에 대한 비디오 카메라 아이콘](./media/video-icon.png "비디오 시청") | [Ubuntu에서 C# 및 .NET Core를 사용하여 Visual Studio Code 시작](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu)에 관한 비디오 시청. |

지원되는 Linux 배포판 및 버전 목록은 [.NET Core 종속성 및 요구 사항](install/dependencies.md?pivots=os-linux) 문서를 참조하세요.

# <a name="macos"></a>[macOS](#tab/macos)

다음 단계별 자습서에 따라 .NET Core 애플리케이션 개발을 시작합니다.

- [자습서: Visual Studio Code를 사용하여 .NET Core 콘솔 애플리케이션 만들기](tutorials/with-visual-studio-code.md)
- [자습서: Mac용 Visual Studio를 사용하여 .NET Core 콘솔 애플리케이션 만들기](tutorials/with-visual-studio-mac.md)
- [Mac용 Visual Studio를 사용하여 macOS에서 .NET Standard 라이브러리 빌드](tutorials/library-with-visual-studio-mac.md)

|   |   |
|---|---|
| ![동영상에 대한 비디오 카메라 아이콘](media/video-icon.png "비디오 시청") | [macOS에서 C# 및 .NET Core를 사용하여 Visual Studio Code 시작](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac)에 관한 동영상을 시청하세요. |

지원되는 OS X/macOS 버전 목록은 [.NET Core 종속성 및 요구 사항](install/dependencies.md?pivots=os-macos) 문서를 참조하세요.

---
