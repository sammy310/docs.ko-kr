---
description: '자세한 정보: -refout(Visual Basic)'
title: -refout
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
ms.openlocfilehash: 2760f7e60d950aaff90becad843824a2e2b4379f
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100474124"
---
# <a name="-refout-visual-basic"></a><span data-ttu-id="bc1d0-103">-refout(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc1d0-103">-refout (Visual Basic)</span></span>

<span data-ttu-id="bc1d0-104">**-refout** 옵션은 참조 어셈블리가 출력되어야 하는 파일 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bc1d0-104">The **-refout** option specifies a file path where the reference assembly should be output.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="bc1d0-105">구문</span><span class="sxs-lookup"><span data-stu-id="bc1d0-105">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="bc1d0-106">인수</span><span class="sxs-lookup"><span data-stu-id="bc1d0-106">Arguments</span></span>

`filepath`  
<span data-ttu-id="bc1d0-107">참조 어셈블리의 경로 및 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="bc1d0-107">The path and filename of the reference assembly.</span></span> <span data-ttu-id="bc1d0-108">일반적으로 기본 어셈블리의 하위 폴더에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc1d0-108">It should generally be in a sub-folder of the primary assembly.</span></span> <span data-ttu-id="bc1d0-109">권장되는 규칙(MSBuild에서 사용됨)은 주 어셈블리에 상대적으로 “ref/” sub-폴더에 참조 어셈블리를 배치하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bc1d0-109">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span> <span data-ttu-id="bc1d0-110">`filepath`의 모든 폴더가 존재해야 합니다. 컴파일러는 폴더를 생성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc1d0-110">All folders in `filepath` must exist; the compiler does not create them.</span></span>

## <a name="remarks"></a><span data-ttu-id="bc1d0-111">설명</span><span class="sxs-lookup"><span data-stu-id="bc1d0-111">Remarks</span></span>

<span data-ttu-id="bc1d0-112">Visual Basic은 버전 15.3부터 `-refout` 스위치를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="bc1d0-112">Visual Basic supports the `-refout` switch starting with version 15.3.</span></span>

<span data-ttu-id="bc1d0-113">참조 어셈블리는 라이브러리의 퍼블릭 API 표면을 나타내는 데 필요한 최소한의 메타데이터만 포함하는 특수한 형식의 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="bc1d0-113">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="bc1d0-114">빌드 도구에서 어셈블리를 참조할 때 중요한 모든 멤버에 대한 선언을 포함하지만, 해당 API 계약에 영향을 미치지 않는 프라이빗 멤버의 선언과 모든 멤버 구현은 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc1d0-114">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="bc1d0-115">자세한 내용은 .NET 가이드에서 [참조 어셈블리](../../../standard/assembly/reference-assemblies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bc1d0-115">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="bc1d0-116">`-refout` 및 [`-refonly`](refonly-compiler-option.md) 옵션은 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bc1d0-116">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="bc1d0-117">참조</span><span class="sxs-lookup"><span data-stu-id="bc1d0-117">See also</span></span>

- [<span data-ttu-id="bc1d0-118">/refonly</span><span class="sxs-lookup"><span data-stu-id="bc1d0-118">-refonly</span></span>](refonly-compiler-option.md)
- [<span data-ttu-id="bc1d0-119">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="bc1d0-119">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="bc1d0-120">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="bc1d0-120">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
