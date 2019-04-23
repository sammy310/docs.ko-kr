---
title: '방법: ResourceDictionary를 사용하여 지역화 가능한 문자열 리소스 관리'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resources [WPF], packaging string resources
- packaging string resources [WPF]
- ResourceDictionary [WPF]
- localization [WPF], packaging string resources
ms.assetid: 19e7d9a5-20df-4ad3-b157-fe6515902e5e
ms.openlocfilehash: b56a307ed31fc8f7573215eac70350ac5e4b9de1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59772117"
---
# <a name="how-to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a><span data-ttu-id="6d7e9-102">방법: ResourceDictionary를 사용하여 지역화 가능한 문자열 리소스 관리</span><span class="sxs-lookup"><span data-stu-id="6d7e9-102">How to: Use a ResourceDictionary to Manage Localizable String Resources</span></span>
<span data-ttu-id="6d7e9-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.ResourceDictionary> 패키지 지역화 가능한 문자열 리소스 Windows Presentation Foundation (WPF) 응용 프로그램에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d7e9-103">This example shows how to use a <xref:System.Windows.ResourceDictionary> to package localizable string resources for Windows Presentation Foundation (WPF) applications.</span></span>  
  
### <a name="to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a><span data-ttu-id="6d7e9-104">ResourceDictionary를 사용하여 지역화 가능한 문자열 리소스를 관리하려면</span><span class="sxs-lookup"><span data-stu-id="6d7e9-104">To use a ResourceDictionary to manage localizable string resources</span></span>  
  
1. <span data-ttu-id="6d7e9-105">만들기는 <xref:System.Windows.ResourceDictionary> 지역화 하려는 문자열을 포함 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d7e9-105">Create a <xref:System.Windows.ResourceDictionary> that contains the strings you would like to localize.</span></span> <span data-ttu-id="6d7e9-106">다음 코드는 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6d7e9-106">The following code shows an example.</span></span>  
  
     [!code-xaml[StringLocalizationSample#StringResourceDictionary](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/StringResources.xaml#stringresourcedictionary)]  
  
     <span data-ttu-id="6d7e9-107">이 코드에서는 문자열 리소스를 정의 `localizedMessage`, 형식 <xref:System.String>에서 <xref:System> mscorlib.dll의 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="6d7e9-107">This code defines a string resource, `localizedMessage`, of type <xref:System.String>, from the <xref:System> namespace in mscorlib.dll.</span></span>  
  
2. <span data-ttu-id="6d7e9-108">추가 된 <xref:System.Windows.ResourceDictionary> 응용 프로그램에 다음 코드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d7e9-108">Add the <xref:System.Windows.ResourceDictionary> to your application, using the following code.</span></span>  
  
     [!code-xaml[StringLocalizationSample#ReferencingStringResourceDictionary](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/App.xaml#referencingstringresourcedictionary)]  
  
3. <span data-ttu-id="6d7e9-109">태그에서 문자열 리소스를 사용 하 여 사용 하 여 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 다음과 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d7e9-109">Use the string resource from markup, using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] like the following.</span></span>  
  
     [!code-xaml[StringLocalizationSample#GetLocalizedResourceFromMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml#getlocalizedresourcefrommarkup)]  
  
4. <span data-ttu-id="6d7e9-110">코드 숨김에서 다음과 같은 코드를 사용하여 문자열 리소스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6d7e9-110">Use the string resource from code-behind, using code like the following.</span></span>  
  
     [!code-csharp[StringLocalizationSample#GetLocalizedResourceFromCode](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml.cs#getlocalizedresourcefromcode)]
     [!code-vb[StringLocalizationSample#GetLocalizedResourceFromCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StringLocalizationSample/VisualBasic/MainWindow.xaml.vb#getlocalizedresourcefromcode)]  
  
5. <span data-ttu-id="6d7e9-111">애플리케이션을 지역화합니다.</span><span class="sxs-lookup"><span data-stu-id="6d7e9-111">Localize the application.</span></span> <span data-ttu-id="6d7e9-112">자세한 내용은 [응용 프로그램 지역화](how-to-localize-an-application.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6d7e9-112">For more information, see [Localize an Application](how-to-localize-an-application.md).</span></span>
