---
title: x:FactoryMethod 지시문
ms.date: 03/30/2017
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
ms.openlocfilehash: 586965dd4094e81fd830a09b64604cf33f195630
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053785"
---
# <a name="xfactorymethod-directive"></a><span data-ttu-id="f7a0e-102">x:FactoryMethod 지시문</span><span class="sxs-lookup"><span data-stu-id="f7a0e-102">x:FactoryMethod Directive</span></span>
<span data-ttu-id="f7a0e-103">지원 형식을 확인 한 후 XAML 프로세서에서 개체를 초기화 하는 데 사용 해야 하는 생성자 이외의 메서드를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a0e-103">Specifies a method other than a constructor that a XAML processor should use to initialize an object after resolving its backing type.</span></span>  
  
## <a name="xaml-attribute-usage-no-xarguments"></a><span data-ttu-id="f7a0e-104">XAML 특성 사용, x:Arguments 안 함</span><span class="sxs-lookup"><span data-stu-id="f7a0e-104">XAML Attribute Usage, no x:Arguments</span></span>  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a><span data-ttu-id="f7a0e-105">XAML 특성 사용, x:Arguments as 요소</span><span class="sxs-lookup"><span data-stu-id="f7a0e-105">XAML Attribute Usage, x:Arguments as Element(s)</span></span>  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="f7a0e-106">XAML 값</span><span class="sxs-lookup"><span data-stu-id="f7a0e-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`methodname`|<span data-ttu-id="f7a0e-107">로 `object`지정 된 인스턴스를 초기화 하기 위해 XAML 프로세서에서 호출 하는 메서드의 문자열 메서드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f7a0e-107">The string method name of a method that XAML processors call to initialize the instance specified as `object`.</span></span> <span data-ttu-id="f7a0e-108">설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f7a0e-108">See Remarks.</span></span>|  
|`oneOrMoreObjectElements`|<span data-ttu-id="f7a0e-109">팩터리 메서드 매개 변수를 지정 하는 개체에 대 한 하나 이상의 개체 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f7a0e-109">One or more object elements for objects that specify factory method parameters.</span></span> <span data-ttu-id="f7a0e-110">순서가 중요 합니다. 인수가 팩터리 메서드에 전달 되어야 하는 순서를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f7a0e-110">Order is significant; it signifies the order in which arguments should be passed to the factory method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7a0e-111">설명</span><span class="sxs-lookup"><span data-stu-id="f7a0e-111">Remarks</span></span>  
 <span data-ttu-id="f7a0e-112">가 `methodname` 인스턴스 메서드인 경우 정규화 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f7a0e-112">If `methodname` is an instance method, it cannot be qualified.</span></span>  
  
 <span data-ttu-id="f7a0e-113">팩터리 메서드인 정적 메서드가 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7a0e-113">Static methods as factory methods are supported.</span></span> <span data-ttu-id="f7a0e-114">가 `methodname` 정적 `methodname` 메서드인 경우는 *typeName*으로 제공 됩니다. *methodName* 조합. 여기서 *typeName* 은 정적 팩터리 메서드를 정의 하는 클래스의 이름을로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a0e-114">If `methodname` is a static method, `methodname` is provided as a *typeName*.*methodName* combination, where *typeName* names the class that defines the static factory method.</span></span> <span data-ttu-id="f7a0e-115">*typeName* 은 매핑된 xmlns의 형식을 참조 하는 경우 접두사를 한정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7a0e-115">*typeName* can be prefix-qualified if referring to a type in a mapped xmlns.</span></span> <span data-ttu-id="f7a0e-116">*typeName* 은와 다른 형식일 `typeof(object)`수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7a0e-116">*typeName* can be a different type than `typeof(object)`.</span></span>  
  
 <span data-ttu-id="f7a0e-117">팩터리 메서드는 관련 개체 요소를 지 원하는 형식의 선언 된 공용 메서드 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a0e-117">The factory method must be a declared public method of the type that backs the relevant object element.</span></span>  
  
 <span data-ttu-id="f7a0e-118">팩터리 메서드는 관련 개체에 할당할 수 있는 인스턴스를 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a0e-118">The factory method must return an instance that is assignable to the relevant object.</span></span> <span data-ttu-id="f7a0e-119">팩터리 메서드는 null을 반환 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a0e-119">Factory methods should never return null.</span></span>  
  
 <span data-ttu-id="f7a0e-120">`x:Arguments`팩터리 메서드의 시그니처와 가장 일치 하는 원칙에 대해 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a0e-120">`x:Arguments` operates on a principle of best match for signatures of factory methods.</span></span> <span data-ttu-id="f7a0e-121">일치는 먼저 매개 변수 개수를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a0e-121">Matching evaluates the parameter count first.</span></span> <span data-ttu-id="f7a0e-122">매개 변수 개수에 대해 일치 하는 항목이 두 개 이상 있는 경우 매개 변수 형식이 평가 되 고 가장 일치 하는 항목이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7a0e-122">If there is more than one possible match for a parameter count, parameter type is then evaluated and best match is determined.</span></span> <span data-ttu-id="f7a0e-123">이 평가 단계 후에도 모호성이 여전히 발생 하면 XAML 프로세서 동작이 정의 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f7a0e-123">If there is still ambiguity after this phase of evaluation, XAML processor behavior is undefined.</span></span>  
  
 <span data-ttu-id="f7a0e-124">지시문 태그가 포함 하는 개체 요소의 형식을 참조 하지 않기 때문에 요소사용은일반적인의미에서속성요소사용이아닙니다.`x:FactoryMethod`</span><span class="sxs-lookup"><span data-stu-id="f7a0e-124">The `x:FactoryMethod` element usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="f7a0e-125">요소 사용이 특성 사용 보다 일반적이 지 않은 것으로 예상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7a0e-125">It is expected that element usage is less common than attribute usage.</span></span> <span data-ttu-id="f7a0e-126">`x:Arguments`(특성 또는 요소 사용)은 `x:FactoryMethod` 요소 사용량과 함께 사용할 수 있지만 사용 섹션에는 구체적으로 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f7a0e-126">`x:Arguments` (either attribute or element usage) can be used along with `x:FactoryMethod` element usage, but this is not specifically shown in the Usage sections.</span></span>  
  
 <span data-ttu-id="f7a0e-127">`x:FactoryMethod`요소는 다른 속성 요소 앞에와 야 하며, 요소로 제공 `x:Arguments` 되는 항목 앞에와 야 하며 모든 내용/내부 텍스트/초기화 텍스트 앞에와 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a0e-127">`x:FactoryMethod` as an element must precede any other property elements, must precede any `x:Arguments` also provided as elements, and must precede any content/inner text/initialization text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7a0e-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="f7a0e-128">See also</span></span>

- [<span data-ttu-id="f7a0e-129">x:Arguments 지시문</span><span class="sxs-lookup"><span data-stu-id="f7a0e-129">x:Arguments Directive</span></span>](x-arguments-directive.md)
