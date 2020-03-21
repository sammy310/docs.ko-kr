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
# <a name="how-to-make-data-available-for-binding-in-xaml"></a><span data-ttu-id="d94e5-102">방법: XAML의 바인딩에 사용할 수 있는 데이터 만들기</span><span class="sxs-lookup"><span data-stu-id="d94e5-102">How to: Make Data Available for Binding in XAML</span></span>
<span data-ttu-id="d94e5-103">이 항목에서는 응용 프로그램의 요구 사항에 따라 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서 바인딩할 수 있도록 데이터를 사용할 수 있도록 하는 다양한 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d94e5-103">This topic discusses various ways you can make data available for binding in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], depending on the needs of your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d94e5-104">예제</span><span class="sxs-lookup"><span data-stu-id="d94e5-104">Example</span></span>  
 <span data-ttu-id="d94e5-105">에서 바인딩하려는 공통 언어 런타임(CLR) 개체가 있는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]경우 바인딩에 개체를 사용할 수 있도록 하는 한 가지 방법은 `x:Key`개체를 리소스로 정의하고 을 지정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d94e5-105">If you have a common language runtime (CLR) object you would like to bind to from [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], one way you can make the object available for binding is to define it as a resource and give it an `x:Key`.</span></span> <span data-ttu-id="d94e5-106">다음 예제에서는 `Person` `PersonName`.라는 문자열 속성이 있는 개체가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d94e5-106">In the following example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="d94e5-107">요소를 포함하는 강조 표시된 줄에서 개체는 라는 `SDKSample`네임스페이스에 정의됩니다. `Person` `<src>`</span><span class="sxs-lookup"><span data-stu-id="d94e5-107">The `Person` object (in the line shown highlighted that contains the `<src>` element) is defined in the namespace called `SDKSample`.</span></span>  
  
 [!code-xaml[SimpleBinding#Instantiation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="d94e5-108">그런 다음 요소가 <xref:System.Windows.Controls.TextBlock> 포함된 강조 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]표시된 줄이 표시될 `<TextBlock>` 때 의 개체에 컨트롤을 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d94e5-108">You can then bind the <xref:System.Windows.Controls.TextBlock> control to the object in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], as the highlighted line that contains the `<TextBlock>` element shows.</span></span>
  
 <span data-ttu-id="d94e5-109">또는 다음 예제와 <xref:System.Windows.Data.ObjectDataProvider> 같이 클래스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d94e5-109">Alternatively, you can use the <xref:System.Windows.Data.ObjectDataProvider> class, as in the following example:</span></span>  
  
 [!code-xaml[ObjectDataProvider}](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 <span data-ttu-id="d94e5-110">요소가 포함된 강조 표시된 선과 동일한 방식으로 `<TextBlock>` 바인딩을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d94e5-110">You define the binding the same way, as the highlighted line that contains the `<TextBlock>` element shows.</span></span>  
  
 <span data-ttu-id="d94e5-111">이 특정 예제에서는 결과가 동일합니다. <xref:System.Windows.Controls.TextBlock> `Joe`</span><span class="sxs-lookup"><span data-stu-id="d94e5-111">In this particular example, the result is the same: you have a <xref:System.Windows.Controls.TextBlock> with the text content `Joe`.</span></span> <span data-ttu-id="d94e5-112">그러나 클래스는 <xref:System.Windows.Data.ObjectDataProvider> 메서드의 결과에 바인딩하는 기능과 같은 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d94e5-112">However, the <xref:System.Windows.Data.ObjectDataProvider> class provides functionality such as the ability to bind to the result of a method.</span></span> <span data-ttu-id="d94e5-113">클래스에서 <xref:System.Windows.Data.ObjectDataProvider> 제공하는 기능이 필요한 경우 클래스를 사용하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d94e5-113">You can choose to use the <xref:System.Windows.Data.ObjectDataProvider> class if you need the functionality it provides.</span></span>  
  
 <span data-ttu-id="d94e5-114">그러나 이미 만들어진 개체에 바인딩하는 경우 다음 예제와 같이 `DataContext` in 코드를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d94e5-114">However, if you are binding to an object that has already been created, you need to set the `DataContext` in code, as in the following example.</span></span>  
  
 [!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 <span data-ttu-id="d94e5-115"><xref:System.Windows.Data.XmlDataProvider> 클래스를 사용하여 바인딩하기 위해 XML 데이터에 액세스하려면 [XMLDataProvider 및 XPath 쿼리를 사용하여 XML 데이터에 바인딩을](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d94e5-115">To access XML data for binding using the <xref:System.Windows.Data.XmlDataProvider> class, see [Bind to XML Data Using an XMLDataProvider and XPath Queries](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span></span> <span data-ttu-id="d94e5-116"><xref:System.Windows.Data.ObjectDataProvider> 클래스를 사용하여 바인딩하기 위해 XML 데이터에 액세스하려면 [XDocument, XElement 또는 XML 쿼리 결과에 대한 LINQ에 바인딩을](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d94e5-116">To access XML data for binding using the <xref:System.Windows.Data.ObjectDataProvider> class, see [Bind to XDocument, XElement, or LINQ for XML Query Results](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span></span>  
  
 <span data-ttu-id="d94e5-117">바인딩할 데이터를 지정할 수 있는 여러 가지 방법에 대한 자세한 내용은 [바인딩 소스 지정을](how-to-specify-the-binding-source.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d94e5-117">For information about many ways you can specify the data you are binding to, see [Specify the Binding Source](how-to-specify-the-binding-source.md).</span></span> <span data-ttu-id="d94e5-118">바인딩할 수 있는 데이터 유형 또는 바인딩을 위해 고유한 공통 언어 런타임(CLR) 개체를 구현하는 방법에 대한 자세한 내용은 [바인딩 소스 개요를](binding-sources-overview.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d94e5-118">For information about what types of data you can bind to or how to implement your own common language runtime (CLR) objects for binding, see [Binding Sources Overview](binding-sources-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d94e5-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d94e5-119">See also</span></span>

- [<span data-ttu-id="d94e5-120">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="d94e5-120">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="d94e5-121">방법 주제</span><span class="sxs-lookup"><span data-stu-id="d94e5-121">How-to Topics</span></span>](data-binding-how-to-topics.md)
