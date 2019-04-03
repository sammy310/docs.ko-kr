---
title: '#다음과 같은 경우... Then... #Else 지시문 (Visual Basic)'
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
ms.openlocfilehash: 8c0aece749edf144fdd5c8ede9ec7e2e4c96ad54
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58823391"
---
# <a name="ifthenelse-directives"></a><span data-ttu-id="67cec-102">#If...Then...#Else 지시문</span><span class="sxs-lookup"><span data-stu-id="67cec-102">#If...Then...#Else Directives</span></span>
<span data-ttu-id="67cec-103">선택한 Visual Basic 코드 블록을을 조건부로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="67cec-103">Conditionally compiles selected blocks of Visual Basic code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67cec-104">구문</span><span class="sxs-lookup"><span data-stu-id="67cec-104">Syntax</span></span>  
  
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
  
## <a name="parts"></a><span data-ttu-id="67cec-105">요소</span><span class="sxs-lookup"><span data-stu-id="67cec-105">Parts</span></span>  
 `expression`  
 <span data-ttu-id="67cec-106">에 필요한 `#If` 및 `#ElseIf` 선택적 문을 다른 곳입니다.</span><span class="sxs-lookup"><span data-stu-id="67cec-106">Required for `#If` and `#ElseIf` statements, optional elsewhere.</span></span> <span data-ttu-id="67cec-107">만으로 구성 된 하나 이상의 조건부 컴파일러 상수, 리터럴 및 연산자 계산 되는 식일 `True` 또는 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="67cec-107">Any expression, consisting exclusively of one or more conditional compiler constants, literals, and operators, that evaluates to `True` or `False`.</span></span>  
  
 `statements`  
 <span data-ttu-id="67cec-108">에 필요한 `#If` 문 블록에서는 선택적 다른 곳입니다.</span><span class="sxs-lookup"><span data-stu-id="67cec-108">Required for `#If` statement block, optional elsewhere.</span></span> <span data-ttu-id="67cec-109">Visual Basic 프로그램 선 또는 연결 된 식이 계산 되는 경우 컴파일되는 컴파일러 지시문 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="67cec-109">Visual Basic program lines or compiler directives that are compiled if the associated expression evaluates to `True`.</span></span>  
  
 `#End If`  
 <span data-ttu-id="67cec-110">종료는 `#If` 문 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="67cec-110">Terminates the `#If` statement block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67cec-111">설명</span><span class="sxs-lookup"><span data-stu-id="67cec-111">Remarks</span></span>  
 <span data-ttu-id="67cec-112">동작 화면에서를 `#If...Then...#Else` 지시문 동일 하 게와 표시는 `If...Then...Else` 문.</span><span class="sxs-lookup"><span data-stu-id="67cec-112">On the surface, the behavior of the `#If...Then...#Else` directives appears the same as that of the `If...Then...Else` statements.</span></span> <span data-ttu-id="67cec-113">그러나 합니다 `#If...Then...#Else` 지시문은 컴파일러에 의해 컴파일되는 내용을 반면 평가 `If...Then...Else` 문은 런타임에 조건을 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="67cec-113">However, the `#If...Then...#Else` directives evaluate what is compiled by the compiler, whereas the `If...Then...Else` statements evaluate conditions at run time.</span></span>  
  
 <span data-ttu-id="67cec-114">조건부 컴파일은 일반적으로 다양 한 플랫폼에 대 한 동일한 프로그램을 컴파일하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67cec-114">Conditional compilation is typically used to compile the same program for different platforms.</span></span> <span data-ttu-id="67cec-115">방지 하기 위해 사용 되는 실행 파일에 표시 되는 코드를 디버깅 합니다.</span><span class="sxs-lookup"><span data-stu-id="67cec-115">It is also used to prevent debugging code from appearing in an executable file.</span></span> <span data-ttu-id="67cec-116">조건부 컴파일 중에 제외 되는 코드 크기 또는 성능에 영향을 주지 것이 아니므로 완전히 최종 실행 파일에서 생략 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67cec-116">Code excluded during conditional compilation is completely omitted from the final executable file, so it has no effect on size or performance.</span></span>  
  
 <span data-ttu-id="67cec-117">모든 평가의 결과 관계 없이 모든 식을 사용 하 여 평가 됩니다 `Option Compare Binary`합니다.</span><span class="sxs-lookup"><span data-stu-id="67cec-117">Regardless of the outcome of any evaluation, all expressions are evaluated using `Option Compare Binary`.</span></span> <span data-ttu-id="67cec-118">합니다 `Option Compare` 문 식에 영향을 주지 않습니다 `#If` 및 `#ElseIf` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="67cec-118">The `Option Compare` statement does not affect expressions in `#If` and `#ElseIf` statements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="67cec-119">없는 한 줄 형식의 합니다 `#If`, `#Else`, `#ElseIf`, 및 `#End If` 지시문 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="67cec-119">No single-line form of the `#If`, `#Else`, `#ElseIf`, and `#End If` directives exists.</span></span> <span data-ttu-id="67cec-120">다른 코드가 없어야 지시문와 동일한 줄에 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67cec-120">No other code can appear on the same line as any of the directives.</span></span> 

<span data-ttu-id="67cec-121">조건부 컴파일 블록 내에서 문을 논리 문을 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67cec-121">The statements within a conditional compilation block must be complete logical statements.</span></span> <span data-ttu-id="67cec-122">예를 들어 함수의 특성만 조건부로 컴파일할 수 없습니다 있지만 특성과 함께 함수를 조건적으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67cec-122">For example, you cannot conditionally compile only the attributes of a function, but you can conditionally declare the function along with its attributes:</span></span>

```vb
   #If DEBUG Then
   <WebMethod()>
   Public Function SomeFunction() As String
   #Else
   <WebMethod(CacheDuration:=86400)>
   Public Function SomeFunction() As String
   #End If
```

## <a name="example"></a><span data-ttu-id="67cec-123">예제</span><span class="sxs-lookup"><span data-stu-id="67cec-123">Example</span></span>
 <span data-ttu-id="67cec-124">이 예제에서는 `#If...Then...#Else` 구문을 특정 문은 컴파일 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="67cec-124">This example uses the `#If...Then...#Else` construct to determine whether to compile certain statements.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="67cec-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="67cec-125">See also</span></span>

- [<span data-ttu-id="67cec-126">#Const 지시문</span><span class="sxs-lookup"><span data-stu-id="67cec-126">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)
- [<span data-ttu-id="67cec-127">If...Then...Else 문</span><span class="sxs-lookup"><span data-stu-id="67cec-127">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="67cec-128">조건부 컴파일</span><span class="sxs-lookup"><span data-stu-id="67cec-128">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- <xref:System.Diagnostics.ConditionalAttribute?displayProperty=nameWithType>
