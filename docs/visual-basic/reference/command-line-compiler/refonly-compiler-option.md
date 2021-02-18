---
description: '자세한 정보: -refonly(Visual Basic)'
title: -refonly
ms.date: 03/16/2018
f1_keywords:
- -refonly
helpviewer_keywords:
- /refonly compiler option [Visual Basic]
- -refonly compiler option [Visual Basic]
- refonly compiler option [Visual Basic]
ms.openlocfilehash: 283aa75fceead38c62c4cf10c1ffe08151aeac9c
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100474137"
---
# <a name="-refonly-visual-basic"></a><span data-ttu-id="fac6b-103">-refonly(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fac6b-103">-refonly (Visual Basic)</span></span>

<span data-ttu-id="fac6b-104">**-refonly** 옵션은 컴파일의 기본 출력이 구현 어셈블리 대신 참조 어셈블리여야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fac6b-104">The **-refonly** option indicates that the primary output of the compilation should be a reference assembly instead of an implementation assembly.</span></span> <span data-ttu-id="fac6b-105">`-refonly` 매개 변수는 참조 어셈블리가 실행될 수 없을 때 PDB 출력을 자동으로 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fac6b-105">The `-refonly` parameter silently disables outputting PDBs, as reference assemblies cannot be executed.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="fac6b-106">구문</span><span class="sxs-lookup"><span data-stu-id="fac6b-106">Syntax</span></span>

```console
-refonly
```

## <a name="remarks"></a><span data-ttu-id="fac6b-107">설명</span><span class="sxs-lookup"><span data-stu-id="fac6b-107">Remarks</span></span>

<span data-ttu-id="fac6b-108">Visual Basic은 버전 15.3부터 `-refonly` 스위치를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="fac6b-108">Visual Basic supports the `-refonly` switch starting with version 15.3.</span></span>

<span data-ttu-id="fac6b-109">참조 어셈블리는 라이브러리의 퍼블릭 API 표면을 나타내는 데 필요한 최소한의 메타데이터만 포함하는 특수한 형식의 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="fac6b-109">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="fac6b-110">빌드 도구에서 어셈블리를 참조할 때 중요한 모든 멤버에 대한 선언을 포함하지만, 해당 API 계약에 영향을 미치지 않는 프라이빗 멤버의 선언과 모든 멤버 구현은 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="fac6b-110">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="fac6b-111">자세한 내용은 .NET 가이드에서 [참조 어셈블리](../../../standard/assembly/reference-assemblies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fac6b-111">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="fac6b-112">`-refonly` 및 [`-refout`](refout-compiler-option.md) 옵션은 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fac6b-112">The `-refonly` and [`-refout`](refout-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="fac6b-113">참조</span><span class="sxs-lookup"><span data-stu-id="fac6b-113">See also</span></span>

- [<span data-ttu-id="fac6b-114">/refout</span><span class="sxs-lookup"><span data-stu-id="fac6b-114">-refout</span></span>](refout-compiler-option.md)
- [<span data-ttu-id="fac6b-115">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="fac6b-115">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="fac6b-116">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="fac6b-116">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
