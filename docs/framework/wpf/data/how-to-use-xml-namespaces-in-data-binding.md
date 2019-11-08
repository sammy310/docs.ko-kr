---
title: '방법: XML 네임스페이스를 데이터 바인딩에 사용'
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: f6e6e042fa5583fcf91bd15c524537490fb6670c
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740579"
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a><span data-ttu-id="f2dc3-102">방법: XML 네임스페이스를 데이터 바인딩에 사용</span><span class="sxs-lookup"><span data-stu-id="f2dc3-102">How to: Use XML Namespaces in Data Binding</span></span>
## <a name="example"></a><span data-ttu-id="f2dc3-103">예제</span><span class="sxs-lookup"><span data-stu-id="f2dc3-103">Example</span></span>
 <span data-ttu-id="f2dc3-104">이 예제에서는 XML 바인딩 소스에 지정 된 네임 스페이스를 처리 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f2dc3-104">This example shows how to handle namespaces specified in your XML binding source.</span></span>

 <span data-ttu-id="f2dc3-105">XML 데이터에 다음 XML 네임 스페이스 정의가 있는 경우:</span><span class="sxs-lookup"><span data-stu-id="f2dc3-105">If your XML data has the following XML namespace definition:</span></span>

 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`

 <span data-ttu-id="f2dc3-106">다음 예제와 같이 <xref:System.Windows.Data.XmlNamespaceMapping> 요소를 사용 하 여 네임 스페이스를 <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>에 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2dc3-106">You can use the <xref:System.Windows.Data.XmlNamespaceMapping> element to map the namespace to a <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, as in the following example.</span></span> <span data-ttu-id="f2dc3-107">그런 다음 <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>를 사용 하 여 XML 네임 스페이스를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2dc3-107">You can then use the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> to refer to the XML namespace.</span></span> <span data-ttu-id="f2dc3-108">이 예제의 <xref:System.Windows.Controls.ListBox>는 각 *항목*의 *제목* 및 *dc: 날짜* 를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2dc3-108">The <xref:System.Windows.Controls.ListBox> in this example displays the *title* and *dc:date* of each *item*.</span></span>

 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]

 <span data-ttu-id="f2dc3-109">지정한 <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> XML 원본에 사용 된 것과 일치 하지 않아도 됩니다. XML 원본에서 접두사가 변경 되 면 매핑이 계속 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2dc3-109">Note that the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> you specify does not have to match the one used in the XML source; if the prefix changes in the XML source your mapping still works.</span></span>

 <span data-ttu-id="f2dc3-110">이 특정 예제에서 XML 데이터는 웹 서비스에서 제공 되지만 <xref:System.Windows.Data.XmlNamespaceMapping> 요소는 포함 된 파일의 인라인 XML 또는 XML 데이터 에서도 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2dc3-110">In this particular example, the XML data comes from a web service, but the <xref:System.Windows.Data.XmlNamespaceMapping> element also works with inline XML or XML data in an embedded file.</span></span>

## <a name="see-also"></a><span data-ttu-id="f2dc3-111">참조</span><span class="sxs-lookup"><span data-stu-id="f2dc3-111">See also</span></span>

- [<span data-ttu-id="f2dc3-112">XMLDataProvider 및 XPath 쿼리를 사용하여 XML 데이터에 바인딩</span><span class="sxs-lookup"><span data-stu-id="f2dc3-112">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="f2dc3-113">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="f2dc3-113">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="f2dc3-114">방법 항목</span><span class="sxs-lookup"><span data-stu-id="f2dc3-114">How-to Topics</span></span>](data-binding-how-to-topics.md)
