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
ms.openlocfilehash: 8496e7c87cf7e6eea996ca7af4f288b7495c7661
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459904"
---
# <a name="xxdata-intrinsic-xaml-type"></a>x:XData 내장 XAML 형식
XAML 프로덕션 내에서 XML 데이터 아일랜드를 배치할 수 있습니다. `x:XData` 내의 XML 요소는 XAML 프로세서에서 처리 하는 기본 XAML 네임 스페이스 또는 다른 XAML 네임 스페이스의 일부인 것 처럼 처리 하면 안 됩니다. `x:XData`은 올바른 형식의 XML을 포함할 수 있습니다.  
  
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
|`elementDataRoot`|포함 된 데이터 아일랜드의 단일 루트 요소입니다. 대부분의 최종 소비자의 경우 단일 루트를 포함 하지 않는 XML은 잘못 된 것으로 간주 됩니다. 특히 데이터 바인딩에 XML 원본을 사용 하는 WPF 또는 다른 여러 기술에 대 한 XML 데이터 원본으로 `x:XData` 하는 경우에는 단일 루트가 필요 합니다.|  
|`[elementData]`|(선택 사항) XML 데이터를 나타내는 XML입니다. 요소 수에 관계 없이 요소 데이터와 중첩 된 요소가 다른 요소에 포함 될 수 있습니다. 그러나 XML의 일반 규칙이 적용 됩니다.|  
  
## <a name="remarks"></a>주의  
 `x:XData` 개체 내의 XML 요소는 데이터 내에 포함 된 XMLDOM의 모든 가능한 네임 스페이스와 접두사를 다시 선언할 수 있습니다.  
  
 XML 데이터 및 `x:XData` 내장 XAML 형식에 대 한 프로그래밍 방식 액세스는 <xref:System.Windows.Markup.XData> 클래스를 통해 .NET Framework XAML 서비스에서 가능 합니다.  
  
## <a name="wpf-usage-notes"></a>WPF 사용 정보  
 `x:XData` 개체는 주로 <xref:System.Windows.Data.XmlDataProvider>의 자식 개체로 사용 되거나 또는 <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> 속성의 자식 개체로 사용 됩니다 (XAML에서 일반적으로 속성 요소 구문으로 표현 됨).  
  
 데이터는 일반적으로 데이터 아일랜드 내의 기본 XML 네임 스페이스를 새 기본 XML 네임 스페이스 (빈 문자열로 설정)로 다시 정의 해야 합니다. 이는 데이터를 참조 하 고 바인딩하는 데 사용 되는 <xref:System.Windows.Data.Binding.XPath%2A> 식이 접두사의 포함을 방지할 수 있기 때문에 단순 데이터 아일랜드에 가장 간편 합니다. 더 복잡 한 데이터 아일랜드는 데이터에 대 한 여러 접두사를 정의 하 고 루트의 XML 네임 스페이스에 대 한 특정 접두사를 사용할 수 있습니다. 이 경우 모든 <xref:System.Windows.Data.Binding.XPath%2A> 식 참조에 적절 한 네임 스페이스 매핑 접두사가 포함 되어야 합니다. 자세한 내용은 [데이터 바인딩 개요](../../desktop-wpf/data/data-binding-overview.md)를 참조하세요.  
  
 기술적으로 `x:XData` <xref:System.Xml.Serialization.IXmlSerializable>형식의 속성 내용으로 사용할 수 있습니다. 그러나 <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType>는 유일한 중요 한 구현입니다.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Data.XmlDataProvider>
- [데이터 바인딩 개요](../../desktop-wpf/data/data-binding-overview.md)
- [Binding 태그 확장](../wpf/advanced/binding-markup-extension.md)
