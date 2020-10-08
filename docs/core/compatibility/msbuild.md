---
title: MSBuild 호환성이 손상되는 변경 사항
description: .NET Core용 MSBuild의 호환성이 손상되는 변경 사항을 나열합니다.
ms.date: 02/10/2020
ms.openlocfilehash: b57c70d21e061c59f26b11a025d4d05ce3b8ca99
ms.sourcegitcommit: 4d45bda8cd9558ea8af4be591e3d5a29360c1ece
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2020
ms.locfileid: "91654741"
---
# <a name="msbuild-breaking-changes"></a><span data-ttu-id="bafeb-103">MSBuild 호환성이 손상되는 변경 사항</span><span class="sxs-lookup"><span data-stu-id="bafeb-103">MSBuild breaking changes</span></span>

<span data-ttu-id="bafeb-104">이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bafeb-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="bafeb-105">주요 변경 내용</span><span class="sxs-lookup"><span data-stu-id="bafeb-105">Breaking change</span></span> | <span data-ttu-id="bafeb-106">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="bafeb-106">Version introduced</span></span> |
| - | - |
| [<span data-ttu-id="bafeb-107">.NET 5를 대상으로 하는 경우 NETCOREAPP3_1 전처리기 기호가 정의되지 않음</span><span class="sxs-lookup"><span data-stu-id="bafeb-107">NETCOREAPP3_1 preprocessor symbol is not defined when targeting .NET 5</span></span>](#netcoreapp3_1-preprocessor-symbol-is-not-defined-when-targeting-net-5) | <span data-ttu-id="bafeb-108">5.0</span><span class="sxs-lookup"><span data-stu-id="bafeb-108">5.0</span></span> |
| [<span data-ttu-id="bafeb-109">PublishDepsFilePath 동작 변경</span><span class="sxs-lookup"><span data-stu-id="bafeb-109">PublishDepsFilePath behavior change</span></span>](#publishdepsfilepath-behavior-change) | <span data-ttu-id="bafeb-110">5.0</span><span class="sxs-lookup"><span data-stu-id="bafeb-110">5.0</span></span> |
| [<span data-ttu-id="bafeb-111">기본적으로 Directory.Packages.props 파일을 가져옴</span><span class="sxs-lookup"><span data-stu-id="bafeb-111">Directory.Packages.props files is imported by default</span></span>](#directorypackagesprops-files-is-imported-by-default) | <span data-ttu-id="bafeb-112">5.0</span><span class="sxs-lookup"><span data-stu-id="bafeb-112">5.0</span></span> |
| [<span data-ttu-id="bafeb-113">리소스 매니페스트 파일 이름 변경</span><span class="sxs-lookup"><span data-stu-id="bafeb-113">Resource manifest file name change</span></span>](#resource-manifest-file-name-change) | <span data-ttu-id="bafeb-114">3.0</span><span class="sxs-lookup"><span data-stu-id="bafeb-114">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="bafeb-115">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="bafeb-115">.NET 5.0</span></span>

[!INCLUDE [netcoreapp3_1-preprocessor-symbol-not-defined](../../../includes/core-changes/msbuild/5.0/netcoreapp3_1-preprocessor-symbol-not-defined.md)]

***

[!INCLUDE [publishdepsfilepath-behavior-change](../../../includes/core-changes/msbuild/5.0/publishdepsfilepath-behavior-change.md)]

***

[!INCLUDE [directory-packages-props-imported-by-default](../../../includes/core-changes/msbuild/5.0/directory-packages-props-imported-by-default.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="bafeb-116">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bafeb-116">.NET Core 3.0</span></span>

[!INCLUDE[Resource file names](~/includes/core-changes/msbuild/3.0/resource-manifest-name.md)]

***
