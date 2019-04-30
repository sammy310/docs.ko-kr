---
title: '방법: 한 배열을 다른 배열 (Visual Basic) 할당'
ms.date: 07/20/2015
helpviewer_keywords:
- covariance, arrays
- arrays [Visual Basic], assigning
- arrays [Visual Basic], covariance
ms.assetid: 1ae89ea5-f292-4282-bcfc-e9b06b37fbd5
ms.openlocfilehash: 78497de3a9aea55320639c55a151a1260a960159
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053680"
---
# <a name="how-to-assign-one-array-to-another-array-visual-basic"></a><span data-ttu-id="1e2fd-102">방법: 한 배열을 다른 배열 (Visual Basic) 할당</span><span class="sxs-lookup"><span data-stu-id="1e2fd-102">How to: Assign One Array to Another Array (Visual Basic)</span></span>

<span data-ttu-id="1e2fd-103">배열 개체 이기 때문에 다른 개체 형식 처럼 대입 문에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e2fd-103">Because arrays are objects, you can use them in assignment statements like other object types.</span></span> <span data-ttu-id="1e2fd-104">배열 변수 배열 요소 및 차수 및 길이 정보를 구성 하는 데이터 포인터를 보유 하 고 할당만이 포인터를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e2fd-104">An array variable holds a pointer to the data constituting the array elements and the rank and length information, and an assignment copies only this pointer.</span></span>

### <a name="to-assign-one-array-to-another-array"></a><span data-ttu-id="1e2fd-105">한 배열을 다른 배열에 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="1e2fd-105">To assign one array to another array</span></span>

1. <span data-ttu-id="1e2fd-106">두 배열의 동일한 차수 (차원 수)과 호환 되는 요소 데이터 형식을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e2fd-106">Ensure that the two arrays have the same rank (number of dimensions) and compatible element data types.</span></span>

2. <span data-ttu-id="1e2fd-107">소스 배열에서 대상 배열에 할당할 표준 대입문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e2fd-107">Use a standard assignment statement to assign the source array to the destination array.</span></span> <span data-ttu-id="1e2fd-108">괄호를 사용 하 여 배열 이름 중 하나를 수행 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="1e2fd-108">Do not follow either array name with parentheses.</span></span>

    ```vb
    Dim formArray() As System.Windows.Forms.Form
    Dim controlArray() As System.Windows.Forms.Control
    controlArray = formArray
    ```

<span data-ttu-id="1e2fd-109">다른 배열에 할당 하는 경우 다음 규칙이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e2fd-109">When you assign one array to another, the following rules apply:</span></span>

- <span data-ttu-id="1e2fd-110">**같은 순위가 결정 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="1e2fd-110">**Equal Ranks.**</span></span> <span data-ttu-id="1e2fd-111">대상 배열의 차수 (차원 수)는 원본 배열의과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e2fd-111">The rank (number of dimensions) of the destination array must be the same as that of the source array.</span></span>

  <span data-ttu-id="1e2fd-112">두 배열의 순위 값이 같으면 제공 차원 필요가 없습니다 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e2fd-112">Provided the ranks of the two arrays are equal, the dimensions do not need to be equal.</span></span> <span data-ttu-id="1e2fd-113">지정 된 차원의 요소 수가 할당 하는 동안 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e2fd-113">The number of elements in a given dimension can change during assignment.</span></span>

- <span data-ttu-id="1e2fd-114">**요소 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="1e2fd-114">**Element Types.**</span></span> <span data-ttu-id="1e2fd-115">두 배열 중 하나 있어야 *참조 형식* 요소 또는 두 배열 있어야 *값 형식* 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="1e2fd-115">Either both arrays must have *reference type* elements or both arrays must have *value type* elements.</span></span> <span data-ttu-id="1e2fd-116">자세한 내용은 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1e2fd-116">For more information, see [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>

  - <span data-ttu-id="1e2fd-117">두 배열의 값 형식 요소의 경우 요소 데이터 형식을 정확 하 게 동일 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e2fd-117">If both arrays have value type elements, the element data types must be exactly the same.</span></span> <span data-ttu-id="1e2fd-118">유일한 예외는 배열을 할당할 수 있는 `Enum` 요소를 사용 하는 기본 형식의 배열 `Enum`합니다.</span><span class="sxs-lookup"><span data-stu-id="1e2fd-118">The only exception to this is that you can assign an array of `Enum` elements to an array of the base type of that `Enum`.</span></span>

  - <span data-ttu-id="1e2fd-119">두 배열은 참조 형식 요소에 있으면 원본 요소 형식이 대상 요소 형식에서 파생 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e2fd-119">If both arrays have reference type elements, the source element type must derive from the destination element type.</span></span> <span data-ttu-id="1e2fd-120">이 경우 두 배열의 경우 해당 요소와 동일한 상속 관계</span><span class="sxs-lookup"><span data-stu-id="1e2fd-120">When this is the case, the two arrays have the same inheritance relationship as their elements.</span></span> <span data-ttu-id="1e2fd-121">이 이라고 *배열 공변성 (covariance)* 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e2fd-121">This is called *array covariance*.</span></span>

<span data-ttu-id="1e2fd-122">컴파일러 오류 위의 규칙 위반 하면 예를 들어 데이터 형식이 호환 되지 않는 경우 또는 순위 같지 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e2fd-122">The compiler reports an error if the above rules are violated, for example if the data types are not compatible or the ranks are unequal.</span></span> <span data-ttu-id="1e2fd-123">오류 처리를 할당 하기 전에 배열 호환 되는지 확인 하기 위해 코드에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e2fd-123">You can add error handling to your code to make sure that the arrays are compatible before attempting an assignment.</span></span> <span data-ttu-id="1e2fd-124">사용할 수도 있습니다는 [TryCast 연산자](../../../../visual-basic/language-reference/operators/trycast-operator.md) 키워드 예외가 throw 되지 않게 하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="1e2fd-124">You can also use the [TryCast Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md) keyword if you want to avoid throwing an exception.</span></span>

## <a name="see-also"></a><span data-ttu-id="1e2fd-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="1e2fd-125">See also</span></span>

- [<span data-ttu-id="1e2fd-126">배열</span><span class="sxs-lookup"><span data-stu-id="1e2fd-126">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="1e2fd-127">배열 문제 해결</span><span class="sxs-lookup"><span data-stu-id="1e2fd-127">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
- [<span data-ttu-id="1e2fd-128">Enum 문</span><span class="sxs-lookup"><span data-stu-id="1e2fd-128">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [<span data-ttu-id="1e2fd-129">배열 규칙</span><span class="sxs-lookup"><span data-stu-id="1e2fd-129">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
