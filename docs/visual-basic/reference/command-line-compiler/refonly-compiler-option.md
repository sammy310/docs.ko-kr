---
title: -refonly (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- -refonly
helpviewer_keywords:
- /refonly compiler option [Visual Basic]
- -refonly compiler option [Visual Basic]
- refonly compiler option [Visual Basic]
ms.openlocfilehash: 8e64989ac1410b51991027ffcb33e8dae0c0284b
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775561"
---
# <a name="-refonly-visual-basic"></a><span data-ttu-id="e9856-102">-refonly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e9856-102">-refonly (Visual Basic)</span></span>

<span data-ttu-id="e9856-103">**-Refonly** 옵션은 컴파일의 기본 출력이 구현 어셈블리 대신 참조 어셈블리 여야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e9856-103">The **-refonly** option indicates that the primary output of the compilation should be a reference assembly instead of an implementation assembly.</span></span> <span data-ttu-id="e9856-104">`-refonly` 매개 변수는 참조 어셈블리가 실행될 수 없을 때 PDB 출력을 자동으로 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e9856-104">The `-refonly` parameter silently disables outputting PDBs, as reference assemblies cannot be executed.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="e9856-105">구문</span><span class="sxs-lookup"><span data-stu-id="e9856-105">Syntax</span></span>

```console
-refonly
```

## <a name="remarks"></a><span data-ttu-id="e9856-106">주의</span><span class="sxs-lookup"><span data-stu-id="e9856-106">Remarks</span></span>

<span data-ttu-id="e9856-107">Visual Basic 버전 15.3부터 `-refonly` 스위치를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9856-107">Visual Basic supports the `-refonly` switch starting with version 15.3.</span></span>

<span data-ttu-id="e9856-108">참조 어셈블리는 라이브러리의 공용 API 화면을 나타내는 데 필요한 최소한의 메타 데이터만 포함 하는 특수 한 형식의 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="e9856-108">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="e9856-109">여기에는 빌드 도구에서 어셈블리를 참조할 때 중요 한 모든 멤버에 대 한 선언이 포함 되지만, 해당 API 계약에 대 한 관찰 효과가 없는 전용 멤버의 모든 멤버 구현 및 선언은 제외 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9856-109">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="e9856-110">자세한 내용은 .NET의 [참조 어셈블리](../../../standard/assembly/reference-assemblies.md) 가이드를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e9856-110">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="e9856-111">`-refonly` 및 [`-refout`](refout-compiler-option.md) 옵션은 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e9856-111">The `-refonly` and [`-refout`](refout-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="e9856-112">참조</span><span class="sxs-lookup"><span data-stu-id="e9856-112">See also</span></span>

- [<span data-ttu-id="e9856-113">/refout</span><span class="sxs-lookup"><span data-stu-id="e9856-113">-refout</span></span>](refout-compiler-option.md)
- [<span data-ttu-id="e9856-114">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="e9856-114">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="e9856-115">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="e9856-115">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
