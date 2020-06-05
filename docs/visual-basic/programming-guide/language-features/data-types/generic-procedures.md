---
title: 제네릭 프로시저
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
ms.openlocfilehash: 2efc0410b9d4bb663e1ff19d5a5456d7ff2c99bd
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84394067"
---
# <a name="generic-procedures-in-visual-basic"></a><span data-ttu-id="b4544-102">Generic Procedures in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b4544-102">Generic Procedures in Visual Basic</span></span>
<span data-ttu-id="b4544-103">제네릭 *메서드*라고도 하는 *제네릭 프로시저*는 하나 이상의 형식 매개 변수를 사용 하 여 정의 된 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="b4544-103">A *generic procedure*, also called a *generic method*, is a procedure defined with at least one type parameter.</span></span> <span data-ttu-id="b4544-104">이를 통해 호출 코드는 프로시저를 호출할 때마다 데이터 형식을 요구 사항에 맞게 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4544-104">This allows the calling code to tailor the data types to its requirements each time it calls the procedure.</span></span>  
  
 <span data-ttu-id="b4544-105">프로시저는 제네릭 클래스 또는 제네릭 구조체 내에서 정의 되는 것 만으로는 제네릭이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="b4544-105">A procedure is not generic simply by virtue of being defined inside a generic class or a generic structure.</span></span> <span data-ttu-id="b4544-106">제네릭 하려면 프로시저에서 사용할 수 있는 일반 매개 변수 외에도 하나 이상의 형식 매개 변수를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4544-106">To be generic, the procedure must take at least one type parameter, in addition to any normal parameters it might take.</span></span> <span data-ttu-id="b4544-107">제네릭 클래스 또는 구조체는 제네릭이 아닌 프로시저를 포함할 수 있으며 제네릭이 아닌 클래스, 구조체 또는 모듈은 제네릭 프로시저를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4544-107">A generic class or structure can contain nongeneric procedures, and a nongeneric class, structure, or module can contain generic procedures.</span></span>  
  
 <span data-ttu-id="b4544-108">제네릭 프로시저의 형식 매개 변수는 해당 형식 매개 변수를 반환 형식 (있는 경우) 및 해당 프로시저 코드에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4544-108">A generic procedure can use its type parameters in its normal parameter list, in its return type if it has one, and in its procedure code.</span></span>  
  
## <a name="type-inference"></a><span data-ttu-id="b4544-109">형식 유추</span><span class="sxs-lookup"><span data-stu-id="b4544-109">Type Inference</span></span>  
 <span data-ttu-id="b4544-110">모든 형식 인수를 제공 하지 않고 제네릭 프로시저를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4544-110">You can call a generic procedure without supplying any type arguments at all.</span></span> <span data-ttu-id="b4544-111">이러한 방식으로 호출 하는 경우 컴파일러는 적절 한 데이터 형식을 확인 하 여 프로시저의 형식 인수에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4544-111">If you call it this way, the compiler attempts to determine the appropriate data types to pass to the procedure's type arguments.</span></span> <span data-ttu-id="b4544-112">이를 *형식 유추*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4544-112">This is called *type inference*.</span></span> <span data-ttu-id="b4544-113">다음 코드는 컴파일러에서 형식 매개 변수에 형식을 전달 해야 한다는 것을 유추 하는 호출을 보여 줍니다 `String` `t` .</span><span class="sxs-lookup"><span data-stu-id="b4544-113">The following code shows a call in which the compiler infers that it should pass type `String` to the type parameter `t`.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#15)]  
  
 <span data-ttu-id="b4544-114">컴파일러가 호출 컨텍스트에서 형식 인수를 유추할 수 없는 경우 오류를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4544-114">If the compiler cannot infer the type arguments from the context of your call, it reports an error.</span></span> <span data-ttu-id="b4544-115">이러한 오류의 가능한 원인 중 하나는 배열 순위가 일치 하지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="b4544-115">One possible cause of such an error is an array rank mismatch.</span></span> <span data-ttu-id="b4544-116">예를 들어 일반 매개 변수를 형식 매개 변수의 배열로 정의 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4544-116">For example, suppose you define a normal parameter as an array of a type parameter.</span></span> <span data-ttu-id="b4544-117">다른 순위 (차원 수)의 배열을 제공 하는 제네릭 프로시저를 호출 하면 형식 유추가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4544-117">If you call the generic procedure supplying an array of a different rank (number of dimensions), the mismatch causes type inference to fail.</span></span> <span data-ttu-id="b4544-118">다음 코드에서는 2 차원 배열이 1 차원 배열을 필요로 하는 프로시저로 전달 되는 호출을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b4544-118">The following code shows a call in which a two-dimensional array is passed to a procedure that expects a one-dimensional array.</span></span>  
  
```vb  
Public Sub demoSub(Of t)(ByVal arg() As t)
End Sub

Public Sub callDemoSub()
    Dim twoDimensions(,) As Integer
    demoSub(twoDimensions)
End Sub
```
  
 <span data-ttu-id="b4544-119">형식 유추는 모든 형식 인수를 생략 하는 경우에만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4544-119">You can invoke type inference only by omitting all the type arguments.</span></span> <span data-ttu-id="b4544-120">하나의 형식 인수를 제공 하는 경우 모두 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4544-120">If you supply one type argument, you must supply them all.</span></span>  
  
 <span data-ttu-id="b4544-121">형식 유추는 제네릭 프로시저에만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4544-121">Type inference is supported only for generic procedures.</span></span> <span data-ttu-id="b4544-122">제네릭 클래스, 구조체, 인터페이스 또는 대리자에 대해서는 형식 유추를 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4544-122">You cannot invoke type inference on generic classes, structures, interfaces, or delegates.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4544-123">예제</span><span class="sxs-lookup"><span data-stu-id="b4544-123">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="b4544-124">Description</span><span class="sxs-lookup"><span data-stu-id="b4544-124">Description</span></span>  
 <span data-ttu-id="b4544-125">다음 예제에서는 `Function` 배열에서 특정 요소를 찾기 위한 제네릭 프로시저를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4544-125">The following example defines a generic `Function` procedure to find a particular element in an array.</span></span> <span data-ttu-id="b4544-126">하나의 형식 매개 변수를 정의 하 고이를 사용 하 여 매개 변수 목록에서 두 개의 매개 변수를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4544-126">It defines one type parameter and uses it to construct the two parameters in the parameter list.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b4544-127">코드</span><span class="sxs-lookup"><span data-stu-id="b4544-127">Code</span></span>  
 [!code-vb[VbVbalrDataTypes#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#14)]  
  
### <a name="comments"></a><span data-ttu-id="b4544-128">주석</span><span class="sxs-lookup"><span data-stu-id="b4544-128">Comments</span></span>  
 <span data-ttu-id="b4544-129">앞의 예제에서는의 각 요소를 비교 하는 기능이 필요 합니다 `searchValue` `searchArray` .</span><span class="sxs-lookup"><span data-stu-id="b4544-129">The preceding example requires the ability to compare `searchValue` against each element of `searchArray`.</span></span> <span data-ttu-id="b4544-130">이 기능을 보장 하기 위해 형식 매개 변수를 제한 하 여 `T` 인터페이스를 구현 <xref:System.IComparable%601> 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4544-130">To guarantee this ability, it constrains the type parameter `T` to implement the <xref:System.IComparable%601> interface.</span></span> <span data-ttu-id="b4544-131"><xref:System.IComparable%601.CompareTo%2A> `=` 에 제공 된 형식 인수가 연산자를 지원 한다는 보장이 없으므로 코드는 연산자 대신 메서드를 사용 합니다 `T` `=` .</span><span class="sxs-lookup"><span data-stu-id="b4544-131">The code uses the <xref:System.IComparable%601.CompareTo%2A> method instead of the `=` operator, because there is no guarantee that a type argument supplied for `T` supports the `=` operator.</span></span>  
  
 <span data-ttu-id="b4544-132">다음 코드를 사용 하 여 프로시저를 테스트할 수 있습니다 `findElement` .</span><span class="sxs-lookup"><span data-stu-id="b4544-132">You can test the `findElement` procedure with the following code.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#13)]  
  
 <span data-ttu-id="b4544-133">앞의 호출은 `MsgBox` 각각 "0", "1" 및 "-1"을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4544-133">The preceding calls to `MsgBox` display "0", "1", and "-1" respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4544-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b4544-134">See also</span></span>

- [<span data-ttu-id="b4544-135">Visual Basic의 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="b4544-135">Generic Types in Visual Basic</span></span>](generic-types.md)
- [<span data-ttu-id="b4544-136">방법: 다른 데이터 형식에 동일한 기능을 제공할 수 있는 클래스 정의</span><span class="sxs-lookup"><span data-stu-id="b4544-136">How to: Define a Class That Can Provide Identical Functionality on Different Data Types</span></span>](how-to-define-a-class-that-can-provide-identical-functionality.md)
- [<span data-ttu-id="b4544-137">방법: 제네릭 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="b4544-137">How to: Use a Generic Class</span></span>](how-to-use-a-generic-class.md)
- [<span data-ttu-id="b4544-138">절차</span><span class="sxs-lookup"><span data-stu-id="b4544-138">Procedures</span></span>](../procedures/index.md)
- [<span data-ttu-id="b4544-139">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="b4544-139">Procedure Parameters and Arguments</span></span>](../procedures/procedure-parameters-and-arguments.md)
- [<span data-ttu-id="b4544-140">Type List</span><span class="sxs-lookup"><span data-stu-id="b4544-140">Type List</span></span>](../../../language-reference/statements/type-list.md)
- [<span data-ttu-id="b4544-141">매개 변수 목록</span><span class="sxs-lookup"><span data-stu-id="b4544-141">Parameter List</span></span>](../../../language-reference/statements/parameter-list.md)
