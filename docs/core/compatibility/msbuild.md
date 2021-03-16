---
title: MSBuild 호환성이 손상되는 변경 사항
description: .NET Core 2.1~3.1용 MSBuild의 호환성이 손상되는 변경을 나열합니다.
ms.date: 02/22/2021
ms.openlocfilehash: 03fcd9807a83c4f679dc659b009c857e351b9b2d
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102105645"
---
# <a name="msbuild-breaking-changes-in-net-core-21---31"></a><span data-ttu-id="d10d7-103">.NET Core 2.1~3.1의 MSBuild 호환성이 손상되는 변경</span><span class="sxs-lookup"><span data-stu-id="d10d7-103">MSBuild breaking changes in .NET Core 2.1 - 3.1</span></span>

<span data-ttu-id="d10d7-104">이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d10d7-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="d10d7-105">주요 변경 내용</span><span class="sxs-lookup"><span data-stu-id="d10d7-105">Breaking change</span></span> | <span data-ttu-id="d10d7-106">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="d10d7-106">Version introduced</span></span> |
| - | - |
| [<span data-ttu-id="d10d7-107">디자인 타임 빌드는 최상위 패키지 참조만 반환</span><span class="sxs-lookup"><span data-stu-id="d10d7-107">Design-time builds only return top-level package references</span></span>](#design-time-builds-only-return-top-level-package-references) | <span data-ttu-id="d10d7-108">3.1</span><span class="sxs-lookup"><span data-stu-id="d10d7-108">3.1</span></span> |
| [<span data-ttu-id="d10d7-109">리소스 매니페스트 파일 이름 변경</span><span class="sxs-lookup"><span data-stu-id="d10d7-109">Resource manifest file name change</span></span>](#resource-manifest-file-name-change) | <span data-ttu-id="d10d7-110">3.0</span><span class="sxs-lookup"><span data-stu-id="d10d7-110">3.0</span></span> |
| [<span data-ttu-id="d10d7-111">이제 프로젝트 도구가 SDK에 포함됨</span><span class="sxs-lookup"><span data-stu-id="d10d7-111">Project tools now included in SDK</span></span>](#project-tools-now-included-in-sdk) | <span data-ttu-id="d10d7-112">2.1</span><span class="sxs-lookup"><span data-stu-id="d10d7-112">2.1</span></span> |

## <a name="net-core-31"></a><span data-ttu-id="d10d7-113">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="d10d7-113">.NET Core 3.1</span></span>

[!INCLUDE [design-time-builds-return-top-level-package-refs](../../../includes/core-changes/msbuild/3.1/design-time-builds-return-top-level-package-refs.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="d10d7-114">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d10d7-114">.NET Core 3.0</span></span>

[!INCLUDE[Resource file names](../../../includes/core-changes/msbuild/3.0/resource-manifest-name.md)]

***

## <a name="net-core-21"></a><span data-ttu-id="d10d7-115">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="d10d7-115">.NET Core 2.1</span></span>

[!INCLUDE [DotNetCliToolReference project elements removed for bundled tools](../../../includes/core-changes/msbuild/2.1/dotnetclitoolreference.md)]

***
