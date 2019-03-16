---
title: x:Class 지시문
ms.date: 03/30/2017
f1_keywords:
- x:Class
- xClass
- Class
helpviewer_keywords:
- Class attribute in XAML [XAML Services]
- XAML [XAML Services], x:Class attribute
- x:Class attribute [XAML Services]
ms.assetid: bc4a3d8e-76e2-423e-a5d1-159a023e82ec
ms.openlocfilehash: 8acc1ac099a71fbf624049b119ebe908f27cbb55
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2019
ms.locfileid: "58031227"
---
# <a name="xclass-directive"></a>x:Class 지시문
태그와 코드 숨김 부분 클래스를 조인 하는 XAML 태그 컴파일을 구성 합니다. 코드 partial 클래스는 별도 코드 파일에 정의 된를 [!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)] 언어 반면 태그 partial 클래스는 대개 XAML 컴파일하는 동안 코드 생성에서 만들어집니다.  
  
## <a name="xaml-attribute-usage"></a>XAML 특성 사용  
  
```  
<object x:Class="namespace.classname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|`namespace`|선택 사항입니다. 지정 된 [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)] 로 식별 되는 partial 클래스를 포함 하는 네임 스페이스 `classname`합니다. 하는 경우 `namespace` 지정 된 경우 점 (.) `namespace` 고 `classname`입니다. 설명 부분을 참조하세요.|  
|`classname`|필수 요소. 지정 된 [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)] 로드 된 XAML 및 코드 숨김에는 XAML에 대 한 연결 하는 partial 클래스의 이름입니다.|  
  
## <a name="dependencies"></a>종속성  
 `x:Class` XAML 프로덕션의 루트 요소에만 지정할 수 있습니다. `x:Class` 부모 XAML 프로덕션에 있는 모든 개체에 올바르지 않습니다. 자세한 내용은 [ \[MS XAML\] 4.3.1.6 섹션](https://go.microsoft.com/fwlink/?LinkId=114525)합니다.  
  
## <a name="remarks"></a>설명  
 `namespace` 값에는.NET Framework 프로그래밍에서 일반적인 기술 관련된 네임 스페이스 이름 계층으로 구성 하는 추가 점이 포함 될 수 있습니다. 문자열의 마지막 점만 `x:Class` 구분 값 해석 됩니다 `namespace` 하 고 `classname.` 으로 사용 되는 클래스 `x:Class` 중첩 클래스일 수 없습니다. 중첩된 클래스에 대 한 점의 의미를 확인 하기 때문에 허용 되지 않습니다 `x:Class` 중첩된 클래스는 허용 하는 경우 문자열 모호 합니다.  
  
 프로그래밍 모델을 사용 하는 기존 `x:Class`, `x:Class` 사용할 수 있는 코드 숨김 없이 XAML 페이지는 점에서 선택 사항입니다. 그러나 해당 기능은 XAML을 사용 하는 프레임 워크에 의해 구현 될 때 빌드 작업을 사용 하 여 상호 작용 합니다. `x:Class` 또한 기능을 응용 프로그램 모델에 지정 된 XAML 콘텐츠의 다양 한 분류 들어 있고 해당 빌드 작업 역할에 의해 받습니다. 제공 해야 하는 이벤트 처리 특성 값 또는 인스턴스화하는 코드 숨김 클래스에서 정의 하는 클래스가 있는 사용자 지정 요소에 XAML 선언 하는 경우는 `x:Class` 지시문 참조 (또는 [X:subclass](x-subclass-directive.md))에 코드 숨김에 대 한 적절 한 클래스입니다.  
  
 값을 `x:Class` 지시문은 어셈블리 정보가 없는 하지만 클래스의 정규화 된 이름을 지정 하는 문자열 이어야 합니다. (해당 하는 <xref:System.Type.FullName%2A?displayProperty=nameWithType>). 간단한 응용 프로그램에 대 한 코드 숨김 (클래스 수준에서 코드 정의 시작)을 이러한 방식으로 구성 된 경우 CLR 네임 스페이스 정보를 생략할 수 있습니다.  
  
 페이지나 응용 프로그램 정의 대 한 코드 숨김 파일을 컴파일된 응용 프로그램을 생성 하 고 태그 컴파일을 포함 된 프로젝트의 일부로 포함 된 코드 파일 내에 있어야 합니다. CLR 클래스에 대 한 이름 규칙을 따라야 합니다. 자세한 내용은 [프레임 워크 디자인 지침](../../standard/design-guidelines/index.md)합니다. 기본적으로 코드 숨김 클래스 여야 합니다 `public`하지만 서로 다른 액세스 수준에서 사용 하 여 정의할 수 있습니다 합니다 [X:classmodifier 지시문](x-classmodifier-directive.md)합니다.  
  
 이의 해석은 `x:Class` 특성에만 적용 됩니다는 CLR 기반 XAML 구현을 특히.NET Framework XAML 서비스입니다. 다른 XAML 구현에 CLR에 기반 하지 않는 및.NET Framework XAML 서비스를 사용 하지 않는 XAML 태그를 연결 하 고 런타임에 코드를 지 원하는 다른 해상도 수식을 사용할 수 있습니다. 보다 일반적인 해석 하는 방법에 대 한 자세한 내용은 `x:Class`를 참조 하세요 [ \[MS XAML\]](https://go.microsoft.com/fwlink/?LinkId=114525)합니다.  
  
 의미는 아키텍처의 특정 수준 `x:Class` .NET Framework XAML 서비스에 정의 되어 있지 않습니다. 즉,.NET Framework XAML 서비스는 XAML에서 태그 및 코드를 지 원하는 연결 된 프로그래밍 모델을 지정 하지 않습니다. 추가 사용을 `x:Class` 지시문 프로그래밍 모델이 나 응용 프로그램 모델을 사용 하 여 CLR 기반 코드 숨김 및 XAML 태그를 연결 하는 방법을 정의 하는 특정 프레임 워크에서 구현할 수 있습니다. 각 프레임 워크 동작 또는 빌드 환경에 포함 되어야 하는 특정 구성 요소 중 일부를 사용 하도록 설정 하는 자체 빌드 작업이 있습니다. 프레임 워크 내에서 빌드 작업도 코드 숨김에 사용 되는 특정 CLR 언어에 따라 달라질 수 있습니다.  
  
## <a name="xclass-in-the-wpf-programming-model"></a>X:class WPF 프로그래밍 모델  
 WPF 응용 프로그램 및 WPF 응용 프로그램 모델 `x:Class` 는 XAML 파일의 루트 이며 컴파일되는 모든 요소에 대 한 특성으로 선언할 수 있습니다 (사용 하 여 WPF 응용 프로그램 프로젝트에서는 XAML 포함 되어 있는 `Page` 빌드 작업), 또는 < c4 > <xref:System.Windows.Application>  컴파일된 WPF 응용 프로그램의 응용 프로그램 정의의 루트입니다. 선언 `x:Class` 루트 페이지 또는 응용 프로그램 루트 이외의 요소 또는 WPF XAML 파일을 컴파일되지 않은에서 컴파일 타임 오류가 발생 합니다 [!INCLUDE[net_v30_short](../../../includes/net-v30-short-md.md)] 고 [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] WPF XAML 컴파일러. 다른 측면에 대 한 자세한 `x:Class` WPF의 처리를 참조 하세요 [코드 숨김 및 WPF에서 XAML](../wpf/advanced/code-behind-and-xaml-in-wpf.md)합니다.  
  
## <a name="xclass-for-windows-workflow-foundation"></a>Windows Workflow Foundation에 대 한 x: 클래스  
 Windows Workflow Foundation에 대 한 `x:Class` 클래스를 XAML로만 작성 된 사용자 지정 활동의 이름 또는 코드 숨김을 사용 하 여 activity designer에 대 한 XAML 페이지의 partial 클래스의 이름을 지정 합니다.  
  
## <a name="silverlight-usage-notes"></a>Silverlight 사용 정보  
 `x:Class` Silverlight 용은 별도로 설명 됩니다. 자세한 내용은 참조 하세요. [XAML Namespace (x:) 언어 기능 (Silverlight)](https://go.microsoft.com/fwlink/?LinkId=199081)합니다.  
  
## <a name="see-also"></a>참고자료
- [x:Subclass 지시문](x-subclass-directive.md)
- [WPF에 대한 XAML 및 사용자 지정 클래스](../wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [x:ClassModifier 지시문](x-classmodifier-directive.md)
- [WPF에서 System.Xaml로 마이그레이션된 형식](types-migrated-from-wpf-to-system-xaml.md)
