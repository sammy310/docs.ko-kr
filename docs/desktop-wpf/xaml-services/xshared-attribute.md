---
title: x:Shared 특성
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], x:Shared attribute
- x:Shared attribute [XAML Services]
- Shared attribute in XAML [XAML Services]
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
ms.openlocfilehash: d5000b51d83066ec2d529db2033d8ac54f7ad329
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557790"
---
# <a name="xshared-attribute"></a>x:Shared 특성

로 설정 `false` 된 경우 특성을 사용 하는 리소스에 대 한 요청이 모든 요청에 대해 동일한 인스턴스를 공유 하는 대신 각 요청에 대해 새 인스턴스를 만들도록 WPF 리소스 검색 동작을 수정 합니다.

## <a name="xaml-attribute-usage"></a>XAML 특성 사용

```xaml
<ResourceDictionary>
  <object x:Shared="false".../>
</ResourceDictionary>
```

## <a name="remarks"></a>설명

`x:Shared` 는 XAML 언어 XAML 네임 스페이스에 매핑되고 .NET XAML 서비스 및 해당 XAML 판독기에서 유효한 XAML 언어 요소로 인식 됩니다. 그러나의 설명 된 기능은 `x:Shared` wpf 응용 프로그램 및 WPF XAML 파서에만 관련 됩니다. WPF에서 `x:Shared` 는 wpf 내에 있는 개체에 적용 되는 경우에만 특성으로 유용 <xref:System.Windows.ResourceDictionary> 합니다. 다른 용도는 구문 분석 예외 나 기타 오류를 throw 하지 않지만 아무런 영향을 주지 않습니다.

의 의미는 `x:Shared` XAML 언어 사양에 지정 되어 있지 않습니다. .NET XAML 서비스를 기반으로 하는 것과 같은 다른 XAML 구현은 반드시 리소스 공유 지원을 제공 하지는 않습니다. 이러한 XAML 구현은 지원 프레임 워크 에서도 값을 사용 하는 유사한 동작을 제공할 수 있습니다 `x:Shared` .

WPF에서 `x:Shared` 리소스에 대 한 기본 조건은 `true` 입니다. 이 조건은 지정 된 모든 리소스 요청이 항상 동일한 인스턴스를 반환 함을 의미 합니다.

등의 리소스 API를 통해 반환 되는 개체를 수정 <xref:System.Windows.FrameworkElement.FindResource%2A> 하거나에서 직접 개체를 수정 <xref:System.Windows.ResourceDictionary> 하면 원래 리소스가 변경 됩니다. 해당 리소스에 대 한 참조가 동적 리소스 참조 인 경우 해당 리소스의 소비자는 변경 된 리소스를 가져옵니다.

리소스에 대 한 참조가 정적 리소스 참조 인 경우 처리 시간 이후 리소스에 대 한 변경 내용이 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 관련이 없습니다. 정적 및 동적 리소스 참조에 대 한 자세한 내용은 [XAML 리소스](../fundamentals/xaml-resources-define.md)를 참조 하세요.

가 이미 기본값 이기 때문에를 명시적으로 지정 하 `x:Shared="true"` 는 것은 거의 수행 되지 않습니다. WPF 개체 모델에는에 해당 하는 직접 코드가 없습니다 `x:Shared` . XAML 사용에만 지정할 수 있으며, .NET XAML 서비스 및 해당 xaml 판독기를 사용 하 여 처리 하는 경우 로드 경로에서 기본 WPF 동작이 나 중간 XAML 노드 스트림에서 처리 되어야 합니다.

의 시나리오는 `x:Shared="false"` <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement> 파생 클래스를 리소스로 정의한 다음 요소 리소스를 콘텐츠 모델에 도입 하는 경우입니다. `x:Shared="false"` 같은 컬렉션에서 요소 리소스를 여러 번 도입할 수 있도록 합니다 (예: <xref:System.Windows.Controls.UIElementCollection> ). `x:Shared="false"`컬렉션은 내용에 고유성이 적용 되므로이는 유효 하지 않습니다. 그러나이 `x:Shared="false"` 동작은 동일한 인스턴스를 반환 하는 대신 동일한 리소스의 다른 인스턴스를 만듭니다.

의 또 다른 시나리오 `x:Shared="false"` 는 <xref:System.Windows.Freezable> 애니메이션 값에 리소스를 사용 하지만 애니메이션 별로 리소스를 수정 하려는 경우입니다.

의 문자열 처리는 `false` 대/소문자를 구분 하지 않습니다.

WPF에서 `x:Shared` 는 다음 조건 에서만 유효 합니다.

- <xref:System.Windows.ResourceDictionary>를 포함 하는 항목이 포함 된를 `x:Shared` 컴파일해야 합니다. 는 <xref:System.Windows.ResourceDictionary> 느슨한 XAML 내에 있거나 테마에 사용 될 수 없습니다.

- <xref:System.Windows.ResourceDictionary>항목을 포함 하는가 다른에 중첩 되지 않아야 합니다 <xref:System.Windows.ResourceDictionary> . 예를 들어 `x:Shared` <xref:System.Windows.ResourceDictionary> 이미 항목인 내에 있는 항목에는를 사용할 수 없습니다 <xref:System.Windows.Style> <xref:System.Windows.ResourceDictionary> .

## <a name="see-also"></a>참조

- <xref:System.Windows.ResourceDictionary>
- [XAML 리소스](../fundamentals/xaml-resources-define.md)
- [기본 요소](/dotnet/desktop/wpf/advanced/base-elements)
