---
title: x:Arguments 지시문
ms.date: 03/30/2017
helpviewer_keywords:
- x:Arguments directive [XAML Services]
- Arguments directive in XAML [XAML Services]
- XAML [XAML Services], x:Arguments directive
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
ms.openlocfilehash: 5ec6e192688e1065ea847db6c175ad9da0e743fe
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432835"
---
# <a name="xarguments-directive"></a><span data-ttu-id="bd89c-102">x:Arguments 지시문</span><span class="sxs-lookup"><span data-stu-id="bd89c-102">x:Arguments Directive</span></span>

<span data-ttu-id="bd89c-103">XAML에서 비매개 변수 생성자 개체 요소 요소 선언 또는 팩터리 메서드 개체 선언에 대 한 생성 인수를 패키지 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd89c-103">Packages construction arguments for a non-parameterless constructor object element declaration in XAML, or for a factory method object declaration.</span></span>

## <a name="xaml-element-usage-nonparameterless-constructor"></a><span data-ttu-id="bd89c-104">XAML 요소 사용(비매개 변수 없는 생성자)</span><span class="sxs-lookup"><span data-stu-id="bd89c-104">XAML Element Usage (Nonparameterless constructor)</span></span>

```xaml
<object ...>
  <x:Arguments>
    oneOrMoreObjectElements
  </x:Arguments>
</object>
```

## <a name="xaml-element-usage-factory-method"></a><span data-ttu-id="bd89c-105">XAML 요소 사용(공장 방법)</span><span class="sxs-lookup"><span data-stu-id="bd89c-105">XAML Element Usage (factory method)</span></span>

```xaml
<object x:FactoryMethod="methodName"...>
  <x:Arguments>
    oneOrMoreObjectElements
  </x:Arguments>
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="bd89c-106">XAML 값</span><span class="sxs-lookup"><span data-stu-id="bd89c-106">XAML Values</span></span>

|||
|-|-|
|`oneOrMoreObjectElements`|<span data-ttu-id="bd89c-107">매개 변수가 없는 백업 생성자 또는 팩터리 메서드에 전달할 인수를 지정하는 하나 이상의 개체 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="bd89c-107">One or more object elements that specify arguments to be passed to the backing non-parameterless constructor or factory method.</span></span><br /><br /> <span data-ttu-id="bd89c-108">일반적인 용도는 개체 요소 내에서 초기화 텍스트를 사용하여 실제 인수 값을 지정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bd89c-108">Typical usage is to use initialization text within the object elements to specify the actual argument values.</span></span> <span data-ttu-id="bd89c-109">예제 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bd89c-109">See Examples section.</span></span><br /><br /> <span data-ttu-id="bd89c-110">요소의 순서는 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="bd89c-110">The order of the elements is significant.</span></span> <span data-ttu-id="bd89c-111">XAML 형식은 백업 생성자 또는 팩터리 메서드 오버로드의 형식 및 형식 순서와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd89c-111">The XAML types in order must match the types and type order of the backing constructor or factory method overload.</span></span>|
|`methodName`|<span data-ttu-id="bd89c-112">인수를 `x:Arguments` 처리해야 하는 팩터리 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="bd89c-112">The name of the factory method that should process any `x:Arguments` arguments.</span></span>|

## <a name="dependencies"></a><span data-ttu-id="bd89c-113">종속성</span><span class="sxs-lookup"><span data-stu-id="bd89c-113">Dependencies</span></span>

<span data-ttu-id="bd89c-114">`x:FactoryMethod`범위가 적용되는 경우 `x:Arguments` 동작을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd89c-114">`x:FactoryMethod` can modify the scope and behavior where `x:Arguments` applies.</span></span>

<span data-ttu-id="bd89c-115">아니오를 `x:FactoryMethod` 지정하면 `x:Arguments` 백업 생성자의 대체(기본값이 아닌) 서명에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd89c-115">If no `x:FactoryMethod` is specified, `x:Arguments` applies to alternate (non-default) signatures of the backing constructors.</span></span>

<span data-ttu-id="bd89c-116">`x:FactoryMethod` 지정하면 명명된 메서드의 오버로드에 `x:Arguments` 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd89c-116">If `x:FactoryMethod` is specified, `x:Arguments` applies to an overload of the named method.</span></span>

## <a name="remarks"></a><span data-ttu-id="bd89c-117">설명</span><span class="sxs-lookup"><span data-stu-id="bd89c-117">Remarks</span></span>

<span data-ttu-id="bd89c-118">XAML 2006은 초기화 텍스트를 통해 기본이 아닌 초기화를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd89c-118">XAML 2006 can support non-default initialization through initialization text.</span></span> <span data-ttu-id="bd89c-119">그러나 초기화 텍스트 생성 기술의 실제 적용은 제한적입니다.</span><span class="sxs-lookup"><span data-stu-id="bd89c-119">However, the practical application of an initialization text construction technique is limited.</span></span> <span data-ttu-id="bd89c-120">초기화 텍스트는 단일 텍스트 문자열로 처리됩니다. 따라서 사용자 지정 정보 항목 및 문자열에서 사용자 지정 구분자를 구문 분석할 수 있는 구성 동작에 대 한 형식 변환기가 정의 되지 않는 한 단일 매개 변수 초기화에 대 한 기능만 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd89c-120">Initialization text is treated as a single text string; therefore, it only adds capability for a single parameter initialization unless a type converter is defined for the construction behavior that can parse custom information items and custom delimiters from the string.</span></span> <span data-ttu-id="bd89c-121">또한 개체 논리에 대한 텍스트 문자열은 실제 문자열 이 아닌 프리미티브를 처리하기 위한 지정된 XAML 파서의 기본 기본 형식 변환기일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd89c-121">Also, the text string to object logic is potentially a given XAML parser's native default type converter for handling primitives other than a true string.</span></span>

<span data-ttu-id="bd89c-122">지시문 태그가 `x:Arguments` 포함된 개체 요소의 형식을 참조하지 않으므로 XAML 사용은 일반적인 의미에서 속성 요소 사용이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="bd89c-122">The `x:Arguments` XAML usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="bd89c-123">요소가 자식 내용의 기본값 `x:Code` 이 아닌 다른 것으로 태그가 해석되어야 하는 범위를 나타내는 다른 지시문과 더 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="bd89c-123">It is more akin to other directives such as `x:Code` where the element demarks a range in which the markup should be interpreted as other than the default for child contents.</span></span> <span data-ttu-id="bd89c-124">이 경우 각 개체 요소의 XAML 형식은 XAML 파서에서 사용하는 인수 형식에 대한 정보를 전달하여 `x:Arguments` 사용이 참조하려고 하는 특정 생성자 팩터리 메서드 서명을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="bd89c-124">In this case, the XAML type of each object element communicates information about the argument types, which is used by XAML parsers to determine which specific constructor factory method signature an `x:Arguments` usage is attempting to reference.</span></span>

<span data-ttu-id="bd89c-125">`x:Arguments`생성되는 개체 요소의 경우 개체 요소의 다른 속성 요소, 콘텐츠, 내부 텍스트 또는 초기화 문자열 앞에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd89c-125">`x:Arguments` for an object element being constructed must precede any other property elements, content, inner text, or initialization strings of the object element.</span></span> <span data-ttu-id="bd89c-126">내의 `x:Arguments` 개체 요소에는 해당 XAML 형식 및 백업 생성자 또는 팩터리 메서드에서 허용하는 특성 및 초기화 문자열이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd89c-126">The object elements within `x:Arguments` can include attributes and initialization strings, as permitted by that XAML type and its backing constructor or factory method.</span></span> <span data-ttu-id="bd89c-127">개체 또는 인수의 경우 설정된 접두사 매핑을 참조하여 기본 XAML 네임스페이스 외부에 있는 사용자 지정 XAML 형식 또는 XAML 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd89c-127">For either the object or the arguments, you can specify custom XAML types or XAML types that are otherwise outside the default XAML namespace by referencing established prefix mappings.</span></span>

<span data-ttu-id="bd89c-128">XAML 프로세서는 다음 지침을 사용하여 지정된 `x:Arguments` 인수를 개체를 생성하는 데 사용하는 방법을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="bd89c-128">XAML processors use the following guidelines to determine how the arguments specified in `x:Arguments` should be used to construct an object.</span></span> <span data-ttu-id="bd89c-129">`x:FactoryMethod` 지정하면 정보가 지정된 `x:FactoryMethod` 정보와 `x:FactoryMethod` 비교됩니다(값은 메서드 이름이며 명명된 메서드에는 오버로드가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd89c-129">If `x:FactoryMethod` is specified, information is compared to the specified `x:FactoryMethod` (note that the value of `x:FactoryMethod` is the method name, and the named method can have overloads.</span></span> <span data-ttu-id="bd89c-130">지정하지 않으면 `x:FactoryMethod` 정보는 개체의 모든 공용 생성자 오버로드 집합과 비교됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd89c-130">If `x:FactoryMethod` is not specified, information is compared to the set of all public constructor overloads of the object.</span></span> <span data-ttu-id="bd89c-131">그런 다음 XAML 처리 논리는 매개 변수 수를 비교하고 일치하는 arity와 오버로드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bd89c-131">XAML processing logic then compares the number of parameters and selects the overload with matching arity.</span></span> <span data-ttu-id="bd89c-132">일치하는 개체가 두 개 이상인 경우 XAML 프로세서는 제공된 개체 요소의 XAML 형식을 기반으로 하는 매개 변수 의 형식을 비교해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd89c-132">If there is more than one match, the XAML processor should compare the types of the parameters based on the XAML types of the provided object elements.</span></span> <span data-ttu-id="bd89c-133">여전히 일치하는 일치가 두 개 이상인 경우 XAML 프로세서 동작은 정의되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bd89c-133">If there is still more than one match, the XAML processor behavior is undefined.</span></span> <span data-ttu-id="bd89c-134">a를 `x:FactoryMethod` 지정했지만 메서드를 확인할 수 없는 경우 XAML 프로세서는 예외를 throw해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd89c-134">If a `x:FactoryMethod` is specified but the method cannot be resolved, a XAML processor should throw an exception.</span></span>

<span data-ttu-id="bd89c-135">XAML 특성 `<x:Arguments>string</x:Arguments>` 사용은 기술적으로 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="bd89c-135">A XAML attribute usage `<x:Arguments>string</x:Arguments>` is technically possible.</span></span> <span data-ttu-id="bd89c-136">그러나 이렇게 하면 초기화 텍스트 및 형식 변환기를 통해 수행할 수 있는 기능 이상으로 사용할 수 없으며 이 구문을 사용하는 것은 XAML 2009 팩터리 메서드 기능의 디자인 의도가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="bd89c-136">However, this provides no capabilities beyond what could be done otherwise through initialization text and type converters, and using this syntax is not the design intention of the XAML 2009 factory method features.</span></span>

## <a name="examples"></a><span data-ttu-id="bd89c-137">예</span><span class="sxs-lookup"><span data-stu-id="bd89c-137">Examples</span></span>

<span data-ttu-id="bd89c-138">다음 예제에서는 비매개 변수 없는 생성자 서명을 보여 주는 `x:Arguments` 다음 해당 서명에 액세스 하는 XAML 사용.</span><span class="sxs-lookup"><span data-stu-id="bd89c-138">The following example shows a non-parameterless constructor signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>

```csharp
public class Food {
  private string _name;
  private Int32 _calories;
  public Food(string name, Int32 calories) {
      _name=name;
      _calories=calories;
  }
}
```

```xaml
<my:Food>
  <x:Arguments>
      <x:String>Apple</x:String>
      <x:Int32>150</x:Int32>
  </x:Arguments>
</my:Food>
```

<span data-ttu-id="bd89c-139">다음 예제에서는 대상 팩터리 메서드 시그니처를 보여 `x:Arguments` 주는 다음 해당 서명의 XAML 사용 이 해당 서명에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="bd89c-139">The following example shows a target factory method signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>

```csharp
public Food TryLookupFood(string name)
{
switch (name) {
  case "Apple": return new Food("Apple",150);
  case "Chocolate": return new Food("Chocolate",200);
  case "Cheese": return new Food("Cheese", 450);
  default: {return new Food(name,0);
}
}
```

```xaml
<my:Food x:FactoryMethod="TryLookupFood">
  <x:Arguments>
      <x:String>Apple</x:String>
  </x:Arguments>
</my:Food>
```

## <a name="see-also"></a><span data-ttu-id="bd89c-140">참조</span><span class="sxs-lookup"><span data-stu-id="bd89c-140">See also</span></span>

- [<span data-ttu-id="bd89c-141">.NET XAML 서비스에서 사용할 사용자 지정 형식 정의</span><span class="sxs-lookup"><span data-stu-id="bd89c-141">Defining Custom Types for Use with .NET XAML Services</span></span>](define-custom-types.md)
- [<span data-ttu-id="bd89c-142">XAML 개요(WPF)</span><span class="sxs-lookup"><span data-stu-id="bd89c-142">XAML Overview (WPF)</span></span>](../fundamentals/xaml.md)
