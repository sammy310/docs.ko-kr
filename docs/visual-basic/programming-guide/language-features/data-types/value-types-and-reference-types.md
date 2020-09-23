---
title: Value Types and Reference Types
ms.date: 07/20/2015
helpviewer_keywords:
- reference data types [Visual Basic]
- reference types [Visual Basic]
- value types [Visual Basic]
- value data types [Visual Basic]
- types [Visual Basic]
- data types [Visual Basic], value types
- data types [Visual Basic], reference types
ms.assetid: fc82ce15-5a40-4c5c-a1e1-a556830e7391
ms.openlocfilehash: 72cb1455300e1ff00d9d558aa5a9df95f32aa7b0
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91090120"
---
# <a name="value-types-and-reference-types"></a><span data-ttu-id="f3513-102">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="f3513-102">Value Types and Reference Types</span></span>

<span data-ttu-id="f3513-103">Visual Basic에는 참조 형식 및 값 형식 이라는 두 가지 종류의 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3513-103">There are two kinds of types in Visual Basic: reference types and value types.</span></span> <span data-ttu-id="f3513-104">참조 형식의 변수에는 데이터(개체)에 대한 참조가 저장되며, 값 형식의 변수에는 해당 데이터가 직접 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3513-104">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="f3513-105">참조 형식에서는 두 가지 변수가 같은 개체를 참조할 수 있으므로 한 변수에 대한 작업이 다른 변수에서 참조하는 개체에 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3513-105">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="f3513-106">값 형식에서는 각 변수에 데이터의 자체 복사본이 있으며 한 변수의 작업이 다른 변수에 영향을 줄 수 없습니다 ( [매개 변수에 대 한 ByRef 한정자](../../../language-reference/modifiers/byref.md)의 경우 제외).</span><span class="sxs-lookup"><span data-stu-id="f3513-106">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of the [ByRef modifier on parameters](../../../language-reference/modifiers/byref.md)).</span></span>
  
## <a name="value-types"></a><span data-ttu-id="f3513-107">값 형식</span><span class="sxs-lookup"><span data-stu-id="f3513-107">Value Types</span></span>  

 <span data-ttu-id="f3513-108">데이터 형식은 자체 메모리 할당 내에 데이터를 저장 하는 경우 *값 형식* 입니다.</span><span class="sxs-lookup"><span data-stu-id="f3513-108">A data type is a *value type* if it holds the data within its own memory allocation.</span></span> <span data-ttu-id="f3513-109">값 형식에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3513-109">Value types include the following:</span></span>  
  
- <span data-ttu-id="f3513-110">모든 숫자 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="f3513-110">All numeric data types</span></span>  
  
- <span data-ttu-id="f3513-111">`Boolean`, `Char`, `Date`</span><span class="sxs-lookup"><span data-stu-id="f3513-111">`Boolean`, `Char`, and `Date`</span></span>  
  
- <span data-ttu-id="f3513-112">멤버가 참조 형식인 경우에도 모든 구조체</span><span class="sxs-lookup"><span data-stu-id="f3513-112">All structures, even if their members are reference types</span></span>  
  
- <span data-ttu-id="f3513-113">열거형의 기본 형식은 항상,,,,,, `SByte` `Short` `Integer` `Long` `Byte` `UShort` `UInteger` 또는 이기 때문입니다. `ULong`</span><span class="sxs-lookup"><span data-stu-id="f3513-113">Enumerations, since their underlying type is always `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, or `ULong`</span></span>  
  
 <span data-ttu-id="f3513-114">참조 형식 멤버가 포함 된 경우에도 모든 구조체는 값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f3513-114">Every structure is a value type, even if it contains reference type members.</span></span> <span data-ttu-id="f3513-115">이러한 이유로 및와 같은 값 형식은 `Char` `Integer` .NET Framework 구조에 의해 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3513-115">For this reason, value types such as `Char` and `Integer` are implemented by .NET Framework structures.</span></span>  
  
 <span data-ttu-id="f3513-116">예약 된 키워드 (예:)를 사용 하 여 값 형식을 선언할 수 있습니다 `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="f3513-116">You can declare a value type by using the reserved keyword, for example, `Decimal`.</span></span> <span data-ttu-id="f3513-117">키워드를 사용 하 여 `New` 값 형식을 초기화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3513-117">You can also use the `New` keyword to initialize a value type.</span></span> <span data-ttu-id="f3513-118">이는 형식에 매개 변수를 사용 하는 생성자가 있는 경우 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3513-118">This is especially useful if the type has a constructor that takes parameters.</span></span> <span data-ttu-id="f3513-119">이에 대 한 예는 <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> 제공 된 파트에서 새 값을 작성 하는 생성자입니다 `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="f3513-119">An example of this is the <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> constructor, which builds a new `Decimal` value from the supplied parts.</span></span>  
  
## <a name="reference-types"></a><span data-ttu-id="f3513-120">참조 형식</span><span class="sxs-lookup"><span data-stu-id="f3513-120">Reference Types</span></span>  

 <span data-ttu-id="f3513-121">*참조 형식은* 해당 데이터에 대 한 참조를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3513-121">A *reference type* stores a reference to its data.</span></span> <span data-ttu-id="f3513-122">참조 형식에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3513-122">Reference types include the following:</span></span>  
  
- `String`  
  
- <span data-ttu-id="f3513-123">모든 배열 (해당 요소가 값 형식인 경우에도)</span><span class="sxs-lookup"><span data-stu-id="f3513-123">All arrays, even if their elements are value types</span></span>  
  
- <span data-ttu-id="f3513-124">클래스 형식 (예:) <xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="f3513-124">Class types, such as <xref:System.Windows.Forms.Form></span></span>  
  
- <span data-ttu-id="f3513-125">대리자</span><span class="sxs-lookup"><span data-stu-id="f3513-125">Delegates</span></span>  
  
 <span data-ttu-id="f3513-126">클래스는 *참조 형식*입니다.</span><span class="sxs-lookup"><span data-stu-id="f3513-126">A class is a *reference type*.</span></span> <span data-ttu-id="f3513-127">모든 배열은 멤버가 값 형식인 경우에도 참조 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f3513-127">Note that every array is a reference type, even if its members are value types.</span></span>  
  
 <span data-ttu-id="f3513-128">모든 참조 형식은 기본 .NET Framework 클래스를 나타내므로 초기화할 때 [New Operator](../../../language-reference/operators/new-operator.md) 키워드를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3513-128">Since every reference type represents an underlying .NET Framework class, you must use the [New Operator](../../../language-reference/operators/new-operator.md) keyword when you initialize it.</span></span> <span data-ttu-id="f3513-129">다음 문은 배열을 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3513-129">The following statement initializes an array.</span></span>  
  
```vb  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a><span data-ttu-id="f3513-130">형식이 아닌 요소</span><span class="sxs-lookup"><span data-stu-id="f3513-130">Elements That Are Not Types</span></span>  

 <span data-ttu-id="f3513-131">다음 프로그래밍 요소는 선언 된 요소에 대 한 데이터 형식으로 지정할 수 없으므로 형식으로 한정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f3513-131">The following programming elements do not qualify as types, because you cannot specify any of them as a data type for a declared element:</span></span>  
  
- <span data-ttu-id="f3513-132">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="f3513-132">Namespaces</span></span>  
  
- <span data-ttu-id="f3513-133">모듈</span><span class="sxs-lookup"><span data-stu-id="f3513-133">Modules</span></span>  
  
- <span data-ttu-id="f3513-134">이벤트</span><span class="sxs-lookup"><span data-stu-id="f3513-134">Events</span></span>  
  
- <span data-ttu-id="f3513-135">속성 및 프로시저</span><span class="sxs-lookup"><span data-stu-id="f3513-135">Properties and procedures</span></span>  
  
- <span data-ttu-id="f3513-136">변수, 상수 및 필드</span><span class="sxs-lookup"><span data-stu-id="f3513-136">Variables, constants, and fields</span></span>  
  
## <a name="working-with-the-object-data-type"></a><span data-ttu-id="f3513-137">Object 데이터 형식 작업</span><span class="sxs-lookup"><span data-stu-id="f3513-137">Working with the Object Data Type</span></span>  

 <span data-ttu-id="f3513-138">참조 형식 또는 값 형식을 데이터 형식의 변수에 할당할 수 있습니다 `Object` .</span><span class="sxs-lookup"><span data-stu-id="f3513-138">You can assign either a reference type or a value type to a variable of the `Object` data type.</span></span> <span data-ttu-id="f3513-139">`Object`변수는 항상 데이터에 대 한 참조를 보유 하며 데이터 자체는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f3513-139">An `Object` variable always holds a reference to the data, never the data itself.</span></span> <span data-ttu-id="f3513-140">그러나 변수에 값 형식을 할당 하는 경우이 값은 자체 데이터를 보유 하는 것 `Object` 처럼 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3513-140">However, if you assign a value type to an `Object` variable, it behaves as if it holds its own data.</span></span> <span data-ttu-id="f3513-141">자세한 내용은 [Object Data Type](../../../language-reference/data-types/object-data-type.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3513-141">For more information, see [Object Data Type](../../../language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="f3513-142">`Object`변수를 <xref:Microsoft.VisualBasic.Information.IsReference%2A> <xref:Microsoft.VisualBasic.Information> 네임 스페이스 클래스의 메서드에 전달 하 여 변수를 참조 형식 또는 값 형식으로 사용할지 여부를 확인할 수 있습니다 <xref:Microsoft.VisualBasic?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="f3513-142">You can find out whether an `Object` variable is acting as a reference type or a value type by passing it to the <xref:Microsoft.VisualBasic.Information.IsReference%2A> method in the <xref:Microsoft.VisualBasic.Information> class of the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="f3513-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType>`True` `Object` 변수의 내용이 참조 형식을 나타내면를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3513-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> returns `True` if the content of the `Object` variable represents a reference type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3513-144">참조</span><span class="sxs-lookup"><span data-stu-id="f3513-144">See also</span></span>

- [<span data-ttu-id="f3513-145">Nullable 값 형식</span><span class="sxs-lookup"><span data-stu-id="f3513-145">Nullable Value Types</span></span>](nullable-value-types.md)
- [<span data-ttu-id="f3513-146">Visual Basic의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="f3513-146">Type Conversions in Visual Basic</span></span>](type-conversions.md)
- [<span data-ttu-id="f3513-147">Structure 문</span><span class="sxs-lookup"><span data-stu-id="f3513-147">Structure Statement</span></span>](../../../language-reference/statements/structure-statement.md)
- [<span data-ttu-id="f3513-148">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="f3513-148">Efficient Use of Data Types</span></span>](efficient-use-of-data-types.md)
- [<span data-ttu-id="f3513-149">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="f3513-149">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="f3513-150">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="f3513-150">Data Types</span></span>](index.md)
