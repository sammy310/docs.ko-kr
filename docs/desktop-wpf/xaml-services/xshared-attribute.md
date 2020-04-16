---
title: x:Shared 특성
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], x:Shared attribute
- x:Shared attribute [XAML Services]
- Shared attribute in XAML [XAML Services]
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
ms.openlocfilehash: e1cd1d9db5c19decd840b433f986e0ba53557a8b
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432649"
---
# <a name="xshared-attribute"></a>x:Shared 특성

`false`로 설정하면 WPF 리소스 검색 동작을 수정하여 특성 처리된 리소스에 대한 요청이 모든 요청에 대해 동일한 인스턴스를 공유하는 대신 각 요청에 대한 새 인스턴스를 만듭니다.

## <a name="xaml-attribute-usage"></a>XAML 특성 사용

```xaml
<ResourceDictionary>
  <object x:Shared="false".../>
</ResourceDictionary>
```

## <a name="remarks"></a>설명

`x:Shared`XAML 언어 XAML 네임스페이스에 매핑되며 .NET XAML 서비스 및 XAML 판독기에서 유효한 XAML 언어 요소로 인식됩니다. 그러나 명시된 기능은 `x:Shared` WPF 응용 프로그램 및 WPF XAML 파서에만 관련이 있습니다. WPF에서 `x:Shared` WPF <xref:System.Windows.ResourceDictionary>내에 있는 개체에 적용 될 때 특성으로만 유용 합니다. 다른 사용법은 구문 분석 예외 나 다른 오류를 throw하지 않지만 아무런 영향을 미치지 않습니다.

의 `x:Shared` 의미는 XAML 언어 사양에 지정되지 않았습니다. .NET XAML 서비스를 기반으로 하는 것과 같은 다른 XAML 구현은 반드시 리소스 공유 지원을 제공하지는 않습니다. 이러한 XAML 구현은 값을 사용하는 `x:Shared` 지원 프레임워크에서도 유사한 동작을 제공할 수 있습니다.

WPF에서 리소스의 `x:Shared` 기본 조건은 `true`. 이 조건은 지정된 리소스 요청이 항상 동일한 인스턴스를 반환한다는 것을 의미합니다.

와 같은 <xref:System.Windows.FrameworkElement.FindResource%2A>리소스 API를 통해 반환되는 개체를 수정하거나 <xref:System.Windows.ResourceDictionary>에서 직접 개체를 수정하면 원래 리소스가 변경됩니다. 해당 리소스에 대한 참조가 동적 리소스 참조인 경우 해당 리소스의 소비자는 변경된 리소스를 가져옵니다.

리소스에 대한 참조가 정적 리소스 참조인 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 경우 처리 시간 후에 리소스에 대한 변경은 관련이 없습니다. 정적 리소스 참조와 동적 리소스 참조에 대한 자세한 내용은 [XAML 리소스](../fundamentals/xaml-resources-define.md)를 참조하십시오.

명시적으로 지정하는 `x:Shared="true"` 것은 거의 수행되지 않습니다. WPF 개체 모델에 `x:Shared` 해당하는 직접 코드가 없습니다. XAML 사용법에서만 지정할 수 있으며 .NET XAML 서비스 및 XAML 리더를 사용하여 처리한 경우 기본 WPF 동작또는 로드 경로의 중간 XAML 노드 스트림에서 처리해야 합니다.

`x:Shared="false"` 시나리오는 a <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement> 파생 클래스를 리소스로 정의한 다음 요소 리소스를 콘텐츠 모델에 도입하는 경우입니다. `x:Shared="false"`을 사용하면 요소 리소스를 동일한 컬렉션(예: a)에서 여러 번 도입할 수 있습니다. <xref:System.Windows.Controls.UIElementCollection> 컬렉션이 해당 내용의 고유성을 적용하기 때문에 이 항목이 없으면 `x:Shared="false"` 유효하지 않습니다. 그러나 이 `x:Shared="false"` 동작은 동일한 인스턴스를 반환하는 대신 리소스의 다른 동일한 인스턴스를 만듭니다.

또 다른 `x:Shared="false"` 시나리오는 애니메이션 <xref:System.Windows.Freezable> 값에 리소스를 사용하지만 애니메이션별로 리소스를 수정하려는 경우입니다.

의 문자열 `false` 처리는 대소에 민감하지 않습니다.

WPF에서는 `x:Shared` 다음 조건에서만 유효합니다.

- <xref:System.Windows.ResourceDictionary> 포함된 `x:Shared` 항목을 컴파일해야 합니다. 느슨한 <xref:System.Windows.ResourceDictionary> XAML 내에 있을 수 없거나 테마에 사용할 수 없습니다.

- 항목이 포함된 항목은 <xref:System.Windows.ResourceDictionary> 다른 <xref:System.Windows.ResourceDictionary>내에 중첩되어서는 안 됩니다. 예를 들어 이미 `x:Shared` 항목인 a <xref:System.Windows.ResourceDictionary> <xref:System.Windows.Style> 내의 <xref:System.Windows.ResourceDictionary> 항목에는 사용할 수 없습니다.

## <a name="see-also"></a>참조

- <xref:System.Windows.ResourceDictionary>
- [XAML 리소스](../fundamentals/xaml-resources-define.md)
- [기본 요소](../../framework/wpf/advanced/base-elements.md)
