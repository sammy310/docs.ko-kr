---
title: -refout(C# 컴파일러 옵션)
ms.date: 08/08/2017
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [C#]
- /refout compiler option [C#]
- -refout compiler option [C#]
ms.openlocfilehash: f48316a1e6f657e3bd0190d269dfe0e875a833d9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "72771753"
---
# <a name="-refout-c-compiler-options"></a><span data-ttu-id="96faa-102">-refout(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="96faa-102">-refout (C# Compiler Options)</span></span>

<span data-ttu-id="96faa-103">**-refout** 옵션은 참조 어셈블리가 출력되어야 하는 파일 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="96faa-103">The **-refout** option specifies a file path where the reference assembly should be output.</span></span> <span data-ttu-id="96faa-104">이것은 Emit API에서 `metadataPeStream`으로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="96faa-104">This translates to `metadataPeStream` in the Emit API.</span></span> <span data-ttu-id="96faa-105">이 옵션은 MSBuild의 [ProduceReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) 프로젝트 속성에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="96faa-105">This option corresponds to the [ProduceReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) project property of MSBuild.</span></span>

## <a name="syntax"></a><span data-ttu-id="96faa-106">구문</span><span class="sxs-lookup"><span data-stu-id="96faa-106">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="96faa-107">인수</span><span class="sxs-lookup"><span data-stu-id="96faa-107">Arguments</span></span>

 <span data-ttu-id="96faa-108">`filepath` 참조 어셈블리의 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="96faa-108">`filepath` The filepath for the reference assembly.</span></span> <span data-ttu-id="96faa-109">일반적으로 주 어셈블리의 경로와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96faa-109">It should generally match that of the primary assembly.</span></span> <span data-ttu-id="96faa-110">권장되는 규칙(MSBuild에서 사용됨)은 주 어셈블리에 상대적으로 “ref/” sub-폴더에 참조 어셈블리를 배치하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="96faa-110">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span>

## <a name="remarks"></a><span data-ttu-id="96faa-111">설명</span><span class="sxs-lookup"><span data-stu-id="96faa-111">Remarks</span></span>

<span data-ttu-id="96faa-112">참조 어셈블리는 라이브러리의 퍼블릭 API 표면을 나타내는 데 필요한 최소한의 메타데이터만 포함하는 특수한 형식의 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="96faa-112">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="96faa-113">빌드 도구에서 어셈블리를 참조할 때 중요한 모든 멤버에 대한 선언을 포함하지만, 해당 API 계약에 영향을 미치지 않는 프라이빗 멤버의 선언과 모든 멤버 구현은 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="96faa-113">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="96faa-114">자세한 내용은 .NET 가이드에서 [참조 어셈블리](../../../standard/assembly/reference-assemblies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96faa-114">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="96faa-115">`-refout` 및 [`-refonly`](refonly-compiler-option.md) 옵션은 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="96faa-115">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="96faa-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="96faa-116">See also</span></span>

- [<span data-ttu-id="96faa-117">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="96faa-117">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="96faa-118">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="96faa-118">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
