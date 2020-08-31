---
title: 호환성이 손상되는 변경
description: 각 .NET Core 버전의 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 11/27/2019
ms.openlocfilehash: 73c1576aa92f0e236ead0ca1a12ac26efcbf3cbe
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88810900"
---
# <a name="breaking-change-selectors"></a><span data-ttu-id="e4792-103">호환성이 손상되는 변경 선택기</span><span class="sxs-lookup"><span data-stu-id="e4792-103">Breaking change selectors</span></span>

<span data-ttu-id="e4792-104">다음 버전 및 영역 선택기는 다양한 버전의 .NET Core, ASP.NET Core 및 EF Core에 적용 가능하며 호환성이 손상되는 변경 사항을 필터링한 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e4792-104">The following version and area selectors provide a filtered list of applicable breaking changes between different versions of .NET Core, ASP.NET Core, and EF Core.</span></span> <span data-ttu-id="e4792-105">목차에서 버전별 또는 기술 영역별로 문서를 찾아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4792-105">You can also browse version-to-version or technology area articles in the table of contents.</span></span>

## <a name="by-version"></a><span data-ttu-id="e4792-106">버전별</span><span class="sxs-lookup"><span data-stu-id="e4792-106">By version</span></span>

<span data-ttu-id="e4792-107">현재 대상으로 하는 .NET 버전을 선택한 후 마이그레이션할 .NET Core 버전을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e4792-107">Select the .NET version that you're currently targeting and then the .NET Core version you wish to migrate to:</span></span>

> [!div class="op_multi_selector" title1="대상 버전" title2="마이그레이션된 버전"]
>
> - [(3.1 | 5.0)](3.1-5.0.md)
> - [(3.0 | 3.1)](3.0-3.1.md)
> - [(2.2 | 3.1)](2.2-3.1.md)
> - [(2.2 | 3.0)](2.2-3.0.md)
> - [(2.0 | 2.1)](2.0-2.1.md)
> - [(.NET Framework | .NET Core)](fx-core.md)

## <a name="by-technology-area"></a><span data-ttu-id="e4792-116">기술 영역별</span><span class="sxs-lookup"><span data-stu-id="e4792-116">By technology area</span></span>

<span data-ttu-id="e4792-117">관심 있는 .NET Core 기술 영역을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e4792-117">Select the .NET Core technology area that you're interested in.</span></span> <span data-ttu-id="e4792-118">개별 변경 내용은 .NET Core 버전별로 정렬되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4792-118">Individual changes are ordered by .NET Core version.</span></span>

> [!div class="op_single_selector"]
>
> - [ASP.NET Core](aspnetcore.md)
> - [코드 분석](code-analysis.md)
> - [핵심 .NET 라이브러리](corefx.md)
> - [암호화](cryptography.md)
> - [EF Core](/ef/core/what-is-new/ef-core-3.0/breaking-changes)
> - [전역화](globalization.md)
> - [Interop](interop.md)
> - [네트워킹](networking.md)
> - [serialization](serialization.md)
> - [Visual Basic](visualbasic.md)
> - [Windows Forms](winforms.md)

## <a name="github-issues-and-announcements"></a><span data-ttu-id="e4792-130">GitHub 문제 및 알림</span><span class="sxs-lookup"><span data-stu-id="e4792-130">GitHub issues and announcements</span></span>

<span data-ttu-id="e4792-131">.NET Core에 도입된 호환성이 손상되는 변경을 자세히 설명하는 개별 문제를 다음 GitHub 리포지토리에서 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4792-131">You can also view individual issues that detail the breaking changes introduced in .NET Core in the following GitHub repositories:</span></span>

- <span data-ttu-id="e4792-132">.NET Core의 경우 [dotnet/docs](https://github.com/dotnet/docs/issues?q=is%3Aissue+label%3Abreaking-change) 리포지토리.</span><span class="sxs-lookup"><span data-stu-id="e4792-132">For .NET Core, the [dotnet/docs](https://github.com/dotnet/docs/issues?q=is%3Aissue+label%3Abreaking-change) repository.</span></span>
- <span data-ttu-id="e4792-133">ASP.NET Core의 경우 [aspnet/Announcements](https://github.com/aspnet/Announcements/issues?q=is%3Aissue+is%3Aopen+label%3A%22Breaking+change%22+label%3A3.0.0) 리포지토리.</span><span class="sxs-lookup"><span data-stu-id="e4792-133">For ASP.NET Core, the [aspnet/Announcements](https://github.com/aspnet/Announcements/issues?q=is%3Aissue+is%3Aopen+label%3A%22Breaking+change%22+label%3A3.0.0) repository.</span></span>
- <span data-ttu-id="e4792-134">Entity Framework Core의 경우 [dotnet/efcore](https://github.com/dotnet/efcore/issues?q=is%3Aopen+is%3Aissue+label%3Abreaking-change) 리포지토리.</span><span class="sxs-lookup"><span data-stu-id="e4792-134">For Entity Framework Core, the [dotnet/efcore](https://github.com/dotnet/efcore/issues?q=is%3Aopen+is%3Aissue+label%3Abreaking-change) repository.</span></span>

## <a name="see-also"></a><span data-ttu-id="e4792-135">참조</span><span class="sxs-lookup"><span data-stu-id="e4792-135">See also</span></span>

- [<span data-ttu-id="e4792-136">.NET Framework에서 .NET Core로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="e4792-136">Migrate from .NET Framework to .NET Core</span></span>](../porting/index.md)
