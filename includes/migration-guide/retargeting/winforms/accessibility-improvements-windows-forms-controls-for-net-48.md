---
ms.openlocfilehash: e528a41748d9353c96d443f68e15e7a98ee7f4ae
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616281"
---
### <a name="accessibility-improvements-in-windows-forms-controls-for-net-48"></a><span data-ttu-id="e0168-101">.NET 4.8에 대한 Windows Forms 콘트롤의 접근성 개선 사항</span><span class="sxs-lookup"><span data-stu-id="e0168-101">Accessibility improvements in Windows Forms controls for .NET 4.8</span></span>

#### <a name="details"></a><span data-ttu-id="e0168-102">설명</span><span class="sxs-lookup"><span data-stu-id="e0168-102">Details</span></span>

<span data-ttu-id="e0168-103">Windows Forms Framework는 Windows Forms 고객을 더욱 효과적으로 지원하도록 접근성 기술로 작업하는 방법을 지속적으로 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="e0168-103">The Windows Forms Framework is continuing to improve how it works with accessibility technologies to better support Windows Forms customers.</span></span> <span data-ttu-id="e0168-104">여기에는 다음과 같은 변경이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0168-104">These include the following changes:</span></span>

- <span data-ttu-id="e0168-105">고대비 모드 중에 표시를 개선하기 위한 변경 내용</span><span class="sxs-lookup"><span data-stu-id="e0168-105">Changes to improve display during High Contrast mode.</span></span>
- <span data-ttu-id="e0168-106">내레이터와 상호 작용의 변경 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="e0168-106">Changes to interaction with Narrator.</span></span>
- <span data-ttu-id="e0168-107">액세스 가능한 계층 구조의 변경 내용(UI Automation 트리를 통한 탐색 개선).</span><span class="sxs-lookup"><span data-stu-id="e0168-107">Changes in the Accessible hierarchy (improving navigation through the UI Automation tree).</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e0168-108">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="e0168-108">Suggestion</span></span>

<span data-ttu-id="e0168-109">**이러한 변경을 옵트인 또는 옵트아웃하는 방법** 이러한 변경의 이점을 활용하려면 애플리케이션은 .NET Framework 4.8에서 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0168-109">**How to opt in or out of these changes** In order for the application to benefit from these changes, it must run on the .NET Framework 4.8.</span></span> <span data-ttu-id="e0168-110">애플리케이션은 다음과 같은 방법으로 이러한 변경 내용을 옵트인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0168-110">The application can opt in into these changes in either of the following ways:</span></span>

- <span data-ttu-id="e0168-111">.NET Framework 4.8을 대상으로 다시 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0168-111">It is recompiled to target the .NET Framework 4.8.</span></span> <span data-ttu-id="e0168-112">이러한 접근성 변경 내용은 .NET Framework 4.8을 대상으로 하는 Windows Forms 애플리케이션에서 기본적으로 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0168-112">These accessibility changes are enabled by default on Windows Forms applications that target the .NET Framework 4.8.</span></span>
- <span data-ttu-id="e0168-113">.NET Framework 4.7.2 이전 버전을 대상으로 하며 다음 예제와 같이 app.config 파일의 `<runtime>` 섹션에 [AppContext 스위치](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element)를 추가하고 이를 `false`로 설정하여 레거시 접근성 동작을 옵트아웃합니다.</span><span class="sxs-lookup"><span data-stu-id="e0168-113">It targets the .NET Framework 4.7.2 or earlier version and opts out of the legacy accessibility behaviors by adding the following [AppContext switch](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) to the `<runtime>` section of the app config file and setting it to `false`, as the following example shows.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <startup>
    <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7"/>
  </startup>
  <runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true/false;key2=true/false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;Switch.UseLegacyAccessibilityFeatures.3=false" />
  </runtime>
</configuration>
```

<span data-ttu-id="e0168-114">.NET Framework 4.8에 추가된 접근성 기능을 옵트인하려면 .NET Framework 4.7.1 및 4.7.2의 접근성 기능도 옵트인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0168-114">Note that to opt in to the accessibility features added in .NET Framework 4.8, you must also opt in to accessibility features of .NET Framework 4.7.1 and 4.7.2 as well.</span></span> <span data-ttu-id="e0168-115">.NET Framework 4.8을 대상으로 하고 레거시 접근성 동작을 유지하려는 애플리케이션은 이 AppContext 스위치를 `true`로 명확하게 설정하여 레거시 접근성 기능 사용을 옵트인할 수 있습니다. 키보드 도구 설명 호출 지원을 사용하려면 `Switch.System.Windows.Forms.UseLegacyToolTipDisplay=false` 줄을 AppContextSwitchOverrides 값에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0168-115">Applications that target the .NET Framework 4.8 and want to preserve the legacy accessibility behavior can opt in to the use of legacy accessibility features by explicitly setting this AppContext switch to `true`.Enabling the keyboard ToolTip invocation support requires adding the `Switch.System.Windows.Forms.UseLegacyToolTipDisplay=false` line to the AppContextSwitchOverrides value:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;Switch.UseLegacyAccessibilityFeatures.3=false;Switch.System.Windows.Forms.UseLegacyToolTipDisplay=false" />
```

<span data-ttu-id="e0168-116">이 기능을 사용하려면 앞에서 언급한 .NET Framework 4.7.1 - 4.8의 접근성 기능도 옵트인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0168-116">Note that enabling this feature requires opting in to the aforementioned accessibility features of .NET Framework 4.7.1 - 4.8.</span></span> <span data-ttu-id="e0168-117">또한 접근성 기능을 옵트인하지 않고 도구 설명 표시 기능을 옵트인하면 이러한 기능에 처음 액세스할 때 런타임 <xref:System.NotSupportedException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0168-117">Also, if any of the accessibility features are not opted in but the tooltip display feature is opted in, a runtime <xref:System.NotSupportedException> will be thrown on the first access to these features.</span></span> <span data-ttu-id="e0168-118">예외 메시지는 키보드 도구 설명에서 수준 3의 접근성 개선을 사용하도록 요구함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e0168-118">The exception message indicates that keyboard ToolTips require accessibility improvements of level 3 to be enabled.</span></span>

<span data-ttu-id="e0168-119">**고대비 테마에서 OS 정의 색 사용**</span><span class="sxs-lookup"><span data-stu-id="e0168-119">**Use of OS-defined colors in High Contrast themes**</span></span>

- <span data-ttu-id="e0168-120">고대비 테마를 개선했습니다.</span><span class="sxs-lookup"><span data-stu-id="e0168-120">Improved high-contrast themes.</span></span>

<span data-ttu-id="e0168-121">**향상된 내레이터 지원**</span><span class="sxs-lookup"><span data-stu-id="e0168-121">**Improved Narrator support**</span></span>

- <span data-ttu-id="e0168-122">이제 내레이터는 <xref:System.Windows.Forms.DataGridViewCell>의 액세스 가능한 이름을 발표할 때 <xref:System.Windows.Forms.DataGridViewColumn>의 정렬 방향을 공지합니다.</span><span class="sxs-lookup"><span data-stu-id="e0168-122">Narrator now announces the sort direction of the <xref:System.Windows.Forms.DataGridViewColumn> when announcing an accessible name of a <xref:System.Windows.Forms.DataGridViewCell>.</span></span>

<span data-ttu-id="e0168-123">**향상된 CheckedListBox 접근성 지원**</span><span class="sxs-lookup"><span data-stu-id="e0168-123">**Improved CheckedListBox Accessibility support**</span></span>

- <span data-ttu-id="e0168-124"><xref:System.Windows.Forms.CheckedListBox> 컨트롤에 대한 향상된 내레이터 지원.</span><span class="sxs-lookup"><span data-stu-id="e0168-124">Improved Narrator support for the <xref:System.Windows.Forms.CheckedListBox> control.</span></span> <span data-ttu-id="e0168-125">키보드를 사용하여 <xref:System.Windows.Forms.CheckedListBox> 컨트롤로 이동할 때 내레이터는 <xref:System.Windows.Forms.CheckedListBox> 항목에 초점을 맞추고 이를 공지합니다.</span><span class="sxs-lookup"><span data-stu-id="e0168-125">When navigating to the <xref:System.Windows.Forms.CheckedListBox> control using the keyboard, Narrator focuses the <xref:System.Windows.Forms.CheckedListBox> item and announces it.</span></span>
- <span data-ttu-id="e0168-126">이제 빈 CheckedListBox 컨트롤에 컨트롤이 집중되면 가상 첫 번째 항목에 대해 포커스 사각형이 그려집니다.</span><span class="sxs-lookup"><span data-stu-id="e0168-126">An empty CheckedListBox control now has a focus rectangle drawn for a virtual first item when the control becomes focused.</span></span>

<span data-ttu-id="e0168-127">**향상된 ComboBox 접근성 지원**</span><span class="sxs-lookup"><span data-stu-id="e0168-127">**Improved ComboBox Accessibility support**</span></span>

- <span data-ttu-id="e0168-128">UI Automation 알림 및 기타 UI Automation 기능을 사용할 수 있는 기능이 있는 <xref:System.Windows.Forms.ComboBox> 컨트롤에 대한 UI Automation 지원을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0168-128">Enabled UI Automation support for the <xref:System.Windows.Forms.ComboBox> control, with the ability to use UI Automation notifications and other UI Automation features.</span></span>
<span data-ttu-id="e0168-129">**개선된 DataGridView 접근성 지원**</span><span class="sxs-lookup"><span data-stu-id="e0168-129">**Improved DataGridView Accessibility support**</span></span>

- <span data-ttu-id="e0168-130">UI Automation 알림 및 기타 UI Automation 기능을 사용할 수 있는 기능이 있는 <xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 UI Automation 지원을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0168-130">Enabled UI Automation support for <xref:System.Windows.Forms.DataGridView> control with ability to use UI Automation notifications and other UI Automation features.</span></span>
- <span data-ttu-id="e0168-131"><xref:System.Windows.Forms.DataGridViewComboBoxEditingControl> 또는 <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>에 해당하는 UI Automation 요소는 이제 해당 편집 셀의 자식입니다.</span><span class="sxs-lookup"><span data-stu-id="e0168-131">The UI Automation element which corresponds to the <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl> or <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl> is now a child of corresponding editing cell.</span></span>

<span data-ttu-id="e0168-132">**향상된 LinkLabel 접근성 지원**</span><span class="sxs-lookup"><span data-stu-id="e0168-132">**Improved LinkLabel Accessibility support**</span></span>

- <span data-ttu-id="e0168-133">향상된 <xref:System.Windows.Forms.LinkLabel> 컨트롤 접근성: 내레이터는 해당 <xref:System.Windows.Forms.LinkLabel> 컨트롤이 비활성화된 경우 링크의 비활성화 상태를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="e0168-133">Improved <xref:System.Windows.Forms.LinkLabel> control accessibility: Narrator announces the disabled state for the link if the corresponding <xref:System.Windows.Forms.LinkLabel> control is disabled.</span></span>

<span data-ttu-id="e0168-134">**향상된 ProgressBar 접근성 지원**</span><span class="sxs-lookup"><span data-stu-id="e0168-134">**Improved ProgressBar Accessibility support**</span></span>

- <span data-ttu-id="e0168-135">UI Automation 알림 및 기타 UI Automation 기능을 사용할 수 있는 기능이 있는 <xref:System.Windows.Forms.ProgressBar> 컨트롤에 대한 UI Automation 지원을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0168-135">Enabled UI Automation support for the <xref:System.Windows.Forms.ProgressBar> control with the ability to use UI Automation notifications and other UI Automation features.</span></span> <span data-ttu-id="e0168-136">개발자는 이제 내레이터가 진행률을 표시하기 위해 알릴 수 있는 UI Automation 알림을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0168-136">Developers are now able to use UI Automation notifications which Narrator can announce to indicate progress.</span></span>
<span data-ttu-id="e0168-137">UI 자동화 알림 이벤트를 비롯하여 UI 자동화 이벤트 개요는 [UI 자동화 이벤트 개요](https://docs.microsoft.com/windows/desktop/WinAuto/uiauto-eventsoverview)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0168-137">For an overview of UI automation events overview, including UI automation notification events, see the [UI Automation Events Overview](https://docs.microsoft.com/windows/desktop/WinAuto/uiauto-eventsoverview).</span></span>

<span data-ttu-id="e0168-138">**향상된 PropertyGrid 접근성 지원**</span><span class="sxs-lookup"><span data-stu-id="e0168-138">**Improved PropertyGrid Accessibility support**</span></span>

- <span data-ttu-id="e0168-139">UI Automation 알림 및 기타 UI Automation 기능을 사용할 수 있는 기능이 있는 <xref:System.Windows.Forms.PropertyGrid> 컨트롤에 대한 UI Automation 지원을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0168-139">Enabled UI Automation support for the <xref:System.Windows.Forms.PropertyGrid> control, with the ability to use UI Automation notifications and other UI Automation features.</span></span>
- <span data-ttu-id="e0168-140">현재 편집된 속성에 해당하는 UI Automation 요소는 이제 해당 속성 항목 UI Automation 요소의 자식이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0168-140">The UI Automation element which corresponds to the currently edited property is now a child of the corresponding property item UI Automation element.</span></span>
- <span data-ttu-id="e0168-141">부모 <xref:System.Windows.Forms.PropertyGrid> 컨트롤이 범주 보기로 설정된 경우 UI Automation 속성 항목은 이제 해당 범주 요소의 자식이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0168-141">The UI Automation property item element is now a child of the corresponding category element if the parent <xref:System.Windows.Forms.PropertyGrid> control is set to category view.</span></span>

<span data-ttu-id="e0168-142">**향상된 ToolStrip 지원**</span><span class="sxs-lookup"><span data-stu-id="e0168-142">**Improved ToolStrip support**</span></span>

- <span data-ttu-id="e0168-143">UI Automation 알림 및 기타 UI Automation 기능을 사용할 수 있는 기능이 있는 <xref:System.Windows.Forms.ToolStrip> 컨트롤에 대한 UI Automation 지원을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0168-143">Enabled UI Automation support for the <xref:System.Windows.Forms.ToolStrip> control, with the ability to use UI Automation notifications and other UI Automation features.</span></span>
- <span data-ttu-id="e0168-144"><xref:System.Windows.Forms.ToolStrip> 항목을 통한 탐색 기능이 개선되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e0168-144">Improved navigation through <xref:System.Windows.Forms.ToolStrip> items.</span></span>
- <span data-ttu-id="e0168-145">항목 모드에서는 내레이터 포커스는 사라지지 않고 숨겨진 항목으로 이동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0168-145">In items mode, Narrator focus does not disappear and does not go to hidden items.</span></span>

<span data-ttu-id="e0168-146">**개선된 시각적 표시**</span><span class="sxs-lookup"><span data-stu-id="e0168-146">**Improved Visual cues**</span></span>

- <span data-ttu-id="e0168-147">이제 빈 <xref:System.Windows.Forms.CheckedListBox> 컨트롤은 포커스를 수신할 때 포커스 표시기를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="e0168-147">An empty <xref:System.Windows.Forms.CheckedListBox> control now displays a focus indicator when it receives focus.</span></span>
<span data-ttu-id="e0168-148">참고: UI 자동화 지원은 런타임의 컨트롤에 대해 활성화되지만 디자인 타임에는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0168-148">Note: UI automation support is enabled for controls in runtime but is not used in design time.</span></span> <span data-ttu-id="e0168-149">UI 자동화 개요는 [UI Automation 개요](https://docs.microsoft.com/dotnet/framework/ui-automation/ui-automation-overview)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0168-149">For an overview of UI automation, see the [UI Automation Overview](https://docs.microsoft.com/dotnet/framework/ui-automation/ui-automation-overview).</span></span>

<span data-ttu-id="e0168-150">**키보드를 사용하여 컨트롤의 도구 설명 호출**</span><span class="sxs-lookup"><span data-stu-id="e0168-150">**Invoking controls' ToolTips with a keyboard**</span></span>

- <span data-ttu-id="e0168-151">이제 컨트롤 도구 설명은 키보드로 집중하여 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0168-151">Control tooltip can now be invoked by focusing the control with keyboard.</span></span> <span data-ttu-id="e0168-152">이 기능은 애플리케이션에 대해 명시적으로 사용하도록 설정해야 합니다( **&quot;이 변경 내용을 옵트인 또는 옵트아웃하는 방법&quot;** 섹션 참조).</span><span class="sxs-lookup"><span data-stu-id="e0168-152">This feature needs to be enabled explicitly for the application (see section **&quot;How to opt in or out of these changes&quot;**)</span></span>

| <span data-ttu-id="e0168-153">이름</span><span class="sxs-lookup"><span data-stu-id="e0168-153">Name</span></span>    | <span data-ttu-id="e0168-154">값</span><span class="sxs-lookup"><span data-stu-id="e0168-154">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e0168-155">Scope</span><span class="sxs-lookup"><span data-stu-id="e0168-155">Scope</span></span>   | <span data-ttu-id="e0168-156">주요함</span><span class="sxs-lookup"><span data-stu-id="e0168-156">Major</span></span>       |
| <span data-ttu-id="e0168-157">버전</span><span class="sxs-lookup"><span data-stu-id="e0168-157">Version</span></span> | <span data-ttu-id="e0168-158">4.8</span><span class="sxs-lookup"><span data-stu-id="e0168-158">4.8</span></span>         |
| <span data-ttu-id="e0168-159">형식</span><span class="sxs-lookup"><span data-stu-id="e0168-159">Type</span></span>    | <span data-ttu-id="e0168-160">대상 변경</span><span class="sxs-lookup"><span data-stu-id="e0168-160">Retargeting</span></span> |
