---
title: '방법: 애플리케이션 범위 리소스 사전 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dictionaries [WPF], resource
- resource dictionaries [WPF], application-scope
- application-scope resource dictionaries
ms.assetid: 53857682-bd2c-4f2c-8f25-1307d0b451a2
ms.openlocfilehash: 5bfb3ed0304598a5acf4b7682bf4a4169c5153d1
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459802"
---
# <a name="how-to-use-an-application-scope-resource-dictionary"></a><span data-ttu-id="05a6d-102">방법: 애플리케이션 범위 리소스 사전 사용</span><span class="sxs-lookup"><span data-stu-id="05a6d-102">How to: Use an Application-Scope Resource Dictionary</span></span>
<span data-ttu-id="05a6d-103">이 예제에서는 애플리케이션 범위 사용자 지정 리소스 사전을 정의하고 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="05a6d-103">This example shows how to define and use an application-scope custom resource dictionary.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05a6d-104">예제</span><span class="sxs-lookup"><span data-stu-id="05a6d-104">Example</span></span>  
 <span data-ttu-id="05a6d-105"><xref:System.Windows.Application> <xref:System.Windows.Application.Resources%2A>공유 리소스에 대 한 응용 프로그램 범위 저장소를 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a6d-105"><xref:System.Windows.Application> exposes an application-scope store for shared resources: <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="05a6d-106">기본적으로 <xref:System.Windows.Application.Resources%2A> 속성은 <xref:System.Windows.ResourceDictionary> 형식의 인스턴스를 사용 하 여 초기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05a6d-106">By default, the <xref:System.Windows.Application.Resources%2A> property is initialized with an instance of the <xref:System.Windows.ResourceDictionary> type.</span></span> <span data-ttu-id="05a6d-107"><xref:System.Windows.Application.Resources%2A>를 사용 하 여 응용 프로그램 범위 속성을 가져오고 설정할 때이 인스턴스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a6d-107">You use this instance when you get and set application-scope properties using <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="05a6d-108">자세한 내용은 [방법: 응용 프로그램 범위 리소스 가져오기 및 설정](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348547(v=vs.100))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="05a6d-108">For more information, see [How to: Get and Set an Application-Scope Resource](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348547(v=vs.100)).</span></span>
  
 <span data-ttu-id="05a6d-109"><xref:System.Windows.Application.Resources%2A>사용 하 여 설정 하는 리소스가 여러 개 있는 경우에는 대신 사용자 지정 리소스 사전을 사용 하 여 해당 리소스를 저장 하 고 대신 <xref:System.Windows.Application.Resources%2A>를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05a6d-109">If you have multiple resources that you set using <xref:System.Windows.Application.Resources%2A>, you can instead use a custom resource dictionary to store those resources and set <xref:System.Windows.Application.Resources%2A> with it instead.</span></span> <span data-ttu-id="05a6d-110">다음에서는 XAML을 사용 하 여 사용자 지정 리소스 사전을 선언 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="05a6d-110">The following shows how you declare a custom resource dictionary using XAML.</span></span>
  
 [!code-xaml[HOWTOResourceDictionaries#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MyResourceDictionary.xaml#1)]  
  
 <span data-ttu-id="05a6d-111"><xref:System.Windows.Application.Resources%2A>를 사용 하 여 전체 리소스 사전을 바꾸면 각 테마가 단일 리소스 사전에 캡슐화 되는 응용 프로그램 범위 테마를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05a6d-111">Swapping entire resource dictionaries using <xref:System.Windows.Application.Resources%2A> allows you to support application-scope themes, where each theme is encapsulated by a single resource dictionary.</span></span> <span data-ttu-id="05a6d-112">다음 예에서는 <xref:System.Windows.ResourceDictionary>를 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="05a6d-112">The following example shows how to set the <xref:System.Windows.ResourceDictionary>.</span></span>  
  
 [!code-xaml[HOWTOResourceDictionaries#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/App.xaml#2)]  
  
 <span data-ttu-id="05a6d-113">다음은 XAML의 <xref:System.Windows.Application.Resources%2A>에 의해 노출 되는 리소스 사전에서 응용 프로그램 범위 리소스를 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="05a6d-113">The following shows how you can get application-scope resources from the resource dictionary exposed by <xref:System.Windows.Application.Resources%2A> in XAML.</span></span>  
  
 [!code-xaml[HOWTOResourceDictionaries#4](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml#4)]  
  
 <span data-ttu-id="05a6d-114">다음 예제에서는 코드에서 리소스를 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="05a6d-114">The following shows how you can also get the resources in code.</span></span>  
  
 [!code-csharp[HOWTOResourceDictionaries#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml.cs#3)]
 [!code-vb[HOWTOResourceDictionaries#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToResourceDictionaries/VB/MainWindow.xaml.vb#3)]  
  
 <span data-ttu-id="05a6d-115"><xref:System.Windows.Application.Resources%2A>를 사용할 때 고려해 야 할 두 가지 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05a6d-115">There are two considerations to make when using <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="05a6d-116">먼저 사전 *키* 가 개체 이므로 속성 값을 설정 하 고 가져올 때 정확히 동일한 개체 인스턴스를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a6d-116">First, the dictionary *key* is an object, so you must use exactly the same object instance when both setting and getting a property value.</span></span> <span data-ttu-id="05a6d-117">문자열을 사용 하는 경우 키가 대/소문자를 구분 합니다. 둘째, 사전 *값* 은 개체 이므로 속성 값을 가져올 때 값을 원하는 형식으로 변환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a6d-117">(Note that the key is case-sensitive when using a string.) Second, the dictionary *value* is an object, so you will have to convert the value to the desired type when getting a property value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05a6d-118">참조</span><span class="sxs-lookup"><span data-stu-id="05a6d-118">See also</span></span>

- <xref:System.Windows.ResourceDictionary>
- <xref:System.Windows.Application.Resources%2A>
- [<span data-ttu-id="05a6d-119">XAML 리소스</span><span class="sxs-lookup"><span data-stu-id="05a6d-119">XAML Resources</span></span>](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [<span data-ttu-id="05a6d-120">병합된 리소스 사전</span><span class="sxs-lookup"><span data-stu-id="05a6d-120">Merged Resource Dictionaries</span></span>](../advanced/merged-resource-dictionaries.md)
