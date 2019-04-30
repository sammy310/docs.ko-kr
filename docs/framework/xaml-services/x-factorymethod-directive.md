---
title: x:FactoryMethod 지시문
ms.date: 03/30/2017
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
ms.openlocfilehash: 8fff4d62e07bdfd4ecc27d2692c391251afdd6d5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61971836"
---
# <a name="xfactorymethod-directive"></a>x:FactoryMethod 지시문
XAML 프로세서는 지원 형식 해결 한 후 개체를 초기화 하는 데 사용 해야 하는 생성자 이외의 메서드를 지정 합니다.  
  
## <a name="xaml-attribute-usage-no-xarguments"></a>X: 인수 없이 XAML 특성 사용  
  
```  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a>X:arguments 요소도 XAML 특성 사용  
  
```  
<object x:FactoryMethod="methodname"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|`methodname`|XAML 프로세서 호출로 지정 된 인스턴스를 초기화 하는 메서드의 문자열 메서드 이름을 `object`입니다. 설명 부분을 참조하세요.|  
|`oneOrMoreObjectElements`|팩터리 메서드 매개 변수를 지정 하는 개체에 대 한 하나 이상의 개체 요소입니다. 순서가 중요 하지 않습니다. 팩터리 메서드에 인수를 전달 하는 순서를 의미 합니다.|  
  
## <a name="remarks"></a>설명  
 경우 `methodname` 인스턴스 메서드는 정규화 할 수 없습니다.  
  
 팩터리 메서드를 사용 하 여 정적 메서드 지원 됩니다. 하는 경우 `methodname` 는 정적 메서드입니다 `methodname` 으로 제공 되는 *typeName*. *methodName* 조합, 여기서 *typeName* 정적 팩터리 메서드를 정의 하는 클래스의 이름을 지정 합니다. *typeName* 맵핑된 xmlns에서 형식을 참조 하는 경우 접두사 정규화 될 수 있습니다. *typeName* 보다 다양 한 형식일 수 있습니다 `typeof(object)`합니다.  
  
 팩터리 메서드는 관련 개체 요소를 지 원하는 형식의 선언된 된 공용 메서드가 이어야 합니다.  
  
 팩터리 메서드는 관련 개체에 할당 될 수 있는 인스턴스를 반환 해야 합니다. 팩터리 메서드가 null을 반환 해야 합니다.  
  
 `x:Arguments` 팩터리 메서드 서명에 대 한 가장 일치 하는 원칙에서 작동합니다. 일치 하는 매개 변수 개수를 먼저 평가합니다. 매개 변수 개수에 대 한 둘 이상의 가능한 일치 하는 경우 평가 되 고 가장 일치 하는 다음 매개 변수 유형이입니다. 이 평가 단계 후 모호성 지속 되 면 XAML 프로세서 동작은 정의 되지 않습니다.  
  
 `x:FactoryMethod` 요소 사용 아니므로 일반적으로, 속성 요소 사용 지시문 태그가 포함 된 개체 요소 형식을 참조 하지 않습니다. 예상 하지만 요소는 특성 사용 보다 일반적이 지 않습니다. `x:Arguments` (특성 또는 요소 사용)와 함께 사용할 수 있습니다 `x:FactoryMethod` 요소를 사용 하지만이 표시 되지 않으면 특별히 사용 섹션입니다.  
  
 `x:FactoryMethod` 요소는 다른 모든 속성 요소의 앞에 야, 대로 나와야 모든 `x:Arguments` 도 요소로 제공 되며 모든 콘텐츠/내부 텍스트/초기화 텍스트 앞에 야 합니다.  
  
## <a name="see-also"></a>참고자료

- [x:Arguments 지시문](x-arguments-directive.md)
