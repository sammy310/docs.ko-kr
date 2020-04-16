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
# <a name="xfactorymethod-directive"></a>x:FactoryMethod 지시문
XAML 프로세서가 백업 형식을 해결한 후 개체를 초기화하는 데 사용해야 하는 생성자 이외의 메서드를 지정합니다.  
  
## <a name="xaml-attribute-usage-no-xarguments"></a>XAML 특성 사용, x:인수 없음  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a>XAML 특성 사용, x:인수요소로서의 사용  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|`methodname`|XAML 프로세서가 호출하여 로 `object`지정된 인스턴스를 초기화하는 메서드의 문자열 메서드 이름입니다. 설명 부분을 참조하세요.|  
|`oneOrMoreObjectElements`|팩터리 메서드 매개 변수를 지정하는 개체에 대한 하나 이상의 개체 요소입니다. 순서는 중요합니다. 인수를 팩터리 메서드에 전달 해야 하는 순서를 의미 합니다.|  
  
## <a name="remarks"></a>설명  
 인스턴스 `methodname` 메서드인 경우 한정할 수 없습니다.  
  
 팩터리 메서드와 같은 정적 메서드가 지원됩니다. 정적 `methodname` 메서드인 경우 `methodname` 정적 팩터리 메서드를 `typeName.methodName` 정의하는 클래스의 `typeName` 이름을 지정하는 조합으로 제공됩니다. `typeName`매핑된 xmlns의 형식을 참조하는 경우 접두사 한정을 받을 수 있습니다. `typeName``typeof(object)`와 다른 유형일 수 있습니다.  
  
 팩터리 메서드는 관련 개체 요소를 백업하는 형식의 선언된 공용 메서드여야 합니다.  
  
 팩터리 메서드는 관련 개체에 할당할 수 있는 인스턴스를 반환해야 합니다. 팩터리 메서드는 null을 반환해서는 안 됩니다.  
  
 `x:Arguments`공장 방법의 서명에 가장 적합한 원칙에 따라 작동합니다. 일치는 매개 변수 수를 먼저 평가합니다. 매개 변수 수에 대해 가능한 일치가 두 개 이상 있는 경우 매개 변수 형식이 평가되고 일치하는 일치가 결정됩니다. 이 평가 단계 후에도 여전히 모호성이 있으면 XAML 프로세서 동작이 정의되지 않습니다.  
  
 지시문 태그가 `x:FactoryMethod` 포함된 개체 요소의 형식을 참조하지 않으므로 요소 사용은 일반적인 의미에서 속성 요소 사용이 아닙니다. 요소 사용이 특성 사용보다 덜 일반적일 것으로 예상됩니다. `x:Arguments`요소 사용과 `x:FactoryMethod` 함께 사용할 수 있지만(특성 또는 요소 사용) 사용 섹션에는 구체적으로 표시되지 않습니다.  
  
 `x:FactoryMethod`요소는 다른 속성 요소 앞에 있어야 하며 요소로 제공된 요소 `x:Arguments` 앞에 와야 하며 콘텐츠/내부 텍스트/초기화 텍스트 앞에 와야 합니다.  
  
## <a name="see-also"></a>참조

- [x:Arguments 지시문](xarguments-directive.md)
