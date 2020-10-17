---
title: 'NETSDK1059: 프로젝트에 사용되지 않는 .NET CLI 도구가 포함되어 있음'
description: 프로젝트에 사용되지 않는 .NET CLI 도구가 포함되어 있는 문제를 해결하는 방법입니다.
author: sfoslund
ms.topic: error-reference
ms.date: 10/09/2020
f1_keywords:
- NETSDK1059
ms.openlocfilehash: 2960b9255dab9e61a84e49bc029666753d8c9a1e
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2020
ms.locfileid: "91957099"
---
# <a name="netsdk1059-project-contains-obsolete-net-cli-tool"></a><span data-ttu-id="8d5a5-103">NETSDK1059: 프로젝트에 사용되지 않는 .NET CLI 도구가 포함되어 있음</span><span class="sxs-lookup"><span data-stu-id="8d5a5-103">NETSDK1059: Project contains obsolete .NET CLI tool</span></span>

<span data-ttu-id="8d5a5-104">**이 문서의 적용 대상:** ✔️ .NET 2.1.100 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="8d5a5-104">**This article applies to:** ✔️ .NET 2.1.100 SDK and later versions</span></span>

<span data-ttu-id="8d5a5-105">.NET SDK가 NETSDK1059 경고를 실행하는 경우 프로젝트에 사용되지 않는 .NET CLI 도구가 포함되어 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8d5a5-105">When the .NET SDK issues warning NETSDK1059, your project contains an obsolete .NET CLI tool.</span></span> <span data-ttu-id="8d5a5-106">.NET 2.1을 기준으로 .NET SDK에 포함된 해당 도구는 프로젝트에서 명시적으로 참조할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8d5a5-106">As of .NET 2.1, these tools are included in the .NET SDK and do not need to be explicitly referenced by the project.</span></span> <span data-ttu-id="8d5a5-107">.NET 2.1로 마이그레이션하는 방법에 대한 자세한 내용은 [여기](https://aka.ms/dotnetclitools-in-box)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d5a5-107">More information for migrating to .NET 2.1 can be found [here](https://aka.ms/dotnetclitools-in-box).</span></span>
