---
description: -optimize(C# 컴파일러 옵션)
title: -optimize(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /optimize
helpviewer_keywords:
- /optimize compiler option [C#]
- -o compiler option [C#]
- optimize compiler option [C#]
- /o compiler option [C#]
- -optimize compiler option [C#]
- compiler optimization [C#]
- o compiler option [C#]
ms.assetid: 6dd5b6f2-cd1d-4593-a9f4-1c2ed9404ca0
ms.openlocfilehash: 1862794e4d823e38ce19780300a0b04f4e57dc44
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91193987"
---
# <a name="-optimize-c-compiler-options"></a><span data-ttu-id="2a9f6-103">-optimize(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="2a9f6-103">-optimize (C# Compiler Options)</span></span>

<span data-ttu-id="2a9f6-104">**-optimize** 옵션은 컴파일러에서 더 작지만 빠르고 효율적인 출력 파일을 만들기 위해 수행하는 최적화 기능을 사용하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2a9f6-104">The **-optimize** option enables or disables optimizations performed by the compiler to make your output file smaller, faster, and more efficient.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a9f6-105">구문</span><span class="sxs-lookup"><span data-stu-id="2a9f6-105">Syntax</span></span>  
  
```console  
-optimize[+ | -]  
```  
  
## <a name="remarks"></a><span data-ttu-id="2a9f6-106">설명</span><span class="sxs-lookup"><span data-stu-id="2a9f6-106">Remarks</span></span>  

 <span data-ttu-id="2a9f6-107">또한 **-optimize**는 런타임에 코드를 최적화하도록 공용 언어 런타임에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="2a9f6-107">**-optimize** also tells the common language runtime to optimize code at runtime.</span></span>  
  
 <span data-ttu-id="2a9f6-108">최적화는 기본적으로 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2a9f6-108">By default, optimizations are disabled.</span></span> <span data-ttu-id="2a9f6-109">최적화를 사용하려면 **-optimize+** 를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2a9f6-109">Specify **-optimize+** to enable optimizations.</span></span>  
  
 <span data-ttu-id="2a9f6-110">어셈블리에서 사용할 모듈을 빌드하는 경우 어셈블리의 설정과 동일한 **-optimize** 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2a9f6-110">When building a module to be used by an assembly, use the same **-optimize** settings as those of the assembly.</span></span>  
  
 <span data-ttu-id="2a9f6-111">**-o**는 **-optimize**의 약식 형태입니다.</span><span class="sxs-lookup"><span data-stu-id="2a9f6-111">**-o** is the short form of **-optimize**.</span></span>  
  
 <span data-ttu-id="2a9f6-112">**-optimize** 및 [-debug](./debug-compiler-option.md) 옵션을 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a9f6-112">It is possible to combine the **-optimize** and [-debug](./debug-compiler-option.md) options.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="2a9f6-113">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="2a9f6-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="2a9f6-114">프로젝트 **속성** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2a9f6-114">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="2a9f6-115">**빌드** 속성 페이지를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2a9f6-115">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="2a9f6-116">**코드 최적화** 속성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="2a9f6-116">Modify the **Optimize Code** property.</span></span>  
  
 <span data-ttu-id="2a9f6-117">이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.Optimize%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2a9f6-117">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.Optimize%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a9f6-118">예제</span><span class="sxs-lookup"><span data-stu-id="2a9f6-118">Example</span></span>  

 <span data-ttu-id="2a9f6-119">`t2.cs`를 컴파일하고 컴파일러 최적화를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2a9f6-119">Compile `t2.cs` and enable compiler optimizations:</span></span>  
  
```console  
csc t2.cs -optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="2a9f6-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2a9f6-120">See also</span></span>

- [<span data-ttu-id="2a9f6-121">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="2a9f6-121">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="2a9f6-122">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="2a9f6-122">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
