---
title: x:Null 태그 확장
ms.date: 03/30/2017
f1_keywords:
- NullExtension
- x:NullExtension
- x:Null
- "Null"
- xNull
helpviewer_keywords:
- Null markup extension in XAML [XAML Services]
- x:Null markup extension [XAML Services]
- XAML [XAML Services], x:Null markup extension
ms.assetid: 2e3ccc21-4996-481d-91b5-3910d8b3bfa3
ms.openlocfilehash: 34a2de71bec9b0929070aa908741de38b5904643
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2019
ms.locfileid: "58029367"
---
# <a name="xnull-markup-extension"></a>x:Null 태그 확장
지정 `null` XAML 멤버에 대 한 값으로.  
  
## <a name="xaml-attribute-usage"></a>XAML 특성 사용  
  
```xaml  
<object property="{x:Null}" .../>  
```  
  
## <a name="remarks"></a>설명  
 키워드에 대 한 null 참조입니다. C# 하 고 [!INCLUDE[TLA#tla_cpp](../../../includes/tlasharptla-cpp-md.md)] 가 null입니다. Null 참조에 대 한 Microsoft Visual Basic 키워드 `Nothing`, 항상 사용 하지만 `{x:Null}` XAML 사용에 관계 없이 연결 된 XAML을 사용 하 여 코드 숨김 언어도 합니다.  
  
 `x:Null` 태그 확장에 설정할 수 있는 속성이 없습니다.  
  
 Null 사용 관련 clr XAML 멤버 노출 된 경우가 <xref:System.Nullable%601> 값입니다.  
  
 합니다 `x:Null` 중괄호를 사용 하는 모든 XAML 태그 확장과 마찬가지로 태그 확장 (`{,}`) 이스케이프 리터럴 또는 이벤트 처리기 참조 이외의 특성 값의 처리에 대 한 합니다. 특성 구문은이 태그 확장을 사용 하 여 가장 자주 사용 되는 구문입니다. 개체 요소 구문도 `<x:Null />` 기술적으로 가능 하지만 때문에 거의 사용 되지 않습니다는 `x:Null` 태그 확장에는 위치 매개 변수 또는 생성 인수 없습니다.  
  
 태그 확장에 대 한 자세한 내용은 [태그 확장 및 WPF XAML](../wpf/advanced/markup-extensions-and-wpf-xaml.md)합니다.  
  
 .NET Framework XAML 서비스에서이 태그 확장에 대 한 처리에서 정의 됩니다는 <xref:System.Windows.Markup.NullExtension> 클래스입니다.  
  
## <a name="wpf-usage-notes"></a>WPF 사용 정보  
 `null` 반드시 참조 형식 종속성 속성의 초기 설정 되지 않은 값이 아닙니다. 초기 기본값 각 종속성 속성에 대해 다를 수 있습니다 및 속성별 메타 데이터에 기반 할 수 있습니다. 대부분의 종속성 속성을 받지 않는 `null` 태그 또는 유효성 검사 콜백 구현으로 인해 코드를 통해 값으로. 종속성 속성에 대 한 자세한 내용은 참조 하세요. [종속성 속성 개요](../wpf/advanced/dependency-properties-overview.md)합니다.  
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.DependencyProperty.UnsetValue>
- [XAML 개요(WPF)](../wpf/advanced/xaml-overview-wpf.md)
- [태그 확장 및 WPF XAML](../wpf/advanced/markup-extensions-and-wpf-xaml.md)
