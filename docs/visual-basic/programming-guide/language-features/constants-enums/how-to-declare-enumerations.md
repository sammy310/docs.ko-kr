---
title: '방법: 열거형 선언'
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations [Visual Basic]
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
ms.openlocfilehash: 042aea045313bcaf3832274acf1000f87a084b72
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354051"
---
# <a name="how-to-declare-enumerations-visual-basic"></a><span data-ttu-id="34d2e-102">방법: 열거형 선언(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="34d2e-102">How to: Declare Enumerations (Visual Basic)</span></span>
<span data-ttu-id="34d2e-103">클래스 또는 모듈의 선언 섹션에 `Enum` 문을 사용 하 여 열거형을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="34d2e-103">You create an enumeration with the `Enum` statement in the declarations section of a class or module.</span></span> <span data-ttu-id="34d2e-104">메서드 내에서 열거형을 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="34d2e-104">You cannot declare an enumeration within a method.</span></span> <span data-ttu-id="34d2e-105">적절 한 액세스 수준을 지정 하려면 `Private`, `Protected`, `Friend`또는 `Public`를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="34d2e-105">To specify the appropriate level of access, use `Private`, `Protected`, `Friend`, or `Public`.</span></span>  
  
 <span data-ttu-id="34d2e-106">`Enum` 형식에는 각각 상수를 나타내는 이름, 내부 형식 및 필드 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34d2e-106">An `Enum` type has a name, an underlying type, and a set of fields, each representing a constant.</span></span> <span data-ttu-id="34d2e-107">이름은 올바른 Visual Basic .NET 한정자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34d2e-107">The name must be a valid Visual Basic .NET qualifier.</span></span> <span data-ttu-id="34d2e-108">기본 형식은 정수 형식 (`Byte`, `Short`, `Long` 또는 `Integer`중 하나 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34d2e-108">The underlying type must be one of the integer types—`Byte`, `Short`, `Long` or `Integer`.</span></span> <span data-ttu-id="34d2e-109">기본값은 `Integer`입니다.</span><span class="sxs-lookup"><span data-stu-id="34d2e-109">`Integer` is the default.</span></span> <span data-ttu-id="34d2e-110">열거형은 항상 강력한 형식이 며 정수 숫자 형식으로는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="34d2e-110">Enumerations are always strongly typed and are not interchangeable with integer number types.</span></span>  
  
 <span data-ttu-id="34d2e-111">열거형에는 부동 소수점 값을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="34d2e-111">Enumerations cannot have floating-point values.</span></span> <span data-ttu-id="34d2e-112">`Option Strict On`를 사용 하 여 열거형에 부동 소수점 값이 할당 된 경우 컴파일러 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="34d2e-112">If an enumeration is assigned a floating-point value with `Option Strict On`, a compiler error results.</span></span> <span data-ttu-id="34d2e-113">`Option Strict` `Off`되 면 값이 자동으로 `Enum` 형식으로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34d2e-113">If `Option Strict` is `Off`, the value is automatically converted to the `Enum` type.</span></span>  
  
 <span data-ttu-id="34d2e-114">이름 및 이름 정규화를 사용 하지 않는 `Imports` 문을 사용 하는 방법에 대 한 자세한 내용은 [열거형 및 이름 한정](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="34d2e-114">For information on names, and how to use the `Imports` statement to make name qualification unnecessary, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
### <a name="to-declare-an-enumeration"></a><span data-ttu-id="34d2e-115">열거형을 선언 하려면</span><span class="sxs-lookup"><span data-stu-id="34d2e-115">To declare an enumeration</span></span>  
  
1. <span data-ttu-id="34d2e-116">다음 예제와 같이 코드 액세스 수준, `Enum` 키워드 및 올바른 이름을 포함 하는 선언을 작성 합니다. 각는 서로 다른 `Enum`를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="34d2e-116">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name, as in the following examples, each of which declares a different `Enum`.</span></span>  
  
     [!code-vb[VbEnumsTask#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#3)]  
  
2. <span data-ttu-id="34d2e-117">열거형에서 상수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="34d2e-117">Define the constants in the enumeration.</span></span> <span data-ttu-id="34d2e-118">기본적으로 열거형의 첫 번째 상수는 `0`로 초기화 되 고 후속 상수는 이전 상수 보다 1의 값으로 초기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34d2e-118">By default, the first constant in an enumeration is initialized to `0`, and subsequent constants are initialized to a value of one more than the previous constant.</span></span> <span data-ttu-id="34d2e-119">예를 들어, `Days`열거형에는 값 `0`와 함께 `Sunday` 라는 상수, 값 `1`를 사용 하는 `Monday` 상수, `Tuesday` 값을 사용 하는 `2`이라는 상수가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34d2e-119">For example, the following enumeration, `Days`, contains a constant named `Sunday` with the value `0`, a constant named `Monday` with the value `1`, a constant named `Tuesday` with the value of `2`, and so on.</span></span>  
  
     [!code-vb[VbEnumsTask#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#4)]  
  
3. <span data-ttu-id="34d2e-120">대입문을 사용 하 여 열거형의 상수에 값을 명시적으로 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34d2e-120">You can explicitly assign values to constants in an enumeration by using an assignment statement.</span></span> <span data-ttu-id="34d2e-121">음수를 포함 하 여 임의의 정수 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34d2e-121">You can assign any integer value, including negative numbers.</span></span> <span data-ttu-id="34d2e-122">예를 들어 값이 0 보다 작은 상수를 사용 하 여 오류 조건을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34d2e-122">For example, you may want constants with values less than zero to represent error conditions.</span></span> <span data-ttu-id="34d2e-123">다음 열거형에서 상수 `Invalid`에는 `–1`값이 명시적으로 할당 되 고 상수 `Sunday`에는 `0`값이 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34d2e-123">In the following enumeration, the constant `Invalid` is explicitly assigned the value `–1`, and the constant `Sunday` is assigned the value `0`.</span></span> <span data-ttu-id="34d2e-124">열거형의 첫 번째 상수 이므로 `Saturday` `0`값으로도 초기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34d2e-124">Because it is the first constant in the enumeration, `Saturday` is also initialized to the value `0`.</span></span> <span data-ttu-id="34d2e-125">`Monday` 값이 `1` (`Sunday`값 보다 하나 이상) 인 경우 `Tuesday` 값은 `2`입니다.</span><span class="sxs-lookup"><span data-stu-id="34d2e-125">The value of `Monday` is `1` (one more than the value of `Sunday`); the value of `Tuesday` is `2`, and so on.</span></span>  
  
     [!code-vb[VbEnumsTask#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#5)]  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a><span data-ttu-id="34d2e-126">열거형을 명시적 형식으로 선언 하려면</span><span class="sxs-lookup"><span data-stu-id="34d2e-126">To declare an enumeration as an explicit type</span></span>  
  
- <span data-ttu-id="34d2e-127">다음 예제와 같이 `As` 절을 사용 하 여 열거형의 유형을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="34d2e-127">Specify the type of the enum by using the `As` clause, as shown in the following example.</span></span>  
  
     [!code-vb[VbEnumsTask#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="34d2e-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="34d2e-128">See also</span></span>

- [<span data-ttu-id="34d2e-129">열거형 및 이름 한정</span><span class="sxs-lookup"><span data-stu-id="34d2e-129">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="34d2e-130">방법: 열거형 멤버 참조</span><span class="sxs-lookup"><span data-stu-id="34d2e-130">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="34d2e-131">방법: Visual Basic에서 열거형 반복</span><span class="sxs-lookup"><span data-stu-id="34d2e-131">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="34d2e-132">방법: 열거형 값과 연결된 문자열 확인</span><span class="sxs-lookup"><span data-stu-id="34d2e-132">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="34d2e-133">열거형을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="34d2e-133">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="34d2e-134">상수 개요</span><span class="sxs-lookup"><span data-stu-id="34d2e-134">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [<span data-ttu-id="34d2e-135">상수 및 리터럴 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="34d2e-135">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [<span data-ttu-id="34d2e-136">상수 및 열거형</span><span class="sxs-lookup"><span data-stu-id="34d2e-136">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
