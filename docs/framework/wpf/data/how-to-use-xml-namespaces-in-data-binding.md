---
title: '방법: XML 네임스페이스를 데이터 바인딩에 사용'
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: 47ce0d951df39c7b60aa2a543baf845f5471de6c
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460308"
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a>방법: XML 네임스페이스를 데이터 바인딩에 사용
## <a name="example"></a>예제
 이 예제에서는 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 바인딩 소스에 지정된 네임스페이스를 처리하는 방법을 보여 줍니다.

 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터에 다음 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 네임스페이스 정의가 있는 경우

 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`

 다음 예제와 같이 <xref:System.Windows.Data.XmlNamespaceMapping> 요소를 사용 하 여 네임 스페이스를 <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>에 매핑할 수 있습니다. 그런 다음 <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>를 사용 하 여 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 네임 스페이스를 참조할 수 있습니다. 이 예제의 <xref:System.Windows.Controls.ListBox>는 각 *항목*의 *제목* 및 *dc: 날짜* 를 표시 합니다.

 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]

 지정 하는 <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 원본에 사용 된 것과 일치 하지 않아도 됩니다. [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 원본에서 접두사가 변경 되 면 매핑이 계속 작동 합니다.

 이 특정 예제에서 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터는 웹 서비스에서 제공 되지만 <xref:System.Windows.Data.XmlNamespaceMapping> 요소는 포함 된 파일의 인라인 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 또는 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터 에서도 작동 합니다.

## <a name="see-also"></a>참조

- [XMLDataProvider 및 XPath 쿼리를 사용하여 XML 데이터에 바인딩](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)
- [방법 항목](data-binding-how-to-topics.md)
