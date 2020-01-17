---
title: 호환성이 손상되는 변경 사항 - .NET Framework에서 .NET Core로 변경
description: .NET Framework에서 .NET Core로의 호환성이 손상되는 변경 사항을 나열합니다.
ms.date: 12/18/2019
ms.openlocfilehash: 5c29636664632e80e4235e922a3296c34fdbef36
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900130"
---
# <a name="breaking-changes-for-migration-from-net-framework-to-net-core"></a><span data-ttu-id="e620a-103">.NET Framework에서 .NET Core로 마이그레이션 시 호환성이 손상되는 변경 사항</span><span class="sxs-lookup"><span data-stu-id="e620a-103">Breaking changes for migration from .NET Framework to .NET Core</span></span>

<span data-ttu-id="e620a-104">.NET Framework에서 .NET Core로 마이그레이션하는 경우, 다음 문서에 표시된 호환성이 손상되는 변경 사항이 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e620a-104">If you're migrating an app from .NET Framework to .NET Core, the breaking changes listed in this article may affect you.</span></span> <span data-ttu-id="e620a-105">호환성이 손상되는 변경 사항은 범주별로 그룹화됩니다.</span><span class="sxs-lookup"><span data-stu-id="e620a-105">Breaking changes are grouped by category.</span></span>

> [!NOTE]
> <span data-ttu-id="e620a-106">이 문서는 .NET Framework와 .NET Core 간 호환성이 손상되는 변경 사항의 전체 목록이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="e620a-106">This article is not a complete list of breaking changes between .NET Framework and .NET Core.</span></span> <span data-ttu-id="e620a-107">가장 중요한 호환성이 손상되는 변경 사항은 이를 인식하는 대로 여기에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="e620a-107">The most important breaking changes are added here as we become aware of them.</span></span>

## <a name="corefx"></a><span data-ttu-id="e620a-108">CoreFx</span><span class="sxs-lookup"><span data-stu-id="e620a-108">CoreFx</span></span>

[!INCLUDE[Process.Start changes](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

## <a name="windows-forms"></a><span data-ttu-id="e620a-109">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e620a-109">Windows Forms</span></span>

<span data-ttu-id="e620a-110">Windows Forms 앱을 .NET Framework에서 .NET Core 3.0 이상으로 마이그레이션하는 경우의 호환성이 손상되는 변경 사항에 대한 자세한 내용은 [Windows Forms의 호환성이 손상되는 변경 사항(.NET Framework에서 .NET Core로 변경)](../porting/winforms-breaking-changes.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e620a-110">For information about breaking changes when you migrate a Windows Forms app from .NET Framework to .NET Core 3.0 or later, see [Breaking changes in Windows Forms (.NET Framework to .NET Core)](../porting/winforms-breaking-changes.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e620a-111">참조</span><span class="sxs-lookup"><span data-stu-id="e620a-111">See also</span></span>

- [<span data-ttu-id="e620a-112">.NET Core에서 항상 예외를 throw하는 API</span><span class="sxs-lookup"><span data-stu-id="e620a-112">APIs that always throw exceptions on .NET Core</span></span>](unsupported-apis.md)
- [<span data-ttu-id="e620a-113">.NET Core에서 사용할 수 없는 .NET Framework 기술</span><span class="sxs-lookup"><span data-stu-id="e620a-113">.NET Framework technologies unavailable on .NET Core</span></span>](../porting/net-framework-tech-unavailable.md)
