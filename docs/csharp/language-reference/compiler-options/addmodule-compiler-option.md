---
description: -addmodule(C# 컴파일러 옵션)
title: -addmodule(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /addmodule
helpviewer_keywords:
- /addmodule compiler option [C#]
- -addmodule compiler option [C#]
- addmodule compiler option [C#]
ms.assetid: ed604546-0dc2-4bd4-9a3e-610a8d973e58
ms.openlocfilehash: ec72fc76b3d550029b1286f64b8f86e69e721468
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150572"
---
# <a name="-addmodule-c-compiler-options"></a><span data-ttu-id="e495b-103">-addmodule(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="e495b-103">-addmodule (C# Compiler Options)</span></span>

<span data-ttu-id="e495b-104">이 옵션은 target:module 스위치로 만들어진 모듈을 현재 컴파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e495b-104">This option adds a module that was created with the target:module switch to the current compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e495b-105">구문</span><span class="sxs-lookup"><span data-stu-id="e495b-105">Syntax</span></span>  
  
```console  
-addmodule:file[;file2]  
```  
  
## <a name="arguments"></a><span data-ttu-id="e495b-106">인수</span><span class="sxs-lookup"><span data-stu-id="e495b-106">Arguments</span></span>  

 <span data-ttu-id="e495b-107">`file`, `file2`</span><span class="sxs-lookup"><span data-stu-id="e495b-107">`file`, `file2`</span></span>  
 <span data-ttu-id="e495b-108">메타데이터를 포함하는 출력 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="e495b-108">An output file that contains metadata.</span></span> <span data-ttu-id="e495b-109">파일에 어셈블리 매니페스트를 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e495b-109">The file cannot contain an assembly manifest.</span></span> <span data-ttu-id="e495b-110">둘 이상의 파일을 가져오려면 파일 이름을 쉼표 또는 세미콜론으로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="e495b-110">To import more than one file, separate file names with either a comma or a semicolon.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e495b-111">설명</span><span class="sxs-lookup"><span data-stu-id="e495b-111">Remarks</span></span>  

 <span data-ttu-id="e495b-112">**-addmodule**을 사용하여 추가된 모든 모듈은 런타임에 출력 파일과 동일한 디렉터리에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e495b-112">All modules added with **-addmodule** must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="e495b-113">즉, 컴파일 시간에 임의 디렉터리에 있는 모듈을 지정할 수 있지만 런타임에 모듈이 애플리케이션 디렉터리에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e495b-113">That is, you can specify a module in any directory at compile time but the module must be in the application directory at run time.</span></span> <span data-ttu-id="e495b-114">런타임에 모듈이 애플리케이션 디렉터리에 없는 경우 <xref:System.TypeLoadException>이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="e495b-114">If the module is not in the application directory at run time, you will get a <xref:System.TypeLoadException>.</span></span>  
  
 <span data-ttu-id="e495b-115">`file`에 어셈블리를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e495b-115">`file` cannot contain an assembly.</span></span> <span data-ttu-id="e495b-116">예를 들어, [-target:module](./target-module-compiler-option.md)을 사용하여 출력 파일이 만들어진 경우 **-addmodule**을 사용하여 해당 메타데이터를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e495b-116">For example, if the output file was created with [-target:module](./target-module-compiler-option.md), its metadata can be imported with **-addmodule**.</span></span>  
  
 <span data-ttu-id="e495b-117">출력 파일이 **-target:module** 이외의 **-target** 옵션으로 작성된 경우 해당 메타데이터를 **-addmodule**로 가져올 수 없지만 [-reference](./reference-compiler-option.md)로 가져올수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e495b-117">If the output file was created with a **-target** option other than **-target:module**, its metadata cannot be imported with **-addmodule** but can be imported with [-reference](./reference-compiler-option.md).</span></span>  
  
 <span data-ttu-id="e495b-118">이 컴파일러 옵션은 Visual Studio에서 사용할 수 없습니다. 프로젝트에서 모듈을 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e495b-118">This compiler option is unavailable in Visual Studio; a project cannot reference a module.</span></span> <span data-ttu-id="e495b-119">또한 이 컴파일러 옵션은 프로그래밍 방식으로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e495b-119">In addition, this compiler option cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e495b-120">예제</span><span class="sxs-lookup"><span data-stu-id="e495b-120">Example</span></span>  

 <span data-ttu-id="e495b-121">소스 파일 `input.cs`를 컴파일하고 `metad1.netmodule` 및 `metad2.netmodule`의 메타데이터를 추가하여 `out.exe`를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e495b-121">Compile source file `input.cs` and add metadata from `metad1.netmodule` and `metad2.netmodule` to produce `out.exe`:</span></span>  
  
```console  
csc -addmodule:metad1.netmodule;metad2.netmodule -out:out.exe input.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="e495b-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e495b-122">See also</span></span>

- [<span data-ttu-id="e495b-123">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="e495b-123">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="e495b-124">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="e495b-124">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="e495b-125">다중 파일 어셈블리</span><span class="sxs-lookup"><span data-stu-id="e495b-125">Multifile Assemblies</span></span>](../../../framework/app-domains/multifile-assemblies.md)
- [<span data-ttu-id="e495b-126">방법: 다중 파일 어셈블리 빌드</span><span class="sxs-lookup"><span data-stu-id="e495b-126">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/build-multifile-assembly.md)
