---
title: '방법: XAML의 바인딩에 사용할 수 있는 데이터 만들기'
ms.date: 01/29/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], making data available for binding
- binding data [WPF], making data available for
ms.assetid: 7103c2e8-0e31-4a13-bf12-ca382221a8d5
ms.openlocfilehash: 91e89dbf36024c31f4afcd9b6d956944baf13576
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174188"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a>방법: XAML의 바인딩에 사용할 수 있는 데이터 만들기
이 항목에서는 응용 프로그램의 요구 사항에 따라 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서 바인딩할 수 있도록 데이터를 사용할 수 있도록 하는 다양한 방법에 대해 설명합니다.  
  
## <a name="example"></a>예제  
 에서 바인딩하려는 공통 언어 런타임(CLR) 개체가 있는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]경우 바인딩에 개체를 사용할 수 있도록 하는 한 가지 방법은 `x:Key`개체를 리소스로 정의하고 을 지정하는 것입니다. 다음 예제에서는 `Person` `PersonName`.라는 문자열 속성이 있는 개체가 있습니다. 요소를 포함하는 강조 표시된 줄에서 개체는 라는 `SDKSample`네임스페이스에 정의됩니다. `Person` `<src>`  
  
 [!code-xaml[SimpleBinding#Instantiation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 그런 다음 요소가 <xref:System.Windows.Controls.TextBlock> 포함된 강조 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]표시된 줄이 표시될 `<TextBlock>` 때 의 개체에 컨트롤을 바인딩할 수 있습니다.
  
 또는 다음 예제와 <xref:System.Windows.Data.ObjectDataProvider> 같이 클래스를 사용할 수 있습니다.  
  
 [!code-xaml[ObjectDataProvider}](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 요소가 포함된 강조 표시된 선과 동일한 방식으로 `<TextBlock>` 바인딩을 정의합니다.  
  
 이 특정 예제에서는 결과가 동일합니다. <xref:System.Windows.Controls.TextBlock> `Joe` 그러나 클래스는 <xref:System.Windows.Data.ObjectDataProvider> 메서드의 결과에 바인딩하는 기능과 같은 기능을 제공합니다. 클래스에서 <xref:System.Windows.Data.ObjectDataProvider> 제공하는 기능이 필요한 경우 클래스를 사용하도록 선택할 수 있습니다.  
  
 그러나 이미 만들어진 개체에 바인딩하는 경우 다음 예제와 같이 `DataContext` in 코드를 설정해야 합니다.  
  
 [!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 <xref:System.Windows.Data.XmlDataProvider> 클래스를 사용하여 바인딩하기 위해 XML 데이터에 액세스하려면 [XMLDataProvider 및 XPath 쿼리를 사용하여 XML 데이터에 바인딩을](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)참조하십시오. <xref:System.Windows.Data.ObjectDataProvider> 클래스를 사용하여 바인딩하기 위해 XML 데이터에 액세스하려면 [XDocument, XElement 또는 XML 쿼리 결과에 대한 LINQ에 바인딩을](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)참조하십시오.  
  
 바인딩할 데이터를 지정할 수 있는 여러 가지 방법에 대한 자세한 내용은 [바인딩 소스 지정을](how-to-specify-the-binding-source.md)참조하십시오. 바인딩할 수 있는 데이터 유형 또는 바인딩을 위해 고유한 공통 언어 런타임(CLR) 개체를 구현하는 방법에 대한 자세한 내용은 [바인딩 소스 개요를](binding-sources-overview.md)참조하십시오.  
  
## <a name="see-also"></a>참고 항목

- [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)
- [방법 주제](data-binding-how-to-topics.md)
