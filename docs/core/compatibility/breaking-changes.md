---
title: .NET Core 호환성이 손상되는 변경 사항
description: 각 .NET Core 버전의 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 11/27/2019
ms.openlocfilehash: 8bd8ebc803a80069530fe1cf6adc66769f7d6c85
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900150"
---
# <a name="breaking-change-selectors"></a><span data-ttu-id="9745f-103">호환성이 손상되는 변경 선택기</span><span class="sxs-lookup"><span data-stu-id="9745f-103">Breaking change selectors</span></span>

<span data-ttu-id="9745f-104">다음 버전 및 영역 선택기는 다양한 버전의 .NET Core, ASP.NET Core 및 EF Core에 적용 가능하며 호환성이 손상되는 변경 사항을 필터링한 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9745f-104">The following version and area selectors provide a filtered list of applicable breaking changes between different versions of .NET Core, ASP.NET Core, and EF Core.</span></span> <span data-ttu-id="9745f-105">버전별로 찾아보거나 목차에서 문서를 범주화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9745f-105">You can also browse version to version or category articles in the table of contents.</span></span>

## <a name="by-version"></a><span data-ttu-id="9745f-106">버전별</span><span class="sxs-lookup"><span data-stu-id="9745f-106">By version</span></span>

<span data-ttu-id="9745f-107">현재 대상으로 하는 .NET 버전을 선택한 후 마이그레이션할 .NET Core 버전을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9745f-107">Select the .NET version that you're currently targeting and then the .NET Core version you wish to migrate to:</span></span>

[!INCLUDE[versionselector](~/includes/core-changes/versionselector.md)]

> [!TIP]
> <span data-ttu-id="9745f-108">Windows Forms 앱을 .NET Framework에서 .NET Core로 마이그레이션하는 경우 버전 선택기를 사용하는 대신 [Windows Forms의 호환성이 손상되는 변경(.NET Framework 에서 .NET Core로 변경)](../porting/winforms-breaking-changes.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9745f-108">If you're migrating a Windows Forms app from .NET Framework to .NET Core, see [Breaking changes in Windows Forms (.NET Framework to .NET Core)](../porting/winforms-breaking-changes.md) instead of using the version selector.</span></span>

## <a name="by-area"></a><span data-ttu-id="9745f-109">영역별</span><span class="sxs-lookup"><span data-stu-id="9745f-109">By area</span></span>

<span data-ttu-id="9745f-110">관심 있는 .NET Core 기술 영역을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9745f-110">Select the .NET Core technology area that you're interested in.</span></span> <span data-ttu-id="9745f-111">개별 변경 내용은 .NET Core 버전별로 정렬되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9745f-111">Individual changes are ordered by .NET Core version.</span></span>

[!INCLUDE[categoryselector](~/includes/core-changes/categoryselector.md)]

## <a name="github-issues-and-announcements"></a><span data-ttu-id="9745f-112">GitHub 문제 및 알림</span><span class="sxs-lookup"><span data-stu-id="9745f-112">GitHub issues and announcements</span></span>

<span data-ttu-id="9745f-113">.NET Core에 도입된 호환성이 손상되는 변경을 자세히 설명하는 개별 문제를 다음 GitHub 리포지토리에서 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9745f-113">You can also view individual issues that detail the breaking changes introduced in .NET Core in the following GitHub repositories:</span></span>

- <span data-ttu-id="9745f-114">.NET Core의 경우 [dotnet/docs](https://github.com/dotnet/docs/issues?q=is%3Aissue+label%3Abreaking-change) 리포지토리.</span><span class="sxs-lookup"><span data-stu-id="9745f-114">For .NET Core, the [dotnet/docs](https://github.com/dotnet/docs/issues?q=is%3Aissue+label%3Abreaking-change) repository.</span></span>
- <span data-ttu-id="9745f-115">ASP.NET Core의 경우 [aspnet/Announcements](https://github.com/aspnet/Announcements/issues?q=is%3Aissue+is%3Aopen+label%3A%22Breaking+change%22+label%3A3.0.0) 리포지토리.</span><span class="sxs-lookup"><span data-stu-id="9745f-115">For ASP.NET Core, the [aspnet/Announcements](https://github.com/aspnet/Announcements/issues?q=is%3Aissue+is%3Aopen+label%3A%22Breaking+change%22+label%3A3.0.0) repository.</span></span>
- <span data-ttu-id="9745f-116">Entity Framework Core의 경우 [dotnet/efcore](https://github.com/dotnet/efcore/issues?q=is%3Aopen+is%3Aissue+label%3Abreaking-change) 리포지토리.</span><span class="sxs-lookup"><span data-stu-id="9745f-116">For Entity Framework Core, the [dotnet/efcore](https://github.com/dotnet/efcore/issues?q=is%3Aopen+is%3Aissue+label%3Abreaking-change) repository.</span></span>

## <a name="see-also"></a><span data-ttu-id="9745f-117">참조</span><span class="sxs-lookup"><span data-stu-id="9745f-117">See also</span></span>

- [<span data-ttu-id="9745f-118">.NET Framework에서 .NET Core로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="9745f-118">Migrate from .NET Framework to .NET Core</span></span>](../porting/index.md)
