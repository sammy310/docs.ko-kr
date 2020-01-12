---
title: 관리형 디버거 - .NET Core
description: Visual Studio 및 Visual Studio Code 관리형 디버거의 개요입니다.
ms.date: 08/05/2019
ms.openlocfilehash: 065b1b0fc32eb76b398cb3821c8592a1955c9359
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715561"
---
# <a name="net-core-managed-debuggers"></a>.NET Core 관리형 디버거

디버거를 사용하면 프로그램을 일시 중지하거나 단계별로 실행할 수 있습니다. 일시 중지되면 프로세스의 현재 상태를 볼 수 있습니다. 주요 섹션을 단계별로 실행하여 코드를 이해하고 그 결과를 생성하는 이유를 파악할 수 있습니다.

Microsoft는 **Visual Studio** 및 **Visual Studio Code**에서 관리 코드에 대한 디버거를 제공합니다.

## <a name="visual-studio-managed-debugger"></a>Visual Studio 관리형 디버거

**Visual Studio**는 가장 포괄적인 디버거를 사용할 수 있는 통합 개발 환경입니다. Visual Studio는 Windows에서 작업하는 개발자에게 탁월한 선택입니다.

- [자습서 - Visual Studio를 사용하여 Windows에서 .NET Core 애플리케이션 디버깅](../tutorials/debugging-with-visual-studio.md)

Visual Studio는 Windows 애플리케이션이지만, Linux 및 macOS 앱을 원격으로 디버그하는 데 계속 사용할 수 있습니다.

- [Visual Studio를 사용하여 Linux/OSX에서 .NET Core 애플리케이션 디버깅](https://github.com/Microsoft/MIEngine/wiki/Offroad-Debugging-of-.NET-Core-on-Linux---OSX-from-Visual-Studio)

 ASP.NET Core 앱을 디버깅하려면 약간 다른 지침이 필요합니다.

- [Visual Studio에서 ASP.NET Core 앱 디버그](/visualstudio/debugger/how-to-enable-debugging-for-aspnet-applications#debug-aspnet-core-apps)

## <a name="visual-studio-code-managed-debugger"></a>Visual Studio Code 관리형 디버거

**Visual Studio Code**는 간단한 플랫폼 간 코드 편집기입니다. Visual Studio와 동일한 .NET Core 디버거 구현을 사용하지만 사용자 인터페이스가 간소화되었습니다.

- [자습서 - Visual Studio Code를 사용하여 .NET Core 애플리케이션 디버깅](../tutorials/with-visual-studio-code.md#debug)
- [Visual Studio Code의 디버깅](https://code.visualstudio.com/docs/editor/debugging)
