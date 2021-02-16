---
description: '자세한 정보: 속성 프로시저 (Visual Basic)'
title: 속성 프로시저
ms.date: 07/20/2015
helpviewer_keywords:
- Set statement [Visual Basic], Property procedures
- Visual Basic code, procedures
- return values [Visual Basic], Property procedures
- syntax [Visual Basic], Property procedures
- procedures [Visual Basic], property
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], custom
- property procedures
- Get statement [Visual Basic], property procedures
ms.assetid: 46a98379-e1a2-45dd-a48c-b51213f5ab07
ms.openlocfilehash: 55588278cdb8423a4f13a4e7ecc02f7ea692a618
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100466590"
---
# <a name="property-procedures-visual-basic"></a><span data-ttu-id="34213-103">Property 프로시저(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="34213-103">Property Procedures (Visual Basic)</span></span>

<span data-ttu-id="34213-104">속성 프로시저는 모듈, 클래스 또는 구조체의 사용자 지정 속성을 조작 하는 일련의 Visual Basic 문입니다.</span><span class="sxs-lookup"><span data-stu-id="34213-104">A property procedure is a series of Visual Basic statements that manipulate a custom property on a module, class, or structure.</span></span> <span data-ttu-id="34213-105">속성 프로시저를 *속성 접근자* 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="34213-105">Property procedures are also known as *property accessors*.</span></span>

<span data-ttu-id="34213-106">Visual Basic는 다음 속성 프로시저를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="34213-106">Visual Basic provides for the following property procedures:</span></span>

- <span data-ttu-id="34213-107">`Get`프로시저는 속성의 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="34213-107">A `Get` procedure returns the value of a property.</span></span> <span data-ttu-id="34213-108">식의 속성에 액세스할 때 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34213-108">It is called when you access the property in an expression.</span></span>
- <span data-ttu-id="34213-109">`Set`프로시저는 개체 참조를 포함 하 여 속성을 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="34213-109">A `Set` procedure sets a property to a value, including an object reference.</span></span> <span data-ttu-id="34213-110">속성에 값을 할당할 때 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34213-110">It is called when you assign a value to the property.</span></span>

<span data-ttu-id="34213-111">일반적으로 및 문을 사용 하 여 속성 프로시저를 쌍으로 정의 `Get` `Set` 하지만 속성이 읽기 전용 ([Get 문](../../../language-reference/statements/get-statement.md)) 또는 쓰기 전용 ([Set 문](../../../language-reference/statements/set-statement.md)) 인 경우에만 프로시저를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34213-111">You usually define property procedures in pairs, using the `Get` and `Set` statements, but you can define either procedure alone if the property is read-only ([Get Statement](../../../language-reference/statements/get-statement.md)) or write-only ([Set Statement](../../../language-reference/statements/set-statement.md)).</span></span>

<span data-ttu-id="34213-112">`Get` `Set` 자동 구현 속성을 사용 하는 경우 및 프로시저를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34213-112">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="34213-113">자세한 내용은 [자동으로 구현된 속성](./auto-implemented-properties.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="34213-113">For more information, see [Auto-Implemented Properties](./auto-implemented-properties.md).</span></span>

<span data-ttu-id="34213-114">클래스, 구조체 및 모듈에서 속성을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34213-114">You can define properties in classes, structures, and modules.</span></span> <span data-ttu-id="34213-115">속성은 `Public` 기본적으로 이므로 속성의 컨테이너에 액세스할 수 있는 응용 프로그램의 어디에서 나 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34213-115">Properties are `Public` by default, which means you can call them from anywhere in your application that can access the property's container.</span></span>

<span data-ttu-id="34213-116">속성과 변수를 비교 하는 방법에 대 한 자세한 내용은 [Visual Basic의 속성과 변수 간의 차이점](differences-between-properties-and-variables.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="34213-116">For a comparison of properties and variables, see [Differences Between Properties and Variables in Visual Basic](differences-between-properties-and-variables.md).</span></span>

## <a name="declaration-syntax"></a><span data-ttu-id="34213-117">선언 구문</span><span class="sxs-lookup"><span data-stu-id="34213-117">Declaration syntax</span></span>

<span data-ttu-id="34213-118">속성 자체는 [속성 문과](../../../language-reference/statements/property-statement.md) 문 내에 포함 된 코드 블록에 의해 정의 됩니다 `End Property` .</span><span class="sxs-lookup"><span data-stu-id="34213-118">A property itself is defined by a block of code enclosed within the [Property Statement](../../../language-reference/statements/property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="34213-119">이 블록 내에서 각 속성 프로시저는 선언 문 ( `Get` 또는 `Set` ) 및 일치 하는 선언 내에 포함 된 내부 블록으로 나타납니다 `End` .</span><span class="sxs-lookup"><span data-stu-id="34213-119">Inside this block, each property procedure appears as an internal block enclosed within a declaration statement (`Get` or `Set`) and the matching `End` declaration.</span></span>

<span data-ttu-id="34213-120">속성 및 해당 프로시저를 선언 하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="34213-120">The syntax for declaring a property and its procedures is as follows:</span></span>

```vb
[Default] [Modifiers] Property PropertyName[(ParameterList)] [As DataType]
    [AccessLevel] Get
        ' Statements of the Get procedure.
        ' The following statement returns an expression as the property's value.
        Return Expression
    End Get
    [AccessLevel] Set[(ByVal NewValue As DataType)]
        ' Statements of the Set procedure.
        ' The following statement assigns newvalue as the property's value.
        LValue = NewValue
    End Set
End Property
' - or -
[Default] [Modifiers] Property PropertyName [(ParameterList)] [As DataType]
```

<span data-ttu-id="34213-121">는 `Modifiers` 오버 로드, 재정의, 공유 및 숨김과 관련 된 액세스 수준 및 정보와 속성이 읽기 전용 이거나 쓰기 전용인 지 여부에 대 한 정보를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34213-121">The `Modifiers` can specify access level and information regarding overloading, overriding, sharing, and shadowing, as well as whether the property is read-only or write-only.</span></span> <span data-ttu-id="34213-122">`AccessLevel` `Get` 또는 프로시저의는 `Set` 속성 자체에 대해 지정 된 액세스 수준 보다 더 제한적인 수준이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34213-122">The `AccessLevel` on the `Get` or `Set` procedure can be any level that is more restrictive than the access level specified for the property itself.</span></span> <span data-ttu-id="34213-123">자세한 내용은 [Property 문](../../../language-reference/statements/property-statement.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="34213-123">For more information, see [Property Statement](../../../language-reference/statements/property-statement.md).</span></span>

### <a name="data-type"></a><span data-ttu-id="34213-124">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="34213-124">Data Type</span></span>

<span data-ttu-id="34213-125">속성의 데이터 형식 및 보안 주체 액세스 수준은 `Property` 속성 프로시저가 아닌 문에 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34213-125">A property's data type and principal access level are defined in the `Property` statement, not in the property procedures.</span></span> <span data-ttu-id="34213-126">속성에는 데이터 형식이 하나만 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34213-126">A property can have only one data type.</span></span> <span data-ttu-id="34213-127">예를 들어 값을 저장 하 고 값을 검색 하는 속성을 정의할 수 없습니다 `Decimal` `Double` .</span><span class="sxs-lookup"><span data-stu-id="34213-127">For example, you cannot define a property to store a `Decimal` value but retrieve a `Double` value.</span></span>

### <a name="access-level"></a><span data-ttu-id="34213-128">액세스 수준</span><span class="sxs-lookup"><span data-stu-id="34213-128">Access Level</span></span>

<span data-ttu-id="34213-129">그러나 속성의 보안 주체 액세스 수준을 정의 하 고 속성 프로시저 중 하나에서 액세스 수준을 추가로 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34213-129">However, you can define a principal access level for a property and further restrict the access level in one of its property procedures.</span></span> <span data-ttu-id="34213-130">예를 들어 속성을 정의한 `Public` 다음 프로시저를 정의할 수 있습니다 `Private Set` .</span><span class="sxs-lookup"><span data-stu-id="34213-130">For example, you can define a `Public` property and then define a `Private Set` procedure.</span></span> <span data-ttu-id="34213-131">`Get`프로시저는 그대로 유지 `Public` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34213-131">The `Get` procedure remains `Public`.</span></span> <span data-ttu-id="34213-132">속성의 프로시저 중 하나 에서만 액세스 수준을 변경할 수 있으며, 보안 주체 액세스 수준 보다 제한적 으로만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34213-132">You can change the access level in only one of a property's procedures, and you can only make it more restrictive than the principal access level.</span></span> <span data-ttu-id="34213-133">자세한 내용은 [방법: 액세스 수준이 혼합 된 속성 선언](how-to-declare-a-property-with-mixed-access-levels.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="34213-133">For more information, see [How to: Declare a Property with Mixed Access Levels](how-to-declare-a-property-with-mixed-access-levels.md).</span></span>

## <a name="parameter-declaration"></a><span data-ttu-id="34213-134">매개 변수 선언</span><span class="sxs-lookup"><span data-stu-id="34213-134">Parameter declaration</span></span>

<span data-ttu-id="34213-135">전달 메커니즘이 여야 한다는 점을 제외 하 고 [하위 프로시저](sub-procedures.md)와 동일한 방식으로 각 매개 변수를 선언 합니다 `ByVal` .</span><span class="sxs-lookup"><span data-stu-id="34213-135">You declare each parameter the same way you do for [Sub Procedures](sub-procedures.md), except that the passing mechanism must be `ByVal`.</span></span>

<span data-ttu-id="34213-136">매개 변수 목록의 각 매개 변수에 대 한 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="34213-136">The syntax for each parameter in the parameter list is as follows:</span></span>

```vb
[Optional] ByVal [ParamArray] parametername As datatype
```

<span data-ttu-id="34213-137">매개 변수가 선택 사항인 경우에는 해당 선언의 일부로도 기본값을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34213-137">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="34213-138">기본값을 지정 하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="34213-138">The syntax for specifying a default value is as follows:</span></span>

```vb
Optional ByVal parametername As datatype = defaultvalue
```

## <a name="property-value"></a><span data-ttu-id="34213-139">속성 값</span><span class="sxs-lookup"><span data-stu-id="34213-139">Property value</span></span>

<span data-ttu-id="34213-140">프로시저에서 `Get` 반환 값은 속성 값으로 호출 식에 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34213-140">In a `Get` procedure, the return value is supplied to the calling expression as the value of the property.</span></span>

<span data-ttu-id="34213-141">프로시저에서 `Set` 새 속성 값은 문의 매개 변수로 전달 됩니다 `Set` .</span><span class="sxs-lookup"><span data-stu-id="34213-141">In a `Set` procedure, the new property value is passed to the parameter of the `Set` statement.</span></span> <span data-ttu-id="34213-142">매개 변수를 명시적으로 선언 하는 경우에는 속성과 동일한 데이터 형식을 사용 하 여 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34213-142">If you explicitly declare a parameter, you must declare it with the same data type as the property.</span></span> <span data-ttu-id="34213-143">매개 변수를 선언 하지 않으면 컴파일러는 암시적 매개 변수를 사용 하 여 `Value` 속성에 할당 되는 새 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="34213-143">If you do not declare a parameter, the compiler uses the implicit parameter `Value` to represent the new value to be assigned to the property.</span></span>

## <a name="calling-syntax"></a><span data-ttu-id="34213-144">호출 구문</span><span class="sxs-lookup"><span data-stu-id="34213-144">Calling syntax</span></span>

<span data-ttu-id="34213-145">속성을 참조 하 여 암시적으로 속성 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="34213-145">You invoke a property procedure implicitly by making reference to the property.</span></span> <span data-ttu-id="34213-146">변수 이름을 사용 하는 것과 동일한 방식으로 속성의 이름을 사용 합니다. 단, 선택 사항이 아닌 모든 인수에 대 한 값을 제공 해야 하 고 인수 목록을 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34213-146">You use the name of the property the same way you would use the name of a variable, except that you must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="34213-147">인수를 제공 하지 않으면 필요에 따라 괄호를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34213-147">If no arguments are supplied, you can optionally omit the parentheses.</span></span>

<span data-ttu-id="34213-148">프로시저에 대 한 암시적 호출 구문은 `Set` 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="34213-148">The syntax for an implicit call to a `Set` procedure is as follows:</span></span>

```vb
propertyname[(argumentlist)] = expression
```

<span data-ttu-id="34213-149">프로시저에 대 한 암시적 호출 구문은 `Get` 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="34213-149">The syntax for an implicit call to a `Get` procedure is as follows:</span></span>

```vb
lvalue = propertyname[(argumentlist)]
Do While (propertyname[(argumentlist)] > expression)
```

### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="34213-150">선언 및 호출에 대 한 그림</span><span class="sxs-lookup"><span data-stu-id="34213-150">Illustration of declaration and call</span></span>

<span data-ttu-id="34213-151">다음 속성은 이름, 이름 및 성 이라는 두 가지 구성 이름으로 전체 이름을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="34213-151">The following property stores a full name as two constituent names, the first name and the last name.</span></span> <span data-ttu-id="34213-152">호출 코드가 읽는 경우 `fullName` `Get` 프로시저는 두 가지 구성 이름을 결합 하 고 전체 이름을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="34213-152">When the calling code reads `fullName`, the `Get` procedure combines the two constituent names and returns the full name.</span></span> <span data-ttu-id="34213-153">호출 코드에서 새 전체 이름을 할당 하면 `Set` 프로시저는 두 개의 구성 된 이름으로 코드를 분리 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="34213-153">When the calling code assigns a new full name, the `Set` procedure attempts to break it into two constituent names.</span></span> <span data-ttu-id="34213-154">공백을 찾지 못하면 모두 이름으로 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="34213-154">If it does not find a space, it stores it all as the first name.</span></span>

[!code-vb[VbVbcnProcedures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#8)]

<span data-ttu-id="34213-155">다음 예에서는의 속성 프로시저에 대 한 일반적인 호출을 보여 줍니다 `fullName` .</span><span class="sxs-lookup"><span data-stu-id="34213-155">The following example shows typical calls to the property procedures of `fullName`:</span></span>

[!code-vb[VbVbcnProcedures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#9)]

## <a name="see-also"></a><span data-ttu-id="34213-156">추가 정보</span><span class="sxs-lookup"><span data-stu-id="34213-156">See also</span></span>

- [<span data-ttu-id="34213-157">절차</span><span class="sxs-lookup"><span data-stu-id="34213-157">Procedures</span></span>](index.md)
- [<span data-ttu-id="34213-158">함수 프로시저</span><span class="sxs-lookup"><span data-stu-id="34213-158">Function Procedures</span></span>](function-procedures.md)
- [<span data-ttu-id="34213-159">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="34213-159">Operator Procedures</span></span>](operator-procedures.md)
- [<span data-ttu-id="34213-160">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="34213-160">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="34213-161">Visual Basic에서 속성과 변수의 차이점</span><span class="sxs-lookup"><span data-stu-id="34213-161">Differences Between Properties and Variables in Visual Basic</span></span>](differences-between-properties-and-variables.md)
- [<span data-ttu-id="34213-162">방법: 속성 만들기</span><span class="sxs-lookup"><span data-stu-id="34213-162">How to: Create a Property</span></span>](how-to-create-a-property.md)
- [<span data-ttu-id="34213-163">방법: 속성 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="34213-163">How to: Call a Property Procedure</span></span>](how-to-call-a-property-procedure.md)
- [<span data-ttu-id="34213-164">방법: Visual Basic에서 기본 속성 선언 및 호출</span><span class="sxs-lookup"><span data-stu-id="34213-164">How to: Declare and Call a Default Property in Visual Basic</span></span>](how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="34213-165">방법: 속성 값 입력</span><span class="sxs-lookup"><span data-stu-id="34213-165">How to: Put a Value in a Property</span></span>](how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="34213-166">방법: 속성에서 값 가져오기</span><span class="sxs-lookup"><span data-stu-id="34213-166">How to: Get a Value from a Property</span></span>](how-to-get-a-value-from-a-property.md)
