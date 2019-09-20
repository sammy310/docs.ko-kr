---
title: .NET Core 호환성이 손상되는 변경 사항
description: 각 .NET Core 버전의 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 08/12/2019
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 48fc489e20e7f743b94085cfd6bfdac76812d068
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70930013"
---
# <a name="net-core-breaking-changes"></a><span data-ttu-id="789cf-103">.NET Core 호환성이 손상되는 변경 사항</span><span class="sxs-lookup"><span data-stu-id="789cf-103">.NET Core breaking changes</span></span>

<span data-ttu-id="789cf-104">다음 버전 선택기는 .NET Core, ASP.NET Core, EF Core에 적용되는 호환성이 손상되는 변경 사항의 필터링된 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="789cf-104">The following version selector provides a filtered list of breaking changes for .NET Core, ASP.NET Core, and EF Core.</span></span> <span data-ttu-id="789cf-105">대상 버전에는 .NET Core 2.2 및 .NET Core 3.0과 같은 주 릴리스 뿐만 아니라 .NET Core 3.0 미리 보기 7과 같은 미리 보기 릴리스도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="789cf-105">The target versions include not only major releases, such as .NET Core 2.2 and .NET Core 3.0, but also preview releases, such as .NET Core 3.0 Preview 7.</span></span>

<span data-ttu-id="789cf-106">다음 GitHub 리포지토리에서 호환성이 손상되는 변경에 대해 자세히 설명하는 개별 문제를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="789cf-106">You can also view individual issues that detail the breaking changes in the following GitHub repositories:</span></span>

- <span data-ttu-id="789cf-107">.NET Core의 경우 [dotnet/docs](https://github.com/dotnet/docs/issues?q=is%3Aopen+is%3Aissue+label%3Abreaking-change) 리포지토리.</span><span class="sxs-lookup"><span data-stu-id="789cf-107">For .NET Core, the [dotnet/docs](https://github.com/dotnet/docs/issues?q=is%3Aopen+is%3Aissue+label%3Abreaking-change) repo.</span></span>
- <span data-ttu-id="789cf-108">ASP.NET Core의 경우 [aspnet/AspNetCore](https://github.com/aspnet/AspNetCore/issues?q=is%3Aopen+is%3Aissue+label%3Abreaking-change) 리포지토리.</span><span class="sxs-lookup"><span data-stu-id="789cf-108">For ASP.NET Core, the [aspnet/AspNetCore](https://github.com/aspnet/AspNetCore/issues?q=is%3Aopen+is%3Aissue+label%3Abreaking-change) repo.</span></span>
- <span data-ttu-id="789cf-109">Entity Framework Core의 경우 [aspnet/EntityFrameworkCore](https://github.com/aspnet/EntityFrameworkCore/issues?q=is%3Aopen+is%3Aissue+label%3Abreaking-change) 리포지토리.</span><span class="sxs-lookup"><span data-stu-id="789cf-109">For Entity Framework Core, the [aspnet/EntityFrameworkCore](https://github.com/aspnet/EntityFrameworkCore/issues?q=is%3Aopen+is%3Aissue+label%3Abreaking-change) repo.</span></span>

## <a name="breaking-changes-by-version"></a><span data-ttu-id="789cf-110">버전별 호환성이 손상되는 변경 사항</span><span class="sxs-lookup"><span data-stu-id="789cf-110">Breaking changes by version</span></span>

<span data-ttu-id="789cf-111">현재 대상으로 하는 .NET Core 버전을 선택한 후 마이그레이션할 .NET Core 버전을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="789cf-111">Select the .NET Core version that you are currently targeting and then the .NET Core version you wish to migrate to:</span></span>

[!INCLUDE[versionselector](~/includes/core-changes/versionselector.md)]
