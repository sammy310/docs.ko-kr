---
title: .NET Framework에서 내게 필요한 옵션의 새로운 기능
description: .NET Framework 4.7.1부터 적용되는 .NET 접근성의 새로운 기능을 확인하세요. 내게 필요한 옵션 기능을 통해 앱은 보조 기술 사용자에게 적절한 환경을 제공할 수 있습니다.
ms.date: 04/18/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- what's new [.NET Framework]
ms.openlocfilehash: df9188c4f7c2af77f5dc87309880a41724254c5c
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558961"
---
# <a name="whats-new-in-accessibility-in-the-net-framework"></a><span data-ttu-id="33926-104">.NET Framework에서 내게 필요한 옵션의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="33926-104">What's new in accessibility in the .NET Framework</span></span>

<span data-ttu-id="33926-105">.NET Framework는 애플리케이션을 사용자에게 더욱 액세스 가능하도록 만드는 것을 목표로 합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-105">The .NET Framework aims at making applications more accessible for your users.</span></span> <span data-ttu-id="33926-106">내게 필요한 옵션 기능을 통해 애플리케이션은 사용자에게 보조 기술에 대한 적절한 환경을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-106">Accessibility features allow an application to provide an appropriate experience for users of Assistive Technology.</span></span> <span data-ttu-id="33926-107">.NET Framework 4.7.1부터 .NET Framework에 개발자가 액세스 가능한 애플리케이션을 만들도록 허용하는 다수의 내게 필요한 옵션 개선 사항이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-107">Starting with .NET Framework 4.7.1, the .NET Framework includes a large number of accessibility improvements that allow developers to create accessible applications.</span></span>

## <a name="accessibility-switches"></a><span data-ttu-id="33926-108">내게 필요한 옵션 스위치</span><span class="sxs-lookup"><span data-stu-id="33926-108">Accessibility switches</span></span>

<span data-ttu-id="33926-109">.NET Framework 4.7 이전 버전을 대상으로 하지만 .NET Framework 4.7.1 이상에서 실행되는 경우 내게 필요한 옵션 기능으로 옵트인하도록 앱을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-109">You can configure your app to opt into accessibility features if it targets .NET Framework 4.7 or an earlier version but is running on .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="33926-110">.NET Framework 4.7.1 이상을 대상으로 하는 경우 레거시 기능(및 내게 필요한 옵션 기능을 활용하지 못하도록)을 사용하도록 앱을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-110">You can also configure your app to use legacy features (and not take advantage of accessibility features) if it targets .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="33926-111">내게 필요한 옵션 기능을 포함하는 .NET Framework의 각 버전에는 애플리케이션의 구성 파일의 [`<runtime>`](../configure-apps/file-schema/runtime/index.md) 섹션에서 [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 요소에 추가하는 버전별 내게 필요한 옵션 스위치가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-111">Each version of the .NET Framework that includes accessibility features has a version-specific accessibility switch, which you add to the [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](../configure-apps/file-schema/runtime/index.md) section of the application's configuration file.</span></span> <span data-ttu-id="33926-112">다음은 지원되는 스위치입니다.</span><span class="sxs-lookup"><span data-stu-id="33926-112">The following are the supported switches:</span></span>

|<span data-ttu-id="33926-113">버전</span><span class="sxs-lookup"><span data-stu-id="33926-113">Version</span></span>|<span data-ttu-id="33926-114">스위치</span><span class="sxs-lookup"><span data-stu-id="33926-114">Switch</span></span>|
|---|---|
|<span data-ttu-id="33926-115">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="33926-115">.NET Framework 4.7.1</span></span>|<span data-ttu-id="33926-116">"Switch.UseLegacyAccessibilityFeatures"</span><span class="sxs-lookup"><span data-stu-id="33926-116">"Switch.UseLegacyAccessibilityFeatures"</span></span>|
|<span data-ttu-id="33926-117">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="33926-117">.NET Framework 4.7.2</span></span>|<span data-ttu-id="33926-118">"Switch.UseLegacyAccessibilityFeatures.2"</span><span class="sxs-lookup"><span data-stu-id="33926-118">"Switch.UseLegacyAccessibilityFeatures.2"</span></span>|
|<span data-ttu-id="33926-119">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="33926-119">.NET Framework 4.8</span></span>|<span data-ttu-id="33926-120">"Switch.UseLegacyAccessibilityFeatures.3"</span><span class="sxs-lookup"><span data-stu-id="33926-120">"Switch.UseLegacyAccessibilityFeatures.3"</span></span>|

### <a name="taking-advantage-of-accessibility-enhancements"></a><span data-ttu-id="33926-121">내게 필요한 옵션 개선 사항 활용</span><span class="sxs-lookup"><span data-stu-id="33926-121">Taking advantage of accessibility enhancements</span></span>

<span data-ttu-id="33926-122">새로운 내게 필요한 옵션 기능은 .NET Framework 4.7.1 이상을 대상으로 하는 애플리케이션에 대해 기본적으로 활성화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-122">The new accessibility features are enabled by default for applications that target .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="33926-123">또한 이전 버전의 .NET Framework를 대상으로 하지만 .NET Framework 4.7.1 이상에서 실행되는 애플리케이션은 애플리케이션의 구성 파일의 [`<runtime>`](../configure-apps/file-schema/runtime/index.md) 섹션에서 [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 요소에 스위치를 추가하고 해당 값을 `false`로 설정하여 레거시 내게 필요한 옵션 동작을 옵트아웃할 수 있습니다(따라서 내게 필요한 옵션 개선 사항 활용).</span><span class="sxs-lookup"><span data-stu-id="33926-123">In addition, applications that target an earlier version of the .NET Framework but are running on .NET Framework 4.7.1 or later can opt out of legacy accessibility behaviors (and thereby take advantage of accessibility improvements) by adding switches to the [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](../configure-apps/file-schema/runtime/index.md) section of the application's configuration file and setting their value to `false`.</span></span> <span data-ttu-id="33926-124">다음은 .NET Framework 4.7.1에 도입된 내게 필요한 옵션 개선 사항으로 옵트인하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="33926-124">The following shows how to opt in to accessibility enhancements introduced in .NET Framework 4.7.1:</span></span>

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

<span data-ttu-id="33926-125">.NET Framework의 이후 버전에서 내게 필요한 옵션 기능으로 옵트인하도록 선택한 경우 .NET Framework의 이전 버전에서도 기능으로 명시적으로 옵트인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-125">If you choose to opt in to accessibility features in a later version of the .NET Framework, you must also explicitly opt in to the features from earlier versions of the .NET Framework.</span></span> <span data-ttu-id="33926-126">.NET Framework 4.7.1 및 4.7.2 모두에서 내게 필요한 옵션 개선 사항을 활용하도록 앱을 구성하려면 다음 [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-126">Configuring your app to take advantage of accessibility improvements in both .NET Framework 4.7.1 and 4.7.2 requires the following [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element:</span></span>

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
</runtime>
```

<span data-ttu-id="33926-127">.NET Framework 4.7.1 및 4.7.2 및 4.8에서 내게 필요한 옵션 개선 사항을 활용하도록 앱을 구성하려면 다음 [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-127">Configuring your app to take advantage of accessibility improvements in .NET Framework 4.7.1, 4.7.2, and 4.8 requires the following [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element:</span></span>

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;Switch.UseLegacyAccessibilityFeatures.3=false" />
</runtime>
```

### <a name="restoring-legacy-behavior"></a><span data-ttu-id="33926-128">레거시 동작 복원</span><span class="sxs-lookup"><span data-stu-id="33926-128">Restoring legacy behavior</span></span>

<span data-ttu-id="33926-129">4\.7.1부터 시작하는 .NET Framework의 버전을 대상으로 하는 애플리케이션은 애플리케이션의 구성 파일의 [`<runtime>`](../configure-apps/file-schema/runtime/index.md) 섹션에서 [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 요소에 스위치를 추가하고 `true`로 해당 값을 설정하여 내게 필요한 옵션 기능을 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-129">Applications that target versions of the .NET Framework starting with 4.7.1 can disable accessibility features by adding switches to the [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](../configure-apps/file-schema/runtime/index.md) section of the application's configuration file and setting their value to `true`.</span></span> <span data-ttu-id="33926-130">예를 들어 다음 구성은 .NET Framework 4.7.2에 도입된 내게 필요한 옵션 기능을 옵트아웃합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-130">For example, the following configuration opts out of accessibility features introduced in .NET Framework 4.7.2:</span></span>

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures.2=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-net-framework-48"></a><span data-ttu-id="33926-131">.NET Framework 4.8에서 내게 필요한 옵션의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="33926-131">What's new in accessibility in .NET Framework 4.8</span></span>

<span data-ttu-id="33926-132">.NET Framework 4.8에는 다음과 같은 영역의 새로운 내게 필요한 옵션 기능이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="33926-132">.NET Framework 4.8 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="33926-133">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="33926-133">Windows Forms</span></span>](#winforms48)

- [<span data-ttu-id="33926-134">WPF(Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="33926-134">Windows Presentation Foundation (WPF)</span></span>](#wpf48)

- [<span data-ttu-id="33926-135">Windows WF(Workflow Foundation) 워크플로 디자이너</span><span class="sxs-lookup"><span data-stu-id="33926-135">Windows Workflow Foundation (WF) workflow designer</span></span>](#wf48)

<a name="winforms48"></a>

### <a name="windows-forms"></a><span data-ttu-id="33926-136">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="33926-136">Windows Forms</span></span>

<span data-ttu-id="33926-137">.NET Framework 4.8에서 Windows Forms는 자주 사용되는 많은 컨트롤에 LiveRegions 및 알림 이벤트에 대한 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-137">In .NET Framework 4.8, Windows Forms adds support for LiveRegions and Notification Events to many commonly used controls.</span></span> <span data-ttu-id="33926-138">또한 사용자가 키보드를 사용하여 컨트롤로 이동할 때 도구 설명에 대한 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-138">It also adds support for ToolTips when a user navigates to a control by using the keyboard.</span></span>

<span data-ttu-id="33926-139">**레이블 및 StatusStrips에서 UIA LiveRegions 지원**</span><span class="sxs-lookup"><span data-stu-id="33926-139">**UIA LiveRegions Support in Labels and StatusStrips**</span></span>

<span data-ttu-id="33926-140">UIA LiveRegions를 사용하면 애플리케이션 개발자는 사용자가 작업하는 위치와 별도로 위치한 컨트롤의 텍스트 변경 내용을 화면 readers에 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-140">UIA LiveRegions allow application developers to notify screen readers of a text change in a control that is located apart from the location where the user is working.</span></span> <span data-ttu-id="33926-141">예를 들어 연결 상태를 표시하는 <xref:System.Windows.Forms.StatusStrip> 컨트롤에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-141">This is useful, for example, for a <xref:System.Windows.Forms.StatusStrip> control that shows a connection status.</span></span> <span data-ttu-id="33926-142">연결이 끊어지고 상태가 변경되면 개발자가 화면 reader에 알리기를 원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-142">If the connection is dropped and the status changes, the developer might want to notify the screen reader.</span></span>

<span data-ttu-id="33926-143">.NET Framework 4.8부터 Windows Forms는 <xref:System.Windows.Forms.Label> 및 <xref:System.Windows.Forms.StatusStrip> 컨트롤 모두에 대해 UIA LiveRegions를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-143">Starting with .NET Framework 4.8, Windows Forms implements UIA LiveRegions for both the <xref:System.Windows.Forms.Label> and <xref:System.Windows.Forms.StatusStrip> controls.</span></span> <span data-ttu-id="33926-144">예를 들어 다음 코드에서는 `label1`이라는 <xref:System.Windows.Forms.Label> 컨트롤에서 LiveRegion을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-144">For example, the following code uses the LiveRegion in a <xref:System.Windows.Forms.Label> control named `label1`:</span></span>

```csharp
public Form1()
{
   InitializeComponent();
   label1.AutomationLiveSetting = AutomationLiveSetting.Polite;
}

…
Label1.Text = “Ready!”;
```

<span data-ttu-id="33926-145">내레이터는 사용자가 애플리케이션과 상호 작용하는 위치에 관계없이 “준비”를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="33926-145">Narrator announces “Ready” regardless of where the user is interacting with the application.</span></span>

<span data-ttu-id="33926-146"><xref:System.Windows.Forms.UserControl>을 LiveRegion으로 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-146">You can also implement your <xref:System.Windows.Forms.UserControl> as a LiveRegion:</span></span>

```csharp
using System;
using System.Windows.Forms;
using System.Windows.Forms.Automation;

namespace WindowsFormsApplication
{
   public partial class UserControl1 : UserControl, IAutomationLiveRegion
   {
      public UserControl1()
      {
         InitializeComponent();
      }

      public AutomationLiveSetting AutomationLiveSetting { get; set; }
      private AutomationLiveSetting IAutomationLiveRegion.GetLiveSetting()
      {
         return this.AutomationLiveSetting;
      }

      protected override void OnTextChanged(EventArgs e)
      {
         base.OnTextChanged(e);
         AutomationNotifications.UiaRaiseLiveRegionChangedEvent(this.AccessibilityObject);
      }
   }
}
```

<span data-ttu-id="33926-147">**UIA 알림 이벤트**</span><span class="sxs-lookup"><span data-stu-id="33926-147">**UIA notification events**</span></span>

<span data-ttu-id="33926-148">Windows 10 Fall Creators Update에 도입된 UIA 알림 이벤트를 사용하면 앱에서 UIA 이벤트를 발생시킬 수 있습니다. 이로 인해 내레이터가 UI에서 해당 컨트롤을 사용할 필요 없이 이벤트와 함께 제공하는 텍스트를 기반으로 간단히 알림을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="33926-148">The UIA Notification event, introduced in Windows 10 Fall Creators Update, allows your app to raise a UIA event, which leads to Narrator simply making an announcement based on text you supply with the event, without the need to have a corresponding control in the UI.</span></span> <span data-ttu-id="33926-149">일부 시나리오에서는 앱의 액세스 가능성을 크게 개선하는 간단한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="33926-149">In some scenarios, this is a straightforward way to dramatically improve the accessibility of your app.</span></span> <span data-ttu-id="33926-150">시간이 오래 걸릴 수 있는 일부 프로세스의 진행 상황을 알리는 데도 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-150">In can also be useful to notify of the progress of some process that may take a long time.</span></span> <span data-ttu-id="33926-151">UIA 알림 이벤트에 대한 자세한 내용은 [데스크톱 앱이 새 UI 알림 이벤트를 활용할 수 있나요?](https://docs.microsoft.com/archive/blogs/winuiautomation/can-your-desktop-app-leverage-the-new-uia-notification-event-in-order-to-have-narrator-say-exactly-what-your-customers-need)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="33926-151">For more information about UIA Notification Events, see [Can your desktop app leverage the new UI Notification event?](https://docs.microsoft.com/archive/blogs/winuiautomation/can-your-desktop-app-leverage-the-new-uia-notification-event-in-order-to-have-narrator-say-exactly-what-your-customers-need).</span></span>

<span data-ttu-id="33926-152">다음 예제에서는 [알림 이벤트](xref:System.Windows.Forms.AccessibleObject.RaiseAutomationNotification%2A)를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="33926-152">The following example raises the [Notification event](xref:System.Windows.Forms.AccessibleObject.RaiseAutomationNotification%2A):</span></span>

```csharp
MethodInfo raiseMethod = typeof(AccessibleObject).GetMethod("RaiseAutomationNotification");
if (raiseMethod != null) {
   raiseMethod.Invoke(progressBar1.AccessibilityObject, new object[3] {/*Other*/ 4, /*All*/ 2, "The progress is 50%." });
}
```

<span data-ttu-id="33926-153">**키보드 액세스에 대한 도구 설명**</span><span class="sxs-lookup"><span data-stu-id="33926-153">**ToolTips on keyboard access**</span></span>

<span data-ttu-id="33926-154">.NET Framework 4.7.2 및 이전 버전을 대상으로 하는 애플리케이션에서는 마우스 포인터를 컨트롤로 이동하여 컨트롤 [도구 설명](xref:System.Windows.Forms.ToolTip)이 팝업되도록 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-154">In applications that target .NET Framework 4.7.2 and earlier versions, a control [tooltip](xref:System.Windows.Forms.ToolTip) can only be triggered to pop up by moving a mouse pointer into the control.</span></span> <span data-ttu-id="33926-155">.NET Framework 4.8부터 키보드 사용자는 한정자 키의 유무와 상관없이 Tab 키 또는 화살표 키를 사용하여 컨트롤을 중심으로 도구 설명을 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-155">Starting with .NET Framework 4.8, a keyboard user can trigger a control’s tooltip by focusing the control using a Tab key or arrow keys with or without modifier keys.</span></span> <span data-ttu-id="33926-156">이 특정 액세스 가능성 개선을 위해서는 [AppContext 스위치](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-156">This particular accessibility enhancement requires an additional [AppContext switch](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md):</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
   <startup>
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6.1"/>
   </startup>
   <runtime>
      <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false  -->
      <!-- Please note that disabling Switch.UseLegacyAccessibilityFeatures, Switch.UseLegacyAccessibilityFeatures.2 and Switch.UseLegacyAccessibilityFeatures.3 is required to disable Switch.System.Windows.Forms.UseLegacyToolTipDisplay -->
      <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;Switch.UseLegacyAccessibilityFeatures.3=false;Switch.System.Windows.Forms.UseLegacyToolTipDisplay=false"/>
   </runtime>
</configuration>
```

<span data-ttu-id="33926-157">다음 그림은 사용자가 키보드를 사용하여 단추를 선택한 경우의 도구 설명을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="33926-157">The following figure shows the tooltip when the user has selected a button with the keyboard.</span></span>

![사용자가 키보드를 사용하여 단추로 이동하는 경우 도구 설명의 스크린샷](./media/whats-new-in-accessibility/select-tooltip-with-keyboard.png)

<a name="wpf48"></a>

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="33926-159">WPF(Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="33926-159">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="33926-160">.NET Framework 4.8부터 WPF에는 여러 가지 접근성 개선 사항이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-160">Starting with .NET Framework 4.8, WPF includes a number of accessibility improvements.</span></span>

<span data-ttu-id="33926-161">**화면 내레이터가 더 이상 축소되거나 숨겨긴 가시성이 있는 요소를 공지하지 않음**</span><span class="sxs-lookup"><span data-stu-id="33926-161">**Screen narrators no longer announce elements with Collapsed or Hidden visibility**</span></span>

<span data-ttu-id="33926-162">축소되거나 숨겨진 가시성이 있는 요소는 더 이상 화면 reader에서 공지하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-162">Elements with collapsed or hidden visibility are no longer announced by screen reader.</span></span> <span data-ttu-id="33926-163">가시성이 <xref:System.Windows.Visibility.Collapsed?displayProperty=nameWithType> 또는 <xref:System.Windows.Visibility.Hidden?displayProperty=nameWithType>인 요소가 포함된 사용자 인터페이스는 사용자에게 공지된 경우 화면 readers에 의해 잘못 전달될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-163">User interfaces that contain elements with a Visibility of <xref:System.Windows.Visibility.Collapsed?displayProperty=nameWithType> or <xref:System.Windows.Visibility.Hidden?displayProperty=nameWithType> can be misrepresented by screen readers if they are announced to the user.</span></span> <span data-ttu-id="33926-164">.NET Framework 4.8부터 WPF는 더 이상 UIAutomation 트리의 컨트롤 뷰에 축소되거나 숨겨진 요소를 포함하지 않기 때문에 화면 readers는 이러한 요소를 더 이상 공지할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-164">Starting with .NET Framework 4.8, WPF no longer includes collapsed or hidden elements in the Control View of the UIAutomation tree, so the screen readers can no longer announce these elements.</span></span>

<span data-ttu-id="33926-165">**비표시기(Adorner) 기반 텍스트 선택 영역과 함께 사용할 SelectionTextBrush 속성**</span><span class="sxs-lookup"><span data-stu-id="33926-165">**SelectionTextBrush property for use with non-Adorner based text selection**</span></span>

<span data-ttu-id="33926-166">.NET Framework 4.7.2에서 WPF는 표시기 계층을 사용하지 않고 <xref:System.Windows.Controls.TextBox> 및 <xref:System.Windows.Controls.PasswordBox> 텍스트 선택 영역을 그리는 기능을 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-166">In the .NET Framework 4.7.2, WPF added the ability to draw <xref:System.Windows.Controls.TextBox> and <xref:System.Windows.Controls.PasswordBox> text selection without using the Adorner layer.</span></span> <span data-ttu-id="33926-167">이 시나리오에서 선택한 텍스트의 전경색은 <xref:System.Windows.SystemColors.HighlightTextBrush?displayProperty=nameWithType>에 의해 지정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-167">The foreground color of the selected text in this scenario was dictated by <xref:System.Windows.SystemColors.HighlightTextBrush?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="33926-168">.NET Framework 4.8은 개발자가 비표시기 기반 텍스트 선택 영역을 사용할 때 선택한 텍스트에 대한 특정 브러시를 선택할 수 있도록 하는 새 속성(`SelectionTextBrush`)을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-168">.NET Framework 4.8 adds a new property, `SelectionTextBrush`, that allows developers to select the specific brush for the selected text when using non-Adorner based text selection.</span></span> <span data-ttu-id="33926-169">이 속성은 <xref:System.Windows.Controls.Primitives.TextBoxBase>에서 파생된 컨트롤과 비표시기 기반 텍스트 선택이 활성화된 WPF 애플리케이션의 <xref:System.Windows.Controls.PasswordBox> 컨트롤에서만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-169">This property works only on <xref:System.Windows.Controls.Primitives.TextBoxBase>-derived controls and the <xref:System.Windows.Controls.PasswordBox> control in WPF applications with non-Adorner-based text selection enabled.</span></span> <span data-ttu-id="33926-170"><xref:System.Windows.Controls.RichTextBox> 콘트롤에서는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-170">It does not work on the <xref:System.Windows.Controls.RichTextBox> control.</span></span> <span data-ttu-id="33926-171">비표시기 기반 텍스트 선택 영역이 활성화되지 않은 경우 이 속성은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="33926-171">If non-Adorner-based text selection is not enabled, this property is ignored.</span></span>

<span data-ttu-id="33926-172">이 속성을 사용하려면 XAML 코드에 추가하고 적절한 브러시 또는 바인딩을 사용하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="33926-172">To use this property, simply add it to your XAML code and use the appropriate brush or binding.</span></span> <span data-ttu-id="33926-173">결과 텍스트 선택 영역은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-173">The resulting text selection looks like this:</span></span>

![단어 Hello World가 선택되어 실행 중인 앱의 스크린샷](./media/whats-new-in-accessibility/selectiontextbrush-property.png)

<span data-ttu-id="33926-175">`SelectionBrush` 및 `SelectionTextBrush` 속성의 사용을 조합하여 적절한 것으로 간주되는 배경 및 전경색 조합을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-175">You can combine the use of the `SelectionBrush` and `SelectionTextBrush` properties to generate any background and foreground color combination that you deem appropriate.</span></span>

<span data-ttu-id="33926-176">**UIAutomation ControllerFor 속성 지원**</span><span class="sxs-lookup"><span data-stu-id="33926-176">**Support for the UIAutomation ControllerFor property**</span></span>

<span data-ttu-id="33926-177">UIAutomation의 `ControllerFor` 속성은 이 속성을 지원하는 자동화 요소에 의해 조작되는 자동화 요소의 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-177">UIAutomation’s `ControllerFor` property returns an array of automation elements that are manipulated by the automation element that supports this property.</span></span> <span data-ttu-id="33926-178">이 속성은 자동 제안 접근성에 주로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="33926-178">This property is commonly used for Auto-suggest accessibility.</span></span> <span data-ttu-id="33926-179">`ControllerFor`는 자동화 요소가 애플리케이션 UI 또는 데스크톱의 하나 이상의 세그먼트에 영향을 줄 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="33926-179">`ControllerFor` is used when an automation element affects one or more segments of the application UI or the desktop.</span></span> <span data-ttu-id="33926-180">그렇지 않으면 제어 작업의 영향을 UI 요소와 연결시키기가 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-180">Otherwise, it is hard to associate the impact of the control operation with UI elements.</span></span> <span data-ttu-id="33926-181">이 기능은 컨트롤이 `ControllerFor` 속성 값을 제공하는 기능을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-181">This feature adds the ability for controls to provide a value for the `ControllerFor` property.</span></span>

<span data-ttu-id="33926-182">.NET Framework 4.8에는 새로운 가상 메서드인 <xref:System.Windows.Automation.Peers.AutomationPeer.GetControlledPeersCore?displayProperty=nameWithType?displayProperty=nameWithType>이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="33926-182">.NET Framework 4.8 adds a new virtual method, <xref:System.Windows.Automation.Peers.AutomationPeer.GetControlledPeersCore?displayProperty=nameWithType?displayProperty=nameWithType>.</span></span> <span data-ttu-id="33926-183">`ControllerFor` 속성에 대한 값을 제공하려면 이 메서드를 재정의하고 이 <xref:System.Windows.Automation.Peers.AutomationPeer>에 의해 조작되는 컨트롤에 대해 `List<AutomationPeer>`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-183">To provide a value for the `ControllerFor` property, simply override this method and return a `List<AutomationPeer>` for the controls being manipulated by this <xref:System.Windows.Automation.Peers.AutomationPeer>:</span></span>

```csharp
public class AutoSuggestTextBox: TextBox
{
   protected override AutomationPeer OnCreateAutomationPeer()
   {
      return new AutoSuggestTextBoxAutomationPeer(this);
   }

   public ListBox SuggestionListBox;
}

internal class AutoSuggestTextBoxAutomationPeer : TextBoxAutomationPeer
{
   public AutoSuggestTextBoxAutomationPeer(AutoSuggestTextBox owner) : base(owner)
   {
   }

   protected override List<AutomationPeer> GetControlledPeersCore()
   {
      List<AutomationPeer> controlledPeers = new List<AutomationPeer>();
      AutoSuggestTextBox owner = Owner as AutoSuggestTextBox;
      controlledPeers.Add(UIElementAutomationPeer.CreatePeerForElement(owner.SuggestionListBox));
      return controlledPeers;
   }
}
```

<span data-ttu-id="33926-184">**키보드 액세스에 대한 도구 설명**</span><span class="sxs-lookup"><span data-stu-id="33926-184">**Tooltips on keyboard access**</span></span>

<span data-ttu-id="33926-185">.NET Framework 4.7.2 및 이전 버전에서 도구 설명은 사용자가 마우스 커서를 컨트롤 위에 놓을 때만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="33926-185">In .NET Framework 4.7.2 and earlier versions, tooltips display only when the user hovers the mouse cursor over a control.</span></span> <span data-ttu-id="33926-186">.NET Framework 4.8에서 도구 설명은 키보드 포커스뿐만 아니라 바로 가기 키를 통해서도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="33926-186">In .NET Framework 4.8, tooltips also display on keyboard focus, as well as via a keyboard shortcut.</span></span>

<span data-ttu-id="33926-187">이 기능을 사용하려면 애플리케이션이 `Switch.UseLegacyAccessibilityFeatures.3` 및 `Switch.UseLegacyToolTipDisplay` [AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 스위치를 사용하여 .NET Framework 4.8을 대상으로 하거나 옵트인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-187">To enable this feature, an application needs to target .NET Framework 4.8 or opt-in by using the `Switch.UseLegacyAccessibilityFeatures.3` and `Switch.UseLegacyToolTipDisplay` [AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) switches.</span></span> <span data-ttu-id="33926-188">다음은 샘플 애플리케이션 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="33926-188">The following is a sample application configuration file:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
   <startup>
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5" />
   </startup>
   <runtime>
      <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;Switch.UseLegacyAccessibilityFeatures.3=false;Switch.UseLegacyToolTipDisplay=false" />
   </runtime>
</configuration>
```

<span data-ttu-id="33926-189">활성화되어 컨트롤이 키보드 포커스를 받으면 도구 설명이 포함된 모든 컨트롤이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="33926-189">Once enabled, all controls that contain a tooltip display it once the control receives keyboard focus.</span></span> <span data-ttu-id="33926-190">도구 설명은 시간이 경과하거나 키보드 포커스가 변경될 때 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-190">The tooltip can be dismissed over time or when the keyboard focus changes.</span></span> <span data-ttu-id="33926-191">사용자가 새로운 바로 가기 키인 Ctrl + Shift + F10을 사용하여 도구 설명을 수동으로 해제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-191">Users can also dismiss the tooltip manually by using a new keyboard shortcut, Ctrl + Shift + F10.</span></span> <span data-ttu-id="33926-192">도구 설명이 해제되면 동일한 바로 가기 키를 사용하여 다시 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-192">Once the tooltip has been dismissed it can be displayed again by using the same keyboard shortcut.</span></span>

> [!NOTE]
> <span data-ttu-id="33926-193"><xref:System.Windows.Controls.Ribbon.Ribbon> 컨트롤의 [리본 도구 설명](xref:System.Windows.Controls.Ribbon.RibbonToolTip)이 키보드 포커스에 표시되지 않습니다. 바로 가기 키를 통해서만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="33926-193">[Ribbon tooltips](xref:System.Windows.Controls.Ribbon.RibbonToolTip) on <xref:System.Windows.Controls.Ribbon.Ribbon> controls won’t show on keyboard focus; they only show via the keyboard shortcut.</span></span>

<span data-ttu-id="33926-194">**SizeOfSet 및 PositionInSet UIAutomation 속성에 대한 지원 추가**</span><span class="sxs-lookup"><span data-stu-id="33926-194">**Added Support for SizeOfSet and PositionInSet UIAutomation properties**</span></span>

<span data-ttu-id="33926-195">Windows 10에는 애플리케이션에서 집합의 항목 수를 설명하는 데 사용되는 두 개의 새로운 UIAutomation 속성(`SizeOfSet` 및 `PositionInSet`)이 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-195">Windows 10 introduced two new UIAutomation properties, `SizeOfSet` and `PositionInSet`, which are used by applications to describe the count of items in a set.</span></span> <span data-ttu-id="33926-196">그런 다음, 화면 readers와 같은 UIAutomation 클라이언트 애플리케이션은 이러한 속성에 대한 애플리케이션을 쿼리하고 애플리케이션의 UI를 정확하게 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-196">UIAutomation client applications such as screen readers can then query an application for these properties and announce an accurate representation of the application’s UI.</span></span>

<span data-ttu-id="33926-197">.NET Framework 4.8부터 WPF 애플리케이션의 UIAutomation에 이러한 두 속성을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-197">Starting with .NET Framework 4.8, WPF  exposes these two properties to UIAutomation in WPF applications.</span></span> <span data-ttu-id="33926-198">이는 두 가지 방법으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-198">This can be accomplished in two ways:</span></span>

- <span data-ttu-id="33926-199">종속성 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-199">By using dependency properties.</span></span>

  <span data-ttu-id="33926-200">WPF는 두 개의 새 종속성 속성(<xref:System.Windows.Automation.AutomationProperties.SizeOfSet?displayProperty=nameWithType> 및 <xref:System.Windows.Automation.AutomationProperties.PositionInSet?displayProperty=nameWithType>)을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-200">WPF adds two new dependency properties, <xref:System.Windows.Automation.AutomationProperties.SizeOfSet?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationProperties.PositionInSet?displayProperty=nameWithType>.</span></span> <span data-ttu-id="33926-201">개발자는 XAML을 사용하여 해당 값을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-201">A developer can use XAML to set their values:</span></span>

  ```xaml
  <Button AutomationProperties.SizeOfSet="3"
    AutomationProperties.PositionInSet="1">Button 1</Button>

  <Button AutomationProperties.SizeOfSet="3"
    AutomationProperties.PositionInSet="2">Button 2</Button>

  <Button AutomationProperties.SizeOfSet="3"
    AutomationProperties.PositionInSet="3">Button 3</Button>
  ```

- <span data-ttu-id="33926-202">AutomationPeer 가상 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-202">By overriding AutomationPeer virtual methods.</span></span>

  <span data-ttu-id="33926-203"><xref:System.Windows.Automation.Peers.AutomationPeer.GetSizeOfSetCore> 및 <xref:System.Windows.Automation.Peers.AutomationPeer.GetPositionInSetCore> 가상 메서드가 AutomationPeer 클래스에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-203">The <xref:System.Windows.Automation.Peers.AutomationPeer.GetSizeOfSetCore> and <xref:System.Windows.Automation.Peers.AutomationPeer.GetPositionInSetCore> virtual methods been added to the AutomationPeer class.</span></span> <span data-ttu-id="33926-204">개발자는 다음 예제와 같이 이러한 메서드를 재정의하여 `SizeOfSet` 및 `PositionInSet`에 대한 값을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-204">A developer can provide values for `SizeOfSet` and `PositionInSet` by overriding these methods, as shown in the following example:</span></span>

  ```csharp
  public class MyButtonAutomationPeer : ButtonAutomationPeer
  {
    protected override int GetSizeOfSetCore()
    {
        // Call into your own logic to provide a value for SizeOfSet
        return CalculateSizeOfSet();
    }

    protected override int GetPositionInSetCore()
    {
        // Call into your own logic to provide a value for PositionInSet
        return CalculatePositionInSet();
    }
  }
  ```

<span data-ttu-id="33926-205">또한 <xref:System.Windows.Controls.ItemsControl> 인스턴스의 항목은 개발자의 추가 작업 없이 이러한 속성에 대한 값을 자동으로 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-205">In addition, items in <xref:System.Windows.Controls.ItemsControl> instances provide a value for these properties automatically without additional action from the developer.</span></span> <span data-ttu-id="33926-206"><xref:System.Windows.Controls.ItemsControl>이 그룹화되면 그룹의 컬렉션이 집합으로 표시되고, 각 그룹은 별도의 집합으로 계산되며, 그룹 내의 각 항목은 해당 그룹 내에서의 위치뿐 아니라 그룹의 크기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-206">If an <xref:System.Windows.Controls.ItemsControl> is grouped, the collection of groups is represented as a set, and each group is counted as a separate set, with each item inside that group providing its position inside that group as well as the size of the group.</span></span> <span data-ttu-id="33926-207">자동 값은 가상화의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-207">Automatic values are not affected by virtualization.</span></span> <span data-ttu-id="33926-208">항목이 실현되지 않더라도 여전히 집합의 전체 크기로 계산되며, 해당 형제 항목 세트의 위치에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="33926-208">Even if an item is not realized, it is still counted toward the total size of the set and affects the position in the set of its sibling items.</span></span>

<span data-ttu-id="33926-209">자동 값은 애플리케이션이 .NET Framework 4.8을 대상으로 하는 경우에만 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="33926-209">Automatic values are only provided if the application targets .NET Framework 4.8.</span></span> <span data-ttu-id="33926-210">이전 버전의 .NET Framework를 대상으로 하는 애플리케이션의 경우 다음 App.config 파일에 표시된 것처럼 `Switch.UseLegacyAccessibilityFeatures.3` [AppContext 스위치](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-210">For applications that target an earlier version of the .NET Framework, you can set the `Switch.UseLegacyAccessibilityFeatures.3` [AppContext switch](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md), as shown in the following App.config file:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
   <startup>
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5" />
   </startup>
   <runtime>
      <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;Switch.UseLegacyAccessibilityFeatures.3=false" />
   </runtime>
</configuration>
```

<a name="wf48"></a>

### <a name="windows-workflow-foundation-wf-workflow-designer"></a><span data-ttu-id="33926-211">Windows WF(Workflow Foundation) 워크플로 디자이너</span><span class="sxs-lookup"><span data-stu-id="33926-211">Windows Workflow Foundation (WF) workflow designer</span></span>

<span data-ttu-id="33926-212">워크플로 디자이너는 .NET Framework 4.8에서 다음과 같은 변경 내용을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-212">The workflow designer includes the following changes in .NET Framework 4.8:</span></span>

- <span data-ttu-id="33926-213">내레이터를 사용하는 사용자는 FlowSwitch 케이스 레이블의 개선 사항을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-213">Users using Narrator will see improvements in FlowSwitch case labels.</span></span>

- <span data-ttu-id="33926-214">내레이터를 사용하는 사용자는 단추 설명의 개선 사항을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-214">Users using Narrator will see improvements in button descriptions.</span></span>

- <span data-ttu-id="33926-215">고대비 테마를 선택한 사용자는 워크플로 디자이너의 표시 유형에서 개선 사항 및 포커스 요소에 사용되는 요소와 더욱 분명한 선택 영역 상자 사이의 대조율과 같은 해당 컨트롤을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-215">Users who choose High Contrast themes will see improvements in the visibility of the Workflow Designer and its controls, like better contrast ratios between elements and more noticeable selection boxes used for focus elements.</span></span>

<span data-ttu-id="33926-216">애플리케이션이 .NET Framework 4.7.2 또는 이전 버전을 대상으로 하는 경우 애플리케이션 구성 파일에서 `Switch.UseLegacyAccessibilityFeatures.3` [AppContext 스위치](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)를 `false`로 설정하여 이러한 변경 내용을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-216">If your application targets .NET Framework 4.7.2 or an earlier version, you can opt into these changes by setting the `Switch.UseLegacyAccessibilityFeatures.3` [AppContext switch](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) to `false` in your application configuration file.</span></span> <span data-ttu-id="33926-217">자세한 내용은 이 문서의 [내게 필요한 옵션 개선 사항 활용](#taking-advantage-of-accessibility-enhancements) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="33926-217">For more information, see the [Taking advantage of accessibility enhancements](#taking-advantage-of-accessibility-enhancements) section in this article.</span></span>

## <a name="whats-new-in-accessibility-in-net-framework-472"></a><span data-ttu-id="33926-218">.NET Framework 4.7.2에서 내게 필요한 옵션의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="33926-218">What's new in accessibility in .NET Framework 4.7.2</span></span>

<span data-ttu-id="33926-219">.NET Framework 4.7.2에는 다음과 같은 영역의 새로운 내게 필요한 옵션 기능이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="33926-219">.NET Framework 4.7.2 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="33926-220">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="33926-220">Windows Forms</span></span>](#winforms472)

- [<span data-ttu-id="33926-221">WPF(Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="33926-221">Windows Presentation Foundation (WPF)</span></span>](#wpf472)

<a name="winforms472"></a>

### <a name="windows-forms"></a><span data-ttu-id="33926-222">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="33926-222">Windows Forms</span></span>

<span data-ttu-id="33926-223">**고대비 테마에서 OS 정의 색**</span><span class="sxs-lookup"><span data-stu-id="33926-223">**OS-defined colors in High Contrast themes**</span></span>

<span data-ttu-id="33926-224">.NET Framework 4.7.2부터 Windows Forms는 고대비 테마에서 운영 체제에 의해 정의된 색을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-224">Starting with .NET Framework 4.7.2, Windows Forms uses colors defined by the operating system in High Contrast themes.</span></span> <span data-ttu-id="33926-225">이는 다음 컨트롤에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="33926-225">This affects the following controls:</span></span>

- <span data-ttu-id="33926-226"><xref:System.Windows.Forms.ToolStripDropDownButton> 컨트롤의 드롭다운 화살표</span><span class="sxs-lookup"><span data-stu-id="33926-226">The drop-down arrow of the <xref:System.Windows.Forms.ToolStripDropDownButton> control.</span></span>

- <span data-ttu-id="33926-227"><xref:System.Windows.Forms.ButtonBase.FlatStyle>이 <xref:System.Windows.Forms.FlatStyle.Flat?displayProperty=nameWithType> 또는 <xref:System.Windows.Forms.FlatStyle.Popup?displayProperty=nameWithType>으로 설정된 <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.RadioButton> 및 <xref:System.Windows.Forms.CheckBox> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="33926-227">The <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.RadioButton> and <xref:System.Windows.Forms.CheckBox> controls with <xref:System.Windows.Forms.ButtonBase.FlatStyle> set to <xref:System.Windows.Forms.FlatStyle.Flat?displayProperty=nameWithType> or <xref:System.Windows.Forms.FlatStyle.Popup?displayProperty=nameWithType>.</span></span> <span data-ttu-id="33926-228">이전에 선택한 텍스트 및 배경색이 대비되지 않았고 읽기가 어려웠습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-228">Previously, selected text and background colors were not contrasting and were hard to read.</span></span>

- <span data-ttu-id="33926-229">해당 <xref:System.Windows.Forms.Control.Enabled> 속성이 `false`로 설정된 <xref:System.Windows.Forms.GroupBox> 내부에 포함된 컨트롤</span><span class="sxs-lookup"><span data-stu-id="33926-229">Controls contained within a <xref:System.Windows.Forms.GroupBox> that has its <xref:System.Windows.Forms.Control.Enabled> property set to `false`.</span></span>

- <span data-ttu-id="33926-230">고대비 모드에서 명도 대비를 증가시킨 <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripComboBox> 및 <xref:System.Windows.Forms.ToolStripDropDownButton> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="33926-230">The <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripComboBox>, and <xref:System.Windows.Forms.ToolStripDropDownButton> controls, which have an increased luminosity contrast ratio in High Contrast Mode.</span></span>

- <span data-ttu-id="33926-231"><xref:System.Windows.Forms.DataGridViewLinkCell>의 <xref:System.Windows.Forms.DataGridViewLinkCell.LinkColor> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="33926-231">The <xref:System.Windows.Forms.DataGridViewLinkCell.LinkColor> property of the <xref:System.Windows.Forms.DataGridViewLinkCell>.</span></span>

<span data-ttu-id="33926-232">**내레이터 개선 사항**</span><span class="sxs-lookup"><span data-stu-id="33926-232">**Narrator improvements**</span></span>

<span data-ttu-id="33926-233">.NET Framework 4.7.2부터 내레이터 지원이 다음과 같이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="33926-233">Starting with .NET Framework 4.7.2, Narrator support is enhanced as follows:</span></span>

- <span data-ttu-id="33926-234"><xref:System.Windows.Forms.ToolStripMenuItem>의 텍스트를 발표할 경우 <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType> 속성 값도 발표합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-234">It announces the value of the <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType> property when announcing the text of a <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>

- <span data-ttu-id="33926-235"><xref:System.Windows.Forms.ToolStripMenuItem>이 해당 <xref:System.Windows.Forms.Control.Enabled> 속성을 `false`로 설정할 때를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-235">It indicates when a <xref:System.Windows.Forms.ToolStripMenuItem> has its <xref:System.Windows.Forms.Control.Enabled> property set to `false`.</span></span>

- <span data-ttu-id="33926-236"><xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType> 속성이 `true`로 설정될 경우 확인란의 상태에 대한 피드백을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-236">It gives feedback on the state of a check box when the <xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType> property is set to `true`.</span></span>

- <span data-ttu-id="33926-237">내레이터의 스캔 모드 포커스 순서는 ClickOnce 다운로드 대화 상자 창에서 컨트롤의 시각적 개체 순서와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-237">Narrator's Scan Mode focus order is consistent with the visual order of the controls on the ClickOnce download dialog window.</span></span>

<span data-ttu-id="33926-238">**DataGridView의 개선 사항**</span><span class="sxs-lookup"><span data-stu-id="33926-238">**DataGridView improvements**</span></span>

<span data-ttu-id="33926-239">.NET Framework 4.7.2부터 <xref:System.Windows.Forms.DataGridView> 컨트롤에는 다음과 같은 내게 필요한 옵션 개선 사항이 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-239">Starting with .NET Framework 4.7.2, the <xref:System.Windows.Forms.DataGridView> control has introduced the following accessibility improvements:</span></span>

- <span data-ttu-id="33926-240">행은 키보드를 사용하여 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-240">Rows can be sorted using the keyboard.</span></span> <span data-ttu-id="33926-241">현재 열로 정렬하기 위해 사용자는 F3 키를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-241">A user can use the F3 key in order to sort by the current column.</span></span>

- <span data-ttu-id="33926-242"><xref:System.Windows.Forms.DataGridView.SelectionMode?displayProperty=nameWithType>이 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType>으로 설정된 경우 열 헤더는 색을 변경하여 현재 행의 셀을 통해 현재 열을 사용자 탭으로 나타내게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="33926-242">When the <xref:System.Windows.Forms.DataGridView.SelectionMode?displayProperty=nameWithType> is set to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType>, the column header changes color to indicate the current column as the user tabs through the cells in the current row.</span></span>

- <span data-ttu-id="33926-243"><xref:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject?displayProperty=nameWithType>의 <xref:System.Windows.Forms.AccessibleObject.Parent?displayProperty=nameWithType> 속성은 이제 올바른 부모 컨트롤을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-243">The <xref:System.Windows.Forms.AccessibleObject.Parent?displayProperty=nameWithType> property of a  <xref:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject?displayProperty=nameWithType> returns the correct parent control.</span></span>

<span data-ttu-id="33926-244">**개선된 시각적 표시**</span><span class="sxs-lookup"><span data-stu-id="33926-244">**Improved visual cues**</span></span>

- <span data-ttu-id="33926-245"><xref:System.Windows.Forms.ButtonBase.Text> 속성이 빈 <xref:System.Windows.Forms.RadioButton> 및 <xref:System.Windows.Forms.CheckBox> 컨트롤은 포커스를 받을 때 포커스 표시기를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-245">The <xref:System.Windows.Forms.RadioButton> and <xref:System.Windows.Forms.CheckBox> controls with an empty <xref:System.Windows.Forms.ButtonBase.Text> property  display a focus indicator when they receive the focus.</span></span>

<span data-ttu-id="33926-246">**개선된 속성 표 지원**</span><span class="sxs-lookup"><span data-stu-id="33926-246">**Improved Property Grid Support**</span></span>

- <span data-ttu-id="33926-247"><xref:System.Windows.Forms.PropertyGrid> 컨트롤 자식 요소는 PropertyGrid 요소를 사용하도록 설정한 경우에만 <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> 속성에 대한 `true`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-247">The <xref:System.Windows.Forms.PropertyGrid> control child elements now return a `true` for the  <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> property only when a PropertyGrid element is enabled.</span></span>

- <span data-ttu-id="33926-248"><xref:System.Windows.Forms.PropertyGrid> 컨트롤 자식 요소는 PropertyGrid 요소를 사용자가 변경할 수 있는 경우에만 <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> 속성에 대한 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-248">The <xref:System.Windows.Forms.PropertyGrid> control child elements return a `false` for the <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> property only when a PropertyGrid element can be changed by the user.</span></span>

<span data-ttu-id="33926-249">**바로 가기 탐색 개선**</span><span class="sxs-lookup"><span data-stu-id="33926-249">**Improved keyboard navigation**</span></span>

- <span data-ttu-id="33926-250"><xref:System.Windows.Forms.ToolStripButton> 컨트롤은 <xref:System.Windows.Forms.ToolStripPanel.TabStop> 속성이 `true`로 설정된 <xref:System.Windows.Forms.ToolStripPanel>에 포함된 경우 포커스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-250">The <xref:System.Windows.Forms.ToolStripButton> control allows focus when contained within a <xref:System.Windows.Forms.ToolStripPanel> that has the <xref:System.Windows.Forms.ToolStripPanel.TabStop> property set to `true`</span></span>

<a name="wpf472"></a>

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="33926-251">WPF(Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="33926-251">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="33926-252">**CheckBox 및 RadioButton 컨트롤에 대한 변경**</span><span class="sxs-lookup"><span data-stu-id="33926-252">**Changes to the CheckBox and RadioButton controls**</span></span>

<span data-ttu-id="33926-253">.NET Framework 4.7.1 이전 버전에서 WPF <xref:System.Windows.Controls.CheckBox?displayProperty=nameWIthType> 및 <xref:System.Windows.Controls.RadioButton?displayProperty=nameWIthType> 컨트롤에는 일치하지 않는, 그리고 기본 및 고대비 테마에서는 잘못된 포커스 시각적 개체가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-253">In .NET Framework 4.7.1 and earlier versions, the WPF <xref:System.Windows.Controls.CheckBox?displayProperty=nameWIthType> and <xref:System.Windows.Controls.RadioButton?displayProperty=nameWIthType> controls have inconsistent and, in Classic and High Contrast themes, incorrect focus visuals.</span></span>  <span data-ttu-id="33926-254">이러한 문제는 컨트롤에 아무 콘텐츠 집합도 없는 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-254">These issues occur in cases where the controls do not have any content set.</span></span>  <span data-ttu-id="33926-255">이렇게 하면 테마 혼동 및 포커스 시각적 개체 간 전환을 보기 어렵게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-255">This can make the transition between themes confusing and the focus visual hard to see.</span></span>

<span data-ttu-id="33926-256">NET Framework 4.7.2에서 이러한 시각적 개체는 이제 테마에서 더욱 일관적이고 기본 및 고대비 테마에서 더욱 쉽게 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-256">In .NET Framework 4.7.2, these visuals are now more consistent across themes and more easily visible in Classic and High Contrast themes.</span></span>

<span data-ttu-id="33926-257">**WPF 애플리케이션에서 호스트되는 WinForms 컨트롤**</span><span class="sxs-lookup"><span data-stu-id="33926-257">**WinForms controls hosted in a WPF application**</span></span>

<span data-ttu-id="33926-258">.NET Framework 4.7.1 이전 버전의 WPF 애플리케이션에서 호스팅되는 WinForms 컨트롤의 경우 사용자는 해당 계층의 첫 번째 또는 마지막 컨트롤이 WPF <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤이면 WinForms 계층을 탭아웃할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-258">For WinForms control hosted in a WPF application in .NET Framework 4.7.1 and earlier versions, users couldn't tab out of the WinForms layer if the first or last control in that layer is the WPF <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span> <span data-ttu-id="33926-259">.NET Framework 4.7.2에서 사용자는 이제 WinForms 계층을 탭아웃할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-259">In .NET Framework 4.7.2, users are now able to tab out of the WinForms layer.</span></span>

<span data-ttu-id="33926-260">그러나 WinForms 계층을 이스케이프하지 않는 포커스를 사용하는 자동화된 애플리케이션은 더 이상 예상대로 작동하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-260">However, automated applications that rely on focus never escaping the WinForms layer may no longer work as expected.</span></span>

## <a name="whats-new-in-accessibility-in-net-framework-471"></a><span data-ttu-id="33926-261">.NET Framework 4.7.1에서 내게 필요한 옵션의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="33926-261">What's new in accessibility in .NET Framework 4.7.1</span></span>

<span data-ttu-id="33926-262">.NET Framework 4.7.1에는 다음과 같은 영역의 새로운 내게 필요한 옵션 기능이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="33926-262">.NET Framework 4.7.1 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="33926-263">WPF(Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="33926-263">Windows Presentation Foundation (WPF)</span></span>](#wpf471)

- [<span data-ttu-id="33926-264">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="33926-264">Windows Forms</span></span>](#winforms471)

- [<span data-ttu-id="33926-265">ASP.NET 웹 컨트롤</span><span class="sxs-lookup"><span data-stu-id="33926-265">ASP.NET web controls</span></span>](#aspnet471)

- [<span data-ttu-id="33926-266">.NET SDK Tools</span><span class="sxs-lookup"><span data-stu-id="33926-266">.NET SDK Tools</span></span>](#tools471)

- [<span data-ttu-id="33926-267">Windows WF(Workflow Foundation) 워크플로 디자이너</span><span class="sxs-lookup"><span data-stu-id="33926-267">Windows Workflow Foundation (WF) Workflow Designer</span></span>](#wf471)

<a name="wpf471"></a>

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="33926-268">WPF(Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="33926-268">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="33926-269">**화면 판독기 개선 사항**</span><span class="sxs-lookup"><span data-stu-id="33926-269">**Screen reader improvements**</span></span>

<span data-ttu-id="33926-270">내게 필요한 옵션 개선 사항이 활성화된 경우 .NET Framework 4.7.1에는 화면 판독기에 영향을 주는 다음과 같은 향상 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-270">If accessibility improvements are enabled, .NET Framework 4.7.1 includes the following enhancements that affect screen readers:</span></span>

- <span data-ttu-id="33926-271">.NET Framework 4.7 이전 버전에서 <xref:System.Windows.Controls.Expander> 컨트롤은 단추로 화면 readers에서 공지되었습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-271">In .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.Expander> controls were announced by screen readers as buttons.</span></span> <span data-ttu-id="33926-272">.NET Framework 4.7.1부터 확장/축소 가능한 그룹으로 올바르게 공지됩니다.</span><span class="sxs-lookup"><span data-stu-id="33926-272">Starting with .NET Framework 4.7.1, they are correctly announced as expandable/collapsible groups.</span></span>

- <span data-ttu-id="33926-273">.NET Framework 4.7 이전 버전에서 <xref:System.Windows.Controls.DataGridCell> 컨트롤은 “사용자 지정”으로 화면 readers에서 공지되었습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-273">In .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.DataGridCell> controls were announced by screen readers as “custom.”</span></span> <span data-ttu-id="33926-274">.NET Framework 4.7.1부터 이제 데이터 표 셸(지역화된)로 올바르게 공지됩니다.</span><span class="sxs-lookup"><span data-stu-id="33926-274">Starting with .NET Framework 4.7.1, they are now correctly announced as data grid cell (localized).</span></span>

- <span data-ttu-id="33926-275">.NET Framework 4.7.1부터 화면 readers는 편집 가능한 <xref:System.Windows.Controls.ComboBox>의 이름을 공지합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-275">Starting with .NET Framework 4.7.1, screen readers announce the name of an editable <xref:System.Windows.Controls.ComboBox>.</span></span>

- <span data-ttu-id="33926-276">.NET Framework 4.7 이전 버전에서 <xref:System.Windows.Controls.PasswordBox> 컨트롤은 "보기에 항목 없음"으로 공지되었거나 그렇지 않은 경우 잘못된 동작이 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-276">In .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.PasswordBox> controls were announced as “no item in view” or had otherwise incorrect behavior.</span></span> <span data-ttu-id="33926-277">이 문제는 .NET Framework 4.7.1부터 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-277">This issue is fixed starting with .NET Framework 4.7.1.</span></span>

<span data-ttu-id="33926-278">**UIAutomation LiveRegion 지원**</span><span class="sxs-lookup"><span data-stu-id="33926-278">**UIAutomation LiveRegion support**</span></span>

<span data-ttu-id="33926-279">내레이터와 같은 화면 판독기는 사용자가 일반적으로 포커스가 있는 UI 콘텐츠의 텍스트 음성 변환 출력에 의해 애플리케이션의 UI 콘텐츠를 읽는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="33926-279">Screen readers such as Narrator help people read the UI contents of an application, usually by text-to-speech output of the UI content that has the focus.</span></span> <span data-ttu-id="33926-280">그러나 UI 요소가 변경되고 포커스가 없는 경우 사용자는 알림을 받지 못하고 중요한 정보를 놓칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-280">However, if a UI element changes and does not have the focus, the user may not be notified and may miss important information.</span></span> <span data-ttu-id="33926-281">라이브 영역은 이 문제를 해결하는 것을 목표로 합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-281">Live regions aim at solving this problem.</span></span> <span data-ttu-id="33926-282">개발자는 화면 판독기 또는 다른 UIAutomation 클라이언트에게 UI 요소에 중요한 변경 내용이 만들어졌음을 알리는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-282">A developer can use them to inform the screen reader or any other UIAutomation client that an important change has been made to a UI element.</span></span> <span data-ttu-id="33926-283">화면 판독기는 사용자에게 이 변경 내용을 알리는 방법 및 시점을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-283">The screen reader can then decide how and when to inform the user of this change.</span></span>

<span data-ttu-id="33926-284">라이브 영역을 지원하기 위해 다음과 같은 API가 WPF에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-284">To support live regions, the following APIs have been added to WPF:</span></span>

- <span data-ttu-id="33926-285">**LiveSetting** 속성 및 **LiveRegionChanged** 이벤트를 식별하는 <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> 및 <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> 필드</span><span class="sxs-lookup"><span data-stu-id="33926-285">The <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> fields, which identify the **LiveSetting** property and the **LiveRegionChanged** event.</span></span> <span data-ttu-id="33926-286">XAML을 사용하여 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-286">They can be set by using XAML.</span></span>

- <span data-ttu-id="33926-287">**AutomationProperties.LiveSetting** 연결된 속성으로, 화면 판독기에 사용자에 대한 UI 변경 내용의 중요성을 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="33926-287">The **AutomationProperties.LiveSetting** attached property, which informs the screen reader of the importance of the UI change to the user.</span></span>

- <span data-ttu-id="33926-288">**AutomationProperties.LiveSetting** 연결된 속성을 식별하는 <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> 속성</span><span class="sxs-lookup"><span data-stu-id="33926-288">The <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> property, which identifies the **AutomationProperties.LiveSetting** attached property.</span></span>

- <span data-ttu-id="33926-289">**LiveSetting** 값을 제공하도록 재정의될 수 있는 <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> 메서드</span><span class="sxs-lookup"><span data-stu-id="33926-289">The <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> method, which can be overridden to provide a **LiveSetting** value.</span></span>

- <span data-ttu-id="33926-290">**LiveSetting** 값을 가져오고 설정하는 <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> 및 <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> 메서드</span><span class="sxs-lookup"><span data-stu-id="33926-290">The <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> methods, which get and set a **LiveSetting** value.</span></span>

- <span data-ttu-id="33926-291">다음 가능한 **LiveSetting** 값을 정의하는 <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> 열거형</span><span class="sxs-lookup"><span data-stu-id="33926-291">The <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> enumeration, which defines the following possible **LiveSetting** values:</span></span>

  - <span data-ttu-id="33926-292"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="33926-292"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span></span> <span data-ttu-id="33926-293">라이브 영역의 콘텐츠가 변경된 경우 요소는 알림을 보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-293">The element does not send notifications if the content of the live region has changed.</span></span>
  - <span data-ttu-id="33926-294"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="33926-294"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span></span> <span data-ttu-id="33926-295">라이브 영역의 콘텐츠가 변경된 경우 요소는 비중단 알림을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="33926-295">The element sends non-interruptive notifications if the content of the live region has changed.</span></span>

  - <span data-ttu-id="33926-296"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="33926-296"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span></span> <span data-ttu-id="33926-297">라이브 영역의 콘텐츠가 변경된 경우 요소는 중단 알림을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="33926-297">The element sends interruptive notifications if the content of the live region has changed.</span></span>

<span data-ttu-id="33926-298">다음 예제와 같이 관심 있는 요소에 **AutomationProperties.LiveSetting** 속성을 설정하여 LiveRegion을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-298">You can create a LiveRegion by setting the **AutomationProperties.LiveSetting** property on the element of interest, as shown in the following example:</span></span>

```xaml
<TextBlock Name="myTextBlock" AutomationProperties.LiveSetting="Assertive">announcement</TextBlock>
```

<span data-ttu-id="33926-299">라이브 영역에 있는 데이터가 변경되고 화면 판독기에 알려야 하는 경우 다음 샘플과 같이 명시적으로 이벤트를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="33926-299">When the data in the live region changes and you need to inform a screen reader, you explicitly raise an event, as shown in the following sample.</span></span>

```csharp
var peer = FrameworkElementAutomationPeer.FromElement(myTextBlock);

peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged);
```

```vb
Dim peer = FrameworkElementAutomationPeer.FromElement(myTextBlock)
peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged)

```

<span data-ttu-id="33926-300">**고대비**</span><span class="sxs-lookup"><span data-stu-id="33926-300">**High contrast**</span></span>

<span data-ttu-id="33926-301">.NET Framework 4.7.1부터 다양한 WPF 컨트롤에 고대비의 개선 사항이 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-301">Starting with .NET Framework 4.7.1, improvements in high contrast have been made to various WPF controls.</span></span> <span data-ttu-id="33926-302"><xref:System.Windows.SystemParameters.HighContrast%2A> 테마가 설정된 경우 이제 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="33926-302">They are now visible when the <xref:System.Windows.SystemParameters.HighContrast%2A> theme is set.</span></span> <span data-ttu-id="33926-303">여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="33926-303">These include:</span></span>

- <span data-ttu-id="33926-304"><xref:System.Windows.Controls.Expander> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="33926-304"><xref:System.Windows.Controls.Expander> control</span></span>

  <span data-ttu-id="33926-305"><xref:System.Windows.Controls.Expander> 컨트롤에 대한 포커스 시각적 개체는 이제 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="33926-305">The focus visual for the  <xref:System.Windows.Controls.Expander> control is now visible.</span></span> <span data-ttu-id="33926-306"><xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.ListBox> 및 <xref:System.Windows.Controls.RadioButton> 컨트롤에 대한 키보드 시각적 개체도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="33926-306">The keyboard visuals for <xref:System.Windows.Controls.ComboBox>,<xref:System.Windows.Controls.ListBox>, and <xref:System.Windows.Controls.RadioButton> controls are visible as well.</span></span> <span data-ttu-id="33926-307">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="33926-307">For example:</span></span>

  <span data-ttu-id="33926-308">이전:</span><span class="sxs-lookup"><span data-stu-id="33926-308">Before:</span></span>

  ![포커스가 있는 확장기 컨트롤 및 포커스 화면 효과가 없는 확장기 컨트롤의 스크린샷.](./media/whats-new-in-accessibility/expander-control-before.png)

  <span data-ttu-id="33926-310">이후:</span><span class="sxs-lookup"><span data-stu-id="33926-310">After:</span></span>

  ![포커스가 있는 확장기 컨트롤(컨트롤의 텍스트 주위가 점선으로 표시됨)의 스크린샷](./media/whats-new-in-accessibility/expander-control-after.png)

- <span data-ttu-id="33926-312"><xref:System.Windows.Controls.CheckBox> 및 <xref:System.Windows.Controls.RadioButton> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="33926-312"><xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls</span></span>

  <span data-ttu-id="33926-313"><xref:System.Windows.Controls.CheckBox> 및 <xref:System.Windows.Controls.RadioButton> 컨트롤의 텍스트는 이제 고대비 테마에서 선택하면 쉽게 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-313">The text in the <xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls is now easier to see when selected in high contrast themes.</span></span> <span data-ttu-id="33926-314">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="33926-314">For example:</span></span>

  <span data-ttu-id="33926-315">이전:</span><span class="sxs-lookup"><span data-stu-id="33926-315">Before:</span></span>

  ![고대비 테마에서 텍스트 가시성이 낮은 라디오 단추 및 확인 단추의 스크린샷](./media/whats-new-in-accessibility/high-contrast-radio-button-before.png)

  <span data-ttu-id="33926-317">이후:</span><span class="sxs-lookup"><span data-stu-id="33926-317">After:</span></span>

  ![고대비 테마에서 텍스트 가시성이 높은 라디오 단추 및 확인 단추의 스크린샷](./media/whats-new-in-accessibility/high-contrast-radio-button-after.png)

- <span data-ttu-id="33926-319"><xref:System.Windows.Controls.ComboBox> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="33926-319"><xref:System.Windows.Controls.ComboBox> control</span></span>

  <span data-ttu-id="33926-320">.NET Framework 4.7.1부터 비활성화된 <xref:System.Windows.Controls.ComboBox> 컨트롤의 테두리는 비활성화된 텍스트와 동일한 색입니다.</span><span class="sxs-lookup"><span data-stu-id="33926-320">Starting with .NET Framework 4.7.1, the border of a disabled <xref:System.Windows.Controls.ComboBox> control is the same color as disabled text.</span></span> <span data-ttu-id="33926-321">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="33926-321">For example:</span></span>

  <span data-ttu-id="33926-322">이전:</span><span class="sxs-lookup"><span data-stu-id="33926-322">Before:</span></span>

  ![테두리와 컨트롤 텍스트의 색상이 다른 비활성화된 콤보 상자의 스크린샷](./media/whats-new-in-accessibility/combo-disabled-before.png)

  <span data-ttu-id="33926-324">이후:</span><span class="sxs-lookup"><span data-stu-id="33926-324">After:</span></span>

  ![테두리와 컨트롤 텍스트의 색상이 동일한 비활성화된 콤보 상자의 스크린샷](./media/whats-new-in-accessibility/combo-disabled-after.png)

  <span data-ttu-id="33926-326">또한 비활성화되고 포커스가 있는 단추는 올바른 테마 색을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-326">In addition, disabled and focused buttons use the correct theme color.</span></span>

  <span data-ttu-id="33926-327">이전:</span><span class="sxs-lookup"><span data-stu-id="33926-327">Before:</span></span>

  ![회색 텍스트로 나에게 포커스 지정이 표시되는 검은색 단추의 스크린샷](./media/whats-new-in-accessibility/button-theme-colors-before.png)

  <span data-ttu-id="33926-329">이후:</span><span class="sxs-lookup"><span data-stu-id="33926-329">After:</span></span>

  ![검은색 텍스트로 나에게 포커스 지정이 표시되는 파란색 단추의 스크린샷](./media/whats-new-in-accessibility/button-theme-colors-after.png)

  <span data-ttu-id="33926-331">마지막으로 .NET Framework 4.7 이전 버전에서 <xref:System.Windows.Controls.ComboBox> 컨트롤의 스타일을 `Toolbar.ComboBoxStyleKey`로 설정하면 드롭다운 화살표가 표시되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-331">Finally, in .NET Framework 4.7 and earlier versions, setting a <xref:System.Windows.Controls.ComboBox> control’s style to `Toolbar.ComboBoxStyleKey` caused the drop-down arrow to be invisible.</span></span> <span data-ttu-id="33926-332">이 문제는 .NET Framework 4.7.1부터 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-332">This issue is fixed starting with .NET Framework 4.7.1.</span></span> <span data-ttu-id="33926-333">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="33926-333">For example:</span></span>

  <span data-ttu-id="33926-334">이전:</span><span class="sxs-lookup"><span data-stu-id="33926-334">Before:</span></span>

  ![보이지 않는 드롭다운 화살표가 있는 콤보 상자 컨트롤의 스크린샷](./media/whats-new-in-accessibility/combo-box-style-key-before.png)

  <span data-ttu-id="33926-336">이후:</span><span class="sxs-lookup"><span data-stu-id="33926-336">After:</span></span>

  ![드롭다운 화살표가 표시된 콤보 상자 컨트롤의 스크린샷](./media/whats-new-in-accessibility/combo-box-style-key-after.png)

- <span data-ttu-id="33926-338"><xref:System.Windows.Controls.DataGrid> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="33926-338"><xref:System.Windows.Controls.DataGrid> control</span></span>

  <span data-ttu-id="33926-339">.NET Framework 4.7.1부터 <xref:System.Windows.Controls.DataGrid> 컨트롤의 정렬 표시기 화살표는 이제 올바른 테마 색을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-339">Starting with .NET Framework 4.7.1, the sort indicator arrow in <xref:System.Windows.Controls.DataGrid> controls now uses correct theme colors.</span></span> <span data-ttu-id="33926-340">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="33926-340">For example:</span></span>

  <span data-ttu-id="33926-341">이전:</span><span class="sxs-lookup"><span data-stu-id="33926-341">Before:</span></span>

  ![개선 사항 이전의 정렬 표시기 화살표의 스크린샷](./media/whats-new-in-accessibility/sort-indicator-before.png)

  <span data-ttu-id="33926-343">이후:</span><span class="sxs-lookup"><span data-stu-id="33926-343">After:</span></span>

  ![개선 사항 이후의 정렬 표시기 화살표의 스크린샷](./media/whats-new-in-accessibility/sort-indicator-after.png)

  <span data-ttu-id="33926-345">또한 .NET Framework 4.7 이전 버전에서 기본 링크 스타일은 고대비 모드의 마우스에서 잘못된 색으로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-345">In addition, in .NET Framework 4.7 and earlier versions, the default link style changed to an incorrect color on mouse over in high contrast modes.</span></span> <span data-ttu-id="33926-346">이는 .NET Framework 4.7.1부터 해결되었습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-346">This is resolved starting with .NET Framework 4.7.1.</span></span> <span data-ttu-id="33926-347">마찬가지로 <xref:System.Windows.Controls.DataGrid> 확인란 열은 .NET Framework 4.7.1부터 키보드 포커스 피드백에 대해 예상되는 색을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-347">Similarly, <xref:System.Windows.Controls.DataGrid> checkbox columns uses the expected colors for keyboard focus feedback starting with .NET Framework 4.7.1.</span></span>

  <span data-ttu-id="33926-348">이전:</span><span class="sxs-lookup"><span data-stu-id="33926-348">Before:</span></span>

  ![빨간색으로 여기를 클릭하세요가 표시되는 링크의](./media/whats-new-in-accessibility/default-link-style-before.png)

  <span data-ttu-id="33926-351">이후:</span><span class="sxs-lookup"><span data-stu-id="33926-351">After:</span></span>

  ![노란색으로 여기를 클릭하세요가 표시되는 링크의](./media/whats-new-in-accessibility/default-link-style-after.png)

<span data-ttu-id="33926-354">.NET Framework 4.7.1에서 WPF 내게 필요한 옵션 개선 사항에 대한 자세한 내용은 [WPF의 내게 필요한 옵션 개선 사항](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="33926-354">For more information on WPF accessibility improvements in .NET Framework 4.7.1, see [Accessibility improvements in WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).</span></span>

<a name="winforms471"></a>

### <a name="windows-forms-accessibility-improvements"></a><span data-ttu-id="33926-355">Windows Forms 내게 필요한 옵션 개선 사항</span><span class="sxs-lookup"><span data-stu-id="33926-355">Windows Forms accessibility improvements</span></span>

<span data-ttu-id="33926-356">.NET Framework 4.7.1에서 WinForms(Windows Forms)는 다음 영역에서 내게 필요한 옵션 변경 내용을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-356">In .NET Framework 4.7.1, Windows Forms (WinForms) includes accessibility changes in the following areas.</span></span>

<span data-ttu-id="33926-357">**고대비 모드에서 향상된 표시**</span><span class="sxs-lookup"><span data-stu-id="33926-357">**Improved display in High Contrast mode**</span></span>

<span data-ttu-id="33926-358">.NET Framework 4.7.1부터 다양한 WinForms 컨트롤은 운영 체제에서 사용할 수 있는 고대비 모드의 향상된 렌더링을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-358">Starting with .NET Framework 4.7.1, various WinForms controls offer improved rendering in the HighContrast modes available in the operating system.</span></span> <span data-ttu-id="33926-359">Windows 10은 일부 고대비 시스템 색에 대한 값을 변경했으며 Windows Forms는 Windows 10 Win32 프레임워크를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-359">Windows 10 has changed the values for some high contrast system colors, and Windows Forms is based on the Windows 10 Win32 framework.</span></span> <span data-ttu-id="33926-360">최상의 환경을 위해 최신 버전의 Windows를 실행하고 테스트 애플리케이션에 app.manifest 파일을 추가하여 최신 OS로 옵트인하고 다음과 같이 보이도록 Windows 10 지원 OS 줄에 대한 주석을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-360">For the best experience, run on the latest version of Windows and opt in to the latest OS changes by adding an app.manifest file in a test application and un-comment the Windows 10 supported OS  line so that it looks the following:</span></span>

```xml
<!-- Windows 10 -->
<supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
```

<span data-ttu-id="33926-361">고대비 변경 내용의 몇 가지 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-361">Some examples of high contrast changes include:</span></span>

- <span data-ttu-id="33926-362"><xref:System.Windows.Forms.MenuStrip> 항목의 확인 표시는 보기가 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-362">Checkmarks in <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="33926-363">선택하면 비활성화된 <xref:System.Windows.Forms.MenuStrip> 항목이 보기가 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-363">When selected, disabled <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="33926-364">선택된 <xref:System.Windows.Forms.Button> 컨트롤의 텍스트는 선택 영역 색과 대비됩니다.</span><span class="sxs-lookup"><span data-stu-id="33926-364">Text in a selected <xref:System.Windows.Forms.Button> control contrasts with the selection color.</span></span>

- <span data-ttu-id="33926-365">비활성화된 텍스트는 읽기가 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-365">Disabled text is easier to read.</span></span> <span data-ttu-id="33926-366">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="33926-366">For example:</span></span>

  <span data-ttu-id="33926-367">이전:</span><span class="sxs-lookup"><span data-stu-id="33926-367">Before:</span></span>

  ![접근성이 개선되기 전에 고대비 모드에서 실행되는 다른 컨트롤을 사용하는 앱의 스크린샷.](./media/whats-new-in-accessibility/high-contrast-mode-menu-items-before.png)

  <span data-ttu-id="33926-369">이후:</span><span class="sxs-lookup"><span data-stu-id="33926-369">After:</span></span>

  ![접근성이 개선된 후에 고대비 모드에서 실행되는 다른 컨트롤을 사용하는 앱의 스크린샷.](./media/whats-new-in-accessibility/high-contrast-mode-menu-items-after.png)

- <span data-ttu-id="33926-371">스레드 예외 대화 상자의 고대비 개선 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="33926-371">High contrast improvements in the Thread Exception Dialog.</span></span>

<span data-ttu-id="33926-372">**향상된 내레이터 지원**</span><span class="sxs-lookup"><span data-stu-id="33926-372">**Improved Narrator support**</span></span>

<span data-ttu-id="33926-373">.NET Framework 4.7.1에서 Windows Forms는 내레이터에 대한 다음과 같은 내게 필요한 옵션 개선 사항을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-373">Windows Forms in .NET Framework 4.7.1 includes the following accessibility improvements for the Narrator:</span></span>

- <span data-ttu-id="33926-374"><xref:System.Windows.Forms.MonthCalendar> 컨트롤은 내레이터 및 다른 UI 자동화 도구로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-374">The <xref:System.Windows.Forms.MonthCalendar> control can be accessed by the Narrator, as well as by other UI automation tools.</span></span>

- <span data-ttu-id="33926-375"><xref:System.Windows.Forms.CheckedListBox> 컨트롤은 항목의 선택 상태가 변경되어 목록 항목의 값을 변경했음을 사용자에게 알릴 때 내레이터에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="33926-375">The <xref:System.Windows.Forms.CheckedListBox> control notifies Narrator when an item's check state has changed so the user is notified that they’ve changed the value of a list item.</span></span>

- <span data-ttu-id="33926-376"><xref:System.Windows.Forms.DataGridViewCell> 컨트롤은 올바른 읽기 전용 상태를 내레이터에 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-376">The <xref:System.Windows.Forms.DataGridViewCell> control reports the correct read-only status to Narrator.</span></span>

- <span data-ttu-id="33926-377">내레이터는 이제 비활성화된 <xref:System.Windows.Forms.ToolStripMenuItem> 텍스트를 읽을 수 있는 반면 이전에는 비활성화된 메뉴 항목을 건너뛰었습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-377">Narrator can now read disabled <xref:System.Windows.Forms.ToolStripMenuItem> text, whereas previously it would skip over disabled menu items.</span></span>

<span data-ttu-id="33926-378">**UIAutomation 내게 필요한 옵션 패턴에 대한 향상된 지원**</span><span class="sxs-lookup"><span data-stu-id="33926-378">**Enhanced support for UIAutomation accessibility patterns**</span></span>

<span data-ttu-id="33926-379">.NET Framework 4.7.1부터 내게 필요한 옵션 기술 도구의 개발자는 API 내게 필요한 옵션의 일반 패턴 및 여러 WinForms 컨트롤에 대한 속성을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-379">Starting with .NET Framework 4.7.1, developers of accessibility technology tools can leverage common API accessibility patterns and properties for several WinForms controls.</span></span> <span data-ttu-id="33926-380">이러한 내게 필요한 옵션 개선 사항은 다음을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-380">These accessibility improvements include:</span></span>

- <span data-ttu-id="33926-381"><xref:System.Windows.Forms.ComboBox> 및 <xref:System.Windows.Forms.ToolStripSplitButton>은 이제 [확장/축소 패턴](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md)을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-381">The <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ToolStripSplitButton> now support the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>

- <span data-ttu-id="33926-382"><xref:System.Windows.Forms.DataGridViewCheckBoxCell>은 이제 [토글 패턴](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md)을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-382">The <xref:System.Windows.Forms.DataGridViewCheckBoxCell> now supports the [toggle pattern](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span></span>

- <span data-ttu-id="33926-383"><xref:System.Windows.Forms.ToolStripItem> 컨트롤은 <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> 속성 및 [확장/축소 패턴](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md)을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-383">The <xref:System.Windows.Forms.ToolStripItem> control supports the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> property and the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>

- <span data-ttu-id="33926-384"><xref:System.Windows.Forms.NumericUpDown> 및 <xref:System.Windows.Forms.DomainUpDown> 컨트롤은 <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> 속성을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-384">The <xref:System.Windows.Forms.NumericUpDown> and <xref:System.Windows.Forms.DomainUpDown> controls support the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> property.</span></span>

<span data-ttu-id="33926-385">**향상된 속성 브라우저 환경**</span><span class="sxs-lookup"><span data-stu-id="33926-385">**Improved property browser experience**</span></span>

<span data-ttu-id="33926-386">.NET Framework 4.7.1부터 Windows Forms는 다음을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-386">Starting with .NET Framework 4.7.1, Windows Forms includes:</span></span>

- <span data-ttu-id="33926-387">다양한 드롭다운 선택 창을 통한 향상된 키보드 탐색</span><span class="sxs-lookup"><span data-stu-id="33926-387">Better keyboard navigation through the various drop-down selection windows.</span></span>
- <span data-ttu-id="33926-388">불필요한 탭 정지의 감소</span><span class="sxs-lookup"><span data-stu-id="33926-388">A reduction of unnecessary tab stops.</span></span>
- <span data-ttu-id="33926-389">컨트롤 형식의 향상된 보고</span><span class="sxs-lookup"><span data-stu-id="33926-389">Better reporting of control types.</span></span>
- <span data-ttu-id="33926-390">향상된 내레이터 동작</span><span class="sxs-lookup"><span data-stu-id="33926-390">Improved narrator behavior.</span></span>

<a name="aspnet471"></a>

### <a name="aspnet-web-controls"></a><span data-ttu-id="33926-391">ASP.NET 웹 컨트롤</span><span class="sxs-lookup"><span data-stu-id="33926-391">ASP.NET web controls</span></span>

<span data-ttu-id="33926-392">.NET Framework 4.7.1 및 Visual Studio 2017 버전 15.3부터 ASP.NET은 ASP.NET 웹 컨트롤이 Visual Studio의 접근성 기술과 연동하는 방식을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-392">Starting with .NET Framework 4.7.1 and Visual Studio 2017 version 15.3, ASP.NET improves how ASP.NET web controls work with accessibility technology in Visual Studio.</span></span> <span data-ttu-id="33926-393">변경 내용은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-393">Changes include the following:</span></span>

- <span data-ttu-id="33926-394">**자세히 보기** 마법사의 **필드 추가** 대화 상자 또는 **ListView** 마법사의 **ListView 구성** 대화 상자와 같이 컨트롤에서 누락된 UI 액세스 가능성 패턴을 구현하도록 변경됨.</span><span class="sxs-lookup"><span data-stu-id="33926-394">Changes to implement missing UI accessibility patterns in controls, like the **Add Field** dialog in the **Details View** wizard, or the **Configure ListView** dialog of the **ListView** wizard.</span></span>

- <span data-ttu-id="33926-395">**데이터 호출기 필드 편집기**와 같이 고대비 모드에서 디스플레이를 개선하도록 변경됨.</span><span class="sxs-lookup"><span data-stu-id="33926-395">Changes to improve the display in High Contrast mode, like the **Data Pager Fields Editor**.</span></span>

- <span data-ttu-id="33926-396">DataPager 컨트롤의 **호출기 필드 편집** 마법사의 **필드** 대화 상자, **ObjectContext 구성** 대화 상자 또는 **데이터 원본 구성** 마법사의 **데이터 선택 구성** 대화 상자와 같은 컨트롤의 키보드 탐색 환경을 개선하도록 변경됨.</span><span class="sxs-lookup"><span data-stu-id="33926-396">Changes to improve the keyboard navigation experiences for controls, like the **Fields** dialog in the **Edit Pager Fields** wizard of the DataPager control, the **Configure ObjectContext** dialog, or the **Configure Data Selection** dialog of the **Configure Data Source** wizard.</span></span>

<a name="tools471"></a>

### <a name="net-sdk-tools"></a><span data-ttu-id="33926-397">.NET SDK Tools</span><span class="sxs-lookup"><span data-stu-id="33926-397">.NET SDK Tools</span></span>

<span data-ttu-id="33926-398">[Configuration Editor 도구(SvcConfigEditor.exe)](../wcf/configuration-editor-tool-svcconfigeditor-exe.md) 및 [Service Trace Viewer 도구(SvcTraceViewer.exe)](../wcf/service-trace-viewer-tool-svctraceviewer-exe.md)는 다양한 액세스 가능성 문제를 수정하여 향상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-398">The [Configuration Editor Tool (SvcConfigEditor.exe)](../wcf/configuration-editor-tool-svcconfigeditor-exe.md) and [Service Trace Viewer Tool (SvcTraceViewer.exe)](../wcf/service-trace-viewer-tool-svctraceviewer-exe.md) have been improved by fixing varied accessibility issues.</span></span> <span data-ttu-id="33926-399">이들 중 대부분은 정의되지 않은 이름이나 특정 UI 자동화 패턴이 올바르게 구현되지 않은 것과 같은 사소한 문제였습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-399">Most of these were small issues, like a name not being defined or certain UI automation patterns not being implemented correctly.</span></span> <span data-ttu-id="33926-400">많은 사용자가 이러한 잘못된 값을 인식하지 못하지만, 화면 판독기와 같은 보조 기술을 사용하는 고객은 이러한 SDK 도구를 보다 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-400">While many users won’t be aware of these incorrect values, customers who use assistive technologies like screen readers will find these SDK tools more accessible.</span></span>

<span data-ttu-id="33926-401">이러한 개선 사항은 키보드 포커스 순서 등의 일부 이전 동작을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-401">These enhancements change some previous behaviors, such as keyboard focus order.</span></span>

<a name="wf471"></a>

### <a name="windows-workflow-foundation-wf-workflow-designer"></a><span data-ttu-id="33926-402">Windows WF(Workflow Foundation) 워크플로 디자이너</span><span class="sxs-lookup"><span data-stu-id="33926-402">Windows Workflow Foundation (WF) Workflow Designer</span></span>

<span data-ttu-id="33926-403">워크플로 디자이너에서 내게 필요한 옵션 변경 내용은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-403">Accessibility changes in the Workflow Designer include the following:</span></span>

- <span data-ttu-id="33926-404">일부 컨트롤에서 왼쪽에서 오른쪽으로, 위쪽에서 아래쪽으로 탭 순서를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-404">The tab order changes to left to right and top to bottom in some controls:</span></span>

  - <span data-ttu-id="33926-405"><xref:System.ServiceModel.Activities.InitializeCorrelation> 작업에 대한 상관 관계 데이터를 설정하는 초기화 상관 관계 창</span><span class="sxs-lookup"><span data-stu-id="33926-405">The initialize correlation window for setting correlation data for the <xref:System.ServiceModel.Activities.InitializeCorrelation> activity.</span></span>

  - <span data-ttu-id="33926-406"><xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> 및 <xref:System.ServiceModel.Activities.ReceiveReply> 작업에 대한 콘텐츠 정의 창</span><span class="sxs-lookup"><span data-stu-id="33926-406">The content definition window for the <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, and <xref:System.ServiceModel.Activities.ReceiveReply> activities.</span></span>

- <span data-ttu-id="33926-407">바로 가기를 통해 추가 함수가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="33926-407">More functions are available via the keyboard:</span></span>

  - <span data-ttu-id="33926-408">작업의 속성을 편집할 때 처음으로 포커스된 경우 바로 가기에서 속성 그룹을 축소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-408">When editing the properties of an activity, property groups can be collapsed by keyboard the first time they are focused.</span></span>

  - <span data-ttu-id="33926-409">경고 아이콘은 바로 가기에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-409">Warning icons are accessible by keyboard.</span></span>

  - <span data-ttu-id="33926-410">바로 가기에서 **속성** 창의 **추가 속성** 단추에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-410">The **More Properties** button in the **Properties** window is accessible by keyboard.</span></span>

  - <span data-ttu-id="33926-411">바로 가기 사용자는 워크플로 디자이너의 **인수** 및 **변수** 창에 있는 헤더 항목에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33926-411">Keyboard users can access the header items in the **Arguments** and **Variables** panes of the Workflow Designer.</span></span>

- <span data-ttu-id="33926-412">다음과 같은 경우 포커스가 있는 항목의 표시 유형 향상</span><span class="sxs-lookup"><span data-stu-id="33926-412">Improved visibility of items with focus, such as when:</span></span>

  - <span data-ttu-id="33926-413">워크플로 디자이너 및 작업 디자이너에서 사용하는 데이터 그리드에 행 추가</span><span class="sxs-lookup"><span data-stu-id="33926-413">Adding rows to data grids used by the Workflow Designer and activity designers.</span></span>

  - <span data-ttu-id="33926-414"><xref:System.ServiceModel.Activities.ReceiveReply> 및 <xref:System.ServiceModel.Activities.SendReply> 작업에서 필드 누름</span><span class="sxs-lookup"><span data-stu-id="33926-414">Tabbing through fields in the <xref:System.ServiceModel.Activities.ReceiveReply> and <xref:System.ServiceModel.Activities.SendReply> activities.</span></span>

  - <span data-ttu-id="33926-415">변수 또는 인수에 대한 기본값 설정</span><span class="sxs-lookup"><span data-stu-id="33926-415">Setting default values for variables or arguments</span></span>

- <span data-ttu-id="33926-416">이제 화면 읽기 프로그램이 다음 항목을 올바르게 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-416">Screen readers can now correctly recognize:</span></span>

  - <span data-ttu-id="33926-417">워크플로 디자이너에서 설정된 중단점</span><span class="sxs-lookup"><span data-stu-id="33926-417">Breakpoints set in the workflow designer.</span></span>

  - <span data-ttu-id="33926-418"><xref:System.Activities.Statements.FlowSwitch%601>, <xref:System.Activities.Statements.FlowDecision> 및 <xref:System.ServiceModel.Activities.CorrelationScope> 작업</span><span class="sxs-lookup"><span data-stu-id="33926-418">The <xref:System.Activities.Statements.FlowSwitch%601>, <xref:System.Activities.Statements.FlowDecision>, and <xref:System.ServiceModel.Activities.CorrelationScope> activities.</span></span>
  - <span data-ttu-id="33926-419"><xref:System.ServiceModel.Activities.Receive> 작업의 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="33926-419">The contents of the <xref:System.ServiceModel.Activities.Receive> activity.</span></span>

  - <span data-ttu-id="33926-420"><xref:System.Activities.Statements.InvokeMethod> 작업의 대상 유형</span><span class="sxs-lookup"><span data-stu-id="33926-420">The Target Type for the <xref:System.Activities.Statements.InvokeMethod> activity.</span></span>

  - <span data-ttu-id="33926-421"><xref:System.Activities.Statements.TryCatch> 작업의 예외 콤보 상자 및 마지막 섹션</span><span class="sxs-lookup"><span data-stu-id="33926-421">The Exception combo box and the Finally section in the <xref:System.Activities.Statements.TryCatch> activity.</span></span>

  - <span data-ttu-id="33926-422">메시지 유형 콤보 상자, 상관 관계 이니셜라이저 추가 창의 분할기, 콘텐츠 정의 창 및 메시징 작업의 CorrelatesOn 정의 창(<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> 및 <xref:System.ServiceModel.Activities.ReceiveReply>)</span><span class="sxs-lookup"><span data-stu-id="33926-422">The Message Type combo box, the splitter in the Add Correlation Initializers window, the Content Definition window, and the CorrelatesOn Definition window in the messaging activities (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, and <xref:System.ServiceModel.Activities.ReceiveReply>).</span></span>

  - <span data-ttu-id="33926-423">상태 컴퓨터 전환 및 전환 대상</span><span class="sxs-lookup"><span data-stu-id="33926-423">State machine transitions and transitions destinations.</span></span>

  - <span data-ttu-id="33926-424"><xref:System.Activities.Statements.FlowDecision> 작업의 주석 및 커넥터</span><span class="sxs-lookup"><span data-stu-id="33926-424">Annotations and connectors on <xref:System.Activities.Statements.FlowDecision> activities.</span></span>

  - <span data-ttu-id="33926-425">작업의 팝업(마우스 오른쪽 단추 클릭) 메뉴</span><span class="sxs-lookup"><span data-stu-id="33926-425">The context (right-click) menus for activities.</span></span>

  - <span data-ttu-id="33926-426">속성 값 편집기, 검색 정리 단추, 범주별으로 및 사전순 정렬 단추 및 속성 그리드의 식 편집기 대화 상자</span><span class="sxs-lookup"><span data-stu-id="33926-426">The property value editors, the Clear Search button, the By Category and Alphabetical sort buttons, and the Expression Editor dialog in the properties grid.</span></span>

  - <span data-ttu-id="33926-427">워크플로 디자이너의 확대/축소 백분율</span><span class="sxs-lookup"><span data-stu-id="33926-427">The zoom percentage in the Workflow Designer.</span></span>

  - <span data-ttu-id="33926-428"><xref:System.Activities.Statements.Parallel> 및 <xref:System.Activities.Statements.Pick> 작업의 구분 기호</span><span class="sxs-lookup"><span data-stu-id="33926-428">The separator in <xref:System.Activities.Statements.Parallel> and <xref:System.Activities.Statements.Pick> activities.</span></span>

  - <span data-ttu-id="33926-429"><xref:System.Activities.Statements.InvokeDelegate> 작업</span><span class="sxs-lookup"><span data-stu-id="33926-429">The <xref:System.Activities.Statements.InvokeDelegate> activity.</span></span>

  - <span data-ttu-id="33926-430">사전 작업의 형식 선택 창(`Microsoft.Activities.AddToDictionary<TKey,TValue>`, `Microsoft.Activities.RemoveFromDictionary<TKey,TValue>`등)</span><span class="sxs-lookup"><span data-stu-id="33926-430">The Select Types window for dictionary activities (`Microsoft.Activities.AddToDictionary<TKey,TValue>`, `Microsoft.Activities.RemoveFromDictionary<TKey,TValue>`, etc.).</span></span>

  - <span data-ttu-id="33926-431">.NET 형식 찾아보기 및 선택 창</span><span class="sxs-lookup"><span data-stu-id="33926-431">The Browse and Select .NET Type window.</span></span>

  - <span data-ttu-id="33926-432">워크플로 디자이너의 이동 경로</span><span class="sxs-lookup"><span data-stu-id="33926-432">Breadcrumbs in the Workflow Designer.</span></span>

- <span data-ttu-id="33926-433">고대비 테마를 선택한 사용자는 워크플로 디자이너의 표시 유형에서 여러 개선 사항 및 포커스 요소에 사용되는 요소와 더욱 분명한 선택 영역 상자 사이의 대조율과 같은 해당 컨트롤을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="33926-433">Users who choose High Contrast themes will see many improvements in the visibility of the Workflow Designer and its controls, like better contrast ratios between elements and more noticeable selection boxes used for focus elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="33926-434">참조</span><span class="sxs-lookup"><span data-stu-id="33926-434">See also</span></span>

- [<span data-ttu-id="33926-435">.NET Framework의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="33926-435">What's new in the .NET Framework</span></span>](index.md)
