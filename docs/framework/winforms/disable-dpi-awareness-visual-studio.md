---
title: Visual Studio에서 인식 되는 DPI를 사용 하지 않도록 설정
description: HDPI 모니터에 대 한 Windows Forms 디자이너의 제한 사항 및 DPI를 인식 하지 못하는 프로세스로 Visual Studio를 실행 하는 방법에 설명 합니다.
ms.date: 04/05/2019
ms.prod: visual-studio-windows
ms.technology: vs-ide-designers
author: gewarren
ms.author: gewarren
ms.custom: seoapril2019
ms.openlocfilehash: e52debea382033417afe0bd47f899af1666192bc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59181385"
---
# <a name="disable-dpi-awareness-in-visual-studio"></a><span data-ttu-id="239a7-103">Visual Studio에서 인식 되는 DPI를 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="239a7-103">Disable DPI-awareness in Visual Studio</span></span>

<span data-ttu-id="239a7-104">Visual Studio는 dpi 인식 응용 프로그램에 자동으로 표시 배율을 즉 인치당입니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-104">Visual Studio is a dots per inch (DPI) aware application, which means the display scales automatically.</span></span> <span data-ttu-id="239a7-105">응용 프로그램에서 DPI에서 인식 되지 않으면 알 경우 운영 체제에 비트맵으로 응용 프로그램을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-105">If an application states that it's not DPI-aware, the operating system scales the application as a bitmap.</span></span> <span data-ttu-id="239a7-106">이 동작은 DPI 가상화를 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-106">This behavior is also called DPI virtualization.</span></span> <span data-ttu-id="239a7-107">응용 프로그램이 여전히 100% 배율 조정 또는 96dpi에서 실행 되 고 있는지 것으로 생각 합니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-107">The application still thinks that it's running at 100% scaling, or 96 dpi.</span></span>

<span data-ttu-id="239a7-108">이 문서에서는 HDPI 모니터에 대 한 Windows Forms 디자이너의 제한 사항 및 DPI를 인식 하지 못하는 프로세스로 Visual Studio를 실행 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-108">This article discusses the limitations of Windows Forms Designer on HDPI monitors and how to run Visual Studio as a DPI-unaware process.</span></span>

## <a name="windows-forms-designer-on-hdpi-monitors"></a><span data-ttu-id="239a7-109">HDPI 모니터에 Windows Forms 디자이너</span><span class="sxs-lookup"><span data-stu-id="239a7-109">Windows Forms Designer on HDPI monitors</span></span>

<span data-ttu-id="239a7-110">합니다 **Windows Forms 디자이너** Visual Studio에 없는 확장 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-110">The **Windows Forms Designer** in Visual Studio doesn't have scaling support.</span></span> <span data-ttu-id="239a7-111">이 인해 표시 문제에서 몇 가지 형태를 열면 합니다 **Windows Forms 디자이너** hdpi 모니터 인치당 높은에서.</span><span class="sxs-lookup"><span data-stu-id="239a7-111">This causes display issues when you open some forms in the **Windows Forms Designer** on high dots per inch (HDPI) monitors.</span></span> <span data-ttu-id="239a7-112">예를 들어 다음 그림에 나와 있는 것 처럼 중복 컨트롤 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-112">For examples, controls can appear to overlap as shown in the following image:</span></span>

![HDPI 모니터에서 Windows Forms 디자이너](./media/disable-dpi-awareness-visual-studio/win-forms-designer-hdpi.png)

<span data-ttu-id="239a7-114">양식을 열 때 합니다 **Windows Forms 디자이너** HDPI 모니터에서 Visual Studio에서 Visual Studio 디자이너의 맨 위에 있는 노란색 표시줄 정보를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-114">When you open a form in the **Windows Forms Designer** in Visual Studio on an HDPI monitor, Visual Studio displays a yellow informational bar at the top of the designer:</span></span>

![DPI를 인식 하지 못하는 모드에서 다시 시작 하려면 Visual Studio의 정보 표시줄](./media/disable-dpi-awareness-visual-studio/scaling-gold-bar.png)

<span data-ttu-id="239a7-116">메시지 읽고 **기본 디스플레이에 크기 조정 (192dpi) 200%로 설정 됩니다. 디자이너 창에서 렌더링 문제를 발생할 수 있습니다이 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="239a7-116">The message reads **Scaling on your main display is set to 200% (192 dpi). This might cause rendering problems in the designer window.**</span></span>

> [!NOTE]
> <span data-ttu-id="239a7-117">이 정보 표시줄은 Visual Studio 2017 버전 15.8에서에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-117">This informational bar was introduced in Visual Studio 2017 version 15.8.</span></span>

<span data-ttu-id="239a7-118">디자이너에서 작동 하지 않는 경우 폼의 레이아웃을 조정할 필요가 없습니다 정보 표시줄을 무시 하 고 다른 형식의 디자이너 또는 코드 편집기에서 작업을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-118">If you aren't working in the designer and don't need to adjust the layout of your form, you can ignore the informational bar and continue working in the code editor or in other types of designers.</span></span> <span data-ttu-id="239a7-119">(할 수도 있습니다 [알림 사용 안 함](#disable-notifications) 표시할 정보 가로 막대형 계속 되지 않도록 합니다.) 만 **Windows Forms 디자이너** 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-119">(You can also [disable notifications](#disable-notifications) so that the informational bar doesn't continue to appear.) Only the **Windows Forms Designer** is affected.</span></span> <span data-ttu-id="239a7-120">작업할 필요가 없는 경우는 **Windows Forms 디자이너**, 다음 섹션에서는 도움이 [문제를 해결](#to-resolve-the-display-problem)합니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-120">If you do need to work in the **Windows Forms Designer**, the next section helps you [resolve the problem](#to-resolve-the-display-problem).</span></span>

## <a name="to-resolve-the-display-problem"></a><span data-ttu-id="239a7-121">표시 문제를 해결 하려면</span><span class="sxs-lookup"><span data-stu-id="239a7-121">To resolve the display problem</span></span>

<span data-ttu-id="239a7-122">표시 문제를 해결 하는 방법은 세 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-122">There are three options to resolve the display problem:</span></span>

1. [<span data-ttu-id="239a7-123">DPI를 인식 하지 못하는 프로세스로 Visual Studio를 다시 시작</span><span class="sxs-lookup"><span data-stu-id="239a7-123">Restart Visual Studio as a DPI-unaware process</span></span>](#restart-visual-studio-as-a-dpi-unaware-process)
2. [<span data-ttu-id="239a7-124">레지스트리 항목을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-124">Add a registry entry</span></span>](#add-a-registry-entry)
3. [<span data-ttu-id="239a7-125">디스플레이 설정을 100%로 크기 조정 설정</span><span class="sxs-lookup"><span data-stu-id="239a7-125">Set your display scaling setting to 100%</span></span>](#set-your-display-scaling-setting-to-100)

### <a name="restart-visual-studio-as-a-dpi-unaware-process"></a><span data-ttu-id="239a7-126">DPI를 인식 하지 못하는 프로세스로 Visual Studio를 다시 시작</span><span class="sxs-lookup"><span data-stu-id="239a7-126">Restart Visual Studio as a DPI-unaware process</span></span>

<span data-ttu-id="239a7-127">DPI를 인식 하지 못하는 프로세스로 노란색 정보 모음에서 옵션을 선택 하면 Visual Studio를 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-127">You can restart Visual Studio as a DPI-unaware process by selecting the option on the yellow informational bar.</span></span> <span data-ttu-id="239a7-128">이 기본 방법은 문제를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-128">This is the preferred way of resolving the problem.</span></span>

<span data-ttu-id="239a7-129">Visual Studio DPI를 인식 하지 못하는 프로세스로 실행 되 면 디자이너 레이아웃 문제가 해결 되 면 있지만 글꼴 희미하게 보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-129">When Visual Studio runs as a DPI-unaware process, the designer layout issues are resolved, but fonts may appear blurry.</span></span> <span data-ttu-id="239a7-130">Visual Studio는 DPI를 인식 하지 못하는 프로세스로 실행 될 때 다른 노란색 정보 메시지를 표시 **Visual Studio DPI를 인식 하지 못하는 프로세스로 실행 됩니다. WPF 및 XAML 디자이너를 제대로 표시 되지 않을 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="239a7-130">Visual Studio displays a different yellow informational message when it runs as a DPI-unaware process that says **Visual Studio is running as a DPI-unaware process. WPF and XAML designers might not display correctly.**</span></span> <span data-ttu-id="239a7-131">정보 표시줄 하는 옵션도 제공 **DPI 인식 프로세스로 Visual Studio를 다시 시작**합니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-131">The informational bar also provides an option to **Restart Visual Studio as a DPI-aware process**.</span></span>

> [!NOTE]
> - <span data-ttu-id="239a7-132">DPI를 인식 하지 못하는 프로세스로 다시 시작 하는 옵션을 선택 하면 Visual Studio 도구 창 도킹 되지 않았는지 있었습니다, 해당 도구 창의 위치 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-132">If you had undocked tool windows in Visual Studio when you selected the option to restart as a DPI-unaware process, the position of those tool windows may change.</span></span>
> - <span data-ttu-id="239a7-133">있는 경우 또는 Visual Basic 기본 프로필을 사용 하는 경우는 **만들어질 때 새 프로젝트 저장** 옵션의 선택을 취소 **도구** > **옵션**  >  **프로젝트 및 솔루션**, DPI를 인식 하지 못하는 프로세스로 다시 시작 될 때 Visual Studio 프로젝트를 다시 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-133">If you use the default Visual Basic profile, or if you have the **Save new projects when created** option deselected in **Tools** > **Options** > **Projects and Solutions**, Visual Studio cannot reopen your project when it restarts as a DPI-unaware process.</span></span> <span data-ttu-id="239a7-134">아래에서 선택 하 여 프로젝트를 열 수는 있지만 **파일** > **최근 프로젝트 및 솔루션**합니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-134">However, you can open the project by selecting it under **File** > **Recent Projects and Solutions**.</span></span>

<span data-ttu-id="239a7-135">작업 완료 되 면 DPI 인식 프로세스로 Visual Studio를 다시 시작 해야 합니다 **Windows Forms 디자이너**합니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-135">It's important to restart Visual Studio as a DPI-aware process when you're finished working in the **Windows Forms Designer**.</span></span> <span data-ttu-id="239a7-136">DPI를 인식 하지 못하는 프로세스로 실행 중인 경우 글꼴 흐리게 수 및와 같은 문제를 다른 디자이너에 표시 될 수 있습니다 합니다 **XAML 디자이너**합니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-136">When it's running as a DPI-unaware process, fonts can look blurry and you may see issues in other designers such as the **XAML Designer**.</span></span> <span data-ttu-id="239a7-137">닫고 DPI를 인식 하지 못하는 모드에서 실행 되는 경우에 Visual Studio를 다시 열 경우 됩니다 DPI 인식 다시 합니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-137">If you close and reopen Visual Studio when it's running in DPI-unaware mode, it becomes DPI-aware again.</span></span> <span data-ttu-id="239a7-138">클릭할 수도 있습니다는 **DPI 인식 프로세스로 Visual Studio를 다시 시작** 정보 표시줄에 대 한 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-138">You can also click the **Restart Visual Studio as a DPI-aware process** option in the informational bar.</span></span>

### <a name="add-a-registry-entry"></a><span data-ttu-id="239a7-139">레지스트리 항목을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-139">Add a registry entry</span></span>

<span data-ttu-id="239a7-140">레지스트리를 수정 하 여 DPI를 인식 하지 못하는으로 Visual Studio를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-140">You can mark Visual Studio as DPI-unaware by modifying the registry.</span></span> <span data-ttu-id="239a7-141">열기 **레지스트리 편집기** 항목을 추가 합니다 **실행 NT\CurrentVersion\AppCompatFlags\Layers** 하위 키:</span><span class="sxs-lookup"><span data-stu-id="239a7-141">Open **Registry Editor** and add an entry to the **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers** subkey:</span></span>

<span data-ttu-id="239a7-142">**항목**: 여부를 사용 중인 Visual Studio 2017 또는 2019에 따라 다음이 값 중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-142">**Entry**: Depending on whether you're using Visual Studio 2017 or 2019, use one of these values:</span></span>

- <span data-ttu-id="239a7-143">C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE\devenv.exe</span><span class="sxs-lookup"><span data-stu-id="239a7-143">C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE\devenv.exe</span></span>
- <span data-ttu-id="239a7-144">C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\Common7\IDE\devenv.exe</span><span class="sxs-lookup"><span data-stu-id="239a7-144">C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\Common7\IDE\devenv.exe</span></span>

> [!NOTE]
> <span data-ttu-id="239a7-145">Visual studio Professional 또는 Enterprise edition을 사용 하는 경우 교체 **커뮤니티** 사용 하 여 **Professional** 또는 **Enterprise** 항목의 합니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-145">If you're using the Professional or Enterprise edition of Visual Studio, replace **Community** with **Professional** or **Enterprise** in the entry.</span></span> <span data-ttu-id="239a7-146">또한 필요에 따라 드라이브 문자를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-146">Also replace the drive letter as necessary.</span></span>

<span data-ttu-id="239a7-147">**Type**: REG_SZ</span><span class="sxs-lookup"><span data-stu-id="239a7-147">**Type**: REG_SZ</span></span>

<span data-ttu-id="239a7-148">**값**: DPIUNAWARE</span><span class="sxs-lookup"><span data-stu-id="239a7-148">**Value**: DPIUNAWARE</span></span>

> [!NOTE]
> <span data-ttu-id="239a7-149">Visual Studio는 레지스트리 항목을 제거할 때까지 DPI를 인식 하지 못하는 모드로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-149">Visual Studio remains in DPI-unaware mode until you remove the registry entry.</span></span>

### <a name="set-your-display-scaling-setting-to-100"></a><span data-ttu-id="239a7-150">디스플레이 설정을 100%로 크기 조정 설정</span><span class="sxs-lookup"><span data-stu-id="239a7-150">Set your display scaling setting to 100%</span></span>

<span data-ttu-id="239a7-151">Windows 10에서 100%로 설정 크기 조정 하 여 표시를 설정 하려면 다음을 입력 **설정 표시** 작업 표시줄을 선택 하 고 검색 상자에에서 **표시 설정 변경**합니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-151">To set your display scaling setting to 100% in Windows 10, type **display settings** in the task bar search box, and then select **Change display settings**.</span></span> <span data-ttu-id="239a7-152">에 **설정을** 창에서 **텍스트, 앱 및 기타 항목의 크기를 변경** 에 **100%** 합니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-152">In the **Settings** window, set **Change the size of text, apps, and other items** to **100%**.</span></span>

<span data-ttu-id="239a7-153">100%로 크기 조정 디스플레이 설정 적절 하지 않을, 있으므로 사용자 인터페이스를 사용할 수 있으려면 너무 작습니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-153">Setting your display scaling to 100% may be undesirable, because it can make the user interface too small to be usable.</span></span>

## <a name="disable-notifications"></a><span data-ttu-id="239a7-154">알림 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="239a7-154">Disable notifications</span></span>

<span data-ttu-id="239a7-155">Visual Studio에서 문제를 크기 조정의 DPI 알릴 필요가 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-155">You can choose not to be notified of DPI scaling issues in Visual Studio.</span></span> <span data-ttu-id="239a7-156">예를 들어 디자이너에서 작업 하지 않는 경우 알림을 사용 하지 않도록 설정 하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="239a7-156">You might want to disable notifications if you aren't working in the designer, for example.</span></span>

<span data-ttu-id="239a7-157">알림 사용 안 함, 선택 **도구** > **옵션** 열려는 합니다 **옵션** 대화 합니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-157">To disable notifications, choose **Tools** > **Options** to open the **Options** dialog.</span></span> <span data-ttu-id="239a7-158">그런 다음, 선택 **Windows Forms 디자이너** > **일반**, 설정 **DPI 크기 조정 알림** 에 **False**합니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-158">Then, choose **Windows Forms Designer** > **General**, and set **DPI Scaling Notifications** to **False**.</span></span>

![Visual Studio에서 알림 옵션을 확장 하는 DPI](./media/disable-dpi-awareness-visual-studio/notifications-option.png)

<span data-ttu-id="239a7-160">나중에 다시 크기 조정 알림을 사용 하도록 설정 하려는 경우 속성을 설정 **True**합니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-160">If you want to later reenable scaling notifications, set the property to **True**.</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="239a7-161">문제 해결</span><span class="sxs-lookup"><span data-stu-id="239a7-161">Troubleshoot</span></span>

<span data-ttu-id="239a7-162">DPI 인식 전환 Visual Studio에서 예상 대로 작동 하지 않는 경우 확인 해야 합니다 `dpiAwareness` 값을 **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image 파일 실행 Options\devenv.exe**  레지스트리 편집기에서 하위 키입니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-162">If the DPI-awareness transition isn't working as expected in Visual Studio, check to see if you have the `dpiAwareness` value in the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File Execution Options\devenv.exe** subkey in Registry Editor.</span></span> <span data-ttu-id="239a7-163">있는 경우 값을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="239a7-163">Delete the value if it's present.</span></span>

## <a name="see-also"></a><span data-ttu-id="239a7-164">참고자료</span><span class="sxs-lookup"><span data-stu-id="239a7-164">See also</span></span>

- [<span data-ttu-id="239a7-165">Windows Forms의 자동 크기 조정</span><span class="sxs-lookup"><span data-stu-id="239a7-165">Automatic scaling in Windows Forms</span></span>](automatic-scaling-in-windows-forms.md)
