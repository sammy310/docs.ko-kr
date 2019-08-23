---
title: '#... Then ... #Else 지시문 (Visual Basic)'
ms.date: 04/11/2018
f1_keywords:
- vb.#EndIf
- '#End If'
- '#Then'
- '#ElseIf'
- vb.#ElseIf
- vb.#Else
- vb.#If
helpviewer_keywords:
- Visual Basic code, compiling
- '#If directive [Visual Basic]'
- conditional compilation [Visual Basic], directives
- '#End if directive [Visual Basic]'
- selective compiling
- else directive (#else)
- '#Else directive [Visual Basic]'
ms.assetid: 10bba104-e3fd-451b-b672-faa472530502
ms.openlocfilehash: 697521276e2d5a8d0a4aaae38789a21b7aa87fcb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940754"
---
# <a name="ifthenelse-directives"></a><span data-ttu-id="98fc2-102">#If...Then...#Else 지시문</span><span class="sxs-lookup"><span data-stu-id="98fc2-102">#If...Then...#Else Directives</span></span>
<span data-ttu-id="98fc2-103">선택한 Visual Basic 코드 블록을 조건부로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="98fc2-103">Conditionally compiles selected blocks of Visual Basic code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98fc2-104">구문</span><span class="sxs-lookup"><span data-stu-id="98fc2-104">Syntax</span></span>  
  
```  
#If expression Then  
   statements  
[ #ElseIf expression Then  
   [ statements ]  
...  
#ElseIf expression Then  
   [ statements ] ]  
[ #Else  
   [ statements ] ]  
#End If  
```  
  
## <a name="parts"></a><span data-ttu-id="98fc2-105">요소</span><span class="sxs-lookup"><span data-stu-id="98fc2-105">Parts</span></span>  
 `expression`  
 <span data-ttu-id="98fc2-106">및 문에 필요 `#ElseIf` 하며, 다른 위치에 선택적입니다. `#If`</span><span class="sxs-lookup"><span data-stu-id="98fc2-106">Required for `#If` and `#ElseIf` statements, optional elsewhere.</span></span> <span data-ttu-id="98fc2-107">하나 이상의 조건부 컴파일러 상수, 리터럴 및 연산자로만 구성 되며 또는 `True` `False`로 계산 되는 모든 식입니다.</span><span class="sxs-lookup"><span data-stu-id="98fc2-107">Any expression, consisting exclusively of one or more conditional compiler constants, literals, and operators, that evaluates to `True` or `False`.</span></span>  
  
 `statements`  
 <span data-ttu-id="98fc2-108">문 블록 `#If` 에 필요 합니다 (선택 사항).</span><span class="sxs-lookup"><span data-stu-id="98fc2-108">Required for `#If` statement block, optional elsewhere.</span></span> <span data-ttu-id="98fc2-109">연결 된 식이로 `True`계산 될 경우 컴파일되는 프로그램 줄 또는 컴파일러 지시문을 Visual Basic 합니다.</span><span class="sxs-lookup"><span data-stu-id="98fc2-109">Visual Basic program lines or compiler directives that are compiled if the associated expression evaluates to `True`.</span></span>  
  
 `#End If`  
 <span data-ttu-id="98fc2-110">문 블록 `#If` 을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="98fc2-110">Terminates the `#If` statement block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98fc2-111">설명</span><span class="sxs-lookup"><span data-stu-id="98fc2-111">Remarks</span></span>  
 <span data-ttu-id="98fc2-112">화면에서 `#If...Then...#Else` 지시문의 동작은 `If...Then...Else` 문과 동일 하 게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98fc2-112">On the surface, the behavior of the `#If...Then...#Else` directives appears the same as that of the `If...Then...Else` statements.</span></span> <span data-ttu-id="98fc2-113">그러나 지시문은 컴파일러에 의해 컴파일되는 항목을 평가 하는 `If...Then...Else` 반면 문은 런타임에 조건을 평가 합니다. `#If...Then...#Else`</span><span class="sxs-lookup"><span data-stu-id="98fc2-113">However, the `#If...Then...#Else` directives evaluate what is compiled by the compiler, whereas the `If...Then...Else` statements evaluate conditions at run time.</span></span>  
  
 <span data-ttu-id="98fc2-114">조건부 컴파일은 일반적으로 여러 플랫폼에 대해 동일한 프로그램을 컴파일하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98fc2-114">Conditional compilation is typically used to compile the same program for different platforms.</span></span> <span data-ttu-id="98fc2-115">또한 실행 파일에 디버깅 코드가 나타나지 않도록 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98fc2-115">It is also used to prevent debugging code from appearing in an executable file.</span></span> <span data-ttu-id="98fc2-116">조건부 컴파일을 수행 하는 동안 제외 된 코드는 최종 실행 파일에서 완전히 생략 되므로 크기 또는 성능에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="98fc2-116">Code excluded during conditional compilation is completely omitted from the final executable file, so it has no effect on size or performance.</span></span>  
  
 <span data-ttu-id="98fc2-117">모든 계산 결과에 관계 없이 모든 식은을 사용 하 여 `Option Compare Binary`계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98fc2-117">Regardless of the outcome of any evaluation, all expressions are evaluated using `Option Compare Binary`.</span></span> <span data-ttu-id="98fc2-118">`Option Compare` 문은 `#If` 및 문의`#ElseIf` 식에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="98fc2-118">The `Option Compare` statement does not affect expressions in `#If` and `#ElseIf` statements.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="98fc2-119">`#If` ,`#Else`, 및 지시문`#End If` 의 한 줄 형태가 없습니다. `#ElseIf`</span><span class="sxs-lookup"><span data-stu-id="98fc2-119">No single-line form of the `#If`, `#Else`, `#ElseIf`, and `#End If` directives exists.</span></span> <span data-ttu-id="98fc2-120">지시문과 동일한 줄에 다른 코드를 표시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="98fc2-120">No other code can appear on the same line as any of the directives.</span></span> 

<span data-ttu-id="98fc2-121">조건부 컴파일 블록 내의 문은 완전 한 논리적 문 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98fc2-121">The statements within a conditional compilation block must be complete logical statements.</span></span> <span data-ttu-id="98fc2-122">예를 들어 함수 특성만 조건부로 컴파일할 수는 없지만 해당 특성과 함께 함수를 조건부로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98fc2-122">For example, you cannot conditionally compile only the attributes of a function, but you can conditionally declare the function along with its attributes:</span></span>

```vb
   #If DEBUG Then
   <WebMethod()>
   Public Function SomeFunction() As String
   #Else
   <WebMethod(CacheDuration:=86400)>
   Public Function SomeFunction() As String
   #End If
```

## <a name="example"></a><span data-ttu-id="98fc2-123">예제</span><span class="sxs-lookup"><span data-stu-id="98fc2-123">Example</span></span>
 <span data-ttu-id="98fc2-124">이 예제에서는 `#If...Then...#Else` 구문을 사용 하 여 특정 문을 컴파일할 것인지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="98fc2-124">This example uses the `#If...Then...#Else` construct to determine whether to compile certain statements.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="98fc2-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="98fc2-125">See also</span></span>

- [<span data-ttu-id="98fc2-126">#Const 지시문</span><span class="sxs-lookup"><span data-stu-id="98fc2-126">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)
- [<span data-ttu-id="98fc2-127">If...Then...Else 문</span><span class="sxs-lookup"><span data-stu-id="98fc2-127">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="98fc2-128">조건부 컴파일</span><span class="sxs-lookup"><span data-stu-id="98fc2-128">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- <xref:System.Diagnostics.ConditionalAttribute?displayProperty=nameWithType>
