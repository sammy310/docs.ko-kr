---
title: '연습: Win32에서 WPF 시계 호스팅'
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
ms.openlocfilehash: 1fdc0c9ccf1464d7519a4c5935520de1206ca9bb
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794154"
---
# <a name="walkthrough-host-a-wpf-clock-in-win32"></a><span data-ttu-id="6e66f-102">연습: Win32에서 WPF 시계 호스팅</span><span class="sxs-lookup"><span data-stu-id="6e66f-102">Walkthrough: Host a WPF Clock in Win32</span></span>

<span data-ttu-id="6e66f-103">Win32 응용 프로그램 내에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]을 추가 하려면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠를 포함 하는 HWND를 제공 하는 <xref:System.Windows.Interop.HwndSource>을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-103">To put [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside Win32 applications, use <xref:System.Windows.Interop.HwndSource>, which provides the HWND that contains your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span> <span data-ttu-id="6e66f-104">먼저 <xref:System.Windows.Interop.HwndSource>를 만들어 CreateWindow와 유사한 매개 변수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-104">First you create the <xref:System.Windows.Interop.HwndSource>, giving it parameters similar to CreateWindow.</span></span> <span data-ttu-id="6e66f-105">그런 다음 <xref:System.Windows.Interop.HwndSource> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠에 대 한 정보를 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-105">Then you tell the <xref:System.Windows.Interop.HwndSource> about the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content you want inside it.</span></span> <span data-ttu-id="6e66f-106">마지막으로 <xref:System.Windows.Interop.HwndSource>의 HWND를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-106">Finally, you get the HWND out of the <xref:System.Windows.Interop.HwndSource>.</span></span> <span data-ttu-id="6e66f-107">이 연습에서는 운영 체제 **날짜 및 시간 속성** 대화 상자를 다시 구현 하는 Win32 응용 프로그램 내에서 혼합 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-107">This walkthrough illustrates how to create a mixed [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside Win32 application that reimplements the operating system **Date and Time Properties** dialog.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6e66f-108">전제 조건</span><span class="sxs-lookup"><span data-stu-id="6e66f-108">Prerequisites</span></span>

<span data-ttu-id="6e66f-109">[WPF 및 Win32 상호 운용성을](wpf-and-win32-interoperation.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6e66f-109">See [WPF and Win32 Interoperation](wpf-and-win32-interoperation.md).</span></span>

## <a name="how-to-use-this-tutorial"></a><span data-ttu-id="6e66f-110">이 자습서의 사용 방법</span><span class="sxs-lookup"><span data-stu-id="6e66f-110">How to Use This Tutorial</span></span>

<span data-ttu-id="6e66f-111">이 자습서는 상호 운용 애플리케이션을 생성하는 중요한 단계에 대해 중점적으로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-111">This tutorial concentrates on the important steps of producing an interoperation application.</span></span> <span data-ttu-id="6e66f-112">이 자습서는 [Win32 클록 상호 운용성 샘플](https://go.microsoft.com/fwlink/?LinkID=160051)샘플에서 지원 되지만이 샘플은 최종 제품을 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-112">The tutorial is backed by a sample, [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051), but that sample is reflective of the end product.</span></span> <span data-ttu-id="6e66f-113">이 자습서에서는 기존 프로젝트와 같은 기존 Win32 프로젝트를 사용 하 여 시작 하 고 응용 프로그램에 호스트 된 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 추가 하는 것 처럼 단계를 문서화 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-113">This tutorial documents the steps as if you were starting with an existing Win32 project of your own, perhaps a pre-existing project, and you were adding a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] to your application.</span></span> <span data-ttu-id="6e66f-114">최종 제품을 [Win32 클록 상호 운용 샘플과](https://go.microsoft.com/fwlink/?LinkID=160051)비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-114">You can compare your end product with [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051).</span></span>

## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a><span data-ttu-id="6e66f-115">Win32 내에서 Windows Presentation Framework의 연습(HwndSource)</span><span class="sxs-lookup"><span data-stu-id="6e66f-115">A Walkthrough of Windows Presentation Framework Inside Win32 (HwndSource)</span></span>

<span data-ttu-id="6e66f-116">다음 그래픽에서는 이 자습서의 의도된 최종 제품을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-116">The following graphic shows the intended end product of this tutorial:</span></span>

![날짜 및 시간 속성 대화 상자를 보여 주는 스크린샷](./media/walkthrough-hosting-a-wpf-clock-in-win32/date-time-properties-dialog.png)

<span data-ttu-id="6e66f-118">Visual Studio에서 C++ Win32 프로젝트를 만들고 대화 상자 편집기를 사용 하 여 다음을 만드는 방법으로이 대화 상자를 다시 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-118">You can recreate this dialog by creating a C++ Win32 project in Visual Studio, and using the dialog editor to create the following:</span></span>

![다시 생성 한 날짜 및 시간 속성 대화 상자](./media/walkthrough-hosting-a-wpf-clock-in-win32/recreated-date-time-properties-dialog.png)

<span data-ttu-id="6e66f-120">Visual Studio를 사용 하 여 <xref:System.Windows.Interop.HwndSource>를 사용 하지 않아도 되며를 사용 하 여 Win32 프로그램을 작성 C++ 하지 않아도 되지만이를 사용 하는 것은 매우 일반적인 방법 이며 단계별 자습서 설명에도 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-120">(You do not need to use Visual Studio to use <xref:System.Windows.Interop.HwndSource>, and you do not need to use C++ to write Win32 programs, but this is a fairly typical way to do it, and lends itself well to a stepwise tutorial explanation).</span></span>

<span data-ttu-id="6e66f-121">대화 상자에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock을 추가 하려면 5 개의 특정 하위 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-121">You need to accomplish five particular substeps in order to put a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock into the dialog:</span></span>

1. <span data-ttu-id="6e66f-122">Visual Studio에서 프로젝트 설정을 변경 하 여 Win32 프로젝트에서 관리 코드 ( **/clr**)를 호출할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-122">Enable your Win32 project to call managed code (**/clr**) by changing project settings in Visual Studio.</span></span>

2. <span data-ttu-id="6e66f-123">별도의 DLL에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-123">Create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> in a separate DLL.</span></span>

3. <span data-ttu-id="6e66f-124">해당 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>를 <xref:System.Windows.Interop.HwndSource>내에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-124">Put that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> inside an <xref:System.Windows.Interop.HwndSource>.</span></span>

4. <span data-ttu-id="6e66f-125"><xref:System.Windows.Interop.HwndSource.Handle%2A> 속성을 사용 하 여 <xref:System.Windows.Controls.Page>에 대 한 HWND를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-125">Get an HWND for that <xref:System.Windows.Controls.Page> using the <xref:System.Windows.Interop.HwndSource.Handle%2A> property.</span></span>

5. <span data-ttu-id="6e66f-126">Win32를 사용 하 여 더 큰 Win32 응용 프로그램 내에서 HWND를 넣을 위치 결정</span><span class="sxs-lookup"><span data-stu-id="6e66f-126">Use Win32 to decide where to place the HWND within the larger Win32 application</span></span>

## <a name="clr"></a><span data-ttu-id="6e66f-127">/clr</span><span class="sxs-lookup"><span data-stu-id="6e66f-127">/clr</span></span>

<span data-ttu-id="6e66f-128">첫 번째 단계는이 관리 되지 않는 Win32 프로젝트를 관리 코드를 호출할 수 있는 것으로 설정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-128">The first step is to turn this unmanaged Win32 project into one that can call managed code.</span></span> <span data-ttu-id="6e66f-129">/Clr 컴파일러 옵션을 사용 합니다 .이 옵션을 사용 하 여 필요한 Dll에 연결 하 고 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에 사용할 Main 메서드를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-129">You use the /clr compiler option, which will link to the necessary DLLs you want to use, and adjust the Main method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span>

<span data-ttu-id="6e66f-130">C++ 프로젝트 내에서 관리 코드를 사용 하도록 설정 하려면 win32clock 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **속성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-130">To enable the use of managed code inside the C++ project: Right-click on win32clock project and select **Properties**.</span></span> <span data-ttu-id="6e66f-131">**일반** 속성 페이지 (기본값)에서 공용 언어 런타임 지원을 `/clr`변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-131">On the **General** property page (the default), change Common Language Runtime support to `/clr`.</span></span>

<span data-ttu-id="6e66f-132">다음으로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에 필요한 Dll에 대 한 참조를 추가 합니다. PresentationCore, PresentationFramework, Uiautomationprovider.dll, Uiautomationtypes.dll 및.</span><span class="sxs-lookup"><span data-stu-id="6e66f-132">Next, add references to DLLs necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll, PresentationFramework.dll, System.dll, WindowsBase.dll, UIAutomationProvider.dll, and UIAutomationTypes.dll.</span></span> <span data-ttu-id="6e66f-133">다음 지침에서는 운영 체제가 C: 드라이브에 설치되어 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-133">(Following instructions assume the operating system is installed on C: drive.)</span></span>

1. <span data-ttu-id="6e66f-134">Win32clock 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **참조 ...** 를 선택 하 고 해당 대화 상자 내에서 다음을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-134">Right-click win32clock project and select **References...**, and inside that dialog:</span></span>

2. <span data-ttu-id="6e66f-135">Win32clock 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **참조 ...** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-135">Right-click win32clock project and select **References...**.</span></span>

3. <span data-ttu-id="6e66f-136">**새 참조 추가**를 클릭 하 고 찾아보기 탭을 클릭 한 다음 C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll을 입력 하 고 확인을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-136">Click **Add New Reference**, click Browse tab, enter C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll, and click OK.</span></span>

4. <span data-ttu-id="6e66f-137">PresentationFramework.dll(C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll)에 대해 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-137">Repeat for PresentationFramework.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span></span>

5. <span data-ttu-id="6e66f-138">WindowsBase.dll(C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll)에 대해 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-138">Repeat for WindowsBase.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.</span></span>

6. <span data-ttu-id="6e66f-139">UIAutomationTypes.dll(C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll)에 대해 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-139">Repeat for UIAutomationTypes.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span></span>

7. <span data-ttu-id="6e66f-140">UIAutomationProvider.dll(C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll)에 대해 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-140">Repeat for UIAutomationProvider.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span></span>

8. <span data-ttu-id="6e66f-141">**새 참조 추가**를 클릭 하 고, 시스템 .dll을 선택 하 고, **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-141">Click **Add New Reference**, select System.dll, and click **OK**.</span></span>

9. <span data-ttu-id="6e66f-142">**확인** 을 클릭 하 여 참조 추가에 대 한 Win32clock 속성 페이지를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-142">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>

 <span data-ttu-id="6e66f-143">마지막으로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]와 함께 사용 하기 위해 `STAThreadAttribute`를 `_tWinMain` 메서드에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-143">Finally, add the `STAThreadAttribute` to the `_tWinMain` method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:</span></span>

```cpp
[System::STAThreadAttribute]
int APIENTRY _tWinMain(HINSTANCE hInstance,
                     HINSTANCE hPrevInstance,
                     LPTSTR    lpCmdLine,
                     int       nCmdShow)
```

<span data-ttu-id="6e66f-144">이 특성은 COM (구성 요소 개체 모델)을 초기화할 때 CLR (공용 언어 런타임)에 게 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 및 Windows Forms에 필요한 STA (단일 스레드 아파트 모델)를 사용 하도록 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-144">This attribute tells the common language runtime (CLR) that when it initializes Component Object Model (COM), it should use a single threaded apartment model (STA), which is necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (and Windows Forms).</span></span>

## <a name="create-a-windows-presentation-framework-page"></a><span data-ttu-id="6e66f-145">Windows Presentation Framework 페이지 만들기</span><span class="sxs-lookup"><span data-stu-id="6e66f-145">Create a Windows Presentation Framework Page</span></span>

<span data-ttu-id="6e66f-146">그런 다음 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>을 정의 하는 DLL을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-146">Next, you create a DLL that defines a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>.</span></span> <span data-ttu-id="6e66f-147">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>을 독립 실행형 응용 프로그램으로 만들고 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 부분을 작성 하 고 디버그 하는 것이 가장 쉬운 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-147">It’s often easiest to create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> as a standalone application, and write and debug the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion that way.</span></span> <span data-ttu-id="6e66f-148">완료 되 면 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **속성**을 클릭 한 다음 응용 프로그램으로 이동 하 고 출력 형식을 Windows 클래스 라이브러리로 변경 하 여 해당 프로젝트를 DLL로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-148">Once done, that project can be turned into a DLL by right-clicking the project, clicking on **Properties**, going to the Application, and changing Output type to Windows Class Library.</span></span>

<span data-ttu-id="6e66f-149">그런 다음 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll 프로젝트를 Win32 프로젝트 (두 프로젝트를 포함 하는 하나의 솔루션)와 결합할 수 있습니다. 솔루션을 마우스 오른쪽 단추로 클릭 하 고 **Add\Existing project**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-149">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll project can then be combined with the Win32 project (one solution that contains two projects) – right-click on the solution, select **Add\Existing Project**.</span></span>

<span data-ttu-id="6e66f-150">Win32 프로젝트에서 해당 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll을 사용 하려면 참조를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-150">To use that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll from the Win32 project, you need to add a reference:</span></span>

1. <span data-ttu-id="6e66f-151">Win32clock 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **참조 ...** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-151">Right-click win32clock project and select **References...**.</span></span>

2. <span data-ttu-id="6e66f-152">**새 참조 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-152">Click **Add New Reference**.</span></span>

3. <span data-ttu-id="6e66f-153">**프로젝트** 탭을 클릭 합니다. WPFClock를 선택 하 고 확인을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-153">Click the **Projects** tab. Select WPFClock, click OK.</span></span>

4. <span data-ttu-id="6e66f-154">**확인** 을 클릭 하 여 참조 추가에 대 한 Win32clock 속성 페이지를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-154">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>

## <a name="hwndsource"></a><span data-ttu-id="6e66f-155">HwndSource</span><span class="sxs-lookup"><span data-stu-id="6e66f-155">HwndSource</span></span>

<span data-ttu-id="6e66f-156">다음으로 <xref:System.Windows.Interop.HwndSource>를 사용 하 여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> HWND 처럼 보이게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-156">Next, you use <xref:System.Windows.Interop.HwndSource> to make the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> look like an HWND.</span></span> <span data-ttu-id="6e66f-157">다음 코드 블록을 C++ 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-157">You add this block of code to a C++ file:</span></span>

```cpp
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

 <span data-ttu-id="6e66f-158">다음은 약간의 설명이 필요할 수 있는 긴 코드 조각입니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-158">This is a long piece of code that could use some explanation.</span></span> <span data-ttu-id="6e66f-159">첫 번째 부분은 다양한 절이어서 모든 호출을 정규화할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-159">The first part is various clauses so that you do not need to fully qualify all the calls:</span></span>

```cpp
namespace ManagedCode
{
    using namespace System;
    using namespace System::Windows;
    using namespace System::Windows::Interop;
    using namespace System::Windows::Media;
```

 <span data-ttu-id="6e66f-160">그런 다음 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠를 만들고 <xref:System.Windows.Interop.HwndSource>를 배치 하 고 HWND를 반환 하는 함수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-160">Then you define a function that creates the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content, puts an <xref:System.Windows.Interop.HwndSource> around it, and returns the HWND:</span></span>

```cpp
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {
```

<span data-ttu-id="6e66f-161">먼저 매개 변수가 CreateWindow와 유사한 <xref:System.Windows.Interop.HwndSource>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-161">First you create an <xref:System.Windows.Interop.HwndSource>, whose parameters are similar to CreateWindow:</span></span>

```cpp
HwndSource^ source = gcnew HwndSource(
    0, // class style
    WS_VISIBLE | WS_CHILD, // style
    0, // exstyle
    x, y, width, height,
    "hi", // NAME
    IntPtr(parent) // parent window
);
```

<span data-ttu-id="6e66f-162">그런 다음 해당 생성자를 호출 하 여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-162">Then you create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content class by calling its constructor:</span></span>

```cpp
UIElement^ page = gcnew WPFClock::Clock();
```

<span data-ttu-id="6e66f-163">그런 다음 페이지를 <xref:System.Windows.Interop.HwndSource>에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-163">You then connect the page to the <xref:System.Windows.Interop.HwndSource>:</span></span>

```cpp
source->RootVisual = page;
```

 <span data-ttu-id="6e66f-164">마지막 줄에서 <xref:System.Windows.Interop.HwndSource>에 대 한 HWND를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-164">And in the final line, return the HWND for the <xref:System.Windows.Interop.HwndSource>:</span></span>

```cpp
return (HWND) source->Handle.ToPointer();
```

## <a name="positioning-the-hwnd"></a><span data-ttu-id="6e66f-165">Hwnd 위치 지정</span><span class="sxs-lookup"><span data-stu-id="6e66f-165">Positioning the Hwnd</span></span>

<span data-ttu-id="6e66f-166">이제 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock을 포함 하는 HWND가 있으므로 Win32 대화 상자 내에 해당 HWND를 넣어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-166">Now that you have an HWND that contains the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you need to put that HWND inside the Win32 dialog.</span></span> <span data-ttu-id="6e66f-167">HWND를 배치할 위치를 알고 있다면 앞에서 정의한 `GetHwnd` 함수에 해당 크기와 위치를 전달 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-167">If you knew just where to put the HWND, you would just pass that size and location to the `GetHwnd` function you defined earlier.</span></span> <span data-ttu-id="6e66f-168">그러나 리소스 파일을 사용하여 대화 상자를 정의했으므로 HWND를 배치할 위치를 정확하게 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-168">But you used a resource file to define the dialog, so you are not exactly sure where any of the HWNDs are positioned.</span></span> <span data-ttu-id="6e66f-169">Visual Studio 대화 상자 편집기를 사용 하 여 clock을 이동할 위치 ("여기에 clock 삽입")를 표시 하 고이를 사용 하 여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클록을 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-169">You can use the Visual Studio dialog editor to put a Win32 STATIC control where you want the clock to go ("Insert clock here"), and use that to position the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock.</span></span>

<span data-ttu-id="6e66f-170">WM_INITDIALOG를 처리 하는 경우 `GetDlgItem`를 사용 하 여 자리 표시자 정적의 HWND를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-170">Where you handle WM_INITDIALOG, you use `GetDlgItem` to retrieve the HWND for the placeholder STATIC:</span></span>

```cpp
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);
```

<span data-ttu-id="6e66f-171">그런 다음 해당 자리 표시자 고정의 크기와 위치를 계산 하 여 해당 위치에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock을 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-171">You then calculate the size and position of that placeholder STATIC, so you can put the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock in that place:</span></span>

<span data-ttu-id="6e66f-172">RECT 사각형의 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-172">RECT rectangle;</span></span>

```cpp
GetWindowRect(placeholder, &rectangle);
int width = rectangle.right - rectangle.left;
int height = rectangle.bottom - rectangle.top;
POINT point;
point.x = rectangle.left;
point.y = rectangle.top;
result = MapWindowPoints(NULL, hDlg, &point, 1);
```

<span data-ttu-id="6e66f-173">그런 다음 자리 표시자 STATIC을 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-173">Then you hide the placeholder STATIC:</span></span>

```cpp
ShowWindow(placeholder, SW_HIDE);
```

<span data-ttu-id="6e66f-174">그런 다음 해당 위치에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클록 HWND를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-174">And create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock HWND in that location:</span></span>

```cpp
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);
```

<span data-ttu-id="6e66f-175">자습서를 흥미 있게 만들고 실제 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클록을 생성 하려면이 시점에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클록 컨트롤을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-175">To make the tutorial interesting, and to produce a real [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you will need to create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock control at this point.</span></span> <span data-ttu-id="6e66f-176">코드 숨김에서 몇 개의 이벤트 처리기만 사용하여 태그에서 거의 모든 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-176">You can do so mostly in markup, with just a few event handlers in code-behind.</span></span> <span data-ttu-id="6e66f-177">이 자습서는 컨트롤 디자인에 대 한 것이 아니라 상호 운용성에 대 한 것 이므로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클록에 대 한 전체 코드는 여기에서 코드 블록으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-177">Since this tutorial is about interoperation and not about control design, complete code for the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock is provided here as a code block, without discrete instructions for building it up or what each part means.</span></span> <span data-ttu-id="6e66f-178">이 코드를 자유롭게 사용하여 컨트롤의 모양과 느낌 또는 기능을 변경해 보세요.</span><span class="sxs-lookup"><span data-stu-id="6e66f-178">Feel free to experiment with this code to change the look and feel or functionality of the control.</span></span>

<span data-ttu-id="6e66f-179">다음은 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-179">Here is the markup:</span></span>

[!code-xaml[Win32Clock#AllClockXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]

<span data-ttu-id="6e66f-180">다음은 함께 제공되는 코드 숨김입니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-180">And here is the accompanying code-behind:</span></span>

[!code-csharp[Win32Clock#AllClockCS](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]

<span data-ttu-id="6e66f-181">최종 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6e66f-181">The final result looks like:</span></span>

![최종 결과 날짜 및 시간 속성 대화 상자](./media/walkthrough-hosting-a-wpf-clock-in-win32/final-result-date-time-properties-dialog.png)

<span data-ttu-id="6e66f-183">최종 결과를이 스크린샷을 생성 한 코드와 비교 하려면 [Win32 클록 상호 운용성 샘플](https://go.microsoft.com/fwlink/?LinkID=160051)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6e66f-183">To compare your end result to the code that produced this screenshot, see [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051).</span></span>

## <a name="see-also"></a><span data-ttu-id="6e66f-184">참조</span><span class="sxs-lookup"><span data-stu-id="6e66f-184">See also</span></span>

- <xref:System.Windows.Interop.HwndSource>
- [<span data-ttu-id="6e66f-185">WPF 및 Win32 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="6e66f-185">WPF and Win32 Interoperation</span></span>](wpf-and-win32-interoperation.md)
- [<span data-ttu-id="6e66f-186">Win32 시계 상호 운용 샘플</span><span class="sxs-lookup"><span data-stu-id="6e66f-186">Win32 Clock Interoperation Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160051)
