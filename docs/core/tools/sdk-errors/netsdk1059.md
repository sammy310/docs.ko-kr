---
title: 'NETSDK1059: 프로젝트에 사용되지 않는 .NET CLI 도구가 포함되어 있음'
description: 프로젝트에 사용되지 않는 .NET CLI 도구가 포함되어 있는 문제를 해결하는 방법입니다.
author: sfoslund
ms.topic: error-reference
ms.date: 10/09/2020
f1_keywords:
- NETSDK1059
ms.openlocfilehash: cad546ed1636b71be6b77aa00ef2f3a20095daa5
ms.sourcegitcommit: 1dbe25ff484a02025d5c34146e517c236f7161fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "104653038"
---
# <a name="netsdk1059-project-contains-obsolete-net-cli-tool"></a><span data-ttu-id="9316b-103">NETSDK1059: 프로젝트에 사용되지 않는 .NET CLI 도구가 포함되어 있음</span><span class="sxs-lookup"><span data-stu-id="9316b-103">NETSDK1059: Project contains obsolete .NET CLI tool</span></span>

<span data-ttu-id="9316b-104">**이 문서의 적용 대상:** ✔️ .NET Core 2.1.100 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="9316b-104">**This article applies to:** ✔️ .NET Core 2.1.100 SDK and later versions</span></span>

<span data-ttu-id="9316b-105">.NET SDK가 NETSDK1059 경고를 실행하는 경우 프로젝트에 사용되지 않는 .NET CLI 도구가 포함되어 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9316b-105">When the .NET SDK issues warning NETSDK1059, your project contains an obsolete .NET CLI tool.</span></span> <span data-ttu-id="9316b-106">.NET Core 2.1부터는 이러한 도구가 .NET SDK에 포함되며 프로젝트에서 명시적으로 참조할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9316b-106">As of .NET Core 2.1, these tools are included in the .NET SDK and do not need to be explicitly referenced by the project.</span></span> <span data-ttu-id="9316b-107">자세한 내용은 [이제 SDK에 프로젝트 도구가 포함됨](../../compatibility/2.1.md#project-tools-now-included-in-sdk)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9316b-107">For more information, see [Project tools now included in SDK](../../compatibility/2.1.md#project-tools-now-included-in-sdk).</span></span>
