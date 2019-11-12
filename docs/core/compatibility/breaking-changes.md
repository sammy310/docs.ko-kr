---
title: .NET Core 호환성이 손상되는 변경 사항
description: 각 .NET Core 버전의 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 08/12/2019
ms.openlocfilehash: 92ebb627240bce3d9b20dca51263732d1856c2a4
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739771"
---
# <a name="net-core-breaking-changes"></a><span data-ttu-id="15d57-103">.NET Core 호환성이 손상되는 변경 사항</span><span class="sxs-lookup"><span data-stu-id="15d57-103">.NET Core breaking changes</span></span>

<span data-ttu-id="15d57-104">다음 버전 선택기는 .NET Core, ASP.NET Core, EF Core에 적용되는 호환성이 손상되는 변경 사항의 필터링된 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="15d57-104">The following version selector provides a filtered list of breaking changes for .NET Core, ASP.NET Core, and EF Core.</span></span> <span data-ttu-id="15d57-105">대상 버전에는 .NET Core 2.2 및 .NET Core 3.0과 같은 주 릴리스 뿐만 아니라 .NET Core 3.0 미리 보기 7과 같은 미리 보기 릴리스도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="15d57-105">The target versions include not only major releases, such as .NET Core 2.2 and .NET Core 3.0, but also preview releases, such as .NET Core 3.0 Preview 7.</span></span>

<span data-ttu-id="15d57-106">.NET Core에 도입된 호환성이 손상되는 변경을 자세히 설명하는 개별 문제를 다음 GitHub 리포지토리에서 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15d57-106">You can also view individual issues that detail the breaking changes introduced in .NET Core in the following GitHub repositories:</span></span>

- <span data-ttu-id="15d57-107">.NET Core의 경우 [dotnet/docs](https://github.com/dotnet/docs/issues?q=is%3Aissue+label%3Abreaking-change) 리포지토리.</span><span class="sxs-lookup"><span data-stu-id="15d57-107">For .NET Core, the [dotnet/docs](https://github.com/dotnet/docs/issues?q=is%3Aissue+label%3Abreaking-change) repository.</span></span>
- <span data-ttu-id="15d57-108">ASP.NET Core의 경우 [aspnet/Announcements](https://github.com/aspnet/Announcements/issues?q=is%3Aissue+is%3Aopen+label%3A%22Breaking+change%22+label%3A3.0.0) 리포지토리.</span><span class="sxs-lookup"><span data-stu-id="15d57-108">For ASP.NET Core, the [aspnet/Announcements](https://github.com/aspnet/Announcements/issues?q=is%3Aissue+is%3Aopen+label%3A%22Breaking+change%22+label%3A3.0.0) repository.</span></span>
- <span data-ttu-id="15d57-109">Entity Framework Core의 경우 [aspnet/EntityFrameworkCore](https://github.com/aspnet/EntityFrameworkCore/issues?q=is%3Aopen+is%3Aissue+label%3Abreaking-change) 리포지토리.</span><span class="sxs-lookup"><span data-stu-id="15d57-109">For Entity Framework Core, the [aspnet/EntityFrameworkCore](https://github.com/aspnet/EntityFrameworkCore/issues?q=is%3Aopen+is%3Aissue+label%3Abreaking-change) repository.</span></span>

## <a name="breaking-changes-by-version"></a><span data-ttu-id="15d57-110">버전별 호환성이 손상되는 변경 사항</span><span class="sxs-lookup"><span data-stu-id="15d57-110">Breaking changes by version</span></span>

<span data-ttu-id="15d57-111">현재 대상으로 하는 .NET Core 버전을 선택한 후 마이그레이션할 .NET Core 버전을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="15d57-111">Select the .NET Core version that you're currently targeting and then the .NET Core version you wish to migrate to:</span></span>

[!INCLUDE[versionselector](~/includes/core-changes/versionselector.md)]

## <a name="breaking-changes-by-category"></a><span data-ttu-id="15d57-112">범주별 호환성이 손상되는 변경</span><span class="sxs-lookup"><span data-stu-id="15d57-112">Breaking changes by category</span></span>

<span data-ttu-id="15d57-113">관심 있는 .NET Core 기술 영역을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="15d57-113">Select the .NET Core technology area that you're interested in.</span></span> <span data-ttu-id="15d57-114">개별 변경 내용은 .NET Core 버전별로 정렬되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15d57-114">Individual changes are ordered by .NET Core version.</span></span>

[!INCLUDE[cateegoryselector](~/includes/core-changes/categoryselector.md)]
