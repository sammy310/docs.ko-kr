---
ms.openlocfilehash: cc3c2c2be179842f87be8892d057a6c4138086cb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614876"
---
### <a name="accessibility-improvements-in-windows-forms-controls-for-net-472"></a><span data-ttu-id="3e809-101">.NET 4.7.2에 대한 Windows Forms 콘트롤의 접근성 개선 사항</span><span class="sxs-lookup"><span data-stu-id="3e809-101">Accessibility improvements in Windows Forms controls for .NET 4.7.2</span></span>

#### <a name="details"></a><span data-ttu-id="3e809-102">설명</span><span class="sxs-lookup"><span data-stu-id="3e809-102">Details</span></span>

<span data-ttu-id="3e809-103">Windows Forms Framework는 Windows Forms 고객을 더욱 효과적으로 지원하도록 접근성 기술로 작업하는 방법을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="3e809-103">Windows Forms Framework is improving how it works with accessibility technologies to better support Windows Forms customers.</span></span> <span data-ttu-id="3e809-104">여기에는 다음과 같은 변경이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e809-104">These include the following changes:</span></span>

- <span data-ttu-id="3e809-105">고대비 모드 중에 표시를 개선하기 위한 변경 내용</span><span class="sxs-lookup"><span data-stu-id="3e809-105">Changes to improve display during High Contrast mode.</span></span>
- <span data-ttu-id="3e809-106">DataGridView 및 MenuStrip 컨트롤에서 키보드 탐색을 개선하기 위한 변경 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="3e809-106">Changes to improve the keyboard navigation in the DataGridView and MenuStrip controls.</span></span>
- <span data-ttu-id="3e809-107">내레이터와 상호 작용의 변경 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="3e809-107">Changes to interaction with Narrator.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="3e809-108">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="3e809-108">Suggestion</span></span>

<span data-ttu-id="3e809-109">**이러한 변경을 옵트인 또는 옵트아웃하는 방법**: 애플리케이션이 이러한 변경의 이점을 활용하도록 하기 위해 .NET Framework 4.7.2 이상에서 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e809-109">**How to opt in or out of these changes** In order for the application to benefit from these changes, it must run on the .NET Framework 4.7.2 or later.</span></span> <span data-ttu-id="3e809-110">애플리케이션은 다음과 같은 방법으로 이러한 변경의 이점을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e809-110">The application can benefit from these changes in either of the following ways:</span></span>

- <span data-ttu-id="3e809-111">컴파일되어 .NET Framework 4.7.2를 대상으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e809-111">It is recompiled to target the .NET Framework 4.7.2.</span></span> <span data-ttu-id="3e809-112">이러한 접근성 변경 내용은 .NET Framework 4.7.2 이상을 대상으로 하는 Windows Forms 애플리케이션에서 기본적으로 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e809-112">These accessibility changes are enabled by default on Windows Forms applications that target the .NET Framework 4.7.2 or later.</span></span>
- <span data-ttu-id="3e809-113">.NET Framework 4.7.1 이전 버전을 대상으로 하며 다음 예제와 같이 app.config 파일의 `<runtime>` 섹션에 [AppContext 스위치](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element)를 추가하고 이를 `false`로 설정하여 레거시 접근성 동작을 옵트아웃합니다.</span><span class="sxs-lookup"><span data-stu-id="3e809-113">It targets the .NET Framework 4.7.1 or earlier version and opts out of the legacy accessibility behaviors by adding the following [AppContext Switch](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) to the `<runtime>` section of the app config file and setting it to `false`, as the following example shows.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <startup>
    <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7"/>
  </startup>
  <runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true/false;key2=true/false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
  </runtime>
</configuration>
```

<span data-ttu-id="3e809-114">.NET Framework 4.7.2에 추가된 접근성 기능을 옵트인하려면 .NET Framework 4.7.1의 접근성 기능도 옵트인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e809-114">Note that to opt in to the accessibility features added in .NET Framework 4.7.2, you must also opt in to accessibility features of .NET Framework 4.7.1 as well.</span></span> <span data-ttu-id="3e809-115">.NET Framework 4.7.2 이상을 대상으로 하고 레거시 접근성 동작을 유지하려는 애플리케이션은 이 AppContext 스위치를 `true`로 명확하게 설정하여 레거시 접근성 기능 사용을 옵트인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e809-115">Applications that target the .NET Framework 4.7.2 or later and want to preserve the legacy accessibility behavior can opt in to the use of legacy accessibility features by explicitly setting this AppContext switch to `true`.</span></span>

<span data-ttu-id="3e809-116">**고대비 테마에서 OS 정의 색 사용**</span><span class="sxs-lookup"><span data-stu-id="3e809-116">**Use of OS-defined colors in High Contrast themes**</span></span>

- <span data-ttu-id="3e809-117"><xref:System.Windows.Forms.ToolStripDropDownButton>의 드롭다운 화살표는 이제 고대비 테마에서 OS 정의 색을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e809-117">The drop down arrow of the <xref:System.Windows.Forms.ToolStripDropDownButton> now uses OS-defined colors in High Contrast theme.</span></span>
- <span data-ttu-id="3e809-118"><xref:System.Windows.Forms.ButtonBase.FlatStyle>를 <xref:System.Windows.Forms.FlatStyle.Flat?displayProperty=nameWithType> 또는 <xref:System.Windows.Forms.FlatStyle.Popup?displayProperty=nameWithType>으로 설정한 <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.RadioButton> 및 <xref:System.Windows.Forms.CheckBox> 컨트롤은 선택된 경우 고대비 테마에서 OS 정의 색을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e809-118"><xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.RadioButton> and <xref:System.Windows.Forms.CheckBox> controls with <xref:System.Windows.Forms.ButtonBase.FlatStyle> set to <xref:System.Windows.Forms.FlatStyle.Flat?displayProperty=nameWithType> or <xref:System.Windows.Forms.FlatStyle.Popup?displayProperty=nameWithType> now use OS-defined colors in High Contrast theme when selected.</span></span> <span data-ttu-id="3e809-119">이전에 텍스트 및 배경색이 대비되지 않았고 읽기가 어려웠습니다.</span><span class="sxs-lookup"><span data-stu-id="3e809-119">Previously, text and background colors were not contrasting and were hard to read.</span></span>
- <span data-ttu-id="3e809-120"><xref:System.Windows.Forms.Control.Enabled> 속성을 `false`으로 설정한 <xref:System.Windows.Forms.GroupBox>에 포함된 컨트롤은 이제 고대비 테마에서 OS 정의 색을 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e809-120">Controls contained within a <xref:System.Windows.Forms.GroupBox> that has its <xref:System.Windows.Forms.Control.Enabled> property set to `false` will now use OS-defined colors in High Contrast theme.</span></span>
- <span data-ttu-id="3e809-121"><xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripComboBox> 및 <xref:System.Windows.Forms.ToolStripDropDownButton> 컨트롤이 고대비 모드에서 명도 대비를 증가시켰습니다.</span><span class="sxs-lookup"><span data-stu-id="3e809-121">The <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripComboBox>, and <xref:System.Windows.Forms.ToolStripDropDownButton> controls have an increased luminosity contrast ratio in High Contrast Mode.</span></span>
- <span data-ttu-id="3e809-122"><xref:System.Windows.Forms.DataGridViewLinkCell>은 기본적으로 <xref:System.Windows.Forms.DataGridViewLinkCell.LinkColor?displayProperty=nameWithType> 속성에 대한 고대비 모드에서 OS 정의 색을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e809-122"><xref:System.Windows.Forms.DataGridViewLinkCell> will by default use OS-defined colors in High Contrast mode for the <xref:System.Windows.Forms.DataGridViewLinkCell.LinkColor?displayProperty=nameWithType> property.</span></span>
<span data-ttu-id="3e809-123">참고:  Windows 10은 일부 고대비 시스템 색에 대한 값을 변경했습니다.</span><span class="sxs-lookup"><span data-stu-id="3e809-123">NOTE: Windows 10 has changed values for some high contrast system colors.</span></span> <span data-ttu-id="3e809-124">Windows Forms Framework는 Win32 프레임워크를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e809-124">Windows Forms Framework is based on the Win32 framework.</span></span> <span data-ttu-id="3e809-125">환경을 최적화하기 위해 테스트 애플리케이션에 app.manifest 파일을 추가하고 다음과 같은 코드의 주석을 제거하여 최신 버전의 Windows에서 실행하고 최신 OS 변경 사항을 옵트인합니다.</span><span class="sxs-lookup"><span data-stu-id="3e809-125">For the best experience, run on the latest version of Windows and opt in to the latest OS changes by adding an app.manifest file in a test application and un-commenting the following code:</span></span>

```xml
<!-- Windows 10 -->
<supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
```

<span data-ttu-id="3e809-126">**향상된 내레이터 지원**</span><span class="sxs-lookup"><span data-stu-id="3e809-126">**Improved Narrator support**</span></span>

- <span data-ttu-id="3e809-127"><xref:System.Windows.Forms.ToolStripMenuItem>의 텍스트를 발표할 경우 내레이터는 <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType> 속성 값도 발표합니다.</span><span class="sxs-lookup"><span data-stu-id="3e809-127">Narrator now announces the value of the <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType> property when announcing the text of a <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>
- <span data-ttu-id="3e809-128">내레이터는 <xref:System.Windows.Forms.ToolStripMenuItem>이 해당 <xref:System.Windows.Forms.Control.Enabled> 속성을 `false`으로 설정할 때를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e809-128">Narrator now indicates when a <xref:System.Windows.Forms.ToolStripMenuItem> has its <xref:System.Windows.Forms.Control.Enabled> property set to `false`.</span></span>
- <span data-ttu-id="3e809-129">내레이터는 <xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType> 속성이 `true`로 설정될 경우 확인란의 상태에 대한 피드백을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3e809-129">Narrator now gives feedback on the state of a check box when the <xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType> property is set to `true`.</span></span>
- <span data-ttu-id="3e809-130">내레이터 스캔 모드 포커스 순서는 ClickOnce 다운로드 대화 상자 창에서 컨트롤의 시각적 개체 순서와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="3e809-130">Narrator Scan Mode focus order is now consistent with the visual order of the controls on the ClickOnce download dialog window.</span></span>

<span data-ttu-id="3e809-131">**개선된 DataGridView 접근성 지원**</span><span class="sxs-lookup"><span data-stu-id="3e809-131">**Improved DataGridView Accessibility support**</span></span>

- <span data-ttu-id="3e809-132"><xref:System.Windows.Forms.DataGridView>의 행은 키보드를 사용하여 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e809-132">Rows in a <xref:System.Windows.Forms.DataGridView> can now be sorted using the keyboard.</span></span> <span data-ttu-id="3e809-133">현재 열로 정렬하려면 사용자는 F3 키를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e809-133">Now a user can use the F3 key in order to sort by the current column.</span></span>
- <span data-ttu-id="3e809-134"><xref:System.Windows.Forms.DataGridView.SelectionMode?displayProperty=nameWithType>이 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType>로 설정된 경우 열 헤더는 색을 변경하여 현재 행의 셀을 통해 현재 열을 사용자 탭으로 나타내게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e809-134">When the <xref:System.Windows.Forms.DataGridView.SelectionMode?displayProperty=nameWithType> is set to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType>, the column header will change color to indicate the current column as the user tabs through the cells in the current row.</span></span>
- <span data-ttu-id="3e809-135"><xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Parent?displayProperty=nameWithType> 속성은 이제 올바른 부모 컨트롤을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3e809-135">The <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Parent?displayProperty=nameWithType> property now returns the correct parent control.</span></span>

<span data-ttu-id="3e809-136">**개선된 시각적 표시**</span><span class="sxs-lookup"><span data-stu-id="3e809-136">**Improved Visual cues**</span></span>

- <span data-ttu-id="3e809-137"><xref:System.Windows.Forms.ButtonBase.Text> 속성이 빈 <xref:System.Windows.Forms.RadioButton> 및 <xref:System.Windows.Forms.CheckBox> 컨트롤은 포커스를 받을 때 포커스 표시기를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3e809-137">The <xref:System.Windows.Forms.RadioButton> and <xref:System.Windows.Forms.CheckBox> controls with an empty <xref:System.Windows.Forms.ButtonBase.Text> property will now display a focus indicator when they receive focus.</span></span>

<span data-ttu-id="3e809-138">**개선된 속성 표 지원**</span><span class="sxs-lookup"><span data-stu-id="3e809-138">**Improved Property Grid Support**</span></span>

- <span data-ttu-id="3e809-139"><xref:System.Windows.Forms.PropertyGrid> 컨트롤 자식 요소는 PropertyGrid 요소를 사용하도록 설정한 경우에만 <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> 속성에 대한 `true`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3e809-139">The <xref:System.Windows.Forms.PropertyGrid> control child elements now return a `true` for the  <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> property only when a PropertyGrid element is enabled.</span></span>
- <span data-ttu-id="3e809-140"><xref:System.Windows.Forms.PropertyGrid> 컨트롤 자식 요소는 PropertyGrid 요소를 사용자가 변경할 수 있는 경우에만 <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> 속성에 대한 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3e809-140">The <xref:System.Windows.Forms.PropertyGrid> control child elements now return a `false` for the <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> property only when a PropertyGrid element can be changed by the user.</span></span>
<span data-ttu-id="3e809-141">UI 자동화 개요는 [UI Automation 개요](https://docs.microsoft.com/dotnet/framework/ui-automation/ui-automation-overview)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3e809-141">For an overview of UI automation, see the [UI Automation Overview](https://docs.microsoft.com/dotnet/framework/ui-automation/ui-automation-overview).</span></span></p><span data-ttu-id="3e809-142">**바로 가기 탐색 개선**</span><span class="sxs-lookup"><span data-stu-id="3e809-142">**Improved keyboard navigation**</span></span>

- <span data-ttu-id="3e809-143"><xref:System.Windows.Forms.ToolStripButton>은 <xref:System.Windows.Forms.ToolStripPanel.TabStop> 속성이 `true`로 설정된 <xref:System.Windows.Forms.ToolStripPanel>에 포함된 경우 포커스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e809-143"><xref:System.Windows.Forms.ToolStripButton> now allows focus when contained within a <xref:System.Windows.Forms.ToolStripPanel> that has the <xref:System.Windows.Forms.ToolStripPanel.TabStop> property set to `true`.</span></span>

| <span data-ttu-id="3e809-144">이름</span><span class="sxs-lookup"><span data-stu-id="3e809-144">Name</span></span>    | <span data-ttu-id="3e809-145">값</span><span class="sxs-lookup"><span data-stu-id="3e809-145">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3e809-146">Scope</span><span class="sxs-lookup"><span data-stu-id="3e809-146">Scope</span></span>   | <span data-ttu-id="3e809-147">주요함</span><span class="sxs-lookup"><span data-stu-id="3e809-147">Major</span></span>       |
| <span data-ttu-id="3e809-148">버전</span><span class="sxs-lookup"><span data-stu-id="3e809-148">Version</span></span> | <span data-ttu-id="3e809-149">4.7.2</span><span class="sxs-lookup"><span data-stu-id="3e809-149">4.7.2</span></span>       |
| <span data-ttu-id="3e809-150">형식</span><span class="sxs-lookup"><span data-stu-id="3e809-150">Type</span></span>    | <span data-ttu-id="3e809-151">대상 변경</span><span class="sxs-lookup"><span data-stu-id="3e809-151">Retargeting</span></span> |
