---
title: '방법: 열거형 (Visual Basic)를 선언 합니다.'
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations [Visual Basic]
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
ms.openlocfilehash: c74b75adf0f56dd198375cb1ff24656d39ec074c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64610574"
---
# <a name="how-to-declare-enumerations-visual-basic"></a><span data-ttu-id="76086-102">방법: 열거형 (Visual Basic)를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="76086-102">How to: Declare Enumerations (Visual Basic)</span></span>
<span data-ttu-id="76086-103">사용 하 여 열거형을 만듭니다는 `Enum` 클래스 또는 모듈을 선언 섹션에서 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="76086-103">You create an enumeration with the `Enum` statement in the declarations section of a class or module.</span></span> <span data-ttu-id="76086-104">메서드 내에서 열거형을 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76086-104">You cannot declare an enumeration within a method.</span></span> <span data-ttu-id="76086-105">적절 한 수준의 액세스를 지정 하려면 `Private`, `Protected`를 `Friend`, 또는 `Public`합니다.</span><span class="sxs-lookup"><span data-stu-id="76086-105">To specify the appropriate level of access, use `Private`, `Protected`, `Friend`, or `Public`.</span></span>  
  
 <span data-ttu-id="76086-106">`Enum` 형식에는 이름, 내부 형식 및 필드의 집합을 각각 나타내는 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="76086-106">An `Enum` type has a name, an underlying type, and a set of fields, each representing a constant.</span></span> <span data-ttu-id="76086-107">이름은 유효한 Visual Basic.NET 한정자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76086-107">The name must be a valid Visual Basic .NET qualifier.</span></span> <span data-ttu-id="76086-108">기본 형식은 정수 형식 중 하나 여야 합니다-`Byte`, `Short`하십시오 `Long` 또는 `Integer`.</span><span class="sxs-lookup"><span data-stu-id="76086-108">The underlying type must be one of the integer types—`Byte`, `Short`, `Long` or `Integer`.</span></span> <span data-ttu-id="76086-109">기본값은 `Integer`입니다.</span><span class="sxs-lookup"><span data-stu-id="76086-109">`Integer` is the default.</span></span> <span data-ttu-id="76086-110">열거는 항상 강력한 형식이 지정 되며 정수 숫자 형식으로 서로 바꿔 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76086-110">Enumerations are always strongly typed and are not interchangeable with integer number types.</span></span>  
  
 <span data-ttu-id="76086-111">열거형 부동 소수점 값을 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76086-111">Enumerations cannot have floating-point values.</span></span> <span data-ttu-id="76086-112">열거형에는 부동 소수점 값을 할당 되 면 `Option Strict On`, 컴파일러 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="76086-112">If an enumeration is assigned a floating-point value with `Option Strict On`, a compiler error results.</span></span> <span data-ttu-id="76086-113">경우 `Option Strict` 됩니다 `Off`, 값을 자동으로 변환 되며는 `Enum` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="76086-113">If `Option Strict` is `Off`, the value is automatically converted to the `Enum` type.</span></span>  
  
 <span data-ttu-id="76086-114">이름에 대 한 정보 및 사용 하는 방법에 대 한 합니다 `Imports` 문을 이름 한정 불필요 참조 [열거형 및 이름 한정](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="76086-114">For information on names, and how to use the `Imports` statement to make name qualification unnecessary, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
### <a name="to-declare-an-enumeration"></a><span data-ttu-id="76086-115">열거형 선언</span><span class="sxs-lookup"><span data-stu-id="76086-115">To declare an enumeration</span></span>  
  
1. <span data-ttu-id="76086-116">코드 액세스 수준에 포함 하는 선언을 작성 합니다 `Enum` 키워드 및 다른 선언 각각 다음 예제와 같이 유효한 이름을 `Enum`입니다.</span><span class="sxs-lookup"><span data-stu-id="76086-116">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name, as in the following examples, each of which declares a different `Enum`.</span></span>  
  
     [!code-vb[VbEnumsTask#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#3)]  
  
2. <span data-ttu-id="76086-117">열거형의 상수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="76086-117">Define the constants in the enumeration.</span></span> <span data-ttu-id="76086-118">기본적으로 열거형의 첫 번째 상수를 초기화 `0`, 고 후속 상수 이전 상수 보다 하나 더 큰 값으로 초기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76086-118">By default, the first constant in an enumeration is initialized to `0`, and subsequent constants are initialized to a value of one more than the previous constant.</span></span> <span data-ttu-id="76086-119">예를 들어, 다음 열거형 `Days`, 명명 된 상수를 포함 `Sunday` 값을 사용 하 여 `0`, 명명 된 상수 `Monday` 값을 사용 하 여 `1`, 명명 된 상수 `Tuesday` 의값을사용하여`2`등에입니다.</span><span class="sxs-lookup"><span data-stu-id="76086-119">For example, the following enumeration, `Days`, contains a constant named `Sunday` with the value `0`, a constant named `Monday` with the value `1`, a constant named `Tuesday` with the value of `2`, and so on.</span></span>  
  
     [!code-vb[VbEnumsTask#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#4)]  
  
3. <span data-ttu-id="76086-120">대입문을 사용 하 여 열거형에서 상수로 분석 값을 명시적으로 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76086-120">You can explicitly assign values to constants in an enumeration by using an assignment statement.</span></span> <span data-ttu-id="76086-121">음수를 포함 하 여 모든 정수 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76086-121">You can assign any integer value, including negative numbers.</span></span> <span data-ttu-id="76086-122">예를 들어 상수를 오류 상태를 나타내는 0 보다 작은 값을 사용 하 여 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76086-122">For example, you may want constants with values less than zero to represent error conditions.</span></span> <span data-ttu-id="76086-123">다음 열거형에서 상수 `Invalid` 값을 명시적으로 할당 됩니다 `–1`, 및 상수 `Sunday` 값이 할당 됩니다 `0`합니다.</span><span class="sxs-lookup"><span data-stu-id="76086-123">In the following enumeration, the constant `Invalid` is explicitly assigned the value `–1`, and the constant `Sunday` is assigned the value `0`.</span></span> <span data-ttu-id="76086-124">열거형의 첫 번째 상수 이므로 `Saturday` 또한 값으로 초기화 됩니다 `0`합니다.</span><span class="sxs-lookup"><span data-stu-id="76086-124">Because it is the first constant in the enumeration, `Saturday` is also initialized to the value `0`.</span></span> <span data-ttu-id="76086-125">값 `Monday` 됩니다 `1` (값 보다 1 더 큽니다 `Sunday`); 값 `Tuesday` 는 `2`등.</span><span class="sxs-lookup"><span data-stu-id="76086-125">The value of `Monday` is `1` (one more than the value of `Sunday`); the value of `Tuesday` is `2`, and so on.</span></span>  
  
     [!code-vb[VbEnumsTask#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#5)]  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a><span data-ttu-id="76086-126">명시적 형식으로 열거형 선언</span><span class="sxs-lookup"><span data-stu-id="76086-126">To declare an enumeration as an explicit type</span></span>  
  
- <span data-ttu-id="76086-127">열거형 형식을 사용 하 여 지정 된 `As` 절을 다음과 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="76086-127">Specify the type of the enum by using the `As` clause, as shown in the following example.</span></span>  
  
     [!code-vb[VbEnumsTask#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="76086-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="76086-128">See also</span></span>

- [<span data-ttu-id="76086-129">열거형 및 이름 한정</span><span class="sxs-lookup"><span data-stu-id="76086-129">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="76086-130">방법: 열거형 멤버 참조</span><span class="sxs-lookup"><span data-stu-id="76086-130">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="76086-131">방법: Visual Basic에서 열거형 반복</span><span class="sxs-lookup"><span data-stu-id="76086-131">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="76086-132">방법: 열거형 값과 연결 된 문자열 확인</span><span class="sxs-lookup"><span data-stu-id="76086-132">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="76086-133">열거형을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="76086-133">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="76086-134">상수 개요</span><span class="sxs-lookup"><span data-stu-id="76086-134">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [<span data-ttu-id="76086-135">상수 및 리터럴 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="76086-135">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [<span data-ttu-id="76086-136">상수 및 열거형</span><span class="sxs-lookup"><span data-stu-id="76086-136">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
