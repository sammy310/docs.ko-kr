---
title: -refout (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
ms.openlocfilehash: c11d83ff37da41faa3dc6b66a87e2c52c5f6c7ac
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582868"
---
# <a name="-refout-visual-basic"></a><span data-ttu-id="3ba39-102">-refout (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3ba39-102">-refout (Visual Basic)</span></span>

<span data-ttu-id="3ba39-103">**-refout** 옵션은 참조 어셈블리가 출력되어야 하는 파일 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3ba39-103">The **-refout** option specifies a file path where the reference assembly should be output.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="3ba39-104">구문</span><span class="sxs-lookup"><span data-stu-id="3ba39-104">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="3ba39-105">인수</span><span class="sxs-lookup"><span data-stu-id="3ba39-105">Arguments</span></span>

`filepath`  
<span data-ttu-id="3ba39-106">참조 어셈블리의 경로 및 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3ba39-106">The path and filename of the reference assembly.</span></span> <span data-ttu-id="3ba39-107">일반적으로 주 어셈블리의 하위 폴더에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ba39-107">It should generally be in a sub-folder of the primary assembly.</span></span> <span data-ttu-id="3ba39-108">권장되는 규칙(MSBuild에서 사용됨)은 주 어셈블리에 상대적으로 “ref/” sub-폴더에 참조 어셈블리를 배치하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3ba39-108">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span> <span data-ttu-id="3ba39-109">@No__t_0의 모든 폴더가 존재 해야 합니다. 컴파일러는 생성 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3ba39-109">All folders in `filepath` must exist; the compiler does not create them.</span></span>

## <a name="remarks"></a><span data-ttu-id="3ba39-110">주의</span><span class="sxs-lookup"><span data-stu-id="3ba39-110">Remarks</span></span>

<span data-ttu-id="3ba39-111">Visual Basic 버전 15.3부터 `-refout` 스위치를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ba39-111">Visual Basic supports the `-refout` switch starting with version 15.3.</span></span>

<span data-ttu-id="3ba39-112">참조 어셈블리는 메타 데이터를 포함 하지만 구현 코드는 포함 하지 않는 메타 데이터 전용 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="3ba39-112">Reference assemblies are metadata-only assemblies that contain metadata but no implementation code.</span></span> <span data-ttu-id="3ba39-113">익명 형식을 제외한 모든 항목에 대 한 형식 및 멤버 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ba39-113">They include type and member information for everything except anonymous types.</span></span> <span data-ttu-id="3ba39-114">해당 메서드 본문은 단일 `throw null` 문으로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="3ba39-114">Their method bodies are replaced with a single `throw null` statement.</span></span> <span data-ttu-id="3ba39-115">본문이 아닌 `throw null` 메서드 본문을 사용 하는 이유는 PEVerify를 실행 하 고 통과 하 여 메타 데이터의 완전성을 확인할 수 있도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3ba39-115">The reason for using `throw null` method bodies (as opposed to no bodies) is so that PEVerify can run and pass (thus validating the completeness of the metadata).</span></span>

<span data-ttu-id="3ba39-116">참조 어셈블리에는 어셈블리 수준 [Referenceassembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) 특성이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ba39-116">Reference assemblies include an assembly-level [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) attribute.</span></span> <span data-ttu-id="3ba39-117">이 특성을 소스에서 지정할 수 있습니다. 이렇게 하면 컴파일러가 특성을 합성할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3ba39-117">This attribute may be specified in source (then the compiler won't need to synthesize it).</span></span> <span data-ttu-id="3ba39-118">이 특성으로 인해 런타임은 실행을 위해 참조 어셈블리를 로드 하는 것을 거부 하지만 여전히 리플렉션 전용 컨텍스트에서 로드 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ba39-118">Because of this attribute, runtimes refuse to load reference assemblies for execution (but they can still be loaded in a reflection-only context).</span></span> <span data-ttu-id="3ba39-119">어셈블리를 반영 하는 도구는 참조 어셈블리를 리플렉션 전용으로 로드 하도록 해야 합니다. 그렇지 않으면 런타임에서 <xref:System.BadImageFormatException>을 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ba39-119">Tools that reflect on assemblies need to ensure they load reference assemblies as reflection-only; otherwise, the runtime throws a <xref:System.BadImageFormatException>.</span></span>

<span data-ttu-id="3ba39-120">`-refout` 및 [`-refonly`](refonly-compiler-option.md) 옵션은 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3ba39-120">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="3ba39-121">참조</span><span class="sxs-lookup"><span data-stu-id="3ba39-121">See also</span></span>

- [<span data-ttu-id="3ba39-122">/refonly</span><span class="sxs-lookup"><span data-stu-id="3ba39-122">-refonly</span></span>](refonly-compiler-option.md)
- [<span data-ttu-id="3ba39-123">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="3ba39-123">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="3ba39-124">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="3ba39-124">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
