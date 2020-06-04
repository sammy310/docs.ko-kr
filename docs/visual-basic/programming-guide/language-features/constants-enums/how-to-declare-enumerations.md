---
title: '방법: 열거형 선언'
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations [Visual Basic]
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
ms.openlocfilehash: c8f228c205c93adf7f2f555dc840a7daac61950b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414455"
---
# <a name="how-to-declare-enumerations-visual-basic"></a><span data-ttu-id="ec755-102">방법: 열거형 선언(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ec755-102">How to: Declare Enumerations (Visual Basic)</span></span>
<span data-ttu-id="ec755-103">`Enum`클래스 또는 모듈의 선언 섹션에 문을 사용 하 여 열거형을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ec755-103">You create an enumeration with the `Enum` statement in the declarations section of a class or module.</span></span> <span data-ttu-id="ec755-104">메서드 내에서 열거형을 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec755-104">You cannot declare an enumeration within a method.</span></span> <span data-ttu-id="ec755-105">적절 한 수준의 액세스를 지정 하려면,, `Private` 또는를 사용 `Protected` `Friend` `Public` 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec755-105">To specify the appropriate level of access, use `Private`, `Protected`, `Friend`, or `Public`.</span></span>  
  
 <span data-ttu-id="ec755-106">형식에는 `Enum` 각각 상수를 나타내는 이름, 내부 형식 및 필드 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec755-106">An `Enum` type has a name, an underlying type, and a set of fields, each representing a constant.</span></span> <span data-ttu-id="ec755-107">이름은 올바른 Visual Basic .NET 한정자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec755-107">The name must be a valid Visual Basic .NET qualifier.</span></span> <span data-ttu-id="ec755-108">기본 형식은 정수 형식 (, 또는) 중 하나 여야 `Byte` 합니다 `Short` `Long` `Integer` .</span><span class="sxs-lookup"><span data-stu-id="ec755-108">The underlying type must be one of the integer types—`Byte`, `Short`, `Long` or `Integer`.</span></span> <span data-ttu-id="ec755-109">`Integer`은 기본 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="ec755-109">`Integer` is the default.</span></span> <span data-ttu-id="ec755-110">열거형은 항상 강력한 형식이 며 정수 숫자 형식으로는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec755-110">Enumerations are always strongly typed and are not interchangeable with integer number types.</span></span>  
  
 <span data-ttu-id="ec755-111">열거형에는 부동 소수점 값을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec755-111">Enumerations cannot have floating-point values.</span></span> <span data-ttu-id="ec755-112">열거형에 부동 소수점 값이 할당 된 경우 `Option Strict On` 컴파일러 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec755-112">If an enumeration is assigned a floating-point value with `Option Strict On`, a compiler error results.</span></span> <span data-ttu-id="ec755-113">`Option Strict`가 이면 `Off` 값이 자동으로 형식으로 변환 됩니다 `Enum` .</span><span class="sxs-lookup"><span data-stu-id="ec755-113">If `Option Strict` is `Off`, the value is automatically converted to the `Enum` type.</span></span>  
  
 <span data-ttu-id="ec755-114">이름 및 문을 사용 하 여 이름 정규화를 불필요 하 게 만드는 방법에 대 한 자세한 내용은 `Imports` [열거형 및 이름 한정](enumerations-and-name-qualification.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ec755-114">For information on names, and how to use the `Imports` statement to make name qualification unnecessary, see [Enumerations and Name Qualification](enumerations-and-name-qualification.md).</span></span>  
  
### <a name="to-declare-an-enumeration"></a><span data-ttu-id="ec755-115">열거형을 선언 하려면</span><span class="sxs-lookup"><span data-stu-id="ec755-115">To declare an enumeration</span></span>  
  
1. <span data-ttu-id="ec755-116">다음 예제와 같이 코드 액세스 수준, 키워드 및 올바른 이름을 포함 하는 선언을 작성 합니다 `Enum` . 각는 서로 다른를 선언 합니다 `Enum` .</span><span class="sxs-lookup"><span data-stu-id="ec755-116">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name, as in the following examples, each of which declares a different `Enum`.</span></span>  
  
     [!code-vb[VbEnumsTask#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#3)]  
  
2. <span data-ttu-id="ec755-117">열거형에서 상수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec755-117">Define the constants in the enumeration.</span></span> <span data-ttu-id="ec755-118">기본적으로 열거형의 첫 번째 상수는로 초기화 되 `0` 고 후속 상수는 이전 상수 보다 1의 값으로 초기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec755-118">By default, the first constant in an enumeration is initialized to `0`, and subsequent constants are initialized to a value of one more than the previous constant.</span></span> <span data-ttu-id="ec755-119">예를 들어, 다음 열거형에는 값, 값을 사용 하 여 라는 상수, 값으로 명명 된 상수 등의 이라는 상수가 `Days` 포함 되어 있습니다 `Sunday` `0` `Monday` `1` `Tuesday` `2` .</span><span class="sxs-lookup"><span data-stu-id="ec755-119">For example, the following enumeration, `Days`, contains a constant named `Sunday` with the value `0`, a constant named `Monday` with the value `1`, a constant named `Tuesday` with the value of `2`, and so on.</span></span>  
  
     [!code-vb[VbEnumsTask#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#4)]  
  
3. <span data-ttu-id="ec755-120">대입문을 사용 하 여 열거형의 상수에 값을 명시적으로 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec755-120">You can explicitly assign values to constants in an enumeration by using an assignment statement.</span></span> <span data-ttu-id="ec755-121">음수를 포함 하 여 임의의 정수 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec755-121">You can assign any integer value, including negative numbers.</span></span> <span data-ttu-id="ec755-122">예를 들어 값이 0 보다 작은 상수를 사용 하 여 오류 조건을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec755-122">For example, you may want constants with values less than zero to represent error conditions.</span></span> <span data-ttu-id="ec755-123">다음 열거형에서 상수에는 `Invalid` 값이 명시적으로 할당 되 `–1` 고 상수에는 `Sunday` 값이 할당 됩니다 `0` .</span><span class="sxs-lookup"><span data-stu-id="ec755-123">In the following enumeration, the constant `Invalid` is explicitly assigned the value `–1`, and the constant `Sunday` is assigned the value `0`.</span></span> <span data-ttu-id="ec755-124">는 열거형의 첫 번째 상수 이므로 `Saturday` 도 값으로 초기화 됩니다 `0` .</span><span class="sxs-lookup"><span data-stu-id="ec755-124">Because it is the first constant in the enumeration, `Saturday` is also initialized to the value `0`.</span></span> <span data-ttu-id="ec755-125">값은 `Monday` `1` (값 보다 하나 이상)이 고의 값은입니다 `Sunday` `Tuesday` `2` .</span><span class="sxs-lookup"><span data-stu-id="ec755-125">The value of `Monday` is `1` (one more than the value of `Sunday`); the value of `Tuesday` is `2`, and so on.</span></span>  
  
     [!code-vb[VbEnumsTask#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#5)]  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a><span data-ttu-id="ec755-126">열거형을 명시적 형식으로 선언 하려면</span><span class="sxs-lookup"><span data-stu-id="ec755-126">To declare an enumeration as an explicit type</span></span>  
  
- <span data-ttu-id="ec755-127">다음 예제와 같이 절을 사용 하 여 열거형의 유형을 지정 합니다 `As` .</span><span class="sxs-lookup"><span data-stu-id="ec755-127">Specify the type of the enum by using the `As` clause, as shown in the following example.</span></span>  
  
     [!code-vb[VbEnumsTask#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="ec755-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ec755-128">See also</span></span>

- [<span data-ttu-id="ec755-129">열거형 및 이름 한정</span><span class="sxs-lookup"><span data-stu-id="ec755-129">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="ec755-130">방법: 열거형 멤버 참조</span><span class="sxs-lookup"><span data-stu-id="ec755-130">How to: Refer to an Enumeration Member</span></span>](how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="ec755-131">방법: Visual Basic에서 열거형 반복</span><span class="sxs-lookup"><span data-stu-id="ec755-131">How to: Iterate Through An Enumeration in Visual Basic</span></span>](how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="ec755-132">방법: 열거형 값과 연결된 문자열 확인</span><span class="sxs-lookup"><span data-stu-id="ec755-132">How to: Determine the String Associated with an Enumeration Value</span></span>](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="ec755-133">열거형을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="ec755-133">When to Use an Enumeration</span></span>](when-to-use-an-enumeration.md)
- [<span data-ttu-id="ec755-134">상수 개요</span><span class="sxs-lookup"><span data-stu-id="ec755-134">Constants Overview</span></span>](constants-overview.md)
- [<span data-ttu-id="ec755-135">상수 및 리터럴 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ec755-135">Constant and Literal Data Types</span></span>](constant-and-literal-data-types.md)
- [<span data-ttu-id="ec755-136">상수 및 열거형</span><span class="sxs-lookup"><span data-stu-id="ec755-136">Constants and Enumerations</span></span>](../../../language-reference/constants-and-enumerations.md)
