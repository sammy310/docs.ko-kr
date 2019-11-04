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
ms.openlocfilehash: 2bfd9809a6ad487a7e706366dc6bce8fe951c940
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459755"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a><span data-ttu-id="9725a-102">방법: XAML의 바인딩에 사용할 수 있는 데이터 만들기</span><span class="sxs-lookup"><span data-stu-id="9725a-102">How to: Make Data Available for Binding in XAML</span></span>
<span data-ttu-id="9725a-103">이 항목에서는 응용 프로그램의 요구 사항에 따라 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서 바인딩에 사용할 수 있는 데이터를 만들 수 있는 다양 한 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9725a-103">This topic discusses various ways you can make data available for binding in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], depending on the needs of your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9725a-104">예제</span><span class="sxs-lookup"><span data-stu-id="9725a-104">Example</span></span>  
 <span data-ttu-id="9725a-105">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 바인딩할 CLR (공용 언어 런타임) 개체가 있는 경우이 개체를 바인딩에 사용할 수 있도록 설정 하는 방법 중 하나는 리소스로 정의 하 고 `x:Key`를 제공 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9725a-105">If you have a common language runtime (CLR) object you would like to bind to from [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], one way you can make the object available for binding is to define it as a resource and give it an `x:Key`.</span></span> <span data-ttu-id="9725a-106">다음 예제에서는 `PersonName`라는 문자열 속성을 사용 하는 `Person` 개체가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9725a-106">In the following example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="9725a-107">`<src>` 요소를 포함 하는 강조 표시 된 줄의 `Person` 개체는 `SDKSample`라는 네임 스페이스에 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9725a-107">The `Person` object (in the line shown highlighted that contains the `<src>` element) is defined in the namespace called `SDKSample`.</span></span>  
  
 [!code-xaml[SimpleBinding#Instantiation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="9725a-108">그런 다음 `<TextBlock>` 요소를 포함 하는 강조 표시 된 줄과 같이 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 개체에 <xref:System.Windows.Controls.TextBlock> 컨트롤을 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9725a-108">You can then bind the <xref:System.Windows.Controls.TextBlock> control to the object in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], as the highlighted line that contains the `<TextBlock>` element shows.</span></span> 
  
 <span data-ttu-id="9725a-109">또는 다음 예제와 같이 <xref:System.Windows.Data.ObjectDataProvider> 클래스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9725a-109">Alternatively, you can use the <xref:System.Windows.Data.ObjectDataProvider> class, as in the following example:</span></span>  
  
 [!code-xaml[ObjectDataProvider}](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 <span data-ttu-id="9725a-110">`<TextBlock>` 요소를 포함 하는 강조 표시 된 줄과 같이 동일한 방식으로 바인딩을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="9725a-110">You define the binding the same way, as the highlighted line that contains the `<TextBlock>` element shows.</span></span>  
  
 <span data-ttu-id="9725a-111">이 특정 예제에서 결과는 동일 합니다. `Joe`텍스트 콘텐츠를 사용 하는 <xref:System.Windows.Controls.TextBlock> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9725a-111">In this particular example, the result is the same: you have a <xref:System.Windows.Controls.TextBlock> with the text content `Joe`.</span></span> <span data-ttu-id="9725a-112">그러나 <xref:System.Windows.Data.ObjectDataProvider> 클래스는 메서드의 결과에 바인딩하는 기능과 같은 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9725a-112">However, the <xref:System.Windows.Data.ObjectDataProvider> class provides functionality such as the ability to bind to the result of a method.</span></span> <span data-ttu-id="9725a-113">제공 하는 기능이 필요한 경우 <xref:System.Windows.Data.ObjectDataProvider> 클래스를 사용 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9725a-113">You can choose to use the <xref:System.Windows.Data.ObjectDataProvider> class if you need the functionality it provides.</span></span>  
  
 <span data-ttu-id="9725a-114">그러나 이미 생성 된 개체에 바인딩하는 경우에는 다음 예제와 같이 코드에서 `DataContext`를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9725a-114">However, if you are binding to an object that has already been created, you need to set the `DataContext` in code, as in the following example.</span></span>  
  
 [!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 <span data-ttu-id="9725a-115"><xref:System.Windows.Data.XmlDataProvider> 클래스를 사용 하 여 바인딩에 대 한 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터에 액세스 하려면 [XMLDataProvider 및 XPath 쿼리를 사용 하 여 XML 데이터에 바인딩](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9725a-115">To access [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data for binding using the <xref:System.Windows.Data.XmlDataProvider> class, see [Bind to XML Data Using an XMLDataProvider and XPath Queries](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span></span> <span data-ttu-id="9725a-116"><xref:System.Windows.Data.ObjectDataProvider> 클래스를 사용 하 여 바인딩하기 위한 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터에 액세스 하려면 [XDocument, XElement 또는 LINQ FOR XML 쿼리 결과에 바인딩](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9725a-116">To access [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data for binding using the <xref:System.Windows.Data.ObjectDataProvider> class, see [Bind to XDocument, XElement, or LINQ for XML Query Results](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span></span>  
  
 <span data-ttu-id="9725a-117">바인딩할 데이터를 지정할 수 있는 여러 가지 방법에 대 한 자세한 내용은 [바인딩 소스 지정](how-to-specify-the-binding-source.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9725a-117">For information about many ways you can specify the data you are binding to, see [Specify the Binding Source](how-to-specify-the-binding-source.md).</span></span> <span data-ttu-id="9725a-118">바인딩할 수 있는 데이터 형식에 대 한 자세한 내용 또는 바인딩을 위한 고유한 CLR (공용 언어 런타임) 개체를 구현 하는 방법에 대 한 자세한 내용은 [바인딩 소스 개요](binding-sources-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9725a-118">For information about what types of data you can bind to or how to implement your own common language runtime (CLR) objects for binding, see [Binding Sources Overview](binding-sources-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9725a-119">참조</span><span class="sxs-lookup"><span data-stu-id="9725a-119">See also</span></span>

- [<span data-ttu-id="9725a-120">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="9725a-120">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="9725a-121">방법 항목</span><span class="sxs-lookup"><span data-stu-id="9725a-121">How-to Topics</span></span>](data-binding-how-to-topics.md)
