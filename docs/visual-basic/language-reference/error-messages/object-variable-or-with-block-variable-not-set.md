---
title: Object 변수 또는 With 블록 변수가 설정되지 않았습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID91
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
ms.openlocfilehash: 1b24bec6dd7c4b5af10349cf523d9a7e93b385fe
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58831659"
---
# <a name="object-variable-or-with-block-variable-not-set"></a><span data-ttu-id="09e3c-102">Object 변수 또는 With 블록 변수가 설정되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="09e3c-102">Object variable or With block variable not set</span></span>
<span data-ttu-id="09e3c-103">잘못 된 개체 변수는 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09e3c-103">An invalid object variable is being referenced.</span></span>   <span data-ttu-id="09e3c-104">여러 가지 원인에 의해 이런 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e3c-104">This error can occur for several reasons:</span></span>  
  
-   <span data-ttu-id="09e3c-105">변수는 형식을 지정 하지 않고 선언 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="09e3c-105">A variable was declared without specifying a type.</span></span> <span data-ttu-id="09e3c-106">기본적으로 입력 변수 형식을 지정 하지 않고 선언 된 경우 `Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="09e3c-106">If a variable is declared without specifying a type, it defaults to type `Object`.</span></span>  
  
     <span data-ttu-id="09e3c-107">예를 들어, 사용 하 여 선언 된 변수에 `Dim x` 형식의 것 `Object;` 로 선언 된 변수 `Dim x As String` 형식일 수는 `String`합니다.</span><span class="sxs-lookup"><span data-stu-id="09e3c-107">For example, a variable declared with `Dim x` would be of type `Object;` a variable declared with `Dim x As String` would be of type `String`.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="09e3c-108">합니다 `Option Strict` 문이 발생 되는 암시적 형식을 허용 하지 않는 `Object` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="09e3c-108">The `Option Strict` statement disallows implicit typing that results in an `Object` type.</span></span> <span data-ttu-id="09e3c-109">형식을 생략 하면 컴파일 타임 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e3c-109">If you omit the type, a compile-time error will occur.</span></span> <span data-ttu-id="09e3c-110">참조 [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="09e3c-110">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
-   <span data-ttu-id="09e3c-111">에 설정 된 개체를 참조 하려고 합니다. `Nothing`</span><span class="sxs-lookup"><span data-stu-id="09e3c-111">You are attempting to reference an object that has been set to `Nothing`</span></span>  
  
     <span data-ttu-id="09e3c-112">.</span><span class="sxs-lookup"><span data-stu-id="09e3c-112">.</span></span>  
  
-   <span data-ttu-id="09e3c-113">배열 변수를 제대로 선언 되지 않은의 요소에 액세스 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e3c-113">You are attempting to access an element of an array variable that wasn't properly declared.</span></span>  
  
     <span data-ttu-id="09e3c-114">로 배열을 선언 하는 예를 들어 `products() As String` 배열의 요소를 참조 하려고 하면 오류를 트리거할 `products(3) = "Widget"`합니다.</span><span class="sxs-lookup"><span data-stu-id="09e3c-114">For example, an array declared as `products() As String` will trigger the error if you try to reference an element of the array `products(3) = "Widget"`.</span></span> <span data-ttu-id="09e3c-115">배열의 요소가 없는 고 개체로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09e3c-115">The array has no elements and is treated as an object.</span></span>  
  
-   <span data-ttu-id="09e3c-116">내의 코드에서 액세스 하려는 `With...End With` 블록 초기화 되기 전에 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e3c-116">You are attempting to access code within a `With...End With` block before the block has been initialized.</span></span>   <span data-ttu-id="09e3c-117">A `With...End With` 블록을 실행 하 여 초기화 해야 합니다 `With` 문 진입점입니다.</span><span class="sxs-lookup"><span data-stu-id="09e3c-117">A `With...End With` block must be initialized by executing the `With` statement entry point.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="09e3c-118">이전 버전의 Visual Basic 또는 VBA에서이 오류도을 트리거한 것을 사용 하지 않고 값을 변수에 할당 합니다 `Set` 키워드 (`x = "name"` 대신 `Set x = "name"`).</span><span class="sxs-lookup"><span data-stu-id="09e3c-118">In earlier versions of Visual Basic or VBA this error was also triggered by assigning a value to a variable without using the `Set` keyword (`x = "name"` instead of `Set x = "name"`).</span></span> <span data-ttu-id="09e3c-119">`Set` 키워드 Visual Basic.net에서 더 이상 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e3c-119">The `Set` keyword is no longer valid in Visual Basic .Net.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="09e3c-120">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="09e3c-120">To correct this error</span></span>  
  
1.  <span data-ttu-id="09e3c-121">설정할 `Option Strict` 에 `On` 파일의 시작 부분에 다음 코드를 추가 하 여:</span><span class="sxs-lookup"><span data-stu-id="09e3c-121">Set `Option Strict` to `On` by adding the following code to the beginning of the file:</span></span>  
  
```vb  
Option Strict On  
```  

     When you run the project, a compiler error will appear in the **Error List** for any variable that was specified without a type.  
  
2.  <span data-ttu-id="09e3c-122">사용 하도록 설정 하지 않으려면 `Option Strict`, 형식을 사용 하지 않고 지정 된 변수에 대 한 코드 검색 (`Dim x` 대신 `Dim x As String`) 의도 된 형식 선언에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e3c-122">If you don't want to enable `Option Strict`, search your code for any variables that were specified without a type (`Dim x` instead of `Dim x As String`) and add the intended type to the declaration.</span></span>  
  
3.  <span data-ttu-id="09e3c-123">에 설정 된 개체 변수에 참조 되지 있는지 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="09e3c-123">Make sure you aren't referring to  an object variable that has been set to `Nothing`.</span></span>  <span data-ttu-id="09e3c-124">키워드에 대 한 코드 검색 `Nothing`, 개체 설정 되지 않도록 코드를 수정 하 고 `Nothing` 참조 한 후 될 때까지 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e3c-124">Search your code for the keyword `Nothing`, and revise your code so that the object isn't set to `Nothing` until after you have referenced it.</span></span>  
  
4.  <span data-ttu-id="09e3c-125">액세스 하기 전에 모든 배열 변수는 차원이 구분 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e3c-125">Make sure that any array  variables are dimensioned before you access them.</span></span> <span data-ttu-id="09e3c-126">배열을 처음 만들 때 차원을 할당 하거나 (`Dim x(5) As String` 대신 `Dim x() As String`)를 사용할지를 `ReDim` 처음으로 액세스 하기 전에 배열의 차수를 설정 하려면 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="09e3c-126">You can either assign a dimension when you first create the array (`Dim x(5) As String` instead of `Dim x() As String`), or use the `ReDim` keyword to set the dimensions of the array before you first access it.</span></span>  
  
5.  <span data-ttu-id="09e3c-127">있는지 확인 하 `With` 블록을 실행 하 여 초기화를 `With` 문 진입점입니다.</span><span class="sxs-lookup"><span data-stu-id="09e3c-127">Make sure your `With` block is initialized by executing the `With` statement entry point.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09e3c-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="09e3c-128">See also</span></span>

- [<span data-ttu-id="09e3c-129">개체 변수 선언</span><span class="sxs-lookup"><span data-stu-id="09e3c-129">Object Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="09e3c-130">ReDim 문</span><span class="sxs-lookup"><span data-stu-id="09e3c-130">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
- [<span data-ttu-id="09e3c-131">With...End With 문</span><span class="sxs-lookup"><span data-stu-id="09e3c-131">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
