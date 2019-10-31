---
title: -refonly(C# 컴파일러 옵션)
ms.date: 07/08/2017
f1_keywords:
- /refonly
helpviewer_keywords:
- /refonly compiler option [C#]
- -refonly compiler option [C#]
- refonly compiler option [C#]
ms.openlocfilehash: 856b65d3b2217dbe5d53ecda00723b47247d80a4
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72773846"
---
# <a name="-refonly-c-compiler-options"></a><span data-ttu-id="c659e-102">-refonly(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="c659e-102">-refonly (C# Compiler Options)</span></span>

<span data-ttu-id="c659e-103">**-refonly** 옵션은 구현 어셈블리 대신 참조 어셈블리가 기본 출력으로 출력되어야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c659e-103">The **-refonly** option indicates that a reference assembly should be output instead of an implementation assembly, as the primary output.</span></span> <span data-ttu-id="c659e-104">`-refonly` 매개 변수는 참조 어셈블리가 실행될 수 없을 때 PDB 출력을 자동으로 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c659e-104">The `-refonly` parameter silently disables outputting PDBs, as reference assemblies cannot be executed.</span></span> <span data-ttu-id="c659e-105">이 옵션은 MSBuild의 [ProduceOnlyReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) 프로젝트 속성에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="c659e-105">This option corresponds to the [ProduceOnlyReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) project property of MSBuild.</span></span>

## <a name="syntax"></a><span data-ttu-id="c659e-106">구문</span><span class="sxs-lookup"><span data-stu-id="c659e-106">Syntax</span></span>

```console
-refonly
```

## <a name="remarks"></a><span data-ttu-id="c659e-107">설명</span><span class="sxs-lookup"><span data-stu-id="c659e-107">Remarks</span></span>

<span data-ttu-id="c659e-108">참조 어셈블리는 라이브러리의 퍼블릭 API 표면을 나타내는 데 필요한 최소한의 메타데이터만 포함하는 특수한 형식의 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="c659e-108">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="c659e-109">빌드 도구에서 어셈블리를 참조할 때 중요한 모든 멤버에 대한 선언을 포함하지만, 해당 API 계약에 영향을 미치지 않는 프라이빗 멤버의 선언과 모든 멤버 구현은 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="c659e-109">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="c659e-110">자세한 내용은 .NET 가이드에서 [참조 어셈블리](../../../standard/assembly/reference-assemblies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c659e-110">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="c659e-111">`-refonly` 및 [`-refout`](refout-compiler-option.md) 옵션은 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c659e-111">The `-refonly` and [`-refout`](refout-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="c659e-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c659e-112">See also</span></span>

- [<span data-ttu-id="c659e-113">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="c659e-113">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="c659e-114">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="c659e-114">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
