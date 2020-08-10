---
title: 네임스페이스 사용 - C# 프로그래밍 가이드
description: 네임스페이스 액세스, 네임스페이스 별칭, 범위 제어를 위한 네임스페이스 사용 등 C# 프로그래밍에서 네임스페이스를 사용하는 방법을 알아봅니다.
ms.date: 07/20/2015
f1_keywords:
- cs.names
helpviewer_keywords:
- fully qualified names [C#]
- namespaces [C#], how to use
ms.assetid: 1fe8bf39-addc-438a-bd9e-86410e32381d
ms.openlocfilehash: 86892f50e059c16ee9c133d7ba9f2716e11a8e56
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381699"
---
# <a name="using-namespaces-c-programming-guide"></a><span data-ttu-id="71e0e-103">네임스페이스 사용(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="71e0e-103">Using namespaces (C# Programming Guide)</span></span>

<span data-ttu-id="71e0e-104">네임스페이스는 C# 프로그램 내에서 두 가지 방법으로 많이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-104">Namespaces are heavily used within C# programs in two ways.</span></span> <span data-ttu-id="71e0e-105">첫째, .NET 클래스는 네임스페이스를 사용하여 많은 클래스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-105">Firstly, the .NET classes use namespaces to organize its many classes.</span></span> <span data-ttu-id="71e0e-106">둘째, 고유한 네임스페이스를 선언하면 대규모 프로그래밍 프로젝트에서 클래스 및 메서드 이름의 범위를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-106">Secondly, declaring your own namespaces can help control the scope of class and method names in larger programming projects.</span></span>  
  
## <a name="accessing-namespaces"></a><span data-ttu-id="71e0e-107">네임스페이스 액세스</span><span class="sxs-lookup"><span data-stu-id="71e0e-107">Accessing namespaces</span></span>

 <span data-ttu-id="71e0e-108">대부분의 C# 애플리케이션은 `using` 지시문 섹션으로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-108">Most C# applications begin with a section of `using` directives.</span></span> <span data-ttu-id="71e0e-109">이 섹션에는 애플리케이션이 자주 사용하는 네임스페이스가 나열되어, 프로그래머가 내부에 포함된 메서드를 사용할 때마다 정규화된 이름을 지정할 필요가 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-109">This section lists the namespaces that the application will be using frequently, and saves the programmer from specifying a fully qualified name every time that a method that is contained within is used.</span></span>  
  
 <span data-ttu-id="71e0e-110">예를 들어 다음 줄을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-110">For example, by including the line:</span></span>  
  
 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]  
  
 <span data-ttu-id="71e0e-111">프로그램의 시작 부분에서 프로그래머는 다음 코드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-111">At the start of a program, the programmer can use the code:</span></span>  
  
 [!code-csharp[csProgGuide#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#31)]  
  
 <span data-ttu-id="71e0e-112">위 코드를 아래 코드 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-112">Instead of:</span></span>  
  
 [!code-csharp[csProgGuide#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#30)]  
  
## <a name="namespace-aliases"></a><span data-ttu-id="71e0e-113">네임스페이스 별칭</span><span class="sxs-lookup"><span data-stu-id="71e0e-113">Namespace aliases</span></span>

 <span data-ttu-id="71e0e-114">[`using` 지시문](../../language-reference/keywords/using-directive.md)을 사용하여 네임스페이스에 대한 별칭을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-114">You can also use the [`using` directive](../../language-reference/keywords/using-directive.md) to create an alias for a namespace.</span></span> <span data-ttu-id="71e0e-115">[네임스페이스 별칭 한정자`::`](../../language-reference/operators/namespace-alias-qualifier.md)를 사용하여 별칭이 지정된 네임스페이스의 구성원에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-115">Use the [namespace alias qualifier `::`](../../language-reference/operators/namespace-alias-qualifier.md) to access the members of the aliased namespace.</span></span> <span data-ttu-id="71e0e-116">다음 예제에서는 네임스페이스 별칭을 만들고 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-116">The following example shows how to create and use a namespace alias:</span></span>
  
[!code-csharp[csProgGuideNamespaces#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#5)]
  
## <a name="using-namespaces-to-control-scope"></a><span data-ttu-id="71e0e-117">네임스페이스를 사용하여 범위 제어</span><span class="sxs-lookup"><span data-stu-id="71e0e-117">Using namespaces to control scope</span></span>

 <span data-ttu-id="71e0e-118">`namespace` 키워드는 범위를 선언하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-118">The `namespace` keyword is used to declare a scope.</span></span> <span data-ttu-id="71e0e-119">프로젝트 내에서 범위를 만드는 기능은 코드 구성에 도움이 되며, 전역적으로 고유한 형식을 만들 수 있게 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-119">The ability to create scopes within your project helps organize code and lets you create globally-unique types.</span></span> <span data-ttu-id="71e0e-120">다음 예제에서 `SampleClass`라는 클래스는 서로 중첩된 두 개의 네임스페이스에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-120">In the following example, a class titled `SampleClass` is defined in two namespaces, one nested inside the other.</span></span> <span data-ttu-id="71e0e-121">[`.` 토큰](../../language-reference/operators/member-access-operators.md#member-access-expression-)은 호출되는 메서드를 구분하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-121">The [`.` token](../../language-reference/operators/member-access-operators.md#member-access-expression-) is used to differentiate which method gets called.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#8)]  
  
## <a name="fully-qualified-names"></a><span data-ttu-id="71e0e-122">정규화된 이름</span><span class="sxs-lookup"><span data-stu-id="71e0e-122">Fully qualified names</span></span>

 <span data-ttu-id="71e0e-123">네임스페이스 및 형식에는 논리적 계층 구조를 나타내는 정규화된 이름으로 설명된 고유한 제목이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-123">Namespaces and types have unique titles described by fully qualified names that indicate a logical hierarchy.</span></span> <span data-ttu-id="71e0e-124">예를 들어 `A.B` 문은 `A`는 네임스페이스 또는 형식의 이름이고 `B`는 그 안에 중첩됨을 암시합니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-124">For example, the statement `A.B` implies that `A` is the name of the namespace or type, and `B` is nested inside it.</span></span>  
  
 <span data-ttu-id="71e0e-125">다음 예제에서는 중첩된 클래스 및 네임스페이스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-125">In the following example, there are nested classes and namespaces.</span></span> <span data-ttu-id="71e0e-126">정규화된 이름이 각 엔터티 뒤에 주석으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-126">The fully qualified name is indicated as a comment following each entity.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#9)]  
  
 <span data-ttu-id="71e0e-127">앞의 코드 세그먼트에서:</span><span class="sxs-lookup"><span data-stu-id="71e0e-127">In the previous code segment:</span></span>  
  
- <span data-ttu-id="71e0e-128">`N1` 네임스페이스는 전역 네임스페이스의 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-128">The namespace `N1` is a member of the global namespace.</span></span> <span data-ttu-id="71e0e-129">정규화된 이름은 `N1`입니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-129">Its fully qualified name is `N1`.</span></span>  
  
- <span data-ttu-id="71e0e-130">`N2` 네임스페이스는 `N1`의 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-130">The namespace `N2` is a member of `N1`.</span></span> <span data-ttu-id="71e0e-131">정규화된 이름은 `N1.N2`입니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-131">Its fully qualified name is `N1.N2`.</span></span>  
  
- <span data-ttu-id="71e0e-132">`C1` 클래스는 `N1`의 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-132">The class `C1` is a member of `N1`.</span></span> <span data-ttu-id="71e0e-133">정규화된 이름은 `N1.C1`입니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-133">Its fully qualified name is `N1.C1`.</span></span>  
  
- <span data-ttu-id="71e0e-134">이 코드에서는 클래스 이름 `C2`가 두 번 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-134">The class name `C2` is used two times in this code.</span></span> <span data-ttu-id="71e0e-135">그러나 정규화된 이름은 고유합니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-135">However, the fully qualified names are unique.</span></span> <span data-ttu-id="71e0e-136">`C2`의 첫 번째 인스턴스는 `C1` 내에서 선언되었으므로 정규화된 이름이 `N1.C1.C2`입니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-136">The first instance of `C2` is declared inside `C1`; therefore, its fully qualified name is: `N1.C1.C2`.</span></span> <span data-ttu-id="71e0e-137">`C2`의 두 번째 인스턴스는 `N2` 네임스페이스 내에서 선언되었으므로 정규화된 이름이 `N1.N2.C2`입니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-137">The second instance of `C2` is declared inside a namespace `N2`; therefore, its fully qualified name is `N1.N2.C2`.</span></span>  
  
 <span data-ttu-id="71e0e-138">앞의 코드 세그먼트를 사용하여 다음과 같이 `N1.N2` 네임스페이스에 새 클래스 멤버 `C3`를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-138">Using the previous code segment, you can add a new class member, `C3`, to the namespace `N1.N2` as follows:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#10)]  
  
 <span data-ttu-id="71e0e-139">일반적으로 [네임스페이스 별칭 한정자 `::`](../../language-reference/operators/namespace-alias-qualifier.md)을(를) 사용하여 네임스페이스 별칭을 참조하거나, `global::`을(를) 사용하여 전역 네임스페이스를 참조하고 `.`을(를) 사용하여 형식 또는 구성원을 한정합니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-139">In general, use the [namespace alias qualifier `::`](../../language-reference/operators/namespace-alias-qualifier.md) to reference a namespace alias or `global::` to reference the global namespace and `.` to qualify types or members.</span></span>  
  
 <span data-ttu-id="71e0e-140">네임스페이스 대신 형식을 참조하는 별칭과 함께 `::`을 사용하면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-140">It is an error to use `::` with an alias that references a type instead of a namespace.</span></span> <span data-ttu-id="71e0e-141">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-141">For example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces2.cs#11)]  
  
 [!code-csharp[csProgGuideNamespaces#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces2.cs#12)]  
  
 <span data-ttu-id="71e0e-142">`global` 단어는 미리 정의된 별칭이 아니므로 `global.X`에 특별한 의미가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-142">Remember that the word `global` is not a predefined alias; therefore, `global.X` does not have any special meaning.</span></span> <span data-ttu-id="71e0e-143">`::`과 함께 사용하는 경우에만 특별한 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-143">It acquires a special meaning only when it is used with `::`.</span></span>  
  
 <span data-ttu-id="71e0e-144">`global::`은 항상 별칭이 아니라 전역 네임스페이스를 참조하기 때문에 global이란 별칭을 정의할 경우 컴파일러 경고 CS0440이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-144">Compiler warning CS0440 is generated if you define an alias named global because `global::` always references the global namespace and not an alias.</span></span> <span data-ttu-id="71e0e-145">예를 들어 다음 줄에서는 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-145">For example, the following line generates the warning:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces2.cs#13)]  
  
 <span data-ttu-id="71e0e-146">별칭과 함께 `::`을 사용하는 것은 좋은 방법이며, 예기치 않은 추가 형식의 도입을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-146">Using `::` with aliases is a good idea and protects against the unexpected introduction of additional types.</span></span> <span data-ttu-id="71e0e-147">예를 들어 다음 예제를 고려해보세요.</span><span class="sxs-lookup"><span data-stu-id="71e0e-147">For example, consider this example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#14)]  
  
 [!code-csharp[csProgGuideNamespaces#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#15)]  
  
 <span data-ttu-id="71e0e-148">이 예제는 작동하지만, `Alias`라는 형식을 이후에 도입할 경우 `Alias.`가 해당 형식에 대신 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-148">This works, but if a type named `Alias` were to subsequently be introduced, `Alias.` would bind to that type instead.</span></span> <span data-ttu-id="71e0e-149">`Alias::Exception`을 사용하면 `Alias`가 네임스페이스 별칭으로 처리되며 형식으로 잘못 인식되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71e0e-149">Using `Alias::Exception` ensures that `Alias` is treated as a namespace alias and not mistaken for a type.</span></span>  

## <a name="see-also"></a><span data-ttu-id="71e0e-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="71e0e-150">See also</span></span>

- [<span data-ttu-id="71e0e-151">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="71e0e-151">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="71e0e-152">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="71e0e-152">Namespaces</span></span>](./index.md)
- [<span data-ttu-id="71e0e-153">멤버 액세스 식</span><span class="sxs-lookup"><span data-stu-id="71e0e-153">Member access expression</span></span>](../../language-reference/operators/member-access-operators.md#member-access-expression-)
- [<span data-ttu-id="71e0e-154">:: 연산자</span><span class="sxs-lookup"><span data-stu-id="71e0e-154">:: operator</span></span>](../../language-reference/operators/namespace-alias-qualifier.md)
- [<span data-ttu-id="71e0e-155">extern alias</span><span class="sxs-lookup"><span data-stu-id="71e0e-155">extern alias</span></span>](../../language-reference/keywords/extern-alias.md)
