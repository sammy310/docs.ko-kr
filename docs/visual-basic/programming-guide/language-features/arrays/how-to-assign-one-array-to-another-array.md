---
description: '자세한 정보: 방법: 한 배열에 다른 배열 할당 (Visual Basic)'
title: '방법: 한 배열에 다른 배열 할당'
ms.date: 07/20/2015
helpviewer_keywords:
- covariance, arrays
- arrays [Visual Basic], assigning
- arrays [Visual Basic], covariance
ms.assetid: 1ae89ea5-f292-4282-bcfc-e9b06b37fbd5
ms.openlocfilehash: dc86225c1f25c207e793e33a048d948646ac77b6
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100434734"
---
# <a name="how-to-assign-one-array-to-another-array-visual-basic"></a><span data-ttu-id="7f1f7-103">방법: 한 배열에 다른 배열 할당(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7f1f7-103">How to: Assign One Array to Another Array (Visual Basic)</span></span>

<span data-ttu-id="7f1f7-104">배열은 개체 이기 때문에 다른 개체 형식과 같은 대입문에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-104">Because arrays are objects, you can use them in assignment statements like other object types.</span></span> <span data-ttu-id="7f1f7-105">배열 변수는 배열 요소와 차수 및 length 정보를 백업을 위해 하는 데이터에 대 한 포인터를 보유 하 고 할당은이 포인터만 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-105">An array variable holds a pointer to the data constituting the array elements and the rank and length information, and an assignment copies only this pointer.</span></span>

### <a name="to-assign-one-array-to-another-array"></a><span data-ttu-id="7f1f7-106">한 배열을 다른 배열에 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="7f1f7-106">To assign one array to another array</span></span>

1. <span data-ttu-id="7f1f7-107">두 배열의 차수 (차원 수)와 호환 되는 요소 데이터 형식이 같은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-107">Ensure that the two arrays have the same rank (number of dimensions) and compatible element data types.</span></span>

2. <span data-ttu-id="7f1f7-108">표준 대입문을 사용 하 여 소스 배열을 대상 배열에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-108">Use a standard assignment statement to assign the source array to the destination array.</span></span> <span data-ttu-id="7f1f7-109">괄호를 사용 하 여 배열 이름을 따르지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-109">Do not follow either array name with parentheses.</span></span>

    ```vb
    Dim formArray() As System.Windows.Forms.Form
    Dim controlArray() As System.Windows.Forms.Control
    controlArray = formArray
    ```

<span data-ttu-id="7f1f7-110">한 배열을 다른 배열에 할당 하는 경우 다음 규칙이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-110">When you assign one array to another, the following rules apply:</span></span>

- <span data-ttu-id="7f1f7-111">**순위가 동일 합니다.**</span><span class="sxs-lookup"><span data-stu-id="7f1f7-111">**Equal Ranks.**</span></span> <span data-ttu-id="7f1f7-112">대상 배열의 차수 (차원 수)는 원본 배열의 차수 (차원 수)와 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-112">The rank (number of dimensions) of the destination array must be the same as that of the source array.</span></span>

  <span data-ttu-id="7f1f7-113">두 배열의 순위가 동일 하 게 지정 된 경우 차원이 같을 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-113">Provided the ranks of the two arrays are equal, the dimensions do not need to be equal.</span></span> <span data-ttu-id="7f1f7-114">지정 된 차원의 요소 수는 할당 중에 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-114">The number of elements in a given dimension can change during assignment.</span></span>

- <span data-ttu-id="7f1f7-115">**요소 형식.**</span><span class="sxs-lookup"><span data-stu-id="7f1f7-115">**Element Types.**</span></span> <span data-ttu-id="7f1f7-116">두 배열 중 하나에 *참조 형식* 요소가 있거나 두 배열에 모두 *값 형식* 요소가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-116">Either both arrays must have *reference type* elements or both arrays must have *value type* elements.</span></span> <span data-ttu-id="7f1f7-117">자세한 내용은 [값 형식 및 참조 형식](../data-types/value-types-and-reference-types.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-117">For more information, see [Value Types and Reference Types](../data-types/value-types-and-reference-types.md).</span></span>

  - <span data-ttu-id="7f1f7-118">두 배열에 모두 값 형식 요소가 있으면 요소 데이터 형식이 정확히 동일 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-118">If both arrays have value type elements, the element data types must be exactly the same.</span></span> <span data-ttu-id="7f1f7-119">이에 대 한 유일한 예외는 `Enum` 요소의 배열을 기본 형식의 배열에 할당할 수 있다는 것입니다 `Enum` .</span><span class="sxs-lookup"><span data-stu-id="7f1f7-119">The only exception to this is that you can assign an array of `Enum` elements to an array of the base type of that `Enum`.</span></span>

  - <span data-ttu-id="7f1f7-120">두 배열에 모두 참조 형식 요소가 있으면 원본 요소 형식이 대상 요소 형식에서 파생 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-120">If both arrays have reference type elements, the source element type must derive from the destination element type.</span></span> <span data-ttu-id="7f1f7-121">이 경우 두 배열의 요소와 상속 관계가 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-121">When this is the case, the two arrays have the same inheritance relationship as their elements.</span></span> <span data-ttu-id="7f1f7-122">이를 *배열 공분산* 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-122">This is called *array covariance*.</span></span>

<span data-ttu-id="7f1f7-123">위의 규칙을 위반 하는 경우 (예: 데이터 형식이 호환 되지 않거나 순위가 같지 않은 경우) 컴파일러에서 오류를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-123">The compiler reports an error if the above rules are violated, for example if the data types are not compatible or the ranks are unequal.</span></span> <span data-ttu-id="7f1f7-124">코드에 오류 처리를 추가 하 여 배열이 호환 되는지 확인 하 고 할당을 시도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-124">You can add error handling to your code to make sure that the arrays are compatible before attempting an assignment.</span></span> <span data-ttu-id="7f1f7-125">예외를 throw 하지 않으려면 [TryCast Operator](../../../language-reference/operators/trycast-operator.md) 키워드를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-125">You can also use the [TryCast Operator](../../../language-reference/operators/trycast-operator.md) keyword if you want to avoid throwing an exception.</span></span>

## <a name="see-also"></a><span data-ttu-id="7f1f7-126">참조</span><span class="sxs-lookup"><span data-stu-id="7f1f7-126">See also</span></span>

- [<span data-ttu-id="7f1f7-127">배열</span><span class="sxs-lookup"><span data-stu-id="7f1f7-127">Arrays</span></span>](index.md)
- [<span data-ttu-id="7f1f7-128">배열 문제 해결</span><span class="sxs-lookup"><span data-stu-id="7f1f7-128">Troubleshooting Arrays</span></span>](troubleshooting-arrays.md)
- [<span data-ttu-id="7f1f7-129">Enum 문</span><span class="sxs-lookup"><span data-stu-id="7f1f7-129">Enum Statement</span></span>](../../../language-reference/statements/enum-statement.md)
- [<span data-ttu-id="7f1f7-130">배열 규칙</span><span class="sxs-lookup"><span data-stu-id="7f1f7-130">Array Conversions</span></span>](../data-types/array-conversions.md)
