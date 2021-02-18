---
description: '자세한 정보: -moduleassemblyname'
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: 1b5daac8fea264e86b7200f3cead4cb657641000
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100434318"
---
# <a name="-moduleassemblyname"></a><span data-ttu-id="ba4f5-103">-moduleassemblyname</span><span class="sxs-lookup"><span data-stu-id="ba4f5-103">-moduleassemblyname</span></span>

<span data-ttu-id="ba4f5-104">이 모듈이 속할 어셈블리의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ba4f5-104">Specifies the name of the assembly that this module will be a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba4f5-105">구문</span><span class="sxs-lookup"><span data-stu-id="ba4f5-105">Syntax</span></span>  
  
```console  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="ba4f5-106">인수</span><span class="sxs-lookup"><span data-stu-id="ba4f5-106">Arguments</span></span>  
  
|<span data-ttu-id="ba4f5-107">용어</span><span class="sxs-lookup"><span data-stu-id="ba4f5-107">Term</span></span>|<span data-ttu-id="ba4f5-108">정의</span><span class="sxs-lookup"><span data-stu-id="ba4f5-108">Definition</span></span>|  
|---|---|  
|`assembly_name`|<span data-ttu-id="ba4f5-109">이 모듈이 속할 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ba4f5-109">The name of the assembly that this module will be a part of.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba4f5-110">설명</span><span class="sxs-lookup"><span data-stu-id="ba4f5-110">Remarks</span></span>  

 <span data-ttu-id="ba4f5-111">컴파일러는 `-target:module` 옵션이 지정된 경우에만 `-moduleassemblyname` 옵션을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="ba4f5-111">The compiler processes the `-moduleassemblyname` option only if the `-target:module` option has been specified.</span></span> <span data-ttu-id="ba4f5-112">이렇게 하면 컴파일러가 모듈을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ba4f5-112">This causes the compiler to create a module.</span></span> <span data-ttu-id="ba4f5-113">컴파일러에서 만든 모듈은 `-moduleassemblyname` 옵션으로 지정된 어셈블리에만 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="ba4f5-113">The module created by the compiler is valid only for the assembly specified with the `-moduleassemblyname` option.</span></span> <span data-ttu-id="ba4f5-114">모듈을 다른 어셈블리에 배치하면 런타임 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ba4f5-114">If you place the module in a different assembly, run-time errors will occur.</span></span>  
  
 <span data-ttu-id="ba4f5-115">`-moduleassemblyname` 옵션은 다음 조건이 충족되는 경우에만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ba4f5-115">The `-moduleassemblyname` option is needed only when the following are true:</span></span>  
  
- <span data-ttu-id="ba4f5-116">모듈의 데이터 형식에는 참조된 어셈블리의 `Friend` 형식에 대한 액세스 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ba4f5-116">A data type in the module needs access to a `Friend` type in a referenced assembly.</span></span>  
  
- <span data-ttu-id="ba4f5-117">참조된 어셈블리는 모듈을 빌드할 어셈블리에 대한 friend 어셈블리 액세스 권한을 부여했습니다.</span><span class="sxs-lookup"><span data-stu-id="ba4f5-117">The referenced assembly has granted friend assembly access to the assembly into which the module will be built.</span></span>  
  
 <span data-ttu-id="ba4f5-118">모듈 만들기에 대한 자세한 내용은 [-target(Visual Basic)](target.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba4f5-118">For more information about creating a module, see [-target (Visual Basic)](target.md).</span></span> <span data-ttu-id="ba4f5-119">friend 어셈블리에 대한 자세한 내용은 [Friend 어셈블리](../../../standard/assembly/friend.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba4f5-119">For more information about friend assemblies, see [Friend Assemblies](../../../standard/assembly/friend.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ba4f5-120">Visual Studio 개발 환경 내에서는 `-moduleassemblyname` 옵션을 사용할 수 없습니다. 명령 프롬프트에서 컴파일하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba4f5-120">The `-moduleassemblyname` option is not available from within the Visual Studio development environment; it is available only when you compile from a command prompt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba4f5-121">참조</span><span class="sxs-lookup"><span data-stu-id="ba4f5-121">See also</span></span>

- [<span data-ttu-id="ba4f5-122">방법: 다중 파일 어셈블리 빌드</span><span class="sxs-lookup"><span data-stu-id="ba4f5-122">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/build-multifile-assembly.md)
- [<span data-ttu-id="ba4f5-123">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="ba4f5-123">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="ba4f5-124">-target(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ba4f5-124">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="ba4f5-125">-main</span><span class="sxs-lookup"><span data-stu-id="ba4f5-125">-main</span></span>](main.md)
- [<span data-ttu-id="ba4f5-126">-reference(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ba4f5-126">-reference (Visual Basic)</span></span>](reference.md)
- [<span data-ttu-id="ba4f5-127">-addmodule</span><span class="sxs-lookup"><span data-stu-id="ba4f5-127">-addmodule</span></span>](addmodule.md)
- [<span data-ttu-id="ba4f5-128">.NET 어셈블리</span><span class="sxs-lookup"><span data-stu-id="ba4f5-128">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="ba4f5-129">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="ba4f5-129">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="ba4f5-130">Friend 어셈블리</span><span class="sxs-lookup"><span data-stu-id="ba4f5-130">Friend Assemblies</span></span>](../../../standard/assembly/friend.md)
