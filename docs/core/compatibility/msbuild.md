---
title: MSBuild 호환성이 손상되는 변경 사항
description: .NET Core용 MSBuild의 호환성이 손상되는 변경 사항을 나열합니다.
ms.date: 02/10/2020
ms.openlocfilehash: 7493516dff68b8bd45740c9877ebf21886e667ff
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679331"
---
# <a name="msbuild-breaking-changes"></a><span data-ttu-id="0ad16-103">MSBuild 호환성이 손상되는 변경 사항</span><span class="sxs-lookup"><span data-stu-id="0ad16-103">MSBuild breaking changes</span></span>

<span data-ttu-id="0ad16-104">이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ad16-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="0ad16-105">주요 변경 내용</span><span class="sxs-lookup"><span data-stu-id="0ad16-105">Breaking change</span></span> | <span data-ttu-id="0ad16-106">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="0ad16-106">Version introduced</span></span> |
| - | - |
| [<span data-ttu-id="0ad16-107">PublishDepsFilePath 동작 변경</span><span class="sxs-lookup"><span data-stu-id="0ad16-107">PublishDepsFilePath behavior change</span></span>](#publishdepsfilepath-behavior-change) | <span data-ttu-id="0ad16-108">5.0</span><span class="sxs-lookup"><span data-stu-id="0ad16-108">5.0</span></span> |
| [<span data-ttu-id="0ad16-109">기본적으로 Directory.Packages.props 파일을 가져옴</span><span class="sxs-lookup"><span data-stu-id="0ad16-109">Directory.Packages.props files is imported by default</span></span>](#directorypackagesprops-files-is-imported-by-default) | <span data-ttu-id="0ad16-110">5.0</span><span class="sxs-lookup"><span data-stu-id="0ad16-110">5.0</span></span> |
| [<span data-ttu-id="0ad16-111">리소스 매니페스트 파일 이름 변경</span><span class="sxs-lookup"><span data-stu-id="0ad16-111">Resource manifest file name change</span></span>](#resource-manifest-file-name-change) | <span data-ttu-id="0ad16-112">3.0</span><span class="sxs-lookup"><span data-stu-id="0ad16-112">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="0ad16-113">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="0ad16-113">.NET 5.0</span></span>

[!INCLUDE [publishdepsfilepath-behavior-change](../../../includes/core-changes/msbuild/5.0/publishdepsfilepath-behavior-change.md)]

***

[!INCLUDE [directory-packages-props-imported-by-default](../../../includes/core-changes/msbuild/5.0/directory-packages-props-imported-by-default.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="0ad16-114">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="0ad16-114">.NET Core 3.0</span></span>

[!INCLUDE[Resource file names](~/includes/core-changes/msbuild/3.0/resource-manifest-name.md)]

***
