---
description: -refonly(C# 컴파일러 옵션)
title: -refonly(C# 컴파일러 옵션)
ms.date: 07/08/2017
f1_keywords:
- /refonly
helpviewer_keywords:
- /refonly compiler option [C#]
- -refonly compiler option [C#]
- refonly compiler option [C#]
ms.openlocfilehash: f9a92462203bedff93a4a711ca8742465b7a561c
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89124749"
---
# <a name="-refonly-c-compiler-options"></a><span data-ttu-id="aeda3-103">-refonly(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="aeda3-103">-refonly (C# Compiler Options)</span></span>

<span data-ttu-id="aeda3-104">**-refonly** 옵션은 구현 어셈블리 대신 참조 어셈블리가 기본 출력으로 출력되어야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="aeda3-104">The **-refonly** option indicates that a reference assembly should be output instead of an implementation assembly, as the primary output.</span></span> <span data-ttu-id="aeda3-105">`-refonly` 매개 변수는 참조 어셈블리가 실행될 수 없을 때 PDB 출력을 자동으로 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="aeda3-105">The `-refonly` parameter silently disables outputting PDBs, as reference assemblies cannot be executed.</span></span> <span data-ttu-id="aeda3-106">이 옵션은 MSBuild의 [ProduceOnlyReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) 프로젝트 속성에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="aeda3-106">This option corresponds to the [ProduceOnlyReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) project property of MSBuild.</span></span>

## <a name="syntax"></a><span data-ttu-id="aeda3-107">구문</span><span class="sxs-lookup"><span data-stu-id="aeda3-107">Syntax</span></span>

```console
-refonly
```

## <a name="remarks"></a><span data-ttu-id="aeda3-108">설명</span><span class="sxs-lookup"><span data-stu-id="aeda3-108">Remarks</span></span>

<span data-ttu-id="aeda3-109">참조 어셈블리는 라이브러리의 퍼블릭 API 표면을 나타내는 데 필요한 최소한의 메타데이터만 포함하는 특수한 형식의 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="aeda3-109">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="aeda3-110">빌드 도구에서 어셈블리를 참조할 때 중요한 모든 멤버에 대한 선언을 포함하지만, 해당 API 계약에 영향을 미치지 않는 프라이빗 멤버의 선언과 모든 멤버 구현은 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="aeda3-110">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="aeda3-111">자세한 내용은 .NET 가이드에서 [참조 어셈블리](../../../standard/assembly/reference-assemblies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aeda3-111">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="aeda3-112">`-refonly` 및 [`-refout`](refout-compiler-option.md) 옵션은 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aeda3-112">The `-refonly` and [`-refout`](refout-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="aeda3-113">참조</span><span class="sxs-lookup"><span data-stu-id="aeda3-113">See also</span></span>

- [<span data-ttu-id="aeda3-114">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="aeda3-114">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="aeda3-115">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="aeda3-115">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
