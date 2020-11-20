---
title: 'NETSDK1079: Microsoft.AspNetCore.All 패키지는 .NET Core 3.0 이상을 대상으로 지정하는 경우 지원되지 않습니다.'
description: Microsoft.AspNetCore.App에서 마이그레이션을 확인하는 방법
author: dsplaisted
ms.topic: error-reference
ms.date: 10/09/2020
f1_keywords:
- NETSDK1079
ms.openlocfilehash: e0b7aba909dbd2931f755238a2de2418d294751d
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94445705"
---
# <a name="netsdk1079-the-microsoftaspnetcoreall-package-is-not-supported-when-targeting-net-core-30-or-higher"></a><span data-ttu-id="a881f-103">NETSDK1079: Microsoft.AspNetCore.All 패키지는 .NET Core 3.0 이상을 대상으로 지정하는 경우 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a881f-103">NETSDK1079: The Microsoft.AspNetCore.All package is not supported when targeting .NET Core 3.0 or higher.</span></span>

<span data-ttu-id="a881f-104">**이 문서의 적용 대상:** ✔️ .NET Core SDK 3.1.100 이상 버전</span><span class="sxs-lookup"><span data-stu-id="a881f-104">**This article applies to:** ✔️ .NET Core SDK 3.1.100 and later versions</span></span>

<span data-ttu-id="a881f-105">다음과 같은 경우 이 오류 메시지가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a881f-105">You may receive this error message when:</span></span>

- <span data-ttu-id="a881f-106">ASP.NET Core 프로젝트의 대상을 .NET Core 2.2 이전 버전에서 .NET Core 3.0 이상 버전으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a881f-106">You retarget an ASP.NET Core project from .NET Core 2.2 or earlier to .NET Core 3.0 or later.</span></span>
- <span data-ttu-id="a881f-107">프로젝트는 Microsoft.AspNetCore.All 패키지를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a881f-107">The project uses the Microsoft.AspNetCore.All package.</span></span>

<span data-ttu-id="a881f-108">Microsoft.AspNetCore.All에 대한 `PackageReference`를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="a881f-108">Remove the `PackageReference` for Microsoft.AspNetCore.All.</span></span>  <span data-ttu-id="a881f-109">Microsoft.AspNetCore.All에서 참조되었지만 ASP.NET Core 공유 프레임워크에 포함되지 않은 패키지에 대한 패키지 참조를 추가해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a881f-109">You may also need to add package references for packages that were referenced from Microsoft.AspNetCore.All but are not included in the ASP.NET Core shared framework.</span></span>  <span data-ttu-id="a881f-110">이러한 패키지는 다음에 나열되어 있습니다. [Microsoft.AspNetCore.All에서 Microsoft.AspNetCore.App으로 마이그레이션](/aspnet/core/fundamentals/metapackage#migrating-from-microsoftaspnetcoreall-to-microsoftaspnetcoreapp)</span><span class="sxs-lookup"><span data-stu-id="a881f-110">These packages are listed here: [Migrating from Microsoft.AspNetCore.All to Microsoft.AspNetCore.App](/aspnet/core/fundamentals/metapackage#migrating-from-microsoftaspnetcoreall-to-microsoftaspnetcoreapp).</span></span>

<span data-ttu-id="a881f-111">[ASP.NET Core 2.2에서 3.0으로 마이그레이션](/aspnet/core/migration/22-to-30)도 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a881f-111">See also [Migrate from ASP.NET Core 2.2 to 3.0](/aspnet/core/migration/22-to-30)</span></span>
