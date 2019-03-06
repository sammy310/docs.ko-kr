---
title: '연습: Win32에서 WPF 시계 호스팅'
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
ms.openlocfilehash: a58d7e5848ccd62b889b8a7645c08a35822b3352
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352726"
---
# <a name="walkthrough-hosting-a-wpf-clock-in-win32"></a><span data-ttu-id="73df0-102">연습: Win32에서 WPF 시계 호스팅</span><span class="sxs-lookup"><span data-stu-id="73df0-102">Walkthrough: Hosting a WPF Clock in Win32</span></span>
<span data-ttu-id="73df0-103">삽입할 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 내 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 응용 프로그램을 사용 하 여 <xref:System.Windows.Interop.HwndSource>를 포함 하는 HWND를 제공 하는 프로그램 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠.</span><span class="sxs-lookup"><span data-stu-id="73df0-103">To put [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] applications, use <xref:System.Windows.Interop.HwndSource>, which provides the HWND that contains your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span> <span data-ttu-id="73df0-104">먼저 만듭니다는 <xref:System.Windows.Interop.HwndSource>, CreateWindow와 유사한 매개 변수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-104">First you create the <xref:System.Windows.Interop.HwndSource>, giving it parameters similar to CreateWindow.</span></span>  <span data-ttu-id="73df0-105">그런 합니다 <xref:System.Windows.Interop.HwndSource> 에 대 한는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 내부에 넣으려는 콘텐츠입니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-105">Then you tell the <xref:System.Windows.Interop.HwndSource> about the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content you want inside it.</span></span>  <span data-ttu-id="73df0-106">HWND를 마지막으로 표시 된 <xref:System.Windows.Interop.HwndSource>합니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-106">Finally, you get the HWND out of the <xref:System.Windows.Interop.HwndSource>.</span></span> <span data-ttu-id="73df0-107">이 연습에는 혼합을 만드는 방법을 보여 줍니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 안쪽 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 운영 체제를 다시 구현 하는 응용 프로그램 **날짜 및 시간 속성** 대화 합니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-107">This walkthrough illustrates how to create a mixed [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] application that reimplements the operating system **Date and Time Properties** dialog.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="73df0-108">전제 조건</span><span class="sxs-lookup"><span data-stu-id="73df0-108">Prerequisites</span></span>  
 <span data-ttu-id="73df0-109">참조 [WPF 및 Win32 상호 운용성](wpf-and-win32-interoperation.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-109">See [WPF and Win32 Interoperation](wpf-and-win32-interoperation.md).</span></span>  
  
## <a name="how-to-use-this-tutorial"></a><span data-ttu-id="73df0-110">이 자습서를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="73df0-110">How to Use This Tutorial</span></span>  
 <span data-ttu-id="73df0-111">이 자습서는 상호 운용 애플리케이션을 생성하는 중요한 단계에 대해 중점적으로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-111">This tutorial concentrates on the important steps of producing an interoperation application.</span></span> <span data-ttu-id="73df0-112">자습서 샘플을 받으며 [Win32 시계 상호 운용 샘플](https://go.microsoft.com/fwlink/?LinkID=160051)하지만 샘플은 최종 제품의 반사 합니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-112">The tutorial is backed by a sample, [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051), but that sample is reflective of the end product.</span></span> <span data-ttu-id="73df0-113">기존 시작 된 것 처럼이 자습서의 단계를 설명 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 자신만의 프로젝트 및 아마도 기존 프로젝트를 추가 하는 호스팅된 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-113">This tutorial documents the steps as if you were starting with an existing [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project of your own, perhaps a pre-existing project, and you were adding a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] to your application.</span></span> <span data-ttu-id="73df0-114">최종 제품을 비교할 수 있습니다 [Win32 시계 상호 운용 샘플](https://go.microsoft.com/fwlink/?LinkID=160051)합니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-114">You can compare your end product with [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051).</span></span>  
  
## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a><span data-ttu-id="73df0-115">Win32 내에서 Windows Presentation Framework의 연습(HwndSource)</span><span class="sxs-lookup"><span data-stu-id="73df0-115">A Walkthrough of Windows Presentation Framework Inside Win32 (HwndSource)</span></span>  
 <span data-ttu-id="73df0-116">다음 그래픽에서는 이 자습서의 의도된 최종 제품을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-116">The following graphic shows the intended end product of this tutorial:</span></span>  
  
 <span data-ttu-id="73df0-117">![날짜 및 시간 속성 대화 상자](./media/interoparch06.PNG "InteropArch06")</span><span class="sxs-lookup"><span data-stu-id="73df0-117">![Date and Time Properties dialog box](./media/interoparch06.PNG "InteropArch06")</span></span>  
  
 <span data-ttu-id="73df0-118">C + +를 만들어이 대화 상자를 다시 만들 수 있습니다 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 프로젝트에서 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], 및 대화 상자 편집기를 사용 하 여 다음을 만들려면:</span><span class="sxs-lookup"><span data-stu-id="73df0-118">You can recreate this dialog by creating C++ [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], and using the dialog editor to create the following:</span></span>  
  
 <span data-ttu-id="73df0-119">![날짜 및 시간 속성 대화 상자](./media/interoparch07.PNG "InteropArch07")</span><span class="sxs-lookup"><span data-stu-id="73df0-119">![Date and Time Properties dialog box](./media/interoparch07.PNG "InteropArch07")</span></span>  
  
 <span data-ttu-id="73df0-120">(사용할 필요가 없습니다 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] 데 <xref:System.Windows.Interop.HwndSource>, 및 c + +를 사용 하 여 쓸 필요가 없습니다 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 프로그램 이지만이 수행 하는 일반적인 방식 이며 단계별 자습서 설명에 적합).</span><span class="sxs-lookup"><span data-stu-id="73df0-120">(You do not need to use [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] to use <xref:System.Windows.Interop.HwndSource>, and you do not need to use C++ to write [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] programs, but this is a fairly typical way to do it, and lends itself well to a stepwise tutorial explanation).</span></span>  
  
 <span data-ttu-id="73df0-121">넣으려면 5 개의 배치 하기 위해 수행 해야 할는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 시계를 대화 상자:</span><span class="sxs-lookup"><span data-stu-id="73df0-121">You need to accomplish five particular substeps in order to put a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock into the dialog:</span></span>  
  
1.  <span data-ttu-id="73df0-122">사용 하도록 설정 하 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 관리 되는 코드를 호출 하는 프로젝트 (**/clr**)에서 프로젝트 설정을 변경 하 여 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]입니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-122">Enable your [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project to call managed code (**/clr**) by changing project settings in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)].</span></span>  
  
2.  <span data-ttu-id="73df0-123">만들기는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> 별도의 DLL입니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-123">Create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> in a separate DLL.</span></span>  
  
3.  <span data-ttu-id="73df0-124">에 넣을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> 안에 <xref:System.Windows.Interop.HwndSource>합니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-124">Put that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> inside an <xref:System.Windows.Interop.HwndSource>.</span></span>  
  
4.  <span data-ttu-id="73df0-125">에 대 한 HWND를 가져오려면 <xref:System.Windows.Controls.Page> 를 사용 하는 <xref:System.Windows.Interop.HwndSource.Handle%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-125">Get an HWND for that <xref:System.Windows.Controls.Page> using the <xref:System.Windows.Interop.HwndSource.Handle%2A> property.</span></span>  
  
5.  <span data-ttu-id="73df0-126">사용 하 여 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 클수록 내의 HWND를 배치할 위치를 결정 하 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="73df0-126">Use [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] to decide where to place the HWND within the larger [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] application</span></span>  
  
## <a name="clr"></a><span data-ttu-id="73df0-127">/clr</span><span class="sxs-lookup"><span data-stu-id="73df0-127">/clr</span></span>  
 <span data-ttu-id="73df0-128">이 관리 되지 않는 첫 번째 단계는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 관리 코드를 호출할 수 있는 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-128">The first step is to turn this unmanaged [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project into one that can call managed code.</span></span>  <span data-ttu-id="73df0-129">사용 및 사용에 대 한 기본 메서드를 조정 하려면 필요한 Dll에 연결 하는 /clr 컴파일러 옵션을 사용 하면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-129">You use the /clr compiler option, which will link to the necessary DLLs you want to use, and adjust the Main method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="73df0-130">C + + 프로젝트 내에서 관리 코드의 사용할 수 있도록 합니다. Win32clock 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-130">To enable the use of managed code inside the C++ project: Right-click on win32clock project and select **Properties**.</span></span>  <span data-ttu-id="73df0-131">에 **일반적인** 속성 페이지 (기본값), 공용 언어 런타임 지원 변경 `/clr`합니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-131">On the **General** property page (the default), change Common Language Runtime support to `/clr`.</span></span>  
  
 <span data-ttu-id="73df0-132">그런 다음에 대 한 필요한 Dll에 대 한 참조를 추가 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll, PresentationFramework.dll, System.dll, WindowsBase.dll, UIAutomationProvider.dll 및 UIAutomationTypes.dll 합니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-132">Next, add references to DLLs necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll, PresentationFramework.dll, System.dll, WindowsBase.dll, UIAutomationProvider.dll, and UIAutomationTypes.dll.</span></span> <span data-ttu-id="73df0-133">다음 지침에서는 운영 체제가 C: 드라이브에 설치되어 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-133">(Following instructions assume the operating system is installed on C: drive.)</span></span>  
  
1.  <span data-ttu-id="73df0-134">Win32clock 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **참조 하는 중...** , 및 해당 대화 상자 내에서:</span><span class="sxs-lookup"><span data-stu-id="73df0-134">Right-click win32clock project and select **References...**, and inside that dialog:</span></span>  
  
2.  <span data-ttu-id="73df0-135">Win32clock 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **참조 하는 중...** .</span><span class="sxs-lookup"><span data-stu-id="73df0-135">Right-click win32clock project and select **References...**.</span></span>  
  
3.  <span data-ttu-id="73df0-136">클릭 **새 참조 추가**찾아보기 탭 클릭, C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll을 입력 한 확인을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-136">Click **Add New Reference**, click Browse tab, enter C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll, and click OK.</span></span>  
  
4.  <span data-ttu-id="73df0-137">PresentationFramework.dll를 반복 합니다. C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span><span class="sxs-lookup"><span data-stu-id="73df0-137">Repeat for PresentationFramework.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span></span>  
  
5.  <span data-ttu-id="73df0-138">WindowsBase.dll를 반복 합니다. C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.</span><span class="sxs-lookup"><span data-stu-id="73df0-138">Repeat for WindowsBase.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.</span></span>  
  
6.  <span data-ttu-id="73df0-139">UIAutomationTypes.dll를 반복 합니다. C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span><span class="sxs-lookup"><span data-stu-id="73df0-139">Repeat for UIAutomationTypes.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span></span>  
  
7.  <span data-ttu-id="73df0-140">UIAutomationProvider.dll를 반복 합니다. C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span><span class="sxs-lookup"><span data-stu-id="73df0-140">Repeat for UIAutomationProvider.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span></span>  
  
8.  <span data-ttu-id="73df0-141">클릭 **새 참조 추가**System.dll을 선택 하 고 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-141">Click **Add New Reference**, select System.dll, and click **OK**.</span></span>  
  
9. <span data-ttu-id="73df0-142">클릭 **확인** 참조를 추가 하기 위한 win32clock 속성 페이지를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-142">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>  
  
 <span data-ttu-id="73df0-143">마지막으로 추가 합니다 `STAThreadAttribute` 에 `_tWinMain` 메서드 사용에 대 한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="73df0-143">Finally, add the `STAThreadAttribute` to the `_tWinMain` method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:</span></span>  
  
```  
[System::STAThreadAttribute]  
int APIENTRY _tWinMain(HINSTANCE hInstance,  
                     HINSTANCE hPrevInstance,  
                     LPTSTR    lpCmdLine,  
                     int       nCmdShow)  
```  
  
 <span data-ttu-id="73df0-144">이 특성은는 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 는 초기화할 때 [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)]에 필요한 단일 스레드 아파트 모델 (STA)를 사용 해야 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (및 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="73df0-144">This attribute tells the [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] that when it initializes [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)], it should use a single threaded apartment model (STA), which is necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (and [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).</span></span>  
  
## <a name="create-a-windows-presentation-framework-page"></a><span data-ttu-id="73df0-145">Windows Presentation Framework 페이지 만들기</span><span class="sxs-lookup"><span data-stu-id="73df0-145">Create a Windows Presentation Framework Page</span></span>  
 <span data-ttu-id="73df0-146">정의 하는 DLL을 만든 다음에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page>합니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-146">Next, you create a DLL that defines a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>.</span></span> <span data-ttu-id="73df0-147">만드는 가장 쉬운 경우가 합니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> 는 독립 실행형 응용 프로그램을 작성 하 고 디버그로는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이런 방식으로 부분.</span><span class="sxs-lookup"><span data-stu-id="73df0-147">It’s often easiest to create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> as a standalone application, and write and debug the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion that way.</span></span>  <span data-ttu-id="73df0-148">해당 프로젝트를 클릭 하 고 프로젝트를 마우스 오른쪽 단추로 클릭 하 여 DLL로 설정할 수 있습니다 완료 되 면 **속성**, 응용 프로그램으로 이동 하 고 출력 형식을 Windows 클래스 라이브러리로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-148">Once done, that project can be turned into a DLL by right-clicking the project, clicking on **Properties**, going to the Application, and changing Output type to Windows Class Library.</span></span>  
  
 <span data-ttu-id="73df0-149">합니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll 프로젝트와 결합할 수 있습니다 합니다 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 선택 솔루션을 마우스 오른쪽 단추로 클릭 (하나의 솔루션에 두 프로젝트가 포함 된) – 프로젝트 **추가 \ 기존 프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-149">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll project can then be combined with the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project (one solution that contains two projects) – right-click on the solution, select **Add\Existing Project**.</span></span>  
  
 <span data-ttu-id="73df0-150">사용 하 여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll에서는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 프로젝트 참조를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-150">To use that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll from the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project, you need to add a reference:</span></span>  
  
1.  <span data-ttu-id="73df0-151">Win32clock 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **참조 하는 중...** .</span><span class="sxs-lookup"><span data-stu-id="73df0-151">Right-click win32clock project and select **References...**.</span></span>  
  
2.  <span data-ttu-id="73df0-152">클릭 **새 참조 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-152">Click **Add New Reference**.</span></span>  
  
3.  <span data-ttu-id="73df0-153">**프로젝트** 탭을 클릭합니다.  WPFClock을 선택하고 [확인]을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-153">Click the **Projects** tab.  Select WPFClock, click OK.</span></span>  
  
4.  <span data-ttu-id="73df0-154">클릭 **확인** 참조를 추가 하기 위한 win32clock 속성 페이지를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-154">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>  
  
## <a name="hwndsource"></a><span data-ttu-id="73df0-155">HwndSource</span><span class="sxs-lookup"><span data-stu-id="73df0-155">HwndSource</span></span>  
 <span data-ttu-id="73df0-156">다음을 사용 하 여 <xref:System.Windows.Interop.HwndSource> 수 있도록 합니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> HWND와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-156">Next, you use <xref:System.Windows.Interop.HwndSource> to make the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> look like an HWND.</span></span>  <span data-ttu-id="73df0-157">다음 코드 블록을 C++ 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-157">You add this block of code to a C++ file:</span></span>  
  
```  
namespace ManagedCode  
{  
    using namespace System;  
    using namespace System::Windows;  
    using namespace System::Windows::Interop;  
    using namespace System::Windows::Media;  
  
    HWND GetHwnd(HWND parent, int x, int y, int width, int height) {  
        HwndSource^ source = gcnew HwndSource(  
            0, // class style  
            WS_VISIBLE | WS_CHILD, // style  
            0, // exstyle  
            x, y, width, height,  
            "hi", // NAME  
            IntPtr(parent)        // parent window   
            );  
  
        UIElement^ page = gcnew WPFClock::Clock();  
        source->RootVisual = page;  
        return (HWND) source->Handle.ToPointer();  
    }  
}  
}  
```  
  
 <span data-ttu-id="73df0-158">다음은 약간의 설명이 필요할 수 있는 긴 코드 조각입니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-158">This is a long piece of code that could use some explanation.</span></span>  <span data-ttu-id="73df0-159">첫 번째 부분은 다양한 절이어서 모든 호출을 정규화할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-159">The first part is various clauses so that you do not need to fully qualify all the calls:</span></span>  
  
```  
namespace ManagedCode  
{  
    using namespace System;  
    using namespace System::Windows;  
    using namespace System::Windows::Interop;  
    using namespace System::Windows::Media;  
```  
  
 <span data-ttu-id="73df0-160">만드는 함수를 정의한 다음를 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠를 넣습니다는 <xref:System.Windows.Interop.HwndSource> , 및 HWND 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-160">Then you define a function that creates the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content, puts an <xref:System.Windows.Interop.HwndSource> around it, and returns the HWND:</span></span>  
  
```  
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {  
```  
  
 <span data-ttu-id="73df0-161">먼저 만듭니다는 <xref:System.Windows.Interop.HwndSource>, 매개 변수를 가진 CreateWindow와 유사한는:</span><span class="sxs-lookup"><span data-stu-id="73df0-161">First you create an <xref:System.Windows.Interop.HwndSource>, whose parameters are similar to CreateWindow:</span></span>  
  
```  
HwndSource^ source = gcnew HwndSource(  
    0, // class style  
    WS_VISIBLE | WS_CHILD, // style  
    0, // exstyle  
    x, y, width, height,  
    "hi", // NAME  
    IntPtr(parent) // parent window   
    );  
```  
  
 <span data-ttu-id="73df0-162">만든 후의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클래스 생성자를 호출 하 여 콘텐츠:</span><span class="sxs-lookup"><span data-stu-id="73df0-162">Then you create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content class by calling its constructor:</span></span>  
  
```  
UIElement^ page = gcnew WPFClock::Clock();  
```  
  
 <span data-ttu-id="73df0-163">페이지를 다음으로 연결 된 <xref:System.Windows.Interop.HwndSource>:</span><span class="sxs-lookup"><span data-stu-id="73df0-163">You then connect the page to the <xref:System.Windows.Interop.HwndSource>:</span></span>  
  
```  
source->RootVisual = page;  
```  
  
 <span data-ttu-id="73df0-164">마지막 줄에 대 한 HWND를 반환 하 고는 <xref:System.Windows.Interop.HwndSource>:</span><span class="sxs-lookup"><span data-stu-id="73df0-164">And in the final line, return the HWND for the <xref:System.Windows.Interop.HwndSource>:</span></span>  
  
```  
return (HWND) source->Handle.ToPointer();  
```  
  
## <a name="positioning-the-hwnd"></a><span data-ttu-id="73df0-165">Hwnd 위치 지정</span><span class="sxs-lookup"><span data-stu-id="73df0-165">Positioning the Hwnd</span></span>  
 <span data-ttu-id="73df0-166">포함 하는 HWND 했으므로 합니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 시계를 적용 해야 해당 HWND 내에서 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 대화 합니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-166">Now that you have an HWND that contains the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you need to put that HWND inside the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] dialog.</span></span>  <span data-ttu-id="73df0-167">HWND를 배치할 위치를 알고 있는 경우 전달 하면 해당 크기 및 위치를 `GetHwnd` 앞에서 정의한 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-167">If you knew just where to put the HWND, you would just pass that size and location to the `GetHwnd` function you defined earlier.</span></span>  <span data-ttu-id="73df0-168">그러나 리소스 파일을 사용하여 대화 상자를 정의했으므로 HWND를 배치할 위치를 정확하게 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-168">But you used a resource file to define the dialog, so you are not exactly sure where any of the HWNDs are positioned.</span></span>  <span data-ttu-id="73df0-169">사용할 수는 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] 삽입할 대화 상자 편집기를 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 시계가 들어갈 하려는 정적 컨트롤 ("여기에 시계 삽입"), 위치로 사용 및는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클록.</span><span class="sxs-lookup"><span data-stu-id="73df0-169">You can use the [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] dialog editor to put a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] STATIC control where you want the clock to go ("Insert clock here"), and use that to position the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock.</span></span>  
  
 <span data-ttu-id="73df0-170">WM_INITDIALOG를 처리 하는 경우 사용할 `GetDlgItem` 자리 표시자 STATIC에 대 한 HWND를 검색 하려면:</span><span class="sxs-lookup"><span data-stu-id="73df0-170">Where you handle WM_INITDIALOG, you use `GetDlgItem` to retrieve the HWND for the placeholder STATIC:</span></span>  
  
```  
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);  
```  
  
 <span data-ttu-id="73df0-171">계산한 다음에 크기와 해당 자리 표시자 STATIC의 위치를 활용할 수 있도록는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 시계를 합니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-171">You then calculate the size and position of that placeholder STATIC, so you can put the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock in that place:</span></span>  
  
 <span data-ttu-id="73df0-172">RECT 사각형의 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-172">RECT rectangle;</span></span>  
  
```  
GetWindowRect(placeholder, &rectangle);  
int width = rectangle.right - rectangle.left;  
int height = rectangle.bottom - rectangle.top;  
POINT point;  
point.x = rectangle.left;  
point.y = rectangle.top;  
result = MapWindowPoints(NULL, hDlg, &point, 1);  
```  
  
 <span data-ttu-id="73df0-173">그런 다음 자리 표시자 STATIC을 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-173">Then you hide the placeholder STATIC:</span></span>  
  
```  
ShowWindow(placeholder, SW_HIDE);  
```  
  
 <span data-ttu-id="73df0-174">만들고는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 시계 HWND 해당 위치에서:</span><span class="sxs-lookup"><span data-stu-id="73df0-174">And create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock HWND in that location:</span></span>  
  
```  
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);  
```  
  
 <span data-ttu-id="73df0-175">자습서를 흥미를 확인 하는 데 실제 생성 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 만들려고 해야 클록을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이 시점에서 시계 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-175">To make the tutorial interesting, and to produce a real [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you will need to create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock control at this point.</span></span> <span data-ttu-id="73df0-176">코드 숨김에서 몇 개의 이벤트 처리기만 사용하여 태그에서 거의 모든 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-176">You can do so mostly in markup, with just a few event handlers in code-behind.</span></span> <span data-ttu-id="73df0-177">이 자습서 컨트롤 디자인에 상호 운용성 정보 이므로 전체에 대 한 코드를 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클록 제공 됩니다 작성 또는 각 부분의 의미에 대 한 개별적인 지침 없이 코드 블록으로 여기입니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-177">Since this tutorial is about interoperation and not about control design, complete code for the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock is provided here as a code block, without discrete instructions for building it up or what each part means.</span></span> <span data-ttu-id="73df0-178">이 코드를 자유롭게 사용하여 컨트롤의 모양과 느낌 또는 기능을 변경해 보세요.</span><span class="sxs-lookup"><span data-stu-id="73df0-178">Feel free to experiment with this code to change the look and feel or functionality of the control.</span></span>  
  
 <span data-ttu-id="73df0-179">다음은 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-179">Here is the markup:</span></span>  
  
 [!code-xaml[Win32Clock#AllClockXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]  
  
 <span data-ttu-id="73df0-180">다음은 함께 제공되는 코드 숨김입니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-180">And here is the accompanying code-behind:</span></span>  
  
 [!code-csharp[Win32Clock#AllClockCS](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]  
  
 <span data-ttu-id="73df0-181">최종 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-181">The final result looks like:</span></span>  
  
 <span data-ttu-id="73df0-182">![날짜 및 시간 속성 대화 상자](./media/interoparch08.PNG "InteropArch08")</span><span class="sxs-lookup"><span data-stu-id="73df0-182">![Date and Time Properties dialog box](./media/interoparch08.PNG "InteropArch08")</span></span>  
  
 <span data-ttu-id="73df0-183">이 스크린샷에서 생성 하는 코드를 최종 결과 비교 하려면 참조 [Win32 시계 상호 운용 샘플](https://go.microsoft.com/fwlink/?LinkID=160051)합니다.</span><span class="sxs-lookup"><span data-stu-id="73df0-183">To compare your end result to the code that produced this screenshot, see [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73df0-184">참고자료</span><span class="sxs-lookup"><span data-stu-id="73df0-184">See also</span></span>
- <xref:System.Windows.Interop.HwndSource>
- [<span data-ttu-id="73df0-185">WPF 및 Win32 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="73df0-185">WPF and Win32 Interoperation</span></span>](wpf-and-win32-interoperation.md)
- [<span data-ttu-id="73df0-186">Win32 시계 상호 운용 샘플</span><span class="sxs-lookup"><span data-stu-id="73df0-186">Win32 Clock Interoperation Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160051)
