---
description: extern 별칭 - C# 참조
title: extern 별칭 - C# 참조
ms.date: 07/20/2015
f1_keywords:
- alias_CSharpKeyword
helpviewer_keywords:
- extern alias keyword [C#]
- aliases [C#], extern keyword
- aliases, extern keyword
ms.assetid: f487bf4f-c943-4fca-851b-e540c83d9027
ms.openlocfilehash: 5ecafa5a989bc183d7f52ac3d4b4d50a81b36014
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203347"
---
# <a name="extern-alias-c-reference"></a><span data-ttu-id="68df1-103">extern alias(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="68df1-103">extern alias (C# Reference)</span></span>

<span data-ttu-id="68df1-104">정규화된 형식 이름이 동일한 어셈블리의 두 버전을 참조해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68df1-104">You might have to reference two versions of assemblies that have the same fully-qualified type names.</span></span> <span data-ttu-id="68df1-105">예를 들어 동일한 애플리케이션에서 어셈블리 버전을 두 개 이상 사용해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68df1-105">For example, you might have to use two or more versions of an assembly in the same application.</span></span> <span data-ttu-id="68df1-106">외부 어셈블리 별칭을 사용하면 각 어셈블리의 네임스페이스를 별칭으로 명명된 루트 수준 네임스페이스 내에서 래핑하여 동일한 파일에서 사용하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68df1-106">By using an external assembly alias, the namespaces from each assembly can be wrapped inside root-level namespaces named by the alias, which enables them to be used in the same file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="68df1-107">[extern](./extern.md) 키워드는 메서드 한정자로도 사용되어 비관리 코드로 작성된 메서드를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="68df1-107">The [extern](./extern.md) keyword is also used as a method modifier, declaring a method written in unmanaged code.</span></span>  
  
 <span data-ttu-id="68df1-108">정규화된 형식 이름이 동일한 두 어셈블리를 참조하려면 다음과 같이 명령 프롬프트에서 별칭을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68df1-108">To reference two assemblies with the same fully-qualified type names, an alias must be specified at a command prompt, as follows:</span></span>  
  
 `/r:GridV1=grid.dll`  
  
 `/r:GridV2=grid20.dll`  
  
 <span data-ttu-id="68df1-109">그러면 외부 별칭 `GridV1` 및 `GridV2`가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="68df1-109">This creates the external aliases `GridV1` and `GridV2`.</span></span> <span data-ttu-id="68df1-110">프로그램 내에서 이러한 별칭을 사용하려면 `extern` 키워드를 사용하여 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="68df1-110">To use these aliases from within a program, reference them by using the `extern` keyword.</span></span> <span data-ttu-id="68df1-111">예들 들어 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="68df1-111">For example:</span></span>  
  
 `extern alias GridV1;`  
  
 `extern alias GridV2;`  
  
 <span data-ttu-id="68df1-112">각 extern alias 선언에서는 전역 네임스페이스와 병렬이지만 전역 네임스페이스 내에 있지 않는 추가 루트 수준 네임스페이스를 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="68df1-112">Each extern alias declaration introduces an additional root-level namespace that parallels (but does not lie within) the global namespace.</span></span> <span data-ttu-id="68df1-113">따라서 각 어셈블리의 형식은 적절한 namespace-alias에서 시작되는 정규화된 이름을 사용하여 명확하게 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68df1-113">Thus types from each assembly can be referred to without ambiguity by using their fully qualified name, rooted in the appropriate namespace-alias.</span></span>  
  
 <span data-ttu-id="68df1-114">이전 예제에서 `GridV1::Grid`는 `grid.dll`의 표 컨트롤이 되고 `GridV2::Grid`는 `grid20.dll`의 표 컨트롤이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68df1-114">In the previous example, `GridV1::Grid` would be the grid control from `grid.dll`, and `GridV2::Grid` would be the grid control from `grid20.dll`.</span></span>  
  
## <a name="using-visual-studio"></a><span data-ttu-id="68df1-115">Visual Studio 사용</span><span class="sxs-lookup"><span data-stu-id="68df1-115">Using Visual Studio</span></span>

<span data-ttu-id="68df1-116">Visual Studio를 사용하는 경우 별칭을 비슷한 방식으로 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68df1-116">If you are using Visual Studio, aliases can be provided in similar way.</span></span>

<span data-ttu-id="68df1-117">Visual Studio의 프로젝트에 *grid.dll* 및 *grid20.dll*의 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="68df1-117">Add reference of *grid.dll* and *grid20.dll* to your project in Visual Studio.</span></span> <span data-ttu-id="68df1-118">속성 탭을 열고 별칭을 전역에서 GridV1 및 GridV2로 각각 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="68df1-118">Open a property tab and change the Aliases from global to GridV1 and GridV2 respectively.</span></span>

<span data-ttu-id="68df1-119">다음 별칭을 위와 동일한 방식으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="68df1-119">Use these aliases the same way above</span></span>

```csharp
 extern alias GridV1;  
  
 extern alias GridV2;  
```

<span data-ttu-id="68df1-120">이제 별칭 지시문을 사용하여 네임스페이스 또는 형식에 대한 별칭을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68df1-120">Now you can create alias for a namespace or a type by *using alias directive*.</span></span> <span data-ttu-id="68df1-121">자세한 내용은 [지시문 사용](using-directive.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="68df1-121">For more information, see [using directive](using-directive.md).</span></span>

```csharp
using Class1V1 = GridV1::Namespace.Class1;

using Class1V2 = GridV2::Namespace.Class1;
```

## <a name="c-language-specification"></a><span data-ttu-id="68df1-122">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="68df1-122">C# Language Specification</span></span>  

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="68df1-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="68df1-123">See also</span></span>

- [<span data-ttu-id="68df1-124">C# 참조</span><span class="sxs-lookup"><span data-stu-id="68df1-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="68df1-125">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="68df1-125">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="68df1-126">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="68df1-126">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="68df1-127">:: 연산자</span><span class="sxs-lookup"><span data-stu-id="68df1-127">:: Operator</span></span>](../operators/namespace-alias-qualifier.md)
- [<span data-ttu-id="68df1-128">-reference(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="68df1-128">-reference (C# Compiler Options)</span></span>](../compiler-options/reference-compiler-option.md)
