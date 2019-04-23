---
title: x:Subclass 지시문
ms.date: 03/30/2017
f1_keywords:
- Subclass
- xSubclass
- x:Subclass
helpviewer_keywords:
- x:Subclass attribute [XAML Services]
- XAML [XAML Services], x:Subclass attribute
- Subclass attribute in XAML [XAML Services]
ms.assetid: 99f66072-8107-4362-ab99-8171dc83b469
ms.openlocfilehash: 850fe8acf9e47149bd385e78b30e04ba77d7a8b2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59140792"
---
# <a name="xsubclass-directive"></a>x:Subclass 지시문
XAML 태그 컴파일 동작을 수정 하는 경우 `x:Class` 도 제공 됩니다. 기반이 되는 partial 클래스를 만드는 대신 `x:Class`에 제공 된 `x:Class` 중간 클래스로 만들어집니다 다음 제공 된 파생된 클래스는 기반으로 해야 하 고 `x:Class`입니다.  
  
## <a name="xaml-attribute-usage"></a>XAML 특성 사용  
  
```  
<object x:Class="namespace.classname" x:Subclass="subclassNamespace.subclassName">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|`namespace`|선택 사항입니다. 포함 된 CLR 네임 스페이스를 지정 `classname`합니다. 하는 경우 `namespace` 지정 된 경우 점 (.) `namespace` 고 `classname`입니다.|  
|`classname`|필수 요소. 로드 된 XAML 및 코드 숨김에는 XAML에 대 한 연결 하는 partial 클래스의 CLR 이름을 지정 합니다. 설명 부분을 참조하세요.|  
|`subclassNamespace`|선택 사항입니다. 다를 수 있습니다 `namespace` 각 네임 스페이스는 다른 확인할 수 있는 경우. 포함 된 CLR 네임 스페이스를 지정 `subclassName`합니다. 하는 경우 `subclassName` 지정 된 경우 점 (.) `subclassNamespace` 고 `subclassName`입니다.|  
|`subclassName`|필수 요소. 서브 클래스의 CLR 이름을 지정합니다.|  
  
## <a name="dependencies"></a>종속성  
 [X:class 지시문](x-class-directive.md) 동일한 개체에도 제공 해야 하며 해당 개체에는 XAML 프로덕션의 루트 요소 이어야 합니다.  
  
## <a name="remarks"></a>설명  
 `x:Subclass` 사용량은 주로 partial 클래스 선언을 지원 하지 않는 언어에 대 한 것입니다.  
  
 로 사용 되는 클래스를 `x:Subclass` 중첩된 클래스일 수 없습니다. 및 `x:Subclass` "Dependencies" 섹션에 설명 된 대로 루트 개체를 참조 해야 합니다.  
  
 그렇지 않으면의 의미를 개념적 `x:Subclass` .NET Framework XAML 서비스 구현에서 정의 되어 있지 않습니다. 즉,.NET Framework XAML 서비스 동작에는 XAML에서 태그 및 코드를 지 원하는 연결 된 전체 프로그래밍 모델을 지정 하지 않습니다. 관련 된 추가 개념 구현 `x:Class` 고 `x:Subclass` 프로그래밍 모델이 나 응용 프로그램 모델을 사용 하 여 XAML 태그, 컴파일된 태그 및 코드 숨김 CLR 기반 연결 하는 방법을 정의 하는 특정 프레임 워크에 의해 수행 됩니다. 각 프레임 워크 동작 또는 빌드 환경에 포함 되어야 하는 특정 구성 요소 중 일부를 사용 하도록 설정 하는 자체 빌드 작업이 있을 수 있습니다. 프레임 워크 내에서 빌드 작업은 코드 숨김에 사용 되는 특정 CLR 언어에 따라 달라질 수도 수 있습니다.  
  
## <a name="wpf-usage-notes"></a>WPF 사용 정보  
 `x:Subclass` 페이지 루트 또는 수를 <xref:System.Windows.Application> 이미 있는 응용 프로그램 정의 루트 `x:Class`입니다. 선언 `x:Subclass` 페이지나 응용 프로그램 루트를 또는 없는 위치에서 지정 이외의 모든 요소에 대해 `x:Class` 존재 하 고 컴파일 시간 오류가 발생 합니다.  
  
 파생 클래스를 만드는 올바르게 동작 하는 `x:Subclass` 시나리오는 상당히 복잡 합니다. 중간 파일 (.xaml 파일 이름을 통합 하는 이름의 태그 컴파일에서 프로젝트의 obj 폴더에 생성 된.g 파일)을 검사 해야 합니다. 이러한 중간 파일 컴파일된 응용 프로그램의 결합된 된 partial 클래스에서 특정 프로그래밍 구문의 출처를 확인할 수 있습니다.  
  
 파생된 클래스에서 이벤트 처리기 여야 `internal override` (`Friend Overrides` Microsoft Visual Basic) 컴파일 중에 중간 클래스에서 생성 하는 대로 처리기에 대 한 스텁을 재정의 하려면. 그렇지 않으면 파생된 클래스 구현 (그림자) 중간 클래스 구현을 숨기고 중간 클래스 처리기가 호출 되지 않습니다.  
  
 모두 정의 하는 경우 `x:Class` 하 고 `x:Subclass`를 참조 하는 클래스에 대 한 모든 구현을 제공할 필요가 없습니다 `x:Class`. 통해 이름을 지정 해야 하는 `x:Class` 특성 컴파일러에 중간 파일 (이 컴파일러는 기본 이름이 선택 하지)에 생성 되는 클래스에 대 한 몇 가지 지침입니다. 그러나 제공할 수 있습니다 합니다 `x:Class` 클래스는 구현에 아닙니다 모두 사용 하 여 일반적인 시나리오 `x:Class` 및 `x:Subclass`합니다.  
  
## <a name="see-also"></a>참고자료

- [x:Class 지시문](x-class-directive.md)
- [WPF에 대한 XAML 및 사용자 지정 클래스](../wpf/advanced/xaml-and-custom-classes-for-wpf.md)
