---
title: MSBuild 호환성이 손상되는 변경 사항
description: .NET Core 3.0~3.1용 MSBuild의 호환성이 손상되는 변경을 나열합니다.
ms.date: 12/14/2020
ms.openlocfilehash: 1ed5878845406fa7727c644f1e196d63a860646a
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/16/2020
ms.locfileid: "97593450"
---
# <a name="msbuild-breaking-changes-in-net-core-30---31"></a><span data-ttu-id="1a6e1-103">.NET Core 3.0~3.1의 MSBuild 호환성이 손상되는 변경</span><span class="sxs-lookup"><span data-stu-id="1a6e1-103">MSBuild breaking changes in .NET Core 3.0 - 3.1</span></span>

<span data-ttu-id="1a6e1-104">이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a6e1-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="1a6e1-105">주요 변경 내용</span><span class="sxs-lookup"><span data-stu-id="1a6e1-105">Breaking change</span></span> | <span data-ttu-id="1a6e1-106">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="1a6e1-106">Version introduced</span></span> |
| - | - |
| [<span data-ttu-id="1a6e1-107">디자인 타임 빌드는 최상위 패키지 참조만 반환</span><span class="sxs-lookup"><span data-stu-id="1a6e1-107">Design-time builds only return top-level package references</span></span>](#design-time-builds-only-return-top-level-package-references) | <span data-ttu-id="1a6e1-108">3.1</span><span class="sxs-lookup"><span data-stu-id="1a6e1-108">3.1</span></span> |
| [<span data-ttu-id="1a6e1-109">리소스 매니페스트 파일 이름 변경</span><span class="sxs-lookup"><span data-stu-id="1a6e1-109">Resource manifest file name change</span></span>](#resource-manifest-file-name-change) | <span data-ttu-id="1a6e1-110">3.0</span><span class="sxs-lookup"><span data-stu-id="1a6e1-110">3.0</span></span> |

## <a name="net-core-31"></a><span data-ttu-id="1a6e1-111">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="1a6e1-111">.NET Core 3.1</span></span>

[!INCLUDE [design-time-builds-return-top-level-package-refs](../../../includes/core-changes/msbuild/3.1/design-time-builds-return-top-level-package-refs.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="1a6e1-112">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="1a6e1-112">.NET Core 3.0</span></span>

[!INCLUDE[Resource file names](~/includes/core-changes/msbuild/3.0/resource-manifest-name.md)]

***
