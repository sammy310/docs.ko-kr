---
title: '방법: 주 응용 프로그램 창 가져오기 및 설정'
description: Windows Presentation Foundation (WPF) 응용 프로그램 내에서 주 응용 프로그램 창을 가져오고 설정 하려면 다음 예제를 따르세요.
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
ms.openlocfilehash: 9bb5bce9b90482796acd8c62e77dc8bd9a850eeb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622681"
---
# <a name="how-to-get-and-set-the-main-application-window"></a><span data-ttu-id="2bcbd-103">방법: 주 응용 프로그램 창 가져오기 및 설정</span><span class="sxs-lookup"><span data-stu-id="2bcbd-103">How to: Get and Set the Main Application Window</span></span>
<span data-ttu-id="2bcbd-104">이 예제에서는 주 응용 프로그램 창을 가져오고 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2bcbd-104">This example shows how to get and set the main application window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2bcbd-105">예제</span><span class="sxs-lookup"><span data-stu-id="2bcbd-105">Example</span></span>  
 <span data-ttu-id="2bcbd-106"><xref:System.Windows.Window>Windows Presentation Foundation (WPF) 응용 프로그램 내에서 인스턴스화된 첫 번째는 <xref:System.Windows.Application> 주 응용 프로그램 창으로에 의해 자동으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2bcbd-106">The first <xref:System.Windows.Window> that is instantiated within a Windows Presentation Foundation (WPF) application is automatically set by <xref:System.Windows.Application> as the main application window.</span></span> <span data-ttu-id="2bcbd-107">가장 먼저 <xref:System.Windows.Window> 인스턴스화할 것은 시작 URI (uniform resource identifier)로 지정 된 창이 될 가능성이 높습니다 (참조 <xref:System.Windows.Application.StartupUri%2A> ).</span><span class="sxs-lookup"><span data-stu-id="2bcbd-107">The first <xref:System.Windows.Window> to be instantiated will most likely be the window that is specified as the startup uniform resource identifier (URI) (see <xref:System.Windows.Application.StartupUri%2A>).</span></span>  
  
 <span data-ttu-id="2bcbd-108">첫 번째는 <xref:System.Windows.Window> 코드를 사용 하 여 인스턴스화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bcbd-108">The first <xref:System.Windows.Window> could also be instantiated using code.</span></span> <span data-ttu-id="2bcbd-109">한 가지 예는 다음과 같이 응용 프로그램을 시작 하는 동안 창을 여는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2bcbd-109">One example is opening a window during application startup, like the following:</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/App.xaml.cs#firstwindowusingcodecodebehind)]
 [!code-vb[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/application.xaml.vb#firstwindowusingcodecodebehind)]  
  
 <span data-ttu-id="2bcbd-110">경우에 따라 처음 인스턴스화되는 <xref:System.Windows.Window> 시작 화면과 같은 주 응용 프로그램 창이 아닐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bcbd-110">Sometimes, the first instantiated <xref:System.Windows.Window> is not actually the main application window e.g. a splash screen.</span></span> <span data-ttu-id="2bcbd-111">이 경우 다음과 같이 태그를 사용 하 여 주 응용 프로그램 창을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bcbd-111">In this case, you can specify the main application window using markup, like the following:</span></span>  
  
 [!code-xaml[ApplicationMainWindowSnippets#SetApplicationMainWindowXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/ApplicationMainWindowSnippets/XAML/App.xaml#setapplicationmainwindowxaml)]  
  
 <span data-ttu-id="2bcbd-112">주 창이 자동 또는 수동으로 지정 되었는지 여부에 관계 없이 다음과 <xref:System.Windows.Application.MainWindow%2A> 같은 코드를 사용 하 여 주 창을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bcbd-112">Whether the main window is specified automatically or manually, you can get the main window from <xref:System.Windows.Application.MainWindow%2A> using the following code, like the following:</span></span>  
  
 [!code-csharp[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationMainWindowSnippets/CSharp/App.xaml.cs#getapplicationmainwindowcode)]
 [!code-vb[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationMainWindowSnippets/visualbasic/application.xaml.vb#getapplicationmainwindowcode)]
