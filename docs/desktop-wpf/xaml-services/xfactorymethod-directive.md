---
title: x:FactoryMethod 지시문
ms.date: 03/30/2017
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
ms.openlocfilehash: 5e864b6f5d664b079036a5d915e2f6f81b83639f
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432787"
---
# <a name="xfactorymethod-directive"></a><span data-ttu-id="adc8a-102">x:FactoryMethod 지시문</span><span class="sxs-lookup"><span data-stu-id="adc8a-102">x:FactoryMethod Directive</span></span>
<span data-ttu-id="adc8a-103">XAML 프로세서가 백업 형식을 해결한 후 개체를 초기화하는 데 사용해야 하는 생성자 이외의 메서드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="adc8a-103">Specifies a method other than a constructor that a XAML processor should use to initialize an object after resolving its backing type.</span></span>  
  
## <a name="xaml-attribute-usage-no-xarguments"></a><span data-ttu-id="adc8a-104">XAML 특성 사용, x:인수 없음</span><span class="sxs-lookup"><span data-stu-id="adc8a-104">XAML Attribute Usage, no x:Arguments</span></span>  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a><span data-ttu-id="adc8a-105">XAML 특성 사용, x:인수요소로서의 사용</span><span class="sxs-lookup"><span data-stu-id="adc8a-105">XAML Attribute Usage, x:Arguments as Element(s)</span></span>  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="adc8a-106">XAML 값</span><span class="sxs-lookup"><span data-stu-id="adc8a-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`methodname`|<span data-ttu-id="adc8a-107">XAML 프로세서가 호출하여 로 `object`지정된 인스턴스를 초기화하는 메서드의 문자열 메서드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="adc8a-107">The string method name of a method that XAML processors call to initialize the instance specified as `object`.</span></span> <span data-ttu-id="adc8a-108">설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="adc8a-108">See Remarks.</span></span>|  
|`oneOrMoreObjectElements`|<span data-ttu-id="adc8a-109">팩터리 메서드 매개 변수를 지정하는 개체에 대한 하나 이상의 개체 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="adc8a-109">One or more object elements for objects that specify factory method parameters.</span></span> <span data-ttu-id="adc8a-110">순서는 중요합니다. 인수를 팩터리 메서드에 전달 해야 하는 순서를 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc8a-110">Order is significant; it signifies the order in which arguments should be passed to the factory method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="adc8a-111">설명</span><span class="sxs-lookup"><span data-stu-id="adc8a-111">Remarks</span></span>  
 <span data-ttu-id="adc8a-112">인스턴스 `methodname` 메서드인 경우 한정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="adc8a-112">If `methodname` is an instance method, it cannot be qualified.</span></span>  
  
 <span data-ttu-id="adc8a-113">팩터리 메서드와 같은 정적 메서드가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="adc8a-113">Static methods as factory methods are supported.</span></span> <span data-ttu-id="adc8a-114">정적 `methodname` 메서드인 경우 `methodname` 정적 팩터리 메서드를 `typeName.methodName` 정의하는 클래스의 `typeName` 이름을 지정하는 조합으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="adc8a-114">If `methodname` is a static method, `methodname` is provided as a `typeName.methodName` combination, where `typeName` names the class that defines the static factory method.</span></span> <span data-ttu-id="adc8a-115">`typeName`매핑된 xmlns의 형식을 참조하는 경우 접두사 한정을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adc8a-115">`typeName` can be prefix-qualified if referring to a type in a mapped xmlns.</span></span> <span data-ttu-id="adc8a-116">`typeName``typeof(object)`와 다른 유형일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adc8a-116">`typeName` can be a different type than `typeof(object)`.</span></span>  
  
 <span data-ttu-id="adc8a-117">팩터리 메서드는 관련 개체 요소를 백업하는 형식의 선언된 공용 메서드여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc8a-117">The factory method must be a declared public method of the type that backs the relevant object element.</span></span>  
  
 <span data-ttu-id="adc8a-118">팩터리 메서드는 관련 개체에 할당할 수 있는 인스턴스를 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc8a-118">The factory method must return an instance that is assignable to the relevant object.</span></span> <span data-ttu-id="adc8a-119">팩터리 메서드는 null을 반환해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="adc8a-119">Factory methods should never return null.</span></span>  
  
 <span data-ttu-id="adc8a-120">`x:Arguments`공장 방법의 서명에 가장 적합한 원칙에 따라 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="adc8a-120">`x:Arguments` operates on a principle of best match for signatures of factory methods.</span></span> <span data-ttu-id="adc8a-121">일치는 매개 변수 수를 먼저 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="adc8a-121">Matching evaluates the parameter count first.</span></span> <span data-ttu-id="adc8a-122">매개 변수 수에 대해 가능한 일치가 두 개 이상 있는 경우 매개 변수 형식이 평가되고 일치하는 일치가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="adc8a-122">If there is more than one possible match for a parameter count, parameter type is then evaluated and best match is determined.</span></span> <span data-ttu-id="adc8a-123">이 평가 단계 후에도 여전히 모호성이 있으면 XAML 프로세서 동작이 정의되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="adc8a-123">If there is still ambiguity after this phase of evaluation, XAML processor behavior is undefined.</span></span>  
  
 <span data-ttu-id="adc8a-124">지시문 태그가 `x:FactoryMethod` 포함된 개체 요소의 형식을 참조하지 않으므로 요소 사용은 일반적인 의미에서 속성 요소 사용이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="adc8a-124">The `x:FactoryMethod` element usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="adc8a-125">요소 사용이 특성 사용보다 덜 일반적일 것으로 예상됩니다.</span><span class="sxs-lookup"><span data-stu-id="adc8a-125">It is expected that element usage is less common than attribute usage.</span></span> <span data-ttu-id="adc8a-126">`x:Arguments`요소 사용과 `x:FactoryMethod` 함께 사용할 수 있지만(특성 또는 요소 사용) 사용 섹션에는 구체적으로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="adc8a-126">`x:Arguments` (either attribute or element usage) can be used along with `x:FactoryMethod` element usage, but this is not specifically shown in the Usage sections.</span></span>  
  
 <span data-ttu-id="adc8a-127">`x:FactoryMethod`요소는 다른 속성 요소 앞에 있어야 하며 요소로 제공된 요소 `x:Arguments` 앞에 와야 하며 콘텐츠/내부 텍스트/초기화 텍스트 앞에 와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc8a-127">`x:FactoryMethod` as an element must precede any other property elements, must precede any `x:Arguments` also provided as elements, and must precede any content/inner text/initialization text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adc8a-128">참조</span><span class="sxs-lookup"><span data-stu-id="adc8a-128">See also</span></span>

- [<span data-ttu-id="adc8a-129">x:Arguments 지시문</span><span class="sxs-lookup"><span data-stu-id="adc8a-129">x:Arguments Directive</span></span>](xarguments-directive.md)
