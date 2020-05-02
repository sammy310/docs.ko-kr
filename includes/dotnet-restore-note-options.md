---
ms.openlocfilehash: 6c04437c2a211b244e6c5eda0893b267c59668e9
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102773"
---
<span data-ttu-id="84592-101">`dotnet new`, `dotnet build`, `dotnet run`, `dotnet test`, `dotnet publish` 및 `dotnet pack` 등 복원이 필요한 모든 명령에 의해 암시적으로 실행되므로 [`dotnet restore`](~/docs/core/tools/dotnet-restore.md)를 실행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84592-101">You don't have to run [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) because it's run implicitly by all commands that require a restore to occur, such as `dotnet new`, `dotnet build`, `dotnet run`, `dotnet test`, `dotnet publish`, and `dotnet pack`.</span></span> <span data-ttu-id="84592-102">암시적 복원을 사용하지 않으려면 `--no-restore` 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="84592-102">To disable implicit restore, use the `--no-restore` option.</span></span>

<span data-ttu-id="84592-103">`dotnet restore` 명령은 [Azure DevOps Services의 연속 통합 빌드](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core) 또는 복원 발생 시점을 명시적으로 제어해야 하는 빌드 시스템과 같이 명시적으로 복원이 가능한 특정 시나리오에서 여전히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="84592-103">The `dotnet restore` command is still useful in certain scenarios where explicitly restoring makes sense, such as [continuous integration builds in Azure DevOps Services](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core) or in build systems that need to explicitly control when the restore occurs.</span></span>

<span data-ttu-id="84592-104">NuGet 피드를 관리하는 방법에 대한 자세한 내용은 [`dotnet restore` 설명서](../docs/core/tools/dotnet-restore.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84592-104">For information about how to manage NuGet feeds, see the [`dotnet restore` documentation](../docs/core/tools/dotnet-restore.md).</span></span>

<span data-ttu-id="84592-105">이 명령은 긴 형식(예: `--source`)으로 전달될 때 `dotnet restore` 옵션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="84592-105">This command supports the `dotnet restore` options when passed in the long form (for example, `--source`).</span></span> <span data-ttu-id="84592-106">`-s`와 같이 짧은 형식의 옵션은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84592-106">Short form options, such as `-s`, are not supported.</span></span>
