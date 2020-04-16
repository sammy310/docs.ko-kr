---
title: x:XData 내장 XAML 형식
ms.date: 03/30/2017
f1_keywords:
- x:XData
- XData
- xXData
helpviewer_keywords:
- XAML [XAML Services], x:XData directive element
- XData in XAML [XAML Services]
- x:XData XAML directive element [XAML Services]
ms.assetid: 7ce209c2-621b-4977-b643-565f7e663534
ms.openlocfilehash: b7f0954158988db107feb4a6c51ba81d5db11dcb
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432793"
---
# <a name="xxdata-intrinsic-xaml-type"></a>x:XData 내장 XAML 형식
XAML 프로덕션 내에서 XML 데이터 섬을 배치할 수 있습니다. XAML `x:XData` 프로세서 내의 XML 요소는 작동 기본 XAML 네임스페이스 또는 다른 XAML 네임스페이스의 일부인 것처럼 처리해서는 안 됩니다. `x:XData`임의의 잘 형성된 XML을 포함할 수 있습니다.

## <a name="xaml-object-element-usage"></a>XAML 개체 요소 사용

```xaml
<x:XData>
  <elementDataRoot>
    [elementData]
  </elementDataRoot>
</x:XData>
```

## <a name="xaml-values"></a>XAML 값

|||
|-|-|
|`elementDataRoot`|둘러싸인 데이터 섬의 단일 루트 요소입니다. 대부분의 최종 소비자의 경우 단일 루트가 없는 XML은 유효하지 않은 것으로 간주됩니다. 특히 WPF또는 데이터 바인딩을 `x:XData` 위해 XML 원본을 사용하는 다른 많은 기술에 대한 XML 데이터 원본으로 의도된 경우 단일 루트가 필요합니다.|
|`[elementData]`|(선택 사항) XML 데이터를 나타내는 XML입니다. 요소 데이터로 포함할 수 있는 요소 수와 중첩된 요소가 다른 요소에 포함될 수 있습니다. 그러나 XML의 일반 규칙이 적용됩니다.|

## <a name="remarks"></a>설명

개체 내의 `x:XData` XML 요소는 데이터 내에 포함된 XMLDOM의 가능한 모든 네임스페이스 및 접두사를 다시 선언할 수 있습니다.

XML 데이터와 `x:XData` 본질적인 XAML 형식에 대한 프로그래밍 방식으로 클래스를 <xref:System.Windows.Markup.XData> 통해 .NET XAML 서비스에서 가능합니다.

## <a name="wpf-usage-notes"></a>WPF 사용 정보

개체는 `x:XData` 주로 <xref:System.Windows.Data.XmlDataProvider>속성의 자식 개체(XAML에서 일반적으로 속성 요소 <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> 구문으로 표현)의 자식 개체또는 또는 다른 방법으로 사용됩니다.

데이터는 일반적으로 데이터 섬 내의 기본 XML 네임스페이스를 빈 문자열로 설정된 새 기본 XML 네임스페이스로 재정의해야 합니다. 데이터를 참조하고 바인딩하는 데 <xref:System.Windows.Data.Binding.XPath%2A> 사용되는 식은 접두사를 포함하지 않아도 되므로 간단한 데이터 제도에 가장 적합합니다. 더 복잡한 데이터 제도는 데이터에 대한 여러 접두사를 정의하고 루트의 XML 네임스페이스에 대한 특정 접두사를 사용할 수 있습니다. 이 경우 모든 <xref:System.Windows.Data.Binding.XPath%2A> 표현식 참조에는 적절한 네임스페이스 매핑접두사가 포함되어야 합니다. 자세한 내용은 [데이터 바인딩 개요를](../data/data-binding-overview.md)참조하십시오.

기술적으로, `x:XData` 형식의 <xref:System.Xml.Serialization.IXmlSerializable>모든 속성의 내용으로 사용할 수 있습니다. 그러나, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> 유일한 눈에 띄는 구현이다.

## <a name="see-also"></a>참조

- <xref:System.Windows.Data.XmlDataProvider>
- [데이터 바인딩 개요](../data/data-binding-overview.md)
- [Binding 태그 확장](../../framework/wpf/advanced/binding-markup-extension.md)
