---
title: '방법: 웹 서비스 바인딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], Web service
- Web service binding [WPF]
- data binding [WPF], Web service
ms.assetid: 77e2d373-69ba-4cbd-b6f5-2c83c38fc98b
ms.openlocfilehash: d752f4815de16daa466302881116e80aceec6edf
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040900"
---
# <a name="how-to-bind-to-a-web-service"></a><span data-ttu-id="14e27-102">방법: 웹 서비스 바인딩</span><span class="sxs-lookup"><span data-stu-id="14e27-102">How to: Bind to a Web Service</span></span>
<span data-ttu-id="14e27-103">이 예제에서는 웹 서비스 메서드 호출에서 반환 되는 개체에 바인딩하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="14e27-103">This example shows how to bind to objects returned by Web service method calls.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14e27-104">예제</span><span class="sxs-lookup"><span data-stu-id="14e27-104">Example</span></span>  
 <span data-ttu-id="14e27-105">이 예제에서는 [MSDN/TechNet Publishing 시스템 (MTPS) 콘텐츠 서비스](https://go.microsoft.com/fwlink/?LinkId=95677) 를 사용 하 여 지정 된 문서에서 지원 되는 언어 목록을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="14e27-105">This example uses the [MSDN/TechNet Publishing System (MTPS) Content Service](https://go.microsoft.com/fwlink/?LinkId=95677) to retrieve the list of languages supported by a specified document.</span></span>  
  
 <span data-ttu-id="14e27-106">웹 서비스를 호출 하기 전에 해당 웹 서비스에 대 한 참조를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14e27-106">Before you call a Web service, you need to create a reference to it.</span></span> <span data-ttu-id="14e27-107">Visual Studio를 사용 하 여 MTPS 서비스에 대 한 웹 참조를 만들려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="14e27-107">To create a Web reference to the MTPS service using Visual Studio, follow the following steps:</span></span>  
  
1. <span data-ttu-id="14e27-108">Visual Studio에서 프로젝트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="14e27-108">Open your project in Visual Studio.</span></span>  
  
2. <span data-ttu-id="14e27-109">**프로젝트** 메뉴에서 **웹 참조 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="14e27-109">From the **Project** menu, click **Add Web Reference**.</span></span>  
  
3. <span data-ttu-id="14e27-110">대화 상자에서 **URL** 을 [http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl](https://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl)설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="14e27-110">In the dialog box, set the **URL** to [http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl](https://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl).</span></span>  
  
4. <span data-ttu-id="14e27-111">**Go** 를 누르고 **참조를 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="14e27-111">Press **Go** and then **Add Reference**.</span></span>  
  
 <span data-ttu-id="14e27-112">그런 다음 웹 서비스 메서드를 호출 하 고 적절 한 컨트롤 또는 창의 <xref:System.Windows.FrameworkElement.DataContext%2A>을 반환 된 개체로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="14e27-112">Next, you call the Web service method and set the <xref:System.Windows.FrameworkElement.DataContext%2A> of the appropriate control or window to the returned object.</span></span> <span data-ttu-id="14e27-113">MTPS 서비스의 `GetContent` 메서드는 `getContentRequest` 개체에 대 한 참조를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="14e27-113">The `GetContent` method of the MTPS service takes a reference to the `getContentRequest` object.</span></span> <span data-ttu-id="14e27-114">따라서 다음 예제에서는 먼저 요청 개체를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="14e27-114">Therefore, the following example first sets up a request object:</span></span>  
  
 [!code-csharp[BindToWebService#Namespace](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#namespace)]
 [!code-vb[BindToWebService#Namespace](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#namespace)]  
[!code-csharp[BindToWebService#WebServiceCall](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#webservicecall)]
[!code-vb[BindToWebService#WebServiceCall](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#webservicecall)]  
  
 <span data-ttu-id="14e27-115"><xref:System.Windows.FrameworkElement.DataContext%2A> 설정 된 후에는 <xref:System.Windows.FrameworkElement.DataContext%2A>가 설정 된 개체의 속성에 대 한 바인딩을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14e27-115">After the <xref:System.Windows.FrameworkElement.DataContext%2A> has been set, you can create bindings to the properties of the object that the <xref:System.Windows.FrameworkElement.DataContext%2A> has been set to.</span></span> <span data-ttu-id="14e27-116">이 예제에서 <xref:System.Windows.FrameworkElement.DataContext%2A>는 `GetContent` 메서드에서 반환 되는 `getContentResponse` 개체로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14e27-116">In this example, the <xref:System.Windows.FrameworkElement.DataContext%2A> is set to the `getContentResponse` object returned by the `GetContent` method.</span></span> <span data-ttu-id="14e27-117">다음 예제에서 <xref:System.Windows.Controls.ItemsControl>는에 바인딩되고 `getContentResponse``availableVersionsAndLocales`의 `locale` 값을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="14e27-117">In the following example, the <xref:System.Windows.Controls.ItemsControl> binds to and displays the `locale` values of `availableVersionsAndLocales` of `getContentResponse`.</span></span>  
  
 [!code-xaml[BindToWebService#Binding](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml#binding)]  
  
 <span data-ttu-id="14e27-118">`getContentResponse`구조에 대 한 자세한 내용은 [콘텐츠 서비스 설명서](https://services.msdn.microsoft.com/ContentServices/ContentService.asmx)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="14e27-118">For information about the structure of `getContentResponse`, see [Content Service documentation](https://services.msdn.microsoft.com/ContentServices/ContentService.asmx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14e27-119">참조</span><span class="sxs-lookup"><span data-stu-id="14e27-119">See also</span></span>

- [<span data-ttu-id="14e27-120">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="14e27-120">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="14e27-121">바인딩 소스 개요</span><span class="sxs-lookup"><span data-stu-id="14e27-121">Binding Sources Overview</span></span>](binding-sources-overview.md)
- [<span data-ttu-id="14e27-122">XAML의 바인딩에 사용할 수 있는 데이터 만들기</span><span class="sxs-lookup"><span data-stu-id="14e27-122">Make Data Available for Binding in XAML</span></span>](how-to-make-data-available-for-binding-in-xaml.md)
