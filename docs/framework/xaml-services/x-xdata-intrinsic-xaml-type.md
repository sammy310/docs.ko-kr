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
ms.openlocfilehash: c8044bc341ded6ef7b03bbdf701e724654460d54
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938829"
---
# <a name="xxdata-intrinsic-xaml-type"></a>x:XData 내장 XAML 형식
XAML 프로덕션 내에서 XML 데이터 아일랜드 배치를 사용 하도록 설정 합니다. XML 요소 내에서 `x:XData` 것 처럼 기본 XAML 네임 스페이스의 일부 또는 모든 다른 XAML 네임 스페이스 XAML 프로세서에서 처리 되지 않아야 합니다. `x:XData` 임의의 올바른 형식의 XML을 포함할 수 있습니다.  
  
## <a name="xaml-object-element-usage"></a>XAML 개체 요소 사용  
  
```  
<x:XData>  
  <elementDataRoot>  
    [elementData]  
  </elementDataRoot>  
</x:XData>  
```  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|`elementDataRoot`|포함된 데이터 아일랜드의 단일 루트 요소입니다. 대부분의 최종 소비자에 대 한 단일 루트 되지 않은 XML이 잘못 된 간주 됩니다. 특히, 단일 루트 필요한 경우는 `x:XData` WPF 또는 데이터 바인딩에 대 한 XML 원본을 사용 하는 다른 많은 기술에 대 한 XML 데이터 소스 사용 됩니다.|  
|`[elementData]`|선택 사항입니다. XML 데이터를 나타내는 XML입니다. 요소 데이터 요소를 개수에 관계 없이 포함 될 수 있는 및 중첩 된 요소가 다른 요소에 포함 될 수 있는 그러나 일반 XML 규칙을 적용합니다.|  
  
## <a name="remarks"></a>설명  
 내에서 XML 요소는 `x:XData` 모든 가능한 네임 스페이스 및 접두사 데이터 내에 포함 된 XMLDOM 개체 다시 선언할 수 있습니다.  
  
 XML 데이터에 프로그래밍 방식 액세스 하며 `x:XData` 내장 XAML 형식.NET Framework XAML 서비스를 통해 가능 합니다 <xref:System.Windows.Markup.XData> 클래스.  
  
## <a name="wpf-usage-notes"></a>WPF 사용 정보  
 합니다 `x:XData` 개체의 자식 개체로 주로 <xref:System.Windows.Data.XmlDataProvider>, 또는의 자식 개체로 <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> 속성 (XAML,이 일반적으로 표시 속성 요소 구문에서).  
  
 데이터 (빈 문자열로 설정 됨) 새 기본 XML 네임 스페이스는 데이터 아일랜드 내에서 기본 XML 네임 스페이스를 일반적으로 재정의 해야 합니다. 간단한 데이터 아일랜드 때문에이 가장 쉬운 방법은 <xref:System.Windows.Data.Binding.XPath%2A> 식을 참조 하 고 데이터에 바인딩하는 접두사의 포함을 방지할 수 있습니다. 더 복잡 한 데이터 아일랜드는 데이터에 대 한 여러 개의 접두사를 정의 하 고 루트 XML 네임 스페이스에 대 한 특정 접두사를 사용할 수 있습니다. 이 경우 모든 <xref:System.Windows.Data.Binding.XPath%2A> 식 참조에 적절 한 네임 스페이스 매핑 접두사를 포함 해야 합니다. 자세한 내용은 [데이터 바인딩 개요](../wpf/data/data-binding-overview.md)를 참조하세요.  
  
 기술적으로 보면 `x:XData` 형식의 모든 속성의 콘텐츠로 사용할 수 있습니다 <xref:System.Xml.Serialization.IXmlSerializable>합니다. 그러나 <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> 주로 사용 되는 구현입니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Data.XmlDataProvider>
- [데이터 바인딩 개요](../wpf/data/data-binding-overview.md)
- [Binding 태그 확장](../wpf/advanced/binding-markup-extension.md)
