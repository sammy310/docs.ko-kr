---
title: '방법: XDocument, XElement 또는 LINQ for XML 쿼리 결과에 바인딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], binding to XDocument
- data binding [WPF], binding to XElement
ms.assetid: 6a629a49-fe1c-465d-b76a-3dcbf4307b64
ms.openlocfilehash: 070f67f30613d4522a48e08fd1c208fbe5887525
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920119"
---
# <a name="how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results"></a><span data-ttu-id="12eeb-102">방법: XDocument, XElement 또는 LINQ for XML 쿼리 결과에 바인딩</span><span class="sxs-lookup"><span data-stu-id="12eeb-102">How to: Bind to XDocument, XElement, or LINQ for XML Query Results</span></span>

<span data-ttu-id="12eeb-103">이 예제에서는 <xref:System.Xml.Linq.XDocument>를 사용 하 여 <xref:System.Windows.Controls.ItemsControl>에 XML 데이터를 바인딩하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="12eeb-103">This example demonstrates how to bind XML data to an <xref:System.Windows.Controls.ItemsControl> using <xref:System.Xml.Linq.XDocument>.</span></span>

## <a name="example"></a><span data-ttu-id="12eeb-104">예제</span><span class="sxs-lookup"><span data-stu-id="12eeb-104">Example</span></span>

<span data-ttu-id="12eeb-105">다음 XAML 코드는 <xref:System.Windows.Controls.ItemsControl>를 정의 하 고 `http://planetsNS` XML 네임 스페이스에 `Planet` 형식의 데이터에 대 한 데이터 템플릿을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="12eeb-105">The following XAML code defines an <xref:System.Windows.Controls.ItemsControl> and includes a data template for data of type `Planet` in the `http://planetsNS` XML namespace.</span></span> <span data-ttu-id="12eeb-106">네임스페이스를 차지하는 XML 데이터 형식은 중괄호에서 네임스페이스를 포함해야 하고 XAML 태그 확장이 표시되는 위치에 표시되는 경우 중괄호 이스케이프 시퀀스를 가진 네임스페이스 앞에 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12eeb-106">An XML data type that occupies a namespace must include the namespace in braces, and if it appears where a XAML markup extension could appear, it must precede the namespace with a brace escape sequence.</span></span> <span data-ttu-id="12eeb-107">이 코드는 <xref:System.Xml.Linq.XElement> 클래스의 <xref:System.Xml.Linq.XContainer.Element%2A> 및 <xref:System.Xml.Linq.XElement.Attribute%2A> 메서드에 해당 하는 동적 속성에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="12eeb-107">This code binds to dynamic properties that correspond to the <xref:System.Xml.Linq.XContainer.Element%2A> and <xref:System.Xml.Linq.XElement.Attribute%2A> methods of the <xref:System.Xml.Linq.XElement> class.</span></span> <span data-ttu-id="12eeb-108">동적 속성을 사용하면 XAML을 메서드의 이름을 공유하는 동적 속성에 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12eeb-108">Dynamic properties enable XAML to bind to dynamic properties that share the names of methods.</span></span> <span data-ttu-id="12eeb-109">자세히 알아보려면 [LINQ to XML 동적 속성](linq-to-xml-dynamic-properties.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="12eeb-109">To learn more, see [LINQ to XML dynamic properties](linq-to-xml-dynamic-properties.md).</span></span> <span data-ttu-id="12eeb-110">XML의 기본 네임스페이스 선언이 특성 이름에 적용되지 않는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="12eeb-110">Notice how the default namespace declaration for the XML does not apply to attribute names.</span></span>

[!code-xaml[XLinqExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]
[!code-xaml[XLinqExample#ItemsControl](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#itemscontrol)]

<span data-ttu-id="12eeb-111">다음 C# 코드는<xref:System.Xml.Linq.XDocument.Load%2A>를 호출 하 고`http://planetsNS`XML 네임 스페이스에서`SolarSystemPlanets`라는 요소의 모든 하위 요소로 스택 패널 데이터 컨텍스트를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="12eeb-111">The following C# code calls <xref:System.Xml.Linq.XDocument.Load%2A> and sets the stack panel data context to all subelements of the element named `SolarSystemPlanets` in the `http://planetsNS` XML namespace.</span></span>

[!code-csharp[XLinqExample#LoadDCFromFile](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromfile)]
[!code-vb[XLinqExample#LoadDCFromFile](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromfile)]

<span data-ttu-id="12eeb-112"><xref:System.Windows.Data.ObjectDataProvider>를 사용 하 여 XML 데이터를 XAML 리소스로 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12eeb-112">XML data can be stored as a XAML resource using <xref:System.Windows.Data.ObjectDataProvider>.</span></span> <span data-ttu-id="12eeb-113">전체 예제는 [l2dbform.xaml 소스 코드](l2dbform-xaml-source-code.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="12eeb-113">For a complete example, see  [L2DBForm.xaml source code](l2dbform-xaml-source-code.md).</span></span> <span data-ttu-id="12eeb-114">다음 샘플에서는 코드가 데이터 컨텍스트를 개체 리소스로 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="12eeb-114">The following sample shows how code can set the data context to an object resource.</span></span>

[!code-csharp[XLinqExample#LoadDCFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromxaml)]
[!code-vb[XLinqExample#LoadDCFromXAML](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromxaml)]

<span data-ttu-id="12eeb-115"><xref:System.Xml.Linq.XContainer.Element%2A> 및 <xref:System.Xml.Linq.XElement.Attribute%2A>에 매핑되는 동적 속성은 XAML 내에서 유연성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="12eeb-115">The dynamic properties that map to <xref:System.Xml.Linq.XContainer.Element%2A> and <xref:System.Xml.Linq.XElement.Attribute%2A> provide flexibility within XAML.</span></span> <span data-ttu-id="12eeb-116">코드는 LINQ for XML 쿼리의 결과에 바인딩될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12eeb-116">Your code can also bind to the results of a LINQ for XML query.</span></span> <span data-ttu-id="12eeb-117">이 예제는 요소 값으로 정렬된 쿼리 결과에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="12eeb-117">This example binds to query results ordered by an element value.</span></span>

[!code-csharp[XLinqExample#BindToResults](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#bindtoresults)]
[!code-vb[XLinqExample#BindToResults](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#bindtoresults)]

## <a name="see-also"></a><span data-ttu-id="12eeb-118">참조</span><span class="sxs-lookup"><span data-stu-id="12eeb-118">See also</span></span>

- [<span data-ttu-id="12eeb-119">바인딩 소스 개요</span><span class="sxs-lookup"><span data-stu-id="12eeb-119">Binding Sources Overview</span></span>](binding-sources-overview.md)
- [<span data-ttu-id="12eeb-120">LINQ to XML로 WPF 데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="12eeb-120">WPF Data Binding with LINQ to XML Overview</span></span>](wpf-data-binding-with-linq-to-xml-overview.md)
- [<span data-ttu-id="12eeb-121">LINQ to XML 예제를 사용한 WPF 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="12eeb-121">WPF Data Binding Using LINQ to XML Example</span></span>](linq-to-xml-data-binding-sample.md)
- [<span data-ttu-id="12eeb-122">LINQ to XML 동적 속성</span><span class="sxs-lookup"><span data-stu-id="12eeb-122">LINQ to XML Dynamic Properties</span></span>](linq-to-xml-dynamic-properties.md)
