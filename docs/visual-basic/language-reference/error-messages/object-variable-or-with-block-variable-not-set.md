---
title: Object 변수 또는 With 블록 변수가 설정되지 않았습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID91
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
ms.openlocfilehash: 0264a4235a056c93edb703ec2ef70e7124e0df4e
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873624"
---
# <a name="object-variable-or-with-block-variable-not-set"></a><span data-ttu-id="1c832-102">Object 변수 또는 With 블록 변수가 설정되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="1c832-102">Object variable or With block variable not set</span></span>

<span data-ttu-id="1c832-103">잘못 된 개체 변수를 참조 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c832-103">An invalid object variable is being referenced.</span></span>   <span data-ttu-id="1c832-104">여러 가지 원인에 의해 이런 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c832-104">This error can occur for several reasons:</span></span>

- <span data-ttu-id="1c832-105">형식을 지정 하지 않고 변수가 선언 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1c832-105">A variable was declared without specifying a type.</span></span> <span data-ttu-id="1c832-106">형식을 지정 하지 않고 변수를 선언 하는 경우 기본값은 형식 `Object` 입니다.</span><span class="sxs-lookup"><span data-stu-id="1c832-106">If a variable is declared without specifying a type, it defaults to type `Object`.</span></span>

    <span data-ttu-id="1c832-107">예를 들어를 사용 하 여 선언 된 변수는 `Dim x` 형식입니다 `Object;` `Dim x As String` `String` .</span><span class="sxs-lookup"><span data-stu-id="1c832-107">For example, a variable declared with `Dim x` would be of type `Object;` a variable declared with `Dim x As String` would be of type `String`.</span></span>

    > [!TIP]
    > <span data-ttu-id="1c832-108">`Option Strict`문은 형식을 반환 하는 암시적 형식 지정을 허용 하지 `Object` 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c832-108">The `Option Strict` statement disallows implicit typing that results in an `Object` type.</span></span> <span data-ttu-id="1c832-109">형식을 생략 하면 컴파일 타임 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c832-109">If you omit the type, a compile-time error will occur.</span></span> <span data-ttu-id="1c832-110">[Option Strict 문](../statements/option-strict-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c832-110">See [Option Strict Statement](../statements/option-strict-statement.md).</span></span>

- <span data-ttu-id="1c832-111">로 설정 된 개체를 참조 하려고 `Nothing` 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c832-111">You are attempting to reference an object that has been set to `Nothing`.</span></span>

- <span data-ttu-id="1c832-112">올바르게 선언 되지 않은 배열 변수의 요소에 액세스 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c832-112">You are attempting to access an element of an array variable that wasn't properly declared.</span></span>

    <span data-ttu-id="1c832-113">예를 들어로 선언 된 배열은 `products() As String` 배열의 요소를 참조 하려고 할 때 오류를 트리거합니다 `products(3) = "Widget"` .</span><span class="sxs-lookup"><span data-stu-id="1c832-113">For example, an array declared as `products() As String` will trigger the error if you try to reference an element of the array `products(3) = "Widget"`.</span></span> <span data-ttu-id="1c832-114">배열에는 요소가 없고 개체로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c832-114">The array has no elements and is treated as an object.</span></span>

- <span data-ttu-id="1c832-115">`With...End With`블록이 초기화 되기 전에 블록 내의 코드에 액세스 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c832-115">You are attempting to access code within a `With...End With` block before the block has been initialized.</span></span>   <span data-ttu-id="1c832-116">`With...End With`문 진입점을 실행 하 여 블록을 초기화 해야 합니다 `With` .</span><span class="sxs-lookup"><span data-stu-id="1c832-116">A `With...End With` block must be initialized by executing the `With` statement entry point.</span></span>

> [!NOTE]
> <span data-ttu-id="1c832-117">이전 버전의 Visual Basic 또는 VBA에서이 오류는 `Set` 대신 키워드 ( `x = "name"` 대신)를 사용 하지 않고 변수에 값을 할당 하 여 트리거됩니다 `Set x = "name"` .</span><span class="sxs-lookup"><span data-stu-id="1c832-117">In earlier versions of Visual Basic or VBA this error was also triggered by assigning a value to a variable without using the `Set` keyword (`x = "name"` instead of `Set x = "name"`).</span></span> <span data-ttu-id="1c832-118">`Set`Visual Basic .net에서는 더 이상 키워드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c832-118">The `Set` keyword is no longer valid in Visual Basic .Net.</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="1c832-119">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="1c832-119">To correct this error</span></span>

1. <span data-ttu-id="1c832-120">`Option Strict` `On` 파일의 시작 부분에 다음 코드를 추가 하 여를로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c832-120">Set `Option Strict` to `On` by adding the following code to the beginning of the file:</span></span>

    ```vb
    Option Strict On
    ```

    <span data-ttu-id="1c832-121">프로젝트를 실행 하면 형식 없이 지정 된 변수에 대 한 **오류 목록** 컴파일러 오류가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c832-121">When you run the project, a compiler error will appear in the **Error List** for any variable that was specified without a type.</span></span>

2. <span data-ttu-id="1c832-122">을 사용 하지 않으려는 경우 `Option Strict` 코드에서 형식 없이 지정 된 변수 ( `Dim x` 대신)를 검색 `Dim x As String` 하 고 원하는 형식을 선언에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c832-122">If you don't want to enable `Option Strict`, search your code for any variables that were specified without a type (`Dim x` instead of `Dim x As String`) and add the intended type to the declaration.</span></span>

3. <span data-ttu-id="1c832-123">로 설정 된 개체 변수를 참조 하지 않는지 확인 `Nothing` 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c832-123">Make sure you aren't referring to  an object variable that has been set to `Nothing`.</span></span>  <span data-ttu-id="1c832-124">코드에서 키워드를 검색 하 `Nothing` 고 개체를 참조 한 후에 야로 설정 되도록 코드를 수정 `Nothing` 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c832-124">Search your code for the keyword `Nothing`, and revise your code so that the object isn't set to `Nothing` until after you have referenced it.</span></span>

4. <span data-ttu-id="1c832-125">액세스 하기 전에 배열 변수가 치수화 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c832-125">Make sure that any array  variables are dimensioned before you access them.</span></span> <span data-ttu-id="1c832-126">처음에 배열을 만들 때 차원을 할당 하거나 ( `Dim x(5) As String` 대신 `Dim x() As String` ) 키워드를 사용 `ReDim` 하 여 배열 크기를 설정 하 고 처음 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c832-126">You can either assign a dimension when you first create the array (`Dim x(5) As String` instead of `Dim x() As String`), or use the `ReDim` keyword to set the dimensions of the array before you first access it.</span></span>

5. <span data-ttu-id="1c832-127">`With`문 진입점을 실행 하 여 블록이 초기화 되었는지 확인 `With` 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c832-127">Make sure your `With` block is initialized by executing the `With` statement entry point.</span></span>

## <a name="see-also"></a><span data-ttu-id="1c832-128">참조</span><span class="sxs-lookup"><span data-stu-id="1c832-128">See also</span></span>

- [<span data-ttu-id="1c832-129">개체 변수 선언</span><span class="sxs-lookup"><span data-stu-id="1c832-129">Object Variable Declaration</span></span>](../../programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="1c832-130">ReDim 문</span><span class="sxs-lookup"><span data-stu-id="1c832-130">ReDim Statement</span></span>](../statements/redim-statement.md)
- [<span data-ttu-id="1c832-131">With...End With 문</span><span class="sxs-lookup"><span data-stu-id="1c832-131">With...End With Statement</span></span>](../statements/with-end-with-statement.md)
