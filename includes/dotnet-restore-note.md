---
ms.openlocfilehash: 975edd1bda507b46da353db788d9730560f9b573
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632100"
---
> [!NOTE]
> <span data-ttu-id="1807c-101">.NET Core 2.0 SDK부터 복원을 수행해야 하는 모든 명령(예: `dotnet new`, `dotnet build` 및 `dotnet run`)에서 암시적으로 실행되므로 [`dotnet restore`](~/docs/core/tools/dotnet-restore.md)를 실행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1807c-101">Starting with .NET Core 2.0 SDK, you don't have to run [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) because it's run implicitly by all commands that require a restore to occur, such as `dotnet new`, `dotnet build` and `dotnet run`.</span></span>
> <span data-ttu-id="1807c-102">[Azure DevOps Services의 연속 통합 빌드](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core)와 같이 명시적 복원을 수행하는 것이 올바른 특정 시나리오 또는 복원이 발생하는 시간을 명시적으로 제어해야 하는 빌드 시스템에서는 여전히 유효한 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="1807c-102">It's still a valid command in certain scenarios where doing an explicit restore makes sense, such as [continuous integration builds in Azure DevOps Services](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core) or in build systems that need to explicitly control the time at which the restore occurs.</span></span>
