---
title: '방법: 한 배열에 다른 배열 할당'
ms.date: 07/20/2015
helpviewer_keywords:
- covariance, arrays
- arrays [Visual Basic], assigning
- arrays [Visual Basic], covariance
ms.assetid: 1ae89ea5-f292-4282-bcfc-e9b06b37fbd5
ms.openlocfilehash: be5337e36c2cc7ad9f9b32182b8575ac66bb4a50
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351885"
---
# <a name="how-to-assign-one-array-to-another-array-visual-basic"></a><span data-ttu-id="af68d-102">방법: 한 배열에 다른 배열 할당(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="af68d-102">How to: Assign One Array to Another Array (Visual Basic)</span></span>

<span data-ttu-id="af68d-103">배열은 개체 이기 때문에 다른 개체 형식과 같은 대입문에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af68d-103">Because arrays are objects, you can use them in assignment statements like other object types.</span></span> <span data-ttu-id="af68d-104">배열 변수는 배열 요소와 차수 및 length 정보를 백업을 위해 하는 데이터에 대 한 포인터를 보유 하 고 할당은이 포인터만 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="af68d-104">An array variable holds a pointer to the data constituting the array elements and the rank and length information, and an assignment copies only this pointer.</span></span>

### <a name="to-assign-one-array-to-another-array"></a><span data-ttu-id="af68d-105">한 배열을 다른 배열에 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="af68d-105">To assign one array to another array</span></span>

1. <span data-ttu-id="af68d-106">두 배열의 차수 (차원 수)와 호환 되는 요소 데이터 형식이 같은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="af68d-106">Ensure that the two arrays have the same rank (number of dimensions) and compatible element data types.</span></span>

2. <span data-ttu-id="af68d-107">표준 대입문을 사용 하 여 소스 배열을 대상 배열에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="af68d-107">Use a standard assignment statement to assign the source array to the destination array.</span></span> <span data-ttu-id="af68d-108">괄호를 사용 하 여 배열 이름을 따르지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="af68d-108">Do not follow either array name with parentheses.</span></span>

    ```vb
    Dim formArray() As System.Windows.Forms.Form
    Dim controlArray() As System.Windows.Forms.Control
    controlArray = formArray
    ```

<span data-ttu-id="af68d-109">한 배열을 다른 배열에 할당 하는 경우 다음 규칙이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af68d-109">When you assign one array to another, the following rules apply:</span></span>

- <span data-ttu-id="af68d-110">**순위가 동일 합니다.**</span><span class="sxs-lookup"><span data-stu-id="af68d-110">**Equal Ranks.**</span></span> <span data-ttu-id="af68d-111">대상 배열의 차수 (차원 수)는 원본 배열의 차수 (차원 수)와 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af68d-111">The rank (number of dimensions) of the destination array must be the same as that of the source array.</span></span>

  <span data-ttu-id="af68d-112">두 배열의 순위가 동일 하 게 지정 된 경우 차원이 같을 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af68d-112">Provided the ranks of the two arrays are equal, the dimensions do not need to be equal.</span></span> <span data-ttu-id="af68d-113">지정 된 차원의 요소 수는 할당 중에 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af68d-113">The number of elements in a given dimension can change during assignment.</span></span>

- <span data-ttu-id="af68d-114">**요소 형식.**</span><span class="sxs-lookup"><span data-stu-id="af68d-114">**Element Types.**</span></span> <span data-ttu-id="af68d-115">두 배열 중 하나에 *참조 형식* 요소가 있거나 두 배열에 모두 *값 형식* 요소가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af68d-115">Either both arrays must have *reference type* elements or both arrays must have *value type* elements.</span></span> <span data-ttu-id="af68d-116">자세한 내용은 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="af68d-116">For more information, see [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>

  - <span data-ttu-id="af68d-117">두 배열에 모두 값 형식 요소가 있으면 요소 데이터 형식이 정확히 동일 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af68d-117">If both arrays have value type elements, the element data types must be exactly the same.</span></span> <span data-ttu-id="af68d-118">이에 대 한 유일한 예외는 `Enum` 요소의 배열을 `Enum`기본 형식의 배열에 할당할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="af68d-118">The only exception to this is that you can assign an array of `Enum` elements to an array of the base type of that `Enum`.</span></span>

  - <span data-ttu-id="af68d-119">두 배열에 모두 참조 형식 요소가 있으면 원본 요소 형식이 대상 요소 형식에서 파생 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af68d-119">If both arrays have reference type elements, the source element type must derive from the destination element type.</span></span> <span data-ttu-id="af68d-120">이 경우 두 배열의 요소와 상속 관계가 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="af68d-120">When this is the case, the two arrays have the same inheritance relationship as their elements.</span></span> <span data-ttu-id="af68d-121">이를 *배열 공분산*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="af68d-121">This is called *array covariance*.</span></span>

<span data-ttu-id="af68d-122">위의 규칙을 위반 하는 경우 (예: 데이터 형식이 호환 되지 않거나 순위가 같지 않은 경우) 컴파일러에서 오류를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="af68d-122">The compiler reports an error if the above rules are violated, for example if the data types are not compatible or the ranks are unequal.</span></span> <span data-ttu-id="af68d-123">코드에 오류 처리를 추가 하 여 배열이 호환 되는지 확인 하 고 할당을 시도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af68d-123">You can add error handling to your code to make sure that the arrays are compatible before attempting an assignment.</span></span> <span data-ttu-id="af68d-124">예외를 throw 하지 않으려면 [TryCast Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md) 키워드를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af68d-124">You can also use the [TryCast Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md) keyword if you want to avoid throwing an exception.</span></span>

## <a name="see-also"></a><span data-ttu-id="af68d-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="af68d-125">See also</span></span>

- [<span data-ttu-id="af68d-126">배열</span><span class="sxs-lookup"><span data-stu-id="af68d-126">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="af68d-127">배열 문제 해결</span><span class="sxs-lookup"><span data-stu-id="af68d-127">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
- [<span data-ttu-id="af68d-128">Enum 문</span><span class="sxs-lookup"><span data-stu-id="af68d-128">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [<span data-ttu-id="af68d-129">배열 규칙</span><span class="sxs-lookup"><span data-stu-id="af68d-129">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
