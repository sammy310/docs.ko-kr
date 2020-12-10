---
title: VS Code 확장 작성자용 .NET 설치 도구
description: .NET 런타임 설치를 위한 Visual Studio Code 확장인 확장 작성자용 .NET 설치 도구에 대한 개요입니다.
author: sfoslund
ms.date: 11/18/2020
ms.openlocfilehash: 37be1b9dcdb9fba99554800fea23f28443efb5fa
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599901"
---
# <a name="net-install-tool-for-extension-authors"></a>확장 작성자용 .NET 설치 도구

[확장 작성자용 .NET 설치 도구](https://github.com/dotnet/vscode-dotnet-runtime)는 VS Code 확장 작성자를 위해 특별히 .NET 런타임 획득을 허용하는 Visual Studio Code 확장입니다. 이 도구는 .NET에서 작성된 확장에 활용되며 확장(예: 언어 서버)을 부팅하기 위해 .NET이 필요합니다. 확장은 사용자가 개발용 .NET을 설치하는 데 직접 사용하기 위한 것이 아닙니다.

## <a name="getting-started-extension-authors"></a>시작: 확장 작성자

확장 작성자용 .NET 설치 도구가 사용자의 시나리오에 적합한지 확인하려면 먼저 GitHub 페이지에서 [이 확장의 목표](https://github.com/dotnet/vscode-dotnet-runtime#goals-acquiring-net-core-for-extensions)를 검토하세요.

> [!NOTE]
> 이 도구는 .NET 런타임 설치에만 사용할 수 있으며, 현재 .NET SDK를 설치하는 기능은 없습니다.

확장 작성자용 .NET 설치 도구가 사용자의 요구에 적합한 것을 확인했다면 [확장 매니페스트](https://code.visualstudio.com/api/references/extension-manifest)에서 해당 종속성을 가져오고 [VS Code API](https://code.visualstudio.com/api/extension-guides/command#programmatically-executing-a-command)에 표시되는 명령을 사용하여 시작할 수 있습니다. [GitHub](https://github.com/dotnet/vscode-dotnet-runtime/blob/master/Documentation/commands.md)에서 이 확장이 표시하는 명령 목록을 찾을 수 있습니다.

이러한 단계를 수행하는 방법은 이 [샘플 확장](https://github.com/dotnet/vscode-dotnet-runtime/tree/master/sample)을 참조하세요.

더 많은 예제를 보려면 현재 이 도구를 활용하는 오픈 소스 확장을 확인하세요.

- [Visual Studio Code용 Azure Resource Manager(ARM) 도구](https://github.com/microsoft/vscode-azurearmtools)

- [.NET Interactive Notebook](https://github.com/dotnet/interactive/tree/main/src/dotnet-interactive-vscode)

## <a name="getting-started-end-users"></a>시작: 최종 사용자

일반적으로 최종 사용자는 확장 작성자용 .NET 설치 도구와 상호 작용할 필요가 없습니다. 확장에 문제가 있는 경우 [문제 해결 페이지](https://github.com/dotnet/vscode-dotnet-runtime/blob/master/Documentation/troubleshooting.md)를 확인하거나 [GitHub](https://github.com/dotnet/vscode-dotnet-runtime/issues)에서 문제를 제출하세요.
