---
ms.openlocfilehash: e140b375f4f289df895052aa093f03f381d62488
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102746"
---
`dotnet new`, `dotnet build`, `dotnet run`, `dotnet test`, `dotnet publish` 및 `dotnet pack` 등 복원이 필요한 모든 명령에 의해 암시적으로 실행되므로 [`dotnet restore`](~/docs/core/tools/dotnet-restore.md)를 실행할 필요가 없습니다. 암시적 복원을 사용하지 않으려면 `--no-restore` 옵션을 사용합니다.

`dotnet restore` 명령은 [Azure DevOps Services의 연속 통합 빌드](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core) 또는 복원 발생 시점을 명시적으로 제어해야 하는 빌드 시스템과 같이 명시적으로 복원이 가능한 특정 시나리오에서 여전히 유용합니다.

NuGet 피드를 관리하는 방법에 대한 자세한 내용은 [`dotnet restore` 설명서](../docs/core/tools/dotnet-restore.md)를 참조하세요.
