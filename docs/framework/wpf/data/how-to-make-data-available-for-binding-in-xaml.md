---
title: '방법: XAML에서 바인딩에 사용할 수 있는 데이터 만들기'
ms.date: 01/29/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], making data available for binding
- binding data [WPF], making data available for
ms.assetid: 7103c2e8-0e31-4a13-bf12-ca382221a8d5
ms.openlocfilehash: 2d51f06da31482c46b04d1eb86172c3eda246c20
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59145368"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a>방법: XAML에서 바인딩에 사용할 수 있는 데이터 만들기
이 항목에서는 다양 한 방법으로 사용할 수 있습니다 데이터에 대 한 바인딩 설명 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]응용 프로그램의 필요에 따라 합니다.  
  
## <a name="example"></a>예제  
 있는 경우는 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 에서 바인딩할 하려는 개체 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]를 사용할 수 있게 만드는 개체 바인딩 리소스로 정의 하 고 지정 하는 것에 대 한 한 가지 방법은 `x:Key`합니다. 에 다음 예제는 `Person` 이라는 문자열 속성을 사용 하 여 개체 `PersonName`합니다. 합니다 `Person` 개체 (강조 표시 된 줄에 포함 하는 합니다 `<src>` 요소) 이라는 네임 스페이스에 정의 된 `SDKSample`합니다.  
  
 [!code-xaml[SimpleBinding#Instantiation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 바인딩할 수 있습니다는 <xref:System.Windows.Controls.TextBlock> 개체에 컨트롤 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]강조 표시 된 줄로 포함 합니다 `<TextBlock>` 요소 보여 줍니다. 
  
 사용할 수 있습니다는 <xref:System.Windows.Data.ObjectDataProvider> 다음 예제와 같이 클래스:  
  
 [!code-xaml[ObjectDataProvider}](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 바인딩을 정의 포함 하는 강조 표시 된 줄과 같은 방법으로는 `<TextBlock>` 요소 보여 줍니다.  
  
 이 예의 경우 결과: 해야는 <xref:System.Windows.Controls.TextBlock> 텍스트 콘텐츠로 `Joe`합니다. 그러나는 <xref:System.Windows.Data.ObjectDataProvider> 클래스 메서드의 결과 바인딩할 수와 같은 기능을 제공 합니다. 사용 하도록 선택할 수는 <xref:System.Windows.Data.ObjectDataProvider> 클래스를 제공 하는 기능이 필요한 경우.  
  
 그러나 이미 만든 개체에 바인딩하는 경우 설정 해야 합니다 `DataContext` 다음 예제와 같이 코드에서.  
  
 [!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 에 액세스 하려면 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 바인딩을 사용 하 여 데이터를 <xref:System.Windows.Data.XmlDataProvider> 클래스를 참조 하십시오 [XMLDataProvider 및 XPath 쿼리를 사용 하 여 XML 데이터에 바인딩](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)합니다. 에 액세스 하려면 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 바인딩을 사용 하 여 데이터를 <xref:System.Windows.Data.ObjectDataProvider> 클래스를 참조 하십시오 [XDocument, XElement 또는 LINQ for XML 쿼리 결과에 바인딩](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)합니다.  
  
 바인딩할 데이터를 지정할 수 있습니다 여러 가지 방법에 대 한 정보를 참조 하세요 [바인딩 소스 지정](how-to-specify-the-binding-source.md)합니다. 어떤 유형의 데이터에 바인딩할 수 있습니다 또는 자체적으로 구현 하는 방법에 대 한 자세한 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 바인딩에 대 한 개체 참조 [바인딩 소스 개요](binding-sources-overview.md)합니다.  
  
## <a name="see-also"></a>참고자료

- [데이터 바인딩 개요](data-binding-overview.md)
- [방법 항목](data-binding-how-to-topics.md)
