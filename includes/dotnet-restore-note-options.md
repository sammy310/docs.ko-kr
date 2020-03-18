---
ms.openlocfilehash: 47811d3fab2e4fa531d383dfe818e3cac5613eb3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "72179971"
---
> [!NOTE]
> <span data-ttu-id="6d796-101">.NET Core 2.0부터 복원을 수행해야 하는 모든 명령(예: [ 및 `dotnet restore`)에서 암시적으로 실행되므로 ](~/docs/core/tools/dotnet-restore.md)`dotnet build``dotnet run`를 실행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6d796-101">Starting with .NET Core 2.0, you don't have to run [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) because it's run implicitly by all commands that require a restore to occur, such as `dotnet build` and `dotnet run`.</span></span> <span data-ttu-id="6d796-102">[Azure DevOps Services의 연속 통합 빌드](/azure/devops/build-release/apps/aspnet/build-aspnet-core)와 같이 명시적 복원을 수행하는 것이 올바른 특정 시나리오 또는 복원이 발생하는 시간을 명시적으로 제어해야 하는 빌드 시스템에서는 여전히 유효한 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="6d796-102">It's still a valid command in certain scenarios where doing an explicit restore makes sense, such as [continuous integration builds in Azure DevOps Services](/azure/devops/build-release/apps/aspnet/build-aspnet-core) or in build systems that need to explicitly control the time at which the restore occurs.</span></span>
>
> <span data-ttu-id="6d796-103">또한 이 명령은 긴 형식(예: `dotnet restore`)으로 전달될 때 `--source` 옵션도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="6d796-103">This command also supports the `dotnet restore` options when passed in the long form (for example, `--source`).</span></span> <span data-ttu-id="6d796-104">`-s`와 같이 짧은 형식의 옵션은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d796-104">Short form options, such as `-s`, are not supported.</span></span>
