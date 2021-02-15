---
description: '자세히 알아보기: 오버 로드 된 속성 및 메서드 (Visual Basic)'
title: 오버 로드 된 속성 및 메서드
ms.date: 07/20/2015
helpviewer_keywords:
- properties [Visual Basic], overloading
- methods [Visual Basic], overloading
- shadowing
- names [Visual Basic], multiple procedures with same
- procedures [Visual Basic], multiples with same name
- classes [Visual Basic], properties
- classes [Visual Basic], methods
- method overloading
- Overloads keyword [Visual Basic], overloaded members
ms.assetid: b686fb97-e7d7-4001-afaa-6650cba08f0d
ms.openlocfilehash: fb46876d346ad5f391241aee0b07175df290e656
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100438777"
---
# <a name="overloaded-properties-and-methods-visual-basic"></a><span data-ttu-id="0ed0b-103">오버 로드 된 속성 및 메서드 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0ed0b-103">Overloaded properties and methods (Visual Basic)</span></span>

<span data-ttu-id="0ed0b-104">오버 로드는 이름이 같지만 인수 형식이 다른 클래스에서 둘 이상의 프로시저, 인스턴스 생성자 또는 속성을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0ed0b-104">Overloading is the creation of more than one procedure, instance constructor, or property in a class with the same name but different argument types.</span></span>

## <a name="overloading-usage"></a><span data-ttu-id="0ed0b-105">사용 오버 로드</span><span class="sxs-lookup"><span data-stu-id="0ed0b-105">Overloading usage</span></span>

<span data-ttu-id="0ed0b-106">오버 로드는 개체 모델에서 서로 다른 데이터 형식에 대해 작동 하는 프로시저에 동일한 이름을 사용 하는 경우 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed0b-106">Overloading is especially useful when your object model dictates that you employ identical names for procedures that operate on different data types.</span></span> <span data-ttu-id="0ed0b-107">예를 들어 여러 다른 데이터 형식을 표시할 수 있는 클래스에는 `Display` 다음과 같은 프로시저가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed0b-107">For example, a class that can display several different data types could have `Display` procedures that look like this:</span></span>

[!code-vb[VbVbalrOOP#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#64)]

<span data-ttu-id="0ed0b-108">오버 로드를 사용 하지 않는 경우 다음에 표시 된 것 처럼 동일한 작업을 수행 하는 경우에도 각 프로시저에 대해 고유한 이름을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed0b-108">Without overloading, you would need to create distinct names for each procedure, even though they do the same thing, as shown next:</span></span>

[!code-vb[VbVbalrOOP#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#65)]

<span data-ttu-id="0ed0b-109">오버 로드를 사용 하면 사용할 수 있는 데이터 형식을 선택할 수 있기 때문에 속성 또는 메서드를 보다 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed0b-109">Overloading makes it easier to use properties or methods because it provides a choice of data types that can be used.</span></span> <span data-ttu-id="0ed0b-110">예를 들어 앞에서 설명한 오버 로드 된 `Display` 메서드는 다음 코드 줄을 사용 하 여 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed0b-110">For example, the overloaded `Display` method discussed previously can be called with any of the following lines of code:</span></span>

[!code-vb[VbVbalrOOP#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#66)]

<span data-ttu-id="0ed0b-111">런타임에는 사용자가 지정 하는 매개 변수의 데이터 형식에 따라 올바른 프로시저를 호출 Visual Basic 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed0b-111">At run time, Visual Basic calls the correct procedure based on the data types of the parameters you specify.</span></span>

## <a name="overloading-rules"></a><span data-ttu-id="0ed0b-112">오버 로드 규칙</span><span class="sxs-lookup"><span data-stu-id="0ed0b-112">Overloading rules</span></span>

 <span data-ttu-id="0ed0b-113">동일한 이름을 가진 둘 이상의 속성 또는 메서드를 추가 하 여 클래스에 대해 오버 로드 된 멤버를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0ed0b-113">You create an overloaded member for a class by adding two or more properties or methods with the same name.</span></span> <span data-ttu-id="0ed0b-114">오버 로드 된 파생 멤버를 제외 하 고, 각 오버 로드 된 멤버는 서로 다른 매개 변수 목록을 포함 해야 하며, 다음 항목은 속성이 나 프로시저를 오버 로드할 때 차별화 기능으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed0b-114">Except for overloaded derived members, each overloaded member must have different parameter lists, and the following items cannot be used as a differentiating feature when overloading a property or procedure:</span></span>

- <span data-ttu-id="0ed0b-115">`ByVal` `ByRef` 멤버에 적용 되는 또는와 같은 한정자 또는 멤버의 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="0ed0b-115">Modifiers, such as `ByVal` or `ByRef`, that apply to a member, or parameters of the member.</span></span>

- <span data-ttu-id="0ed0b-116">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="0ed0b-116">Names of parameters</span></span>

- <span data-ttu-id="0ed0b-117">프로시저의 반환 형식</span><span class="sxs-lookup"><span data-stu-id="0ed0b-117">Return types of procedures</span></span>

<span data-ttu-id="0ed0b-118">`Overloads`오버 로드 하는 경우 키워드는 선택 사항 이지만 오버 로드 된 멤버에 키워드를 사용 하는 경우에는 `Overloads` 이름이 같은 오버 로드 된 다른 모든 멤버도이 키워드를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed0b-118">The `Overloads` keyword is optional when overloading, but if any overloaded member uses the `Overloads` keyword, then all other overloaded members with the same name must also specify this keyword.</span></span>

<span data-ttu-id="0ed0b-119">파생 된 클래스는 동일한 매개 변수 및 매개 변수 형식이 있는 멤버로 상속 된 멤버를 오버 로드할 수 있습니다 .이 프로세스는 *이름 및 시그니처로 섀도잉* 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed0b-119">Derived classes can overload inherited members with members that have identical parameters and parameter types, a process known as *shadowing by name and signature*.</span></span> <span data-ttu-id="0ed0b-120">`Overloads`이름 및 시그니처로 숨길 때 키워드를 사용 하는 경우 기본 클래스의 구현 대신 파생 클래스의 멤버 구현이 사용 되며, 해당 멤버에 대 한 다른 모든 오버 로드는 파생 클래스의 인스턴스에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed0b-120">If the `Overloads` keyword is used when shadowing by name and signature, the derived class's implementation of the member will be used instead of the implementation in the base class, and all other overloads for that member will be available to instances of the derived class.</span></span>

<span data-ttu-id="0ed0b-121">`Overloads`동일한 매개 변수 및 매개 변수 형식을 가진 멤버를 사용 하 여 상속 된 멤버를 오버 로드할 때 키워드를 생략 하면 *이름으로 숨김과* 오버 로드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed0b-121">If the `Overloads` keyword is omitted when overloading an inherited member with a member that has identical parameters and parameter types, then the overloading is called *shadowing by name*.</span></span> <span data-ttu-id="0ed0b-122">이름으로 숨김은 멤버의 상속 된 구현을 대체 하 고 파생 클래스의 인스턴스와 다른 모든 오버 로드를 사용할 수 없게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0ed0b-122">Shadowing by name replaces the inherited implementation of a member, and it makes all other overloads unavailable to instances of the derived class and its decedents.</span></span>

<span data-ttu-id="0ed0b-123">`Overloads`및 `Shadows` 한정자는 동일한 속성 또는 메서드와 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed0b-123">The `Overloads` and `Shadows` modifiers cannot both be used with the same property or method.</span></span>

### <a name="example"></a><span data-ttu-id="0ed0b-124">예</span><span class="sxs-lookup"><span data-stu-id="0ed0b-124">Example</span></span>

<span data-ttu-id="0ed0b-125">다음 예에서는 `String` `Decimal` 달러 금액의 또는 표현을 허용 하 고 판매 세금을 포함 하는 문자열을 반환 하는 오버 로드 된 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0ed0b-125">The following example creates overloaded methods that accept either a `String` or `Decimal` representation of a dollar amount and return a string containing the sales tax.</span></span>

#### <a name="to-use-this-example-to-create-an-overloaded-method"></a><span data-ttu-id="0ed0b-126">이 예제를 사용 하 여 오버 로드 된 메서드를 만들려면</span><span class="sxs-lookup"><span data-stu-id="0ed0b-126">To use this example to create an overloaded method</span></span>

1. <span data-ttu-id="0ed0b-127">새 프로젝트를 열고 라는 클래스를 추가 `TaxClass` 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed0b-127">Open a new project and add a class named `TaxClass`.</span></span>

2. <span data-ttu-id="0ed0b-128">`TaxClass` 클래스에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed0b-128">Add the following code to the `TaxClass` class.</span></span>

    [!code-vb[VbVbalrOOP#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#67)]

3. <span data-ttu-id="0ed0b-129">다음 프로시저를 폼에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed0b-129">Add the following procedure to your form.</span></span>

    [!code-vb[VbVbalrOOP#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#68)]

4. <span data-ttu-id="0ed0b-130">폼에 단추를 추가 하 고 `ShowTax` 단추의 이벤트에서 프로시저를 호출 합니다 `Button1_Click` .</span><span class="sxs-lookup"><span data-stu-id="0ed0b-130">Add a button to your form and call the `ShowTax` procedure from the `Button1_Click` event of the button.</span></span>

5. <span data-ttu-id="0ed0b-131">프로젝트를 실행 하 고 폼의 단추를 클릭 하 여 오버 로드 된 프로시저를 테스트 합니다 `ShowTax` .</span><span class="sxs-lookup"><span data-stu-id="0ed0b-131">Run the project and click the button on the form to test the overloaded `ShowTax` procedure.</span></span>

<span data-ttu-id="0ed0b-132">런타임에는 컴파일러에서 사용 되는 매개 변수와 일치 하는 오버 로드 된 적절 한 함수를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed0b-132">At run time, the compiler chooses the appropriate overloaded function that matches the parameters being used.</span></span> <span data-ttu-id="0ed0b-133">단추를 클릭 하면 오버 로드 된 메서드는 `Price` 문자열 및 메시지 "Price가 문자열인 매개 변수를 사용 하 여 먼저 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ed0b-133">When you click the button, the overloaded method is called first with a `Price` parameter that is a string and the message, "Price is a String.</span></span> <span data-ttu-id="0ed0b-134">세금은 $5.12이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ed0b-134">Tax is $5.12" is displayed.</span></span> <span data-ttu-id="0ed0b-135">`TaxAmount` 는 두 번째 시간 값을 사용 하 여 호출 되 `Decimal` 고 메시지 "Price는 10 진수입니다.</span><span class="sxs-lookup"><span data-stu-id="0ed0b-135">`TaxAmount` is called with a `Decimal` value the second time and the message, "Price is a Decimal.</span></span> <span data-ttu-id="0ed0b-136">세금은 $5.12이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ed0b-136">Tax is $5.12" is displayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="0ed0b-137">추가 정보</span><span class="sxs-lookup"><span data-stu-id="0ed0b-137">See also</span></span>

- [<span data-ttu-id="0ed0b-138">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="0ed0b-138">Objects and Classes</span></span>](index.md)
- [<span data-ttu-id="0ed0b-139">Visual Basic에서 숨김</span><span class="sxs-lookup"><span data-stu-id="0ed0b-139">Shadowing in Visual Basic</span></span>](../declared-elements/shadowing.md)
- [<span data-ttu-id="0ed0b-140">Sub 문</span><span class="sxs-lookup"><span data-stu-id="0ed0b-140">Sub Statement</span></span>](../../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="0ed0b-141">상속 기본 사항</span><span class="sxs-lookup"><span data-stu-id="0ed0b-141">Inheritance Basics</span></span>](inheritance-basics.md)
- [<span data-ttu-id="0ed0b-142">Overloads</span><span class="sxs-lookup"><span data-stu-id="0ed0b-142">Shadows</span></span>](../../../language-reference/modifiers/shadows.md)
- [<span data-ttu-id="0ed0b-143">ByVal</span><span class="sxs-lookup"><span data-stu-id="0ed0b-143">ByVal</span></span>](../../../language-reference/modifiers/byval.md)
- [<span data-ttu-id="0ed0b-144">ByRef</span><span class="sxs-lookup"><span data-stu-id="0ed0b-144">ByRef</span></span>](../../../language-reference/modifiers/byref.md)
- [<span data-ttu-id="0ed0b-145">오버로드</span><span class="sxs-lookup"><span data-stu-id="0ed0b-145">Overloads</span></span>](../../../language-reference/modifiers/overloads.md)
- [<span data-ttu-id="0ed0b-146">Overloads</span><span class="sxs-lookup"><span data-stu-id="0ed0b-146">Shadows</span></span>](../../../language-reference/modifiers/shadows.md)
