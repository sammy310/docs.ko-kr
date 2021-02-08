---
description: '자세한 정보: 개체 변수 또는 With block 변수가 설정 되지 않음'
title: Object 변수 또는 With 블록 변수가 설정되지 않았습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID91
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
ms.openlocfilehash: a20655c2219aa5b90015e025a38ea9dd02894a6c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795575"
---
# <a name="object-variable-or-with-block-variable-not-set"></a><span data-ttu-id="b7384-103">Object 변수 또는 With 블록 변수가 설정되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="b7384-103">Object variable or With block variable not set</span></span>

<span data-ttu-id="b7384-104">잘못 된 개체 변수를 참조 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7384-104">An invalid object variable is being referenced.</span></span> <span data-ttu-id="b7384-105">여러 가지 원인에 의해 이런 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7384-105">This error can occur for several reasons:</span></span>

- <span data-ttu-id="b7384-106">형식을 지정 하지 않고 변수가 선언 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b7384-106">A variable was declared without specifying a type.</span></span> <span data-ttu-id="b7384-107">형식을 지정 하지 않고 변수를 선언 하는 경우 기본값은 형식 `Object` 입니다.</span><span class="sxs-lookup"><span data-stu-id="b7384-107">If a variable is declared without specifying a type, it defaults to type `Object`.</span></span>

    <span data-ttu-id="b7384-108">예를 들어를 사용 하 여 선언 된 변수는 `Dim x` 형식입니다 `Object;` `Dim x As String` `String` .</span><span class="sxs-lookup"><span data-stu-id="b7384-108">For example, a variable declared with `Dim x` would be of type `Object;` a variable declared with `Dim x As String` would be of type `String`.</span></span>

    > [!TIP]
    > <span data-ttu-id="b7384-109">`Option Strict`문은 형식을 반환 하는 암시적 형식 지정을 허용 하지 `Object` 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7384-109">The `Option Strict` statement disallows implicit typing that results in an `Object` type.</span></span> <span data-ttu-id="b7384-110">형식을 생략 하면 컴파일 타임 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7384-110">If you omit the type, a compile-time error will occur.</span></span> <span data-ttu-id="b7384-111">[Option Strict 문](../statements/option-strict-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b7384-111">See [Option Strict Statement](../statements/option-strict-statement.md).</span></span>

- <span data-ttu-id="b7384-112">로 설정 된 개체를 참조 하려고 `Nothing` 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7384-112">You are attempting to reference an object that has been set to `Nothing`.</span></span>

- <span data-ttu-id="b7384-113">올바르게 선언 되지 않은 배열 변수의 요소에 액세스 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7384-113">You are attempting to access an element of an array variable that wasn't properly declared.</span></span>

    <span data-ttu-id="b7384-114">예를 들어로 선언 된 배열은 `products() As String` 배열의 요소를 참조 하려고 할 때 오류를 트리거합니다 `products(3) = "Widget"` .</span><span class="sxs-lookup"><span data-stu-id="b7384-114">For example, an array declared as `products() As String` will trigger the error if you try to reference an element of the array `products(3) = "Widget"`.</span></span> <span data-ttu-id="b7384-115">배열에는 요소가 없고 개체로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7384-115">The array has no elements and is treated as an object.</span></span>

- <span data-ttu-id="b7384-116">`With...End With`블록이 초기화 되기 전에 블록 내의 코드에 액세스 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7384-116">You are attempting to access code within a `With...End With` block before the block has been initialized.</span></span>   <span data-ttu-id="b7384-117">`With...End With`문 진입점을 실행 하 여 블록을 초기화 해야 합니다 `With` .</span><span class="sxs-lookup"><span data-stu-id="b7384-117">A `With...End With` block must be initialized by executing the `With` statement entry point.</span></span>

> [!NOTE]
> <span data-ttu-id="b7384-118">이전 버전의 Visual Basic 또는 VBA에서는 `Set` 키워드 (대신)를 사용 하지 않고 변수에 값을 할당 하 여이 오류를 발생 시켰습니다 `x = "name"` `Set x = "name"` .</span><span class="sxs-lookup"><span data-stu-id="b7384-118">In earlier versions of Visual Basic or VBA, this error was also triggered by assigning a value to a variable without using the `Set` keyword (`x = "name"` instead of `Set x = "name"`).</span></span> <span data-ttu-id="b7384-119">`Set`Visual Basic .net에서는 더 이상 키워드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7384-119">The `Set` keyword is no longer valid in Visual Basic .Net.</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="b7384-120">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="b7384-120">To correct this error</span></span>

1. <span data-ttu-id="b7384-121">`Option Strict` `On` 파일의 시작 부분에 다음 코드를 추가 하 여를로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7384-121">Set `Option Strict` to `On` by adding the following code to the beginning of the file:</span></span>

    ```vb
    Option Strict On
    ```

    <span data-ttu-id="b7384-122">프로젝트를 실행 하면 형식 없이 지정 된 변수에 대 한 **오류 목록** 컴파일러 오류가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7384-122">When you run the project, a compiler error will appear in the **Error List** for any variable that was specified without a type.</span></span>

2. <span data-ttu-id="b7384-123">을 사용 하지 않으려는 경우 `Option Strict` 코드에서 형식 없이 지정 된 변수 ( `Dim x` 대신)를 검색 `Dim x As String` 하 고 원하는 형식을 선언에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7384-123">If you don't want to enable `Option Strict`, search your code for any variables that were specified without a type (`Dim x` instead of `Dim x As String`) and add the intended type to the declaration.</span></span>

3. <span data-ttu-id="b7384-124">로 설정 된 개체 변수를 참조 하지 않는지 확인 `Nothing` 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7384-124">Make sure you aren't referring to  an object variable that has been set to `Nothing`.</span></span>  <span data-ttu-id="b7384-125">코드에서 키워드를 검색 하 `Nothing` 고 개체를 참조 한 후에 야로 설정 되도록 코드를 수정 `Nothing` 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7384-125">Search your code for the keyword `Nothing`, and revise your code so that the object isn't set to `Nothing` until after you have referenced it.</span></span>

4. <span data-ttu-id="b7384-126">액세스 하기 전에 배열 변수가 치수화 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7384-126">Make sure that any array  variables are dimensioned before you access them.</span></span> <span data-ttu-id="b7384-127">처음에 배열을 만들 때 차원을 할당 하거나 ( `Dim x(5) As String` 대신 `Dim x() As String` ) 키워드를 사용 `ReDim` 하 여 배열 크기를 설정 하 고 처음 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7384-127">You can either assign a dimension when you first create the array (`Dim x(5) As String` instead of `Dim x() As String`), or use the `ReDim` keyword to set the dimensions of the array before you first access it.</span></span>

5. <span data-ttu-id="b7384-128">`With`문 진입점을 실행 하 여 블록이 초기화 되었는지 확인 `With` 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7384-128">Make sure your `With` block is initialized by executing the `With` statement entry point.</span></span>

## <a name="see-also"></a><span data-ttu-id="b7384-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b7384-129">See also</span></span>

- [<span data-ttu-id="b7384-130">개체 변수 선언</span><span class="sxs-lookup"><span data-stu-id="b7384-130">Object Variable Declaration</span></span>](../../programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="b7384-131">ReDim 문</span><span class="sxs-lookup"><span data-stu-id="b7384-131">ReDim Statement</span></span>](../statements/redim-statement.md)
- [<span data-ttu-id="b7384-132">With...End With 문</span><span class="sxs-lookup"><span data-stu-id="b7384-132">With...End With Statement</span></span>](../statements/with-end-with-statement.md)
