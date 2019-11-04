---
title: x:Arguments 지시문
ms.date: 03/30/2017
helpviewer_keywords:
- x:Arguments directive [XAML Services]
- Arguments directive in XAML [XAML Services]
- XAML [XAML Services], x:Arguments directive
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
ms.openlocfilehash: 338286b417c78b7cceeb30188e888928a15607cd
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458659"
---
# <a name="xarguments-directive"></a><span data-ttu-id="75eaa-102">x:Arguments 지시문</span><span class="sxs-lookup"><span data-stu-id="75eaa-102">x:Arguments Directive</span></span>
<span data-ttu-id="75eaa-103">XAML에서 매개 변수가 없는 생성자 개체 요소 선언 또는 팩터리 메서드 개체 선언의 패키지 생성 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="75eaa-103">Packages construction arguments for a non-parameterless constructor object element declaration in XAML, or for a factory method object declaration.</span></span>  
  
## <a name="xaml-element-usage-nonparameterless-constructor"></a><span data-ttu-id="75eaa-104">XAML 요소 사용 (매개 변수가 없는 생성자)</span><span class="sxs-lookup"><span data-stu-id="75eaa-104">XAML Element Usage (Nonparameterless constructor)</span></span>  
  
```xaml  
<object ...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-element-usage-factory-method"></a><span data-ttu-id="75eaa-105">XAML 요소 사용 (팩터리 메서드)</span><span class="sxs-lookup"><span data-stu-id="75eaa-105">XAML Element Usage (factory method)</span></span>  
  
```xaml  
<object x:FactoryMethod="methodName"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="75eaa-106">XAML 값</span><span class="sxs-lookup"><span data-stu-id="75eaa-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`oneOrMoreObjectElements`|<span data-ttu-id="75eaa-107">매개 변수가 없는 지원 생성자 또는 팩터리 메서드에 전달할 인수를 지정 하는 하나 이상의 개체 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="75eaa-107">One or more object elements that specify arguments to be passed to the backing non-parameterless constructor or factory method.</span></span><br /><br /> <span data-ttu-id="75eaa-108">일반적인 사용법은 개체 요소 내에서 초기화 텍스트를 사용 하 여 실제 인수 값을 지정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="75eaa-108">Typical usage is to use initialization text within the object elements to specify the actual argument values.</span></span> <span data-ttu-id="75eaa-109">예제 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="75eaa-109">See Examples section.</span></span><br /><br /> <span data-ttu-id="75eaa-110">요소의 순서는 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="75eaa-110">The order of the elements is significant.</span></span> <span data-ttu-id="75eaa-111">순서 대로 XAML 형식은 지원 생성자 또는 팩터리 메서드 오버 로드의 형식 및 형식 순서와 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75eaa-111">The XAML types in order must match the types and type order of the backing constructor or factory method overload.</span></span>|  
|`methodName`|<span data-ttu-id="75eaa-112">`x:Arguments` 인수를 처리 해야 하는 팩터리 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="75eaa-112">The name of the factory method that should process any `x:Arguments` arguments.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="75eaa-113">종속성</span><span class="sxs-lookup"><span data-stu-id="75eaa-113">Dependencies</span></span>  
 <span data-ttu-id="75eaa-114">`x:FactoryMethod`은 `x:Arguments` 적용 되는 범위 및 동작을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75eaa-114">`x:FactoryMethod` can modify the scope and behavior where `x:Arguments` applies.</span></span>  
  
 <span data-ttu-id="75eaa-115">`x:FactoryMethod` 지정 하지 않으면 지원 생성자의 대체 (기본값이 아닌) 서명에 `x:Arguments` 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75eaa-115">If no `x:FactoryMethod` is specified, `x:Arguments` applies to alternate (non-default) signatures of the backing constructors.</span></span>  
  
 <span data-ttu-id="75eaa-116">`x:FactoryMethod` 지정 된 경우 `x:Arguments`은 명명 된 메서드의 오버 로드에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75eaa-116">If `x:FactoryMethod` is specified, `x:Arguments` applies to an overload of the named method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75eaa-117">주의</span><span class="sxs-lookup"><span data-stu-id="75eaa-117">Remarks</span></span>  
 <span data-ttu-id="75eaa-118">XAML 2006은 초기화 텍스트를 통해 기본값이 아닌 초기화를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75eaa-118">XAML 2006 can support non-default initialization through initialization text.</span></span> <span data-ttu-id="75eaa-119">그러나 초기화 텍스트 생성 기술의 실용적인 응용 프로그램은 제한적입니다.</span><span class="sxs-lookup"><span data-stu-id="75eaa-119">However, the practical application of an initialization text construction technique is limited.</span></span> <span data-ttu-id="75eaa-120">초기화 텍스트는 단일 텍스트 문자열로 처리 됩니다. 따라서 사용자 지정 정보 항목 및 사용자 지정 구분 기호를 문자열에서 구문 분석할 수 있는 생성 동작에 대해 형식 변환기가 정의 되어 있지 않으면 단일 매개 변수 초기화에 대 한 기능만 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="75eaa-120">Initialization text is treated as a single text string; therefore, it only adds capability for a single parameter initialization unless a type converter is defined for the construction behavior that can parse custom information items and custom delimiters from the string.</span></span> <span data-ttu-id="75eaa-121">또한 개체 논리에 대 한 텍스트 문자열은 실제 문자열 이외의 기본 형식을 처리 하기 위해 지정 된 XAML 파서의 네이티브 기본 형식 변환기가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75eaa-121">Also, the text string to object logic is potentially a given XAML parser's native default type converter for handling primitives other than a true string.</span></span>  
  
 <span data-ttu-id="75eaa-122">지시문 태그가 포함 하는 개체 요소의 형식을 참조 하지 않기 때문에 `x:Arguments` XAML 사용은 일반적인 의미의 속성 요소 사용이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="75eaa-122">The `x:Arguments` XAML usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="75eaa-123">요소에서 태그를 자식 내용에 대 한 기본값 이외의 것으로 해석 해야 하는 범위를 표시 하지 않는 `x:Code`와 같은 다른 지시문과 더 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="75eaa-123">It is more akin to other directives such as `x:Code` where the element demarks a range in which the markup should be interpreted as other than the default for child contents.</span></span> <span data-ttu-id="75eaa-124">이 경우 각 개체 요소의 XAML 형식은 인수 형식에 대 한 정보를 전달 하며,이는 XAML 파서에서 `x:Arguments` 사용이 참조 하는 특정 생성자 팩터리 메서드 시그니처를 결정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75eaa-124">In this case, the XAML type of each object element communicates information about the argument types, which is used by XAML parsers to determine which specific constructor factory method signature an `x:Arguments` usage is attempting to reference.</span></span>  
  
 <span data-ttu-id="75eaa-125">생성 되는 개체 요소에 대 한 `x:Arguments`는 개체 요소의 다른 모든 속성 요소, 내용, 내부 텍스트 또는 초기화 문자열 앞에와 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75eaa-125">`x:Arguments` for an object element being constructed must precede any other property elements, content, inner text, or initialization strings of the object element.</span></span> <span data-ttu-id="75eaa-126">`x:Arguments` 내의 개체 요소에는 해당 XAML 형식과 지원 생성자 또는 팩터리 메서드에서 허용 하는 특성과 초기화 문자열이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75eaa-126">The object elements within `x:Arguments` can include attributes and initialization strings, as permitted by that XAML type and its backing constructor or factory method.</span></span> <span data-ttu-id="75eaa-127">개체 또는 인수 중 하나에 대해 설정 된 접두사 매핑을 참조 하 여 기본 XAML 네임 스페이스의 외부에 있는 사용자 지정 XAML 형식 또는 XAML 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75eaa-127">For either the object or the arguments, you can specify custom XAML types or XAML types that are otherwise outside the default XAML namespace by referencing established prefix mappings.</span></span>  
  
 <span data-ttu-id="75eaa-128">XAML 프로세서는 다음 지침을 사용 하 여 `x:Arguments`에 지정 된 인수를 사용 하 여 개체를 생성 하는 방법을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="75eaa-128">XAML processors use the following guidelines to determine how the arguments specified in `x:Arguments` should be used to construct an object.</span></span> <span data-ttu-id="75eaa-129">`x:FactoryMethod` 지정 된 경우 정보는 지정 된 `x:FactoryMethod`와 비교 됩니다. `x:FactoryMethod` 값은 메서드 이름이 고 명명 된 메서드에는 오버 로드가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75eaa-129">If `x:FactoryMethod` is specified, information is compared to the specified `x:FactoryMethod` (note that the value of `x:FactoryMethod` is the method name, and the named method can have overloads.</span></span> <span data-ttu-id="75eaa-130">`x:FactoryMethod` 지정 하지 않으면 정보를 개체의 모든 공용 생성자 오버 로드 집합과 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="75eaa-130">If `x:FactoryMethod` is not specified, information is compared to the set of all public constructor overloads of the object.</span></span> <span data-ttu-id="75eaa-131">그런 다음 XAML 처리 논리는 매개 변수 수를 비교 하 고 인자 수가 일치 하는 오버 로드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75eaa-131">XAML processing logic then compares the number of parameters and selects the overload with matching arity.</span></span> <span data-ttu-id="75eaa-132">일치 하는 항목이 두 개 이상 있는 경우 XAML 프로세서는 제공 된 개체 요소의 XAML 형식에 따라 매개 변수의 형식을 비교 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75eaa-132">If there is more than one match, the XAML processor should compare the types of the parameters based on the XAML types of the provided object elements.</span></span> <span data-ttu-id="75eaa-133">일치 하는 항목이 두 개 이상 있으면 XAML 프로세서 동작이 정의 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75eaa-133">If there is still more than one match, the XAML processor behavior is undefined.</span></span> <span data-ttu-id="75eaa-134">`x:FactoryMethod` 지정 되었지만 메서드를 확인할 수 없는 경우 XAML 프로세서에서 예외를 throw 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75eaa-134">If a `x:FactoryMethod` is specified but the method cannot be resolved, a XAML processor should throw an exception.</span></span>  
  
 <span data-ttu-id="75eaa-135">XAML 특성 사용 `<x:Arguments>string</x:Arguments>`는 기술적으로 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="75eaa-135">A XAML attribute usage `<x:Arguments>string</x:Arguments>` is technically possible.</span></span> <span data-ttu-id="75eaa-136">그러나이 경우 초기화 텍스트와 형식 변환기를 통해 수행할 수 있는 작업 외에 다른 기능을 제공 하지 않으며,이 구문을 사용 하는 것은 XAML 2009 팩터리 메서드 기능의 디자인 의도가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="75eaa-136">However, this provides no capabilities beyond what could be done otherwise through initialization text and type converters, and using this syntax is not the design intention of the XAML 2009 factory method features.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="75eaa-137">예제</span><span class="sxs-lookup"><span data-stu-id="75eaa-137">Examples</span></span>  
 <span data-ttu-id="75eaa-138">다음 예제에서는 매개 변수가 없는 생성자 시그니처와 해당 서명에 액세스 하는 `x:Arguments`의 XAML 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="75eaa-138">The following example shows a non-parameterless constructor signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>  
  
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
  
 <span data-ttu-id="75eaa-139">다음 예제에서는 대상 팩터리 메서드 시그니처와 해당 서명에 액세스 하는 `x:Arguments`의 XAML 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="75eaa-139">The following example shows a target factory method signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="75eaa-140">참조</span><span class="sxs-lookup"><span data-stu-id="75eaa-140">See also</span></span>

- [<span data-ttu-id="75eaa-141">.NET Framework XAML 서비스에서 사용할 사용자 지정 형식 정의</span><span class="sxs-lookup"><span data-stu-id="75eaa-141">Defining Custom Types for Use with .NET Framework XAML Services</span></span>](defining-custom-types-for-use-with-net-framework-xaml-services.md)
- [<span data-ttu-id="75eaa-142">XAML 개요(WPF)</span><span class="sxs-lookup"><span data-stu-id="75eaa-142">XAML Overview (WPF)</span></span>](../../desktop-wpf/fundamentals/xaml.md)
