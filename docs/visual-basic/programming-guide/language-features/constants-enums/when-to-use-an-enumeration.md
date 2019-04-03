---
title: 열거형을 사용하는 경우(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
ms.openlocfilehash: ff2d8c324aee8bbccef050c020e5392368b05b1c
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58825107"
---
# <a name="when-to-use-an-enumeration-visual-basic"></a><span data-ttu-id="0396a-102">열거형을 사용하는 경우(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0396a-102">When to Use an Enumeration (Visual Basic)</span></span>
<span data-ttu-id="0396a-103">열거형에는 관련 된 상수 집합을 사용 하는 간편한 방법은 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0396a-103">Enumerations offer an easy way to work with sets of related constants.</span></span> <span data-ttu-id="0396a-104">열거형, 또는 `Enum`, 기호화 된 이름 값의 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="0396a-104">An enumeration, or `Enum`, is a symbolic name for a set of values.</span></span> <span data-ttu-id="0396a-105">열거형 데이터 형식으로 처리 됩니다 하 고 변수 및 속성과 함께 사용할 상수 집합을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0396a-105">Enumerations are treated as data types, and you can use them to create sets of constants for use with variables and properties.</span></span>  
  
## <a name="when-to-use-an-enumeration"></a><span data-ttu-id="0396a-106">열거형을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="0396a-106">When to Use an Enumeration</span></span>  
 <span data-ttu-id="0396a-107">프로시저에서 변수 집합을 제한, 열거형을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0396a-107">Whenever a procedure accepts a limited set of variables, consider using an enumeration.</span></span> <span data-ttu-id="0396a-108">열거형은 의미 있는 이름을 사용 하는 경우에 특히 보다 명확 하 고 좀 더 읽기 쉬운 코드를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0396a-108">Enumerations make for clearer and more readable code, particularly when meaningful names are used.</span></span>  
  
 <span data-ttu-id="0396a-109">열거형을 사용 하는 이점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0396a-109">The benefits of using enumerations include:</span></span>  
  
-   <span data-ttu-id="0396a-110">숫자를 잘못 입력 하 여 발생 한 오류를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="0396a-110">Reduces errors caused by transposing or mistyping numbers.</span></span>  
  
-   <span data-ttu-id="0396a-111">에서는 값을 나중에 변경 하기가 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="0396a-111">Makes it easy to change values in the future.</span></span>  
  
-   <span data-ttu-id="0396a-112">에서는 코드는 오류 쉬워지므로 발생할 가능성이 줄어듭니다 즉를 쉽게 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0396a-112">Makes code easier to read, which means it is less likely that errors will creep into it.</span></span>  
  
-   <span data-ttu-id="0396a-113">이후 버전과 호환성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0396a-113">Ensures forward compatibility.</span></span> <span data-ttu-id="0396a-114">열거형을 사용 하 여 코드는 멤버 이름에 해당 하는 값을 나중에 변경 되 면 실패할 가능성이 적습니다.</span><span class="sxs-lookup"><span data-stu-id="0396a-114">With enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>  
  
## <a name="naming-enumerations"></a><span data-ttu-id="0396a-115">열거형 이름 지정</span><span class="sxs-lookup"><span data-stu-id="0396a-115">Naming Enumerations</span></span>  
 <span data-ttu-id="0396a-116">열거형 멤버에 대 한 명명 규칙을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0396a-116">Use a naming convention for enumeration members.</span></span> <span data-ttu-id="0396a-117">Visual Basic에서 열거형 멤버 이름을 발견, 다른 참조 된 형식 라이브러리에는 동일한 이름을 포함 하는 경우 예외가 throw 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0396a-117">When Visual Basic encounters an enumeration member name, an exception may be thrown if other referenced type libraries contain the same name.</span></span> <span data-ttu-id="0396a-118">응용 프로그램 또는 구성 요소에서 값을 식별 하는 고유한 접두사를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0396a-118">Use a unique prefix that identifies the values from your application or component.</span></span>  
  
 <span data-ttu-id="0396a-119">열거형의 멤버를 참조 하는 경우 있습니다 해야 열거형 이름으로 멤버 이름을 한 정하는 그렇지 않으면 사용 된 `Imports` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="0396a-119">When referring to a member of an enumeration, you must qualify the member name with the enumeration name or else use the `Imports` statement.</span></span> <span data-ttu-id="0396a-120">자세한 내용은 [열거형 및 이름 한정](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0396a-120">For more information, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
## <a name="predefined-enumerations"></a><span data-ttu-id="0396a-121">미리 정의 된 열거형</span><span class="sxs-lookup"><span data-stu-id="0396a-121">Predefined Enumerations</span></span>  
 <span data-ttu-id="0396a-122">Visual Basic과 같은 다양 한 미리 정의 된 열거를 제공 합니다 `FirstDayOfWeek` 고 `MsgBoxResult`, 코드를 용이 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="0396a-122">Visual Basic provides a number of predefined enumerations, such as `FirstDayOfWeek` and `MsgBoxResult`, to facilitate your code.</span></span> <span data-ttu-id="0396a-123">이러한 목록은 참조 하세요. [상수 및 열거형](../../../../visual-basic/language-reference/constants-and-enumerations.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0396a-123">For a list of these see [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0396a-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="0396a-124">See also</span></span>

- [<span data-ttu-id="0396a-125">방법: 열거형 선언</span><span class="sxs-lookup"><span data-stu-id="0396a-125">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="0396a-126">방법: 열거형 멤버 참조</span><span class="sxs-lookup"><span data-stu-id="0396a-126">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="0396a-127">열거형 및 이름 한정</span><span class="sxs-lookup"><span data-stu-id="0396a-127">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="0396a-128">방법: Visual Basic에서 열거형 반복</span><span class="sxs-lookup"><span data-stu-id="0396a-128">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="0396a-129">방법: 열거형 값과 연결 된 문자열 확인</span><span class="sxs-lookup"><span data-stu-id="0396a-129">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="0396a-130">Enum 문</span><span class="sxs-lookup"><span data-stu-id="0396a-130">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [<span data-ttu-id="0396a-131">상수 및 열거형</span><span class="sxs-lookup"><span data-stu-id="0396a-131">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
