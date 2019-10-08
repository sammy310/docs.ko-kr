---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: 5b26e36346858d95526f5d5ce7d4645bea1dbe05
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005472"
---
# <a name="-moduleassemblyname"></a><span data-ttu-id="95fc2-102">-moduleassemblyname</span><span class="sxs-lookup"><span data-stu-id="95fc2-102">-moduleassemblyname</span></span>
<span data-ttu-id="95fc2-103">이 모듈이 속할 어셈블리의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="95fc2-103">Specifies the name of the assembly that this module will be a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95fc2-104">구문</span><span class="sxs-lookup"><span data-stu-id="95fc2-104">Syntax</span></span>  
  
```console  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="95fc2-105">인수</span><span class="sxs-lookup"><span data-stu-id="95fc2-105">Arguments</span></span>  
  
|<span data-ttu-id="95fc2-106">용어</span><span class="sxs-lookup"><span data-stu-id="95fc2-106">Term</span></span>|<span data-ttu-id="95fc2-107">정의</span><span class="sxs-lookup"><span data-stu-id="95fc2-107">Definition</span></span>|  
|---|---|  
|`assembly_name`|<span data-ttu-id="95fc2-108">이 모듈에 포함 될 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="95fc2-108">The name of the assembly that this module will be a part of.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95fc2-109">설명</span><span class="sxs-lookup"><span data-stu-id="95fc2-109">Remarks</span></span>  
 <span data-ttu-id="95fc2-110">@No__t-1 옵션이 지정 된 경우에만 컴파일러에서 `-moduleassemblyname` 옵션을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="95fc2-110">The compiler processes the `-moduleassemblyname` option only if the `-target:module` option has been specified.</span></span> <span data-ttu-id="95fc2-111">이렇게 하면 컴파일러가 모듈을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="95fc2-111">This causes the compiler to create a module.</span></span> <span data-ttu-id="95fc2-112">컴파일러에서 만든 모듈은 `-moduleassemblyname` 옵션으로 지정 된 어셈블리에만 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="95fc2-112">The module created by the compiler is valid only for the assembly specified with the `-moduleassemblyname` option.</span></span> <span data-ttu-id="95fc2-113">모듈을 다른 어셈블리에 저장 하는 경우 런타임 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="95fc2-113">If you place the module in a different assembly, run-time errors will occur.</span></span>  
  
 <span data-ttu-id="95fc2-114">@No__t-0 옵션은 다음 조건이 충족 되는 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="95fc2-114">The `-moduleassemblyname` option is needed only when the following are true:</span></span>  
  
- <span data-ttu-id="95fc2-115">모듈의 데이터 형식은 참조 된 어셈블리의 `Friend` 형식에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95fc2-115">A data type in the module needs access to a `Friend` type in a referenced assembly.</span></span>  
  
- <span data-ttu-id="95fc2-116">참조 된 어셈블리에는 모듈이 빌드되는 어셈블리에 대 한 friend 어셈블리 액세스 권한이 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="95fc2-116">The referenced assembly has granted friend assembly access to the assembly into which the module will be built.</span></span>  
  
 <span data-ttu-id="95fc2-117">모듈을 만드는 방법에 대 한 자세한 내용은 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="95fc2-117">For more information about creating a module, see [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span> <span data-ttu-id="95fc2-118">Friend 어셈블리에 대 한 자세한 내용은 [Friend 어셈블리](../../../standard/assembly/friend.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="95fc2-118">For more information about friend assemblies, see [Friend Assemblies](../../../standard/assembly/friend.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="95fc2-119">@No__t-0 옵션은 Visual Studio 개발 환경에서 사용할 수 없습니다. 명령 프롬프트에서 컴파일하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95fc2-119">The `-moduleassemblyname` option is not available from within the Visual Studio development environment; it is available only when you compile from a command prompt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95fc2-120">참조</span><span class="sxs-lookup"><span data-stu-id="95fc2-120">See also</span></span>

- [<span data-ttu-id="95fc2-121">방법: 다중 파일 어셈블리 빌드</span><span class="sxs-lookup"><span data-stu-id="95fc2-121">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/build-multifile-assembly.md)
- [<span data-ttu-id="95fc2-122">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="95fc2-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="95fc2-123">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="95fc2-123">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="95fc2-124">-main</span><span class="sxs-lookup"><span data-stu-id="95fc2-124">-main</span></span>](../../../visual-basic/reference/command-line-compiler/main.md)
- [<span data-ttu-id="95fc2-125">-reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="95fc2-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="95fc2-126">-addmodule</span><span class="sxs-lookup"><span data-stu-id="95fc2-126">-addmodule</span></span>](../../../visual-basic/reference/command-line-compiler/addmodule.md)
- [<span data-ttu-id="95fc2-127">.NET 어셈블리</span><span class="sxs-lookup"><span data-stu-id="95fc2-127">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="95fc2-128">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="95fc2-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="95fc2-129">Friend 어셈블리</span><span class="sxs-lookup"><span data-stu-id="95fc2-129">Friend Assemblies</span></span>](../../../standard/assembly/friend.md)
