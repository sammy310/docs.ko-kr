---
description: -refout(C# 컴파일러 옵션)
title: -refout(C# 컴파일러 옵션)
ms.date: 08/08/2017
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [C#]
- /refout compiler option [C#]
- -refout compiler option [C#]
ms.openlocfilehash: 424782e4607fea63130e95ab09a671c75fe1404d
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128716"
---
# <a name="-refout-c-compiler-options"></a><span data-ttu-id="433fc-103">-refout(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="433fc-103">-refout (C# Compiler Options)</span></span>

<span data-ttu-id="433fc-104">**-refout** 옵션은 참조 어셈블리가 출력되어야 하는 파일 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="433fc-104">The **-refout** option specifies a file path where the reference assembly should be output.</span></span> <span data-ttu-id="433fc-105">이것은 Emit API에서 `metadataPeStream`으로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="433fc-105">This translates to `metadataPeStream` in the Emit API.</span></span> <span data-ttu-id="433fc-106">이 옵션은 MSBuild의 [ProduceReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) 프로젝트 속성에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="433fc-106">This option corresponds to the [ProduceReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) project property of MSBuild.</span></span>

## <a name="syntax"></a><span data-ttu-id="433fc-107">구문</span><span class="sxs-lookup"><span data-stu-id="433fc-107">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="433fc-108">인수</span><span class="sxs-lookup"><span data-stu-id="433fc-108">Arguments</span></span>

 <span data-ttu-id="433fc-109">`filepath` 참조 어셈블리의 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="433fc-109">`filepath` The filepath for the reference assembly.</span></span> <span data-ttu-id="433fc-110">일반적으로 주 어셈블리의 경로와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="433fc-110">It should generally match that of the primary assembly.</span></span> <span data-ttu-id="433fc-111">권장되는 규칙(MSBuild에서 사용됨)은 주 어셈블리에 상대적으로 “ref/” sub-폴더에 참조 어셈블리를 배치하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="433fc-111">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span>

## <a name="remarks"></a><span data-ttu-id="433fc-112">설명</span><span class="sxs-lookup"><span data-stu-id="433fc-112">Remarks</span></span>

<span data-ttu-id="433fc-113">참조 어셈블리는 라이브러리의 퍼블릭 API 표면을 나타내는 데 필요한 최소한의 메타데이터만 포함하는 특수한 형식의 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="433fc-113">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="433fc-114">빌드 도구에서 어셈블리를 참조할 때 중요한 모든 멤버에 대한 선언을 포함하지만, 해당 API 계약에 영향을 미치지 않는 프라이빗 멤버의 선언과 모든 멤버 구현은 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="433fc-114">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="433fc-115">자세한 내용은 .NET 가이드에서 [참조 어셈블리](../../../standard/assembly/reference-assemblies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="433fc-115">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="433fc-116">`-refout` 및 [`-refonly`](refonly-compiler-option.md) 옵션은 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="433fc-116">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="433fc-117">참조</span><span class="sxs-lookup"><span data-stu-id="433fc-117">See also</span></span>

- [<span data-ttu-id="433fc-118">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="433fc-118">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="433fc-119">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="433fc-119">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
