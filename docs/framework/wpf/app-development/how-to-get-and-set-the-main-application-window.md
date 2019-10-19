---
title: '방법: 주 응용 프로그램 창 가져오기 및 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- windows objects [WPF], setting
- setting windows objects [WPF]
- windows objects [WPF], getting
- getting windows objects [WPF]
ms.assetid: ec902bc4-4a59-46f5-8ec1-963b46789356
ms.openlocfilehash: 5894761c4b6258cbf90d369a722ffc5abca51885
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582551"
---
# <a name="how-to-get-and-set-the-main-application-window"></a><span data-ttu-id="69f77-102">방법: 주 응용 프로그램 창 가져오기 및 설정</span><span class="sxs-lookup"><span data-stu-id="69f77-102">How to: Get and Set the Main Application Window</span></span>
<span data-ttu-id="69f77-103">이 예제에서는 주 응용 프로그램 창을 가져오고 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="69f77-103">This example shows how to get and set the main application window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69f77-104">예제</span><span class="sxs-lookup"><span data-stu-id="69f77-104">Example</span></span>  
 <span data-ttu-id="69f77-105">Windows Presentation Foundation (WPF) 응용 프로그램 내에서 인스턴스화된 첫 번째 <xref:System.Windows.Window>는 기본 응용 프로그램 창으로 <xref:System.Windows.Application>에서 자동으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69f77-105">The first <xref:System.Windows.Window> that is instantiated within a Windows Presentation Foundation (WPF) application is automatically set by <xref:System.Windows.Application> as the main application window.</span></span> <span data-ttu-id="69f77-106">인스턴스화할 첫 번째 <xref:System.Windows.Window>는 시작 URI (uniform resource identifier)로 지정 된 창이 될 가능성이 높습니다 (<xref:System.Windows.Application.StartupUri%2A> 참조).</span><span class="sxs-lookup"><span data-stu-id="69f77-106">The first <xref:System.Windows.Window> to be instantiated will most likely be the window that is specified as the startup uniform resource identifier (URI) (see <xref:System.Windows.Application.StartupUri%2A>).</span></span>  
  
 <span data-ttu-id="69f77-107">코드를 사용 하 여 첫 번째 <xref:System.Windows.Window> 인스턴스화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69f77-107">The first <xref:System.Windows.Window> could also be instantiated using code.</span></span> <span data-ttu-id="69f77-108">한 가지 예는 다음과 같이 응용 프로그램을 시작 하는 동안 창을 여는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="69f77-108">One example is opening a window during application startup, like the following:</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/App.xaml.cs#firstwindowusingcodecodebehind)]
 [!code-vb[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/application.xaml.vb#firstwindowusingcodecodebehind)]  
  
 <span data-ttu-id="69f77-109">경우에 따라 첫 번째 인스턴스화된 <xref:System.Windows.Window>는 시작 화면과 같이 실제로 주 응용 프로그램 창이 아닐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69f77-109">Sometimes, the first instantiated <xref:System.Windows.Window> is not actually the main application window e.g. a splash screen.</span></span> <span data-ttu-id="69f77-110">이 경우 다음과 같이 태그를 사용 하 여 주 응용 프로그램 창을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69f77-110">In this case, you can specify the main application window using markup, like the following:</span></span>  
  
 [!code-xaml[ApplicationMainWindowSnippets#SetApplicationMainWindowXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/ApplicationMainWindowSnippets/XAML/App.xaml#setapplicationmainwindowxaml)]  
  
 <span data-ttu-id="69f77-111">주 창이 자동 또는 수동으로 지정 되는지 여부에 따라 다음과 같은 코드를 사용 하 여 <xref:System.Windows.Application.MainWindow%2A>에서 주 창을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69f77-111">Whether the main window is specified automatically or manually, you can get the main window from <xref:System.Windows.Application.MainWindow%2A> using the following code, like the following:</span></span>  
  
 [!code-csharp[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationMainWindowSnippets/CSharp/App.xaml.cs#getapplicationmainwindowcode)]
 [!code-vb[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationMainWindowSnippets/visualbasic/application.xaml.vb#getapplicationmainwindowcode)]
