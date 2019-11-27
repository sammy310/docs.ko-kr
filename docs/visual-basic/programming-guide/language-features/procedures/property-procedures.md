---
title: Property 프로시저
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
ms.openlocfilehash: a4b8ac3e27348764f537ee9502ce1fbb165bb3ef
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352570"
---
# <a name="property-procedures-visual-basic"></a><span data-ttu-id="f7d36-102">Property 프로시저(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f7d36-102">Property Procedures (Visual Basic)</span></span>

<span data-ttu-id="f7d36-103">속성 프로시저는 모듈, 클래스 또는 구조체의 사용자 지정 속성을 조작 하는 일련의 Visual Basic 문입니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-103">A property procedure is a series of Visual Basic statements that manipulate a custom property on a module, class, or structure.</span></span> <span data-ttu-id="f7d36-104">속성 프로시저를 *속성 접근자*라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-104">Property procedures are also known as *property accessors*.</span></span>

<span data-ttu-id="f7d36-105">Visual Basic는 다음 속성 프로시저를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-105">Visual Basic provides for the following property procedures:</span></span>

- <span data-ttu-id="f7d36-106">`Get` 프로시저는 속성의 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-106">A `Get` procedure returns the value of a property.</span></span> <span data-ttu-id="f7d36-107">식의 속성에 액세스할 때 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-107">It is called when you access the property in an expression.</span></span>
- <span data-ttu-id="f7d36-108">`Set` 프로시저는 개체 참조를 포함 하 여 속성을 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-108">A `Set` procedure sets a property to a value, including an object reference.</span></span> <span data-ttu-id="f7d36-109">속성에 값을 할당할 때 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-109">It is called when you assign a value to the property.</span></span>

<span data-ttu-id="f7d36-110">일반적으로 `Get` 및 `Set` 문을 사용 하 여 속성 프로시저를 쌍으로 정의 하지만 속성이 읽기 전용 ([Get 문](../../../../visual-basic/language-reference/statements/get-statement.md)) 또는 쓰기 전용 ([Set 문](../../../../visual-basic/language-reference/statements/set-statement.md)) 인 경우에만 프로시저를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-110">You usually define property procedures in pairs, using the `Get` and `Set` statements, but you can define either procedure alone if the property is read-only ([Get Statement](../../../../visual-basic/language-reference/statements/get-statement.md)) or write-only ([Set Statement](../../../../visual-basic/language-reference/statements/set-statement.md)).</span></span>

<span data-ttu-id="f7d36-111">자동 구현 속성을 사용 하는 경우 `Get` 및 `Set` 프로시저를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-111">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="f7d36-112">자세한 내용은 [자동으로 구현된 속성](./auto-implemented-properties.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f7d36-112">For more information, see [Auto-Implemented Properties](./auto-implemented-properties.md).</span></span>

<span data-ttu-id="f7d36-113">클래스, 구조체 및 모듈에서 속성을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-113">You can define properties in classes, structures, and modules.</span></span> <span data-ttu-id="f7d36-114">속성은 기본적으로 `Public` 됩니다. 즉, 속성의 컨테이너에 액세스할 수 있는 응용 프로그램의 어디에서 나 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-114">Properties are `Public` by default, which means you can call them from anywhere in your application that can access the property's container.</span></span>

<span data-ttu-id="f7d36-115">속성과 변수를 비교 하는 방법에 대 한 자세한 내용은 [Visual Basic의 속성과 변수 간의 차이점](differences-between-properties-and-variables.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f7d36-115">For a comparison of properties and variables, see [Differences Between Properties and Variables in Visual Basic](differences-between-properties-and-variables.md).</span></span>

## <a name="declaration-syntax"></a><span data-ttu-id="f7d36-116">선언 구문</span><span class="sxs-lookup"><span data-stu-id="f7d36-116">Declaration syntax</span></span>

<span data-ttu-id="f7d36-117">속성 자체는 [속성 문과](../../../../visual-basic/language-reference/statements/property-statement.md) `End Property` 문 내에 포함 된 코드 블록으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-117">A property itself is defined by a block of code enclosed within the [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="f7d36-118">이 블록 내에서 각 속성 프로시저는 선언 문 (`Get` 또는 `Set`) 및 일치 하는 `End` 선언에 포함 된 내부 블록으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-118">Inside this block, each property procedure appears as an internal block enclosed within a declaration statement (`Get` or `Set`) and the matching `End` declaration.</span></span>

<span data-ttu-id="f7d36-119">속성 및 해당 프로시저를 선언 하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-119">The syntax for declaring a property and its procedures is as follows:</span></span>

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

<span data-ttu-id="f7d36-120">`Modifiers`는 액세스 수준 및 오버 로드, 재정의, 공유 및 숨김과 관련 된 정보 뿐만 아니라 속성이 읽기 전용 이거나 쓰기 전용인 지 여부에 대 한 정보를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-120">The `Modifiers` can specify access level and information regarding overloading, overriding, sharing, and shadowing, as well as whether the property is read-only or write-only.</span></span> <span data-ttu-id="f7d36-121">`Get` 또는 `Set` 프로시저에 대 한 `AccessLevel`는 속성 자체에 대해 지정 된 액세스 수준 보다 더 제한적인 수준이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-121">The `AccessLevel` on the `Get` or `Set` procedure can be any level that is more restrictive than the access level specified for the property itself.</span></span> <span data-ttu-id="f7d36-122">자세한 내용은 [Property 문](../../../../visual-basic/language-reference/statements/property-statement.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f7d36-122">For more information, see [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md).</span></span>

### <a name="data-type"></a><span data-ttu-id="f7d36-123">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="f7d36-123">Data Type</span></span>

<span data-ttu-id="f7d36-124">속성의 데이터 형식 및 보안 주체 액세스 수준은 속성 프로시저가 아닌 `Property` 문에 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-124">A property's data type and principal access level are defined in the `Property` statement, not in the property procedures.</span></span> <span data-ttu-id="f7d36-125">속성에는 데이터 형식이 하나만 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-125">A property can have only one data type.</span></span> <span data-ttu-id="f7d36-126">예를 들어 `Decimal` 값을 저장 하 고 `Double` 값을 검색 하는 속성을 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-126">For example, you cannot define a property to store a `Decimal` value but retrieve a `Double` value.</span></span>

### <a name="access-level"></a><span data-ttu-id="f7d36-127">액세스 수준</span><span class="sxs-lookup"><span data-stu-id="f7d36-127">Access Level</span></span>

<span data-ttu-id="f7d36-128">그러나 속성의 보안 주체 액세스 수준을 정의 하 고 속성 프로시저 중 하나에서 액세스 수준을 추가로 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-128">However, you can define a principal access level for a property and further restrict the access level in one of its property procedures.</span></span> <span data-ttu-id="f7d36-129">예를 들어 `Public` 속성을 정의한 다음 `Private Set` 프로시저를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-129">For example, you can define a `Public` property and then define a `Private Set` procedure.</span></span> <span data-ttu-id="f7d36-130">`Get` 프로시저는 `Public`남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-130">The `Get` procedure remains `Public`.</span></span> <span data-ttu-id="f7d36-131">속성의 프로시저 중 하나 에서만 액세스 수준을 변경할 수 있으며, 보안 주체 액세스 수준 보다 제한적 으로만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-131">You can change the access level in only one of a property's procedures, and you can only make it more restrictive than the principal access level.</span></span> <span data-ttu-id="f7d36-132">자세한 내용은 [방법: 액세스 수준이 혼합 된 속성 선언](how-to-declare-a-property-with-mixed-access-levels.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f7d36-132">For more information, see [How to: Declare a Property with Mixed Access Levels](how-to-declare-a-property-with-mixed-access-levels.md).</span></span>

## <a name="parameter-declaration"></a><span data-ttu-id="f7d36-133">매개 변수 선언</span><span class="sxs-lookup"><span data-stu-id="f7d36-133">Parameter declaration</span></span>

<span data-ttu-id="f7d36-134">전달 메커니즘을 `ByVal`해야 한다는 점을 제외 하 고 [하위 프로시저](sub-procedures.md)와 동일한 방식으로 각 매개 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-134">You declare each parameter the same way you do for [Sub Procedures](sub-procedures.md), except that the passing mechanism must be `ByVal`.</span></span>

<span data-ttu-id="f7d36-135">매개 변수 목록의 각 매개 변수에 대 한 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-135">The syntax for each parameter in the parameter list is as follows:</span></span>

```vb
[Optional] ByVal [ParamArray] parametername As datatype
```

<span data-ttu-id="f7d36-136">매개 변수가 선택 사항인 경우에는 해당 선언의 일부로도 기본값을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-136">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="f7d36-137">기본값을 지정 하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-137">The syntax for specifying a default value is as follows:</span></span>

```vb
Optional ByVal parametername As datatype = defaultvalue
```

## <a name="property-value"></a><span data-ttu-id="f7d36-138">속성 값</span><span class="sxs-lookup"><span data-stu-id="f7d36-138">Property value</span></span>

<span data-ttu-id="f7d36-139">`Get` 프로시저에서 반환 값은 호출 식에 속성 값으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-139">In a `Get` procedure, the return value is supplied to the calling expression as the value of the property.</span></span>

<span data-ttu-id="f7d36-140">`Set` 프로시저에서는 새 속성 값이 `Set` 문의 매개 변수로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-140">In a `Set` procedure, the new property value is passed to the parameter of the `Set` statement.</span></span> <span data-ttu-id="f7d36-141">매개 변수를 명시적으로 선언 하는 경우에는 속성과 동일한 데이터 형식을 사용 하 여 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-141">If you explicitly declare a parameter, you must declare it with the same data type as the property.</span></span> <span data-ttu-id="f7d36-142">매개 변수를 선언 하지 않으면 컴파일러는 `Value` 암시적 매개 변수를 사용 하 여 속성에 할당 되는 새 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-142">If you do not declare a parameter, the compiler uses the implicit parameter `Value` to represent the new value to be assigned to the property.</span></span>

## <a name="calling-syntax"></a><span data-ttu-id="f7d36-143">호출 구문</span><span class="sxs-lookup"><span data-stu-id="f7d36-143">Calling syntax</span></span>

<span data-ttu-id="f7d36-144">속성을 참조 하 여 암시적으로 속성 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-144">You invoke a property procedure implicitly by making reference to the property.</span></span> <span data-ttu-id="f7d36-145">변수 이름을 사용 하는 것과 동일한 방식으로 속성의 이름을 사용 합니다. 단, 선택 사항이 아닌 모든 인수에 대 한 값을 제공 해야 하 고 인수 목록을 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-145">You use the name of the property the same way you would use the name of a variable, except that you must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="f7d36-146">인수를 제공 하지 않으면 필요에 따라 괄호를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-146">If no arguments are supplied, you can optionally omit the parentheses.</span></span>

<span data-ttu-id="f7d36-147">`Set` 프로시저에 대 한 암시적 호출 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-147">The syntax for an implicit call to a `Set` procedure is as follows:</span></span>

```vb
propertyname[(argumentlist)] = expression
```

<span data-ttu-id="f7d36-148">`Get` 프로시저에 대 한 암시적 호출 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-148">The syntax for an implicit call to a `Get` procedure is as follows:</span></span>

```vb
lvalue = propertyname[(argumentlist)]
Do While (propertyname[(argumentlist)] > expression)
```

### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="f7d36-149">선언 및 호출에 대 한 그림</span><span class="sxs-lookup"><span data-stu-id="f7d36-149">Illustration of declaration and call</span></span>

<span data-ttu-id="f7d36-150">다음 속성은 이름, 이름 및 성 이라는 두 가지 구성 이름으로 전체 이름을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-150">The following property stores a full name as two constituent names, the first name and the last name.</span></span> <span data-ttu-id="f7d36-151">호출 코드가 `fullName`를 읽을 때 `Get` 프로시저는 두 가지 구성 이름을 결합 하 고 전체 이름을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-151">When the calling code reads `fullName`, the `Get` procedure combines the two constituent names and returns the full name.</span></span> <span data-ttu-id="f7d36-152">호출 코드에서 새 전체 이름을 할당 하면 `Set` 프로시저는 두 개의 구성 된 이름으로 코드를 분리 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-152">When the calling code assigns a new full name, the `Set` procedure attempts to break it into two constituent names.</span></span> <span data-ttu-id="f7d36-153">공백을 찾지 못하면 모두 이름으로 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-153">If it does not find a space, it stores it all as the first name.</span></span>

[!code-vb[VbVbcnProcedures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#8)]

<span data-ttu-id="f7d36-154">다음 예에서는 `fullName`의 속성 프로시저에 대 한 일반적인 호출을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f7d36-154">The following example shows typical calls to the property procedures of `fullName`:</span></span>

[!code-vb[VbVbcnProcedures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#9)]

## <a name="see-also"></a><span data-ttu-id="f7d36-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f7d36-155">See also</span></span>

- [<span data-ttu-id="f7d36-156">절차</span><span class="sxs-lookup"><span data-stu-id="f7d36-156">Procedures</span></span>](index.md)
- [<span data-ttu-id="f7d36-157">Function 프로시저</span><span class="sxs-lookup"><span data-stu-id="f7d36-157">Function Procedures</span></span>](function-procedures.md)
- [<span data-ttu-id="f7d36-158">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="f7d36-158">Operator Procedures</span></span>](operator-procedures.md)
- [<span data-ttu-id="f7d36-159">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="f7d36-159">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="f7d36-160">Visual Basic에서 속성과 변수의 차이점</span><span class="sxs-lookup"><span data-stu-id="f7d36-160">Differences Between Properties and Variables in Visual Basic</span></span>](differences-between-properties-and-variables.md)
- [<span data-ttu-id="f7d36-161">방법: 속성 만들기</span><span class="sxs-lookup"><span data-stu-id="f7d36-161">How to: Create a Property</span></span>](how-to-create-a-property.md)
- [<span data-ttu-id="f7d36-162">방법: 속성 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="f7d36-162">How to: Call a Property Procedure</span></span>](how-to-call-a-property-procedure.md)
- [<span data-ttu-id="f7d36-163">방법: Visual Basic에서 기본 속성 선언 및 호출</span><span class="sxs-lookup"><span data-stu-id="f7d36-163">How to: Declare and Call a Default Property in Visual Basic</span></span>](how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="f7d36-164">방법: 속성 값 입력</span><span class="sxs-lookup"><span data-stu-id="f7d36-164">How to: Put a Value in a Property</span></span>](how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="f7d36-165">방법: 속성에서 값 가져오기</span><span class="sxs-lookup"><span data-stu-id="f7d36-165">How to: Get a Value from a Property</span></span>](how-to-get-a-value-from-a-property.md)
