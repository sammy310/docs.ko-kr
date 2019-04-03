---
title: Generic Procedures in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- generic methods [Visual Basic], type inference
- generics [Visual Basic], type inference
- procedures [Visual Basic], generic
- generic procedures
- type inference, generics
- generic methods [Visual Basic]
- type inference
- generics [Visual Basic], procedures
- generic procedures [Visual Basic], type inference
ms.assetid: 95577b28-137f-4d5c-a149-919c828600e5
ms.openlocfilehash: 4aed16ce9eb59da54156a0cd5f1594819788521b
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818919"
---
# <a name="generic-procedures-in-visual-basic"></a><span data-ttu-id="7ea25-102">Generic Procedures in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7ea25-102">Generic Procedures in Visual Basic</span></span>
<span data-ttu-id="7ea25-103">*제네릭 프로시저*라고도 하는 *제네릭 메서드*, 하나 이상의 형식 매개 변수를 사용 하 여 정의 하는 절차입니다.</span><span class="sxs-lookup"><span data-stu-id="7ea25-103">A *generic procedure*, also called a *generic method*, is a procedure defined with at least one type parameter.</span></span> <span data-ttu-id="7ea25-104">따라서 프로시저를 호출할 때마다 데이터 형식 요구 사항에 맞게 코드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ea25-104">This allows the calling code to tailor the data types to its requirements each time it calls the procedure.</span></span>  
  
 <span data-ttu-id="7ea25-105">프로시저는 제네릭 클래스 또는 일반 구조체 내에서 정의 되는 것 만으로 제네릭이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="7ea25-105">A procedure is not generic simply by virtue of being defined inside a generic class or a generic structure.</span></span> <span data-ttu-id="7ea25-106">제네릭 되도록 프로시저 걸릴 수 있습니다 일반 매개 변수 외에도 하나 이상의 형식 매개 변수를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ea25-106">To be generic, the procedure must take at least one type parameter, in addition to any normal parameters it might take.</span></span> <span data-ttu-id="7ea25-107">제네릭이 아닌 프로시저 및 제네릭이 아닌 클래스, 구조체 제네릭 클래스 또는 구조체를 포함 하거나 모듈에서 제네릭 프로시저를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ea25-107">A generic class or structure can contain nongeneric procedures, and a nongeneric class, structure, or module can contain generic procedures.</span></span>  
  
 <span data-ttu-id="7ea25-108">제네릭 프로시저 하나, 그리고 해당 프로시저 코드가 있을 경우 해당 반환 형식에 기본 매개 변수 목록에서 해당 형식 매개 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ea25-108">A generic procedure can use its type parameters in its normal parameter list, in its return type if it has one, and in its procedure code.</span></span>  
  
## <a name="type-inference"></a><span data-ttu-id="7ea25-109">형식 유추</span><span class="sxs-lookup"><span data-stu-id="7ea25-109">Type Inference</span></span>  
 <span data-ttu-id="7ea25-110">제네릭 프로시저가 형식 인수를 전혀 제공 하지 않고 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ea25-110">You can call a generic procedure without supplying any type arguments at all.</span></span> <span data-ttu-id="7ea25-111">이러한 방식으로 호출을 하는 경우 컴파일러는 프로시저의 형식 인수에 전달 하는 적절 한 데이터 형식을 확인 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ea25-111">If you call it this way, the compiler attempts to determine the appropriate data types to pass to the procedure's type arguments.</span></span> <span data-ttu-id="7ea25-112">이 이라고 *형식 유추*합니다.</span><span class="sxs-lookup"><span data-stu-id="7ea25-112">This is called *type inference*.</span></span> <span data-ttu-id="7ea25-113">다음 코드는 호출을 보여 줍니다. 컴파일러 유추 하는 형식 전달 해야 `String` 형식 매개 변수에 `t`합니다.</span><span class="sxs-lookup"><span data-stu-id="7ea25-113">The following code shows a call in which the compiler infers that it should pass type `String` to the type parameter `t`.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#15)]  
  
 <span data-ttu-id="7ea25-114">컴파일러는 호출 컨텍스트에서 형식 인수를 유추할 수 없습니다, 하는 경우 오류를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ea25-114">If the compiler cannot infer the type arguments from the context of your call, it reports an error.</span></span> <span data-ttu-id="7ea25-115">이러한 오류가 발생할 수 있는 배열 차수가 일치 하지 않는 경우</span><span class="sxs-lookup"><span data-stu-id="7ea25-115">One possible cause of such an error is an array rank mismatch.</span></span> <span data-ttu-id="7ea25-116">예를 들어, 형식 매개 변수 배열로 일반 매개 변수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ea25-116">For example, suppose you define a normal parameter as an array of a type parameter.</span></span> <span data-ttu-id="7ea25-117">다른 차수 (차원 수)의 배열을 제공 제네릭 프로시저를 호출 하는 경우 일치 하지 않는 하면 형식을 유추할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7ea25-117">If you call the generic procedure supplying an array of a different rank (number of dimensions), the mismatch causes type inference to fail.</span></span> <span data-ttu-id="7ea25-118">다음 코드는 호출을 보여 줍니다. 2 차원 배열은 1 차원 배열을 필요로 하는 프로시저에 전달 되는에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ea25-118">The following code shows a call in which a two-dimensional array is passed to a procedure that expects a one-dimensional array.</span></span>  
  
```vb  
Public Sub demoSub(Of t)(ByVal arg() As t)
End Sub

Public Sub callDemoSub()
    Dim twoDimensions(,) As Integer
    demoSub(twoDimensions)
End Sub
```
  
 <span data-ttu-id="7ea25-119">모든 형식 인수를 생략 해야만 형식 유추를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ea25-119">You can invoke type inference only by omitting all the type arguments.</span></span> <span data-ttu-id="7ea25-120">하나의 형식 인수를 제공 하는 경우 모두 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ea25-120">If you supply one type argument, you must supply them all.</span></span>  
  
 <span data-ttu-id="7ea25-121">형식 유추가 제네릭 프로시저에만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ea25-121">Type inference is supported only for generic procedures.</span></span> <span data-ttu-id="7ea25-122">제네릭 클래스, 구조체, 인터페이스 또는 대리자에서 형식 유추를 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7ea25-122">You cannot invoke type inference on generic classes, structures, interfaces, or delegates.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ea25-123">예제</span><span class="sxs-lookup"><span data-stu-id="7ea25-123">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="7ea25-124">설명</span><span class="sxs-lookup"><span data-stu-id="7ea25-124">Description</span></span>  
 <span data-ttu-id="7ea25-125">다음 예제에서는 제네릭 정의 `Function` 프로시저 배열에서 특정 요소를 찾으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ea25-125">The following example defines a generic `Function` procedure to find a particular element in an array.</span></span> <span data-ttu-id="7ea25-126">하나의 형식 매개 변수를 정의 하 고 매개 변수 목록에 두 개의 매개 변수를 생성 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ea25-126">It defines one type parameter and uses it to construct the two parameters in the parameter list.</span></span>  
  
### <a name="code"></a><span data-ttu-id="7ea25-127">코드</span><span class="sxs-lookup"><span data-stu-id="7ea25-127">Code</span></span>  
 [!code-vb[VbVbalrDataTypes#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#14)]  
  
### <a name="comments"></a><span data-ttu-id="7ea25-128">설명</span><span class="sxs-lookup"><span data-stu-id="7ea25-128">Comments</span></span>  
 <span data-ttu-id="7ea25-129">앞의 예제 비교 하는 기능을 요구 `searchValue` 의 각 요소에 대해 `searchArray`합니다.</span><span class="sxs-lookup"><span data-stu-id="7ea25-129">The preceding example requires the ability to compare `searchValue` against each element of `searchArray`.</span></span> <span data-ttu-id="7ea25-130">이 기능을 보장 하기 위해 형식 매개 변수를 제한 `T` 를 구현 하는 <xref:System.IComparable%601> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="7ea25-130">To guarantee this ability, it constrains the type parameter `T` to implement the <xref:System.IComparable%601> interface.</span></span> <span data-ttu-id="7ea25-131">코드를 사용 하는 <xref:System.IComparable%601.CompareTo%2A> 메서드 대신 합니다 `=` 연산자에 대 한 형식 인수를 제공 하지 않을 수도 있기 때문에 `T` 지원를 `=` 연산자.</span><span class="sxs-lookup"><span data-stu-id="7ea25-131">The code uses the <xref:System.IComparable%601.CompareTo%2A> method instead of the `=` operator, because there is no guarantee that a type argument supplied for `T` supports the `=` operator.</span></span>  
  
 <span data-ttu-id="7ea25-132">테스트할 수 있습니다는 `findElement` 다음 코드를 사용 하 여 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="7ea25-132">You can test the `findElement` procedure with the following code.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#13)]  
  
 <span data-ttu-id="7ea25-133">에 대 한 호출 앞 `MsgBox` "0", "1" 및 "-1"은 각각 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ea25-133">The preceding calls to `MsgBox` display "0", "1", and "-1" respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ea25-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="7ea25-134">See also</span></span>

- [<span data-ttu-id="7ea25-135">Visual Basic의 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="7ea25-135">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="7ea25-136">방법: 다른 데이터 형식에 동일한 기능을 제공할 수 있는 클래스 정의</span><span class="sxs-lookup"><span data-stu-id="7ea25-136">How to: Define a Class That Can Provide Identical Functionality on Different Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)
- [<span data-ttu-id="7ea25-137">방법: 제네릭 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="7ea25-137">How to: Use a Generic Class</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="7ea25-138">절차</span><span class="sxs-lookup"><span data-stu-id="7ea25-138">Procedures</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="7ea25-139">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="7ea25-139">Procedure Parameters and Arguments</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [<span data-ttu-id="7ea25-140">형식 목록</span><span class="sxs-lookup"><span data-stu-id="7ea25-140">Type List</span></span>](../../../../visual-basic/language-reference/statements/type-list.md)
- [<span data-ttu-id="7ea25-141">매개 변수 목록</span><span class="sxs-lookup"><span data-stu-id="7ea25-141">Parameter List</span></span>](../../../../visual-basic/language-reference/statements/parameter-list.md)
