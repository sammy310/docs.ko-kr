---
title: '방법: 데이터 바인딩에서 XML 네임스페이스 사용'
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: 38bf6e8f88b0325193d49148cd6c33031f7b0a6d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59149996"
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a><span data-ttu-id="01a0e-102">방법: 데이터 바인딩에서 XML 네임스페이스 사용</span><span class="sxs-lookup"><span data-stu-id="01a0e-102">How to: Use XML Namespaces in Data Binding</span></span>
## <a name="example"></a><span data-ttu-id="01a0e-103">예제</span><span class="sxs-lookup"><span data-stu-id="01a0e-103">Example</span></span>  
 <span data-ttu-id="01a0e-104">이 예제에서는 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 바인딩 소스에 지정된 네임스페이스를 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="01a0e-104">This example shows how to handle namespaces specified in your [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] binding source.</span></span>  
  
 <span data-ttu-id="01a0e-105">[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터에 다음 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 네임스페이스 정의가 있는 경우</span><span class="sxs-lookup"><span data-stu-id="01a0e-105">If your [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data has the following [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace definition:</span></span>  
  
 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`  
  
 <span data-ttu-id="01a0e-106">사용할 수는 <xref:System.Windows.Data.XmlNamespaceMapping> 네임 스페이스를 매핑할 요소를 <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>다음 예제와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="01a0e-106">You can use the <xref:System.Windows.Data.XmlNamespaceMapping> element to map the namespace to a <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, as in the following example.</span></span> <span data-ttu-id="01a0e-107">사용할 수 있습니다 합니다 <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> 가리킵니다는 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="01a0e-107">You can then use the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> to refer to the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace.</span></span> <span data-ttu-id="01a0e-108"><xref:System.Windows.Controls.ListBox> 이 예제에 표시 합니다 *제목* 및 *dc:date* 각 *항목*합니다.</span><span class="sxs-lookup"><span data-stu-id="01a0e-108">The <xref:System.Windows.Controls.ListBox> in this example displays the *title* and *dc:date* of each *item*.</span></span>  
  
 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]  
  
 <span data-ttu-id="01a0e-109"><xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> 에 사용 되는 것과 일치 하지 않아도 지정할 합니다 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 소스에서 접두사가 변경 하는 경우를 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 매핑은 계속 작동 하는 원본입니다.</span><span class="sxs-lookup"><span data-stu-id="01a0e-109">Note that the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> you specify does not have to match the one used in the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] source; if the prefix changes in the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] source your mapping still works.</span></span>  
  
 <span data-ttu-id="01a0e-110">이 특정 예제는 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 웹 서비스에서 데이터가 하지만 <xref:System.Windows.Data.XmlNamespaceMapping> 인라인 요소 에서도 작동 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 또는 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 포함 된 파일에서 데이터.</span><span class="sxs-lookup"><span data-stu-id="01a0e-110">In this particular example, the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data comes from a web service, but the <xref:System.Windows.Data.XmlNamespaceMapping> element also works with inline [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] or [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data in an embedded file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01a0e-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="01a0e-111">See also</span></span>

- [<span data-ttu-id="01a0e-112">XMLDataProvider 및 XPath 쿼리를 사용하여 XML 데이터에 바인딩</span><span class="sxs-lookup"><span data-stu-id="01a0e-112">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="01a0e-113">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="01a0e-113">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="01a0e-114">방법 항목</span><span class="sxs-lookup"><span data-stu-id="01a0e-114">How-to Topics</span></span>](data-binding-how-to-topics.md)
