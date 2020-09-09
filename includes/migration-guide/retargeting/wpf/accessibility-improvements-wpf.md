---
ms.openlocfilehash: 895d09e4ec39bd4a92ed1f4910da80474334d99b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497923"
---
### <a name="accessibility-improvements-in-wpf"></a><span data-ttu-id="9fc3e-101">WPF의 접근성 개선 사항</span><span class="sxs-lookup"><span data-stu-id="9fc3e-101">Accessibility improvements in WPF</span></span>

#### <a name="details"></a><span data-ttu-id="9fc3e-102">설명</span><span class="sxs-lookup"><span data-stu-id="9fc3e-102">Details</span></span>

<span data-ttu-id="9fc3e-103">**고대비 개선 사항**</span><span class="sxs-lookup"><span data-stu-id="9fc3e-103">**High Contrast improvements**</span></span>

- <span data-ttu-id="9fc3e-104">이제 <xref:System.Windows.Controls.Expander> 컨트롤에 대한 포커스가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fc3e-104">The focus for the <xref:System.Windows.Controls.Expander> control is now visible.</span></span> <span data-ttu-id="9fc3e-105">이전 버전의 .NET Framework에서는 그렇지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="9fc3e-105">In previous versions of .NET Framework, it was not.</span></span>
- <span data-ttu-id="9fc3e-106"><xref:System.Windows.Controls.CheckBox> 및 <xref:System.Windows.Controls.RadioButton> 컨트롤의 텍스트를 선택하면 이전 .NET Framework 버전보다 보기 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="9fc3e-106">The text in <xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls when they are selected is now easier to see than in previous .NET Framework versions.</span></span>
- <span data-ttu-id="9fc3e-107">비활성화된 <xref:System.Windows.Controls.ComboBox>의 테두리는 이제 비활성화된 텍스트와 동일한 색입니다.</span><span class="sxs-lookup"><span data-stu-id="9fc3e-107">The border of a disabled <xref:System.Windows.Controls.ComboBox> is now the same color as the disabled text.</span></span> <span data-ttu-id="9fc3e-108">이전 버전의 .NET Framework에서는 그렇지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="9fc3e-108">In previous versions of .NET Framework, it was not.</span></span>
- <span data-ttu-id="9fc3e-109">이제 비활성화되고 포커스가 있는 단추는 올바른 테마 색을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9fc3e-109">Disabled and focused buttons now use the correct theme color.</span></span> <span data-ttu-id="9fc3e-110">이전 버전의 .NET Framework에서는 그러지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="9fc3e-110">In previous versions of .NET Framework, they did not.</span></span>
- <span data-ttu-id="9fc3e-111">이제는 <xref:System.Windows.Controls.ComboBox> 컨트롤의 스타일이 <xref:System.Windows.Controls.ToolBar.ComboBoxStyleKey?displayProperty=nameWithType>으로 설정된 경우 드롭다운 단추가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fc3e-111">The dropdown button is now visible when a <xref:System.Windows.Controls.ComboBox> control's style is set to <xref:System.Windows.Controls.ToolBar.ComboBoxStyleKey?displayProperty=nameWithType>.</span></span> <span data-ttu-id="9fc3e-112">이전 버전의 .NET Framework에서는 그렇지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="9fc3e-112">In previous versions of .NET Framework, it was not.</span></span>
- <span data-ttu-id="9fc3e-113">이제 <xref:System.Windows.Controls.DataGrid> 컨트롤의 정렬 표시기 화살표는 테마 색을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9fc3e-113">The sort indicator arrow in a <xref:System.Windows.Controls.DataGrid> control now uses theme colors.</span></span> <span data-ttu-id="9fc3e-114">이전 버전의 .NET Framework에서는 그러지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="9fc3e-114">In previous versions of .NET Framework, it did not.</span></span>
- <span data-ttu-id="9fc3e-115">이제 마우스를 위에 가져가면 기본 하이퍼링크 스타일이 올바른 테마 색으로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fc3e-115">The default hyperlink style now changes to the correct theme color on mouse over.</span></span> <span data-ttu-id="9fc3e-116">이전 버전의 .NET Framework에서는 그러지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="9fc3e-116">In previous versions of .NET Framework, it did not.</span></span>
- <span data-ttu-id="9fc3e-117">이제 라디오 단추에서 바로 가기 포커스가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fc3e-117">The Keyboard focus on radio buttons is now visible.</span></span> <span data-ttu-id="9fc3e-118">이전 버전의 .NET Framework에서는 그렇지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="9fc3e-118">In previous versions of .NET Framework, it was not.</span></span>
- <span data-ttu-id="9fc3e-119">이제 <xref:System.Windows.Controls.DataGrid> 컨트롤의 확인란 열은 바로 가기 포커스 피드백에 예상되는 색을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9fc3e-119">The <xref:System.Windows.Controls.DataGrid> control's checkbox column now uses the expected colors for keyboard focus feedback.</span></span> <span data-ttu-id="9fc3e-120">이전 버전의 .NET Framework에서는 그러지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="9fc3e-120">In previous versions of .NET Framework, it did not.</span></span>
- <span data-ttu-id="9fc3e-121">이제 바로 가기 포커스 시각적 개체가 <xref:System.Windows.Controls.ComboBox> 및 <xref:System.Windows.Controls.ListBox> 컨트롤에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fc3e-121">the Keyboard focus visuals are now visible on <xref:System.Windows.Controls.ComboBox> and <xref:System.Windows.Controls.ListBox> controls.</span></span> <span data-ttu-id="9fc3e-122">이전 버전의 .NET Framework에서는 그렇지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="9fc3e-122">In previous versions of .NET Framework, it was not.</span></span>

<span data-ttu-id="9fc3e-123">**화면 읽기 프로그램 상호 작용 개선 사항**</span><span class="sxs-lookup"><span data-stu-id="9fc3e-123">**Screen reader interaction improvements**</span></span>

- <span data-ttu-id="9fc3e-124">이제 <xref:System.Windows.Controls.Expander> 컨트롤은 화면 읽기 프로그램에서 그룹(확장/축소)으로 올바르게 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fc3e-124"><xref:System.Windows.Controls.Expander> controls are now correctly announced as groups (expand/collapse) by screen readers.</span></span>
- <span data-ttu-id="9fc3e-125">이제 <xref:System.Windows.Controls.DataGridCell> 컨트롤은 화면 읽기 프로그램에서 데이터 그리드(지역화됨)으로 올바르게 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fc3e-125"><xref:System.Windows.Controls.DataGridCell> controls are now correctly announced as data grid cell (localized) by screen readers.</span></span>
- <span data-ttu-id="9fc3e-126">이제 화면 읽기 프로그램이 편집 가능한 <xref:System.Windows.Controls.ComboBox>의 이름을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9fc3e-126">Screen readers will now announce the name of an editable <xref:System.Windows.Controls.ComboBox>.</span></span>
- <span data-ttu-id="9fc3e-127"><xref:System.Windows.Controls.PasswordBox> 컨트롤은 더 이상 화면 읽기 프로그램에서 “보기의 항목 없음”으로 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9fc3e-127"><xref:System.Windows.Controls.PasswordBox> controls are no longer announced as "no item in view" by screen readers.</span></span>

<span data-ttu-id="9fc3e-128">**LiveRegion 지원**</span><span class="sxs-lookup"><span data-stu-id="9fc3e-128">**LiveRegion support**</span></span>

<span data-ttu-id="9fc3e-129">내레이터와 같은 화면 판독기는 현재 포커스가 있는 UI 요소를 설명하는 애플리케이션의 UI(사용자 인터페이스)를 사용자가 이해하는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9fc3e-129">Screen readers, such as Narrator, help people understand the user interface (UI) of an application, usually by describing the UI element that currently has focus.</span></span> <span data-ttu-id="9fc3e-130">그러나 화면에서 UI 요소가 변경되고 포커스가 없는 경우 사용자는 알림을 받지 못하고 중요한 정보를 놓칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fc3e-130">However, if a UI element changes somewhere in the screen and it does not have the focus, the user may not be informed and miss important information.</span></span> <span data-ttu-id="9fc3e-131">LiveRegions는 이 문제를 해결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fc3e-131">LiveRegions are meant to solve this problem.</span></span> <span data-ttu-id="9fc3e-132">개발자는 화면 판독기 또는 다른 [UI Automation](~/docs/framework/ui-automation/ui-automation-overview.md) 클라이언트에게 UI 요소에 중요한 변경 내용이 만들어졌음을 알리는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fc3e-132">A developer can use them to inform the screen reader or any other [UI Automation](~/docs/framework/ui-automation/ui-automation-overview.md) client that an important change has been made to a UI element.</span></span> <span data-ttu-id="9fc3e-133">화면 판독기는 사용자에게 이 변경 내용을 알리는 방법 및 시점을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fc3e-133">The screen reader can then decide how and when to inform the user of this change.</span></span> <span data-ttu-id="9fc3e-134">또한 LiveSetting 속성을 통해 UI에 대한 변경 내용을 사용자에게 알리는 것이 얼마나 중요한지 화면 읽기 프로그램에 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fc3e-134">The LiveSetting property also lets the screen reader know how important it is to inform the user of the change made to the UI.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="9fc3e-135">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="9fc3e-135">Suggestion</span></span>

<span data-ttu-id="9fc3e-136">**이 변경 내용을 옵트인 또는 옵트아웃하는 방법**</span><span class="sxs-lookup"><span data-stu-id="9fc3e-136">**How to opt in or out of these changes**</span></span>

<span data-ttu-id="9fc3e-137">애플리케이션이 이러한 변경의 이점을 활용하도록 하기 위해 .NET Framework 4.7.1 이상에서 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fc3e-137">In order for the application to benefit from these changes, it must run on .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="9fc3e-138">애플리케이션은 다음과 같은 방법으로 이러한 변경의 이점을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fc3e-138">The application can benefit from these changes in either of the following ways:</span></span>

- <span data-ttu-id="9fc3e-139">.NET Framework 4.7.1을 대상으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9fc3e-139">Target .NET Framework 4.7.1.</span></span> <span data-ttu-id="9fc3e-140">이는 권장되는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="9fc3e-140">This is the recommended approach.</span></span> <span data-ttu-id="9fc3e-141">이러한 서비스 효율성 변경 내용은 .NET Framework 4.7.1 이상을 대상으로 하는 WPF 애플리케이션에서 기본적으로 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fc3e-141">These accessibility changes are enabled by default on WPF applications that target .NET Framework 4.7.1 or later.</span></span>
- <span data-ttu-id="9fc3e-142">다음 예제와 같이 app config 파일의 `<runtime>` 섹션에 다음 [AppContext 스위치](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)를 추가하고 이를 `false`로 설정하여 레거시 접근성 동작을 옵트아웃합니다.</span><span class="sxs-lookup"><span data-stu-id="9fc3e-142">It opts out of the legacy accessibility behaviors by adding the following [AppContext Switch](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) in the `<runtime>` section of the app config file and setting it to `false`, as the following example shows.</span></span>

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <configuration>
    <startup>
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7"/>
    </startup>
    <runtime>
      <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true/false;key2=true/false'  -->
      <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
    </runtime>
  </configuration>
  ```

<span data-ttu-id="9fc3e-143">.NET Framework 4.7.1 이상을 대상으로 하고 레거시 접근성 동작을 유지하려는 애플리케이션은 이 AppContext 스위치를 `true`로 명확하게 설정하여 레거시 접근성 기능 사용을 옵트인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fc3e-143">Applications that target .NET Framework 4.7.1 or later and want to preserve the legacy accessibility behavior can opt in to the use of legacy accessibility features by explicitly setting this AppContext switch to `true`.</span></span>
<span data-ttu-id="9fc3e-144">UI 자동화 개요는 [UI Automation 개요](~/docs/framework/ui-automation/ui-automation-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9fc3e-144">For an overview of UI automation, see [UI Automation Overview](~/docs/framework/ui-automation/ui-automation-overview.md).</span></span>

| <span data-ttu-id="9fc3e-145">이름</span><span class="sxs-lookup"><span data-stu-id="9fc3e-145">Name</span></span>    | <span data-ttu-id="9fc3e-146">값</span><span class="sxs-lookup"><span data-stu-id="9fc3e-146">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="9fc3e-147">Scope</span><span class="sxs-lookup"><span data-stu-id="9fc3e-147">Scope</span></span>   | <span data-ttu-id="9fc3e-148">주요함</span><span class="sxs-lookup"><span data-stu-id="9fc3e-148">Major</span></span>       |
| <span data-ttu-id="9fc3e-149">버전</span><span class="sxs-lookup"><span data-stu-id="9fc3e-149">Version</span></span> | <span data-ttu-id="9fc3e-150">4.7.1</span><span class="sxs-lookup"><span data-stu-id="9fc3e-150">4.7.1</span></span>       |
| <span data-ttu-id="9fc3e-151">형식</span><span class="sxs-lookup"><span data-stu-id="9fc3e-151">Type</span></span>    | <span data-ttu-id="9fc3e-152">대상 변경</span><span class="sxs-lookup"><span data-stu-id="9fc3e-152">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="9fc3e-153">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="9fc3e-153">Affected APIs</span></span>

- <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType>
- <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType>
- <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType>
- <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType>
- <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting(System.Windows.DependencyObject,System.Windows.Automation.AutomationLiveSetting)?displayProperty=nameWithType>
- <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting(System.Windows.DependencyObject)?displayProperty=nameWithType>
- <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore?displayProperty=nameWithType>
