---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: 052d6937846df39bd94d532e1b63ebe522dbf6c7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964685"
---
# <a name="-moduleassemblyname"></a><span data-ttu-id="d6bbf-102">-moduleassemblyname</span><span class="sxs-lookup"><span data-stu-id="d6bbf-102">-moduleassemblyname</span></span>
<span data-ttu-id="d6bbf-103">이 모듈이 속할 어셈블리의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d6bbf-103">Specifies the name of the assembly that this module will be a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6bbf-104">구문</span><span class="sxs-lookup"><span data-stu-id="d6bbf-104">Syntax</span></span>  
  
```  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="d6bbf-105">인수</span><span class="sxs-lookup"><span data-stu-id="d6bbf-105">Arguments</span></span>  
  
|<span data-ttu-id="d6bbf-106">용어</span><span class="sxs-lookup"><span data-stu-id="d6bbf-106">Term</span></span>|<span data-ttu-id="d6bbf-107">정의</span><span class="sxs-lookup"><span data-stu-id="d6bbf-107">Definition</span></span>|  
|---|---|  
|`assembly_name`|<span data-ttu-id="d6bbf-108">이 모듈에 포함 될 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d6bbf-108">The name of the assembly that this module will be a part of.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6bbf-109">설명</span><span class="sxs-lookup"><span data-stu-id="d6bbf-109">Remarks</span></span>  
 <span data-ttu-id="d6bbf-110">`-target:module` 옵션이 지정 된 경우 `-moduleassemblyname` 에만 컴파일러에서 옵션을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6bbf-110">The compiler processes the `-moduleassemblyname` option only if the `-target:module` option has been specified.</span></span> <span data-ttu-id="d6bbf-111">이렇게 하면 컴파일러가 모듈을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d6bbf-111">This causes the compiler to create a module.</span></span> <span data-ttu-id="d6bbf-112">컴파일러에서 만든 모듈은 `-moduleassemblyname` 옵션으로 지정 된 어셈블리에 대해서만 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6bbf-112">The module created by the compiler is valid only for the assembly specified with the `-moduleassemblyname` option.</span></span> <span data-ttu-id="d6bbf-113">모듈을 다른 어셈블리에 저장 하는 경우 런타임 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6bbf-113">If you place the module in a different assembly, run-time errors will occur.</span></span>  
  
 <span data-ttu-id="d6bbf-114">옵션 `-moduleassemblyname` 은 다음 조건이 충족 되는 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6bbf-114">The `-moduleassemblyname` option is needed only when the following are true:</span></span>  
  
- <span data-ttu-id="d6bbf-115">모듈의 데이터 형식에는 참조 된 어셈블리의 `Friend` 형식에 대 한 액세스 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6bbf-115">A data type in the module needs access to a `Friend` type in a referenced assembly.</span></span>  
  
- <span data-ttu-id="d6bbf-116">참조 된 어셈블리에는 모듈이 빌드되는 어셈블리에 대 한 friend 어셈블리 액세스 권한이 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6bbf-116">The referenced assembly has granted friend assembly access to the assembly into which the module will be built.</span></span>  
  
 <span data-ttu-id="d6bbf-117">모듈을 만드는 방법에 대 한 자세한 내용은 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d6bbf-117">For more information about creating a module, see [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span> <span data-ttu-id="d6bbf-118">Friend 어셈블리에 대 한 자세한 내용은 [Friend 어셈블리](../../../standard/assembly/friend-assemblies.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d6bbf-118">For more information about friend assemblies, see [Friend Assemblies](../../../standard/assembly/friend-assemblies.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d6bbf-119">이 `-moduleassemblyname` 옵션은 Visual Studio 개발 환경에서 사용할 수 없습니다. 명령 프롬프트에서 컴파일하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6bbf-119">The `-moduleassemblyname` option is not available from within the Visual Studio development environment; it is available only when you compile from a command prompt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6bbf-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="d6bbf-120">See also</span></span>

- [<span data-ttu-id="d6bbf-121">방법: 다중 파일 어셈블리 빌드</span><span class="sxs-lookup"><span data-stu-id="d6bbf-121">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)
- [<span data-ttu-id="d6bbf-122">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="d6bbf-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="d6bbf-123">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d6bbf-123">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="d6bbf-124">-main</span><span class="sxs-lookup"><span data-stu-id="d6bbf-124">-main</span></span>](../../../visual-basic/reference/command-line-compiler/main.md)
- [<span data-ttu-id="d6bbf-125">-reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d6bbf-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="d6bbf-126">-addmodule</span><span class="sxs-lookup"><span data-stu-id="d6bbf-126">-addmodule</span></span>](../../../visual-basic/reference/command-line-compiler/addmodule.md)
- [<span data-ttu-id="d6bbf-127">.NET 어셈블리</span><span class="sxs-lookup"><span data-stu-id="d6bbf-127">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="d6bbf-128">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="d6bbf-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="d6bbf-129">Friend 어셈블리</span><span class="sxs-lookup"><span data-stu-id="d6bbf-129">Friend Assemblies</span></span>](../../../standard/assembly/friend-assemblies.md)
