---
title: 높은 DPI 지원
description: 일반적인 높은 DPI 및 동적 DPI 시나리오에 대 한 Windows Forms 지원에 대해 알아봅니다. 또한 높은 DPI 지원을 위해 Windows Forms 응용 프로그램을 구성 하는 방법에 대해 알아봅니다.
ms.date: 05/16/2017
helpviewer_keywords:
- High DPI in Windows Forms
- Dynamic rescaling in Windows Forms
- Windows Forms layout
- Windows Forms dynamic resizing
ms.assetid: 075ea4c3-900c-4f8a-9dd2-13ea6804346b
ms.openlocfilehash: a9e0766307095da447c772de5a3065c18b7b7154
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325650"
---
# <a name="high-dpi-support-in-windows-forms"></a><span data-ttu-id="1af77-104">Windows Forms의 높은 DPI 지원</span><span class="sxs-lookup"><span data-stu-id="1af77-104">High DPI support in Windows Forms</span></span>

<span data-ttu-id="1af77-105">.NET Framework 4.7부터 Windows Forms 일반적인 높은 DPI 및 동적 DPI 시나리오에 대 한 향상 된 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1af77-105">Starting with the .NET Framework 4.7, Windows Forms includes enhancements for common high DPI and dynamic DPI scenarios.</span></span> <span data-ttu-id="1af77-106">이러한 개체는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1af77-106">These include:</span></span>

- <span data-ttu-id="1af77-107">컨트롤 및 컨트롤과 같은 여러 Windows Forms 컨트롤의 크기 조정 및 레이아웃이 개선 <xref:System.Windows.Forms.MonthCalendar> <xref:System.Windows.Forms.CheckedListBox> 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1af77-107">Improvements in the scaling and layout of a number of Windows Forms controls, such as the <xref:System.Windows.Forms.MonthCalendar> control and the <xref:System.Windows.Forms.CheckedListBox> control.</span></span>

- <span data-ttu-id="1af77-108">단일 패스 크기 조정.</span><span class="sxs-lookup"><span data-stu-id="1af77-108">Single-pass scaling.</span></span>  <span data-ttu-id="1af77-109">.NET Framework 4.6 이전 버전에서는 여러 패스를 통해 크기 조정을 수행 했습니다 .이로 인해 일부 컨트롤의 크기가 필요 이상으로 조정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1af77-109">In the .NET Framework 4.6 and earlier versions, scaling was performed through multiple passes, which caused some controls to be scaled more than was necessary.</span></span>

- <span data-ttu-id="1af77-110">사용자가 Windows Forms 응용 프로그램이 시작 된 후 DPI 또는 배율 인수를 변경 하는 동적 DPI 시나리오에 대 한 지원.</span><span class="sxs-lookup"><span data-stu-id="1af77-110">Support for dynamic DPI scenarios in which the user changes the DPI or scale factor after a Windows Forms application has been launched.</span></span>

<span data-ttu-id="1af77-111">.NET Framework 4.7부터 시작 하는 .NET Framework 버전에서는 향상 된 높은 DPI 지원이 옵트인 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="1af77-111">In versions of the .NET Framework starting with the .NET Framework 4.7, enhanced high DPI support is an opt-in feature.</span></span> <span data-ttu-id="1af77-112">응용 프로그램을 사용 하도록 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1af77-112">You must configure your application to take advantage of it.</span></span>

## <a name="configuring-your-windows-forms-app-for-high-dpi-support"></a><span data-ttu-id="1af77-113">높은 DPI 지원을 위해 Windows Forms 앱 구성</span><span class="sxs-lookup"><span data-stu-id="1af77-113">Configuring your Windows Forms app for high DPI support</span></span>

<span data-ttu-id="1af77-114">높은 DPI 인식을 지 원하는 새로운 Windows Forms 기능은 .NET Framework 4.7를 대상으로 하 고 Windows 10 크리에이터 스 업데이트부터 Windows 운영 체제에서 실행 되는 응용 프로그램 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1af77-114">The new Windows Forms features that support high DPI awareness are available only in applications that target the .NET Framework 4.7 and are running on Windows operating systems starting with the Windows 10 Creators Update.</span></span>

<span data-ttu-id="1af77-115">또한 Windows Forms 응용 프로그램에서 높은 DPI 지원을 구성 하려면 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1af77-115">In addition, to configure high DPI support in your Windows Forms application, you must do the following:</span></span>

- <span data-ttu-id="1af77-116">Windows 10과의 호환성을 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="1af77-116">Declare compatibility with Windows 10.</span></span>

  <span data-ttu-id="1af77-117">이렇게 하려면 매니페스트 파일에 다음을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1af77-117">To do this, add the following to your manifest file:</span></span>

  ```xml
  <compatibility xmlns="urn:schemas-microsoft-com:compatibility.v1">
    <application>
      <!-- Windows 10 compatibility -->
      <supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
    </application>
  </compatibility>
  ```

- <span data-ttu-id="1af77-118">*app.config* 파일에서 모니터 단위 dpi 인식을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1af77-118">Enable per-monitor DPI awareness in the *app.config* file.</span></span>

  <span data-ttu-id="1af77-119">Windows Forms [`<System.Windows.Forms.ApplicationConfigurationSection>`](../configure-apps/file-schema/winforms/index.md) 에서는 새 기능을 지원 하 고 .NET Framework 4.7부터 추가 된 사용자 지정을 지원 하기 위한 새 요소를 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="1af77-119">Windows Forms introduces a new [`<System.Windows.Forms.ApplicationConfigurationSection>`](../configure-apps/file-schema/winforms/index.md) element to support new features and customizations added starting with the .NET Framework 4.7.</span></span> <span data-ttu-id="1af77-120">높은 DPI를 지 원하는 새 기능을 활용 하려면 응용 프로그램 구성 파일에 다음을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1af77-120">To take advantage of the new features that support high DPI, add the following to your application configuration file.</span></span>

  ```xml
  <System.Windows.Forms.ApplicationConfigurationSection>
    <add key="DpiAwareness" value="PerMonitorV2" />
  </System.Windows.Forms.ApplicationConfigurationSection>
  ```

  > [!IMPORTANT]
  > <span data-ttu-id="1af77-121">이전 버전의 .NET Framework에서는 매니페스트를 사용 하 여 높은 DPI 지원을 추가 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1af77-121">In previous versions of the .NET Framework, you used the manifest to add high DPI support.</span></span> <span data-ttu-id="1af77-122">이 방법은 app.config 파일에 정의 된 설정을 재정의 하므로 더 이상 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1af77-122">This approach is no longer recommended, since it overrides settings defined on the app.config file.</span></span>

- <span data-ttu-id="1af77-123">정적 메서드를 호출 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> 합니다.</span><span class="sxs-lookup"><span data-stu-id="1af77-123">Call the static <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>

  <span data-ttu-id="1af77-124">응용 프로그램 진입점의 첫 번째 메서드 호출 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1af77-124">This should be the first method call in your application entry point.</span></span> <span data-ttu-id="1af77-125">예:</span><span class="sxs-lookup"><span data-stu-id="1af77-125">For example:</span></span>

  ```csharp
  static void Main()
  {
      Application.EnableVisualStyles();
      Application.SetCompatibleTextRenderingDefault(false);
      Application.Run(new Form2());
  }
  ```

## <a name="opting-out-of-individual-high-dpi-features"></a><span data-ttu-id="1af77-126">개별 높은 DPI 기능 옵트아웃</span><span class="sxs-lookup"><span data-stu-id="1af77-126">Opting out of individual high DPI features</span></span>

<span data-ttu-id="1af77-127">값을 `DpiAwareness` 로 설정 하면 `PerMonitorV2` 4.7 .NET Framework부터 .NET Framework 버전에서 지 원하는 모든 높은 DPI 인식 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1af77-127">Setting the `DpiAwareness` value to `PerMonitorV2` enables all high DPI awareness features supported by .NET Framework versions starting with the .NET Framework 4.7.</span></span> <span data-ttu-id="1af77-128">일반적으로 대부분의 Windows Forms 응용 프로그램에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="1af77-128">Typically, this is adequate for most Windows Forms applications.</span></span> <span data-ttu-id="1af77-129">그러나 하나 이상의 개별 기능을 옵트아웃 (opt out) 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1af77-129">However, you may want to opt out of one or more individual features.</span></span> <span data-ttu-id="1af77-130">이 작업을 수행 하는 가장 중요 한 이유는 기존 응용 프로그램 코드에서 해당 기능을 이미 처리 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1af77-130">The most important reason for doing this is that your existing application code already handles that feature.</span></span>  <span data-ttu-id="1af77-131">예를 들어 응용 프로그램에서 자동 크기 조정을 처리 하는 경우 다음과 같이 자동 크기 조정 기능을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1af77-131">For example, if your application handles auto scaling, you might want to disable the auto-resizing feature as follows:</span></span>

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="DpiAwareness" value="PerMonitorV2" />
  <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" />
</System.Windows.Forms.ApplicationConfigurationSection>
```

<span data-ttu-id="1af77-132">개별 키와 해당 값의 목록은 [Windows Forms Add Configuration 요소](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1af77-132">For a list of individual keys and their values, see [Windows Forms Add Configuration Element](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md).</span></span>

## <a name="new-dpi-change-events"></a><span data-ttu-id="1af77-133">새 DPI 변경 이벤트</span><span class="sxs-lookup"><span data-stu-id="1af77-133">New DPI change events</span></span>

<span data-ttu-id="1af77-134">.NET Framework 4.7부터 3 개의 새 이벤트를 사용 하 여 동적 DPI 변경을 프로그래밍 방식으로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1af77-134">Starting with the .NET Framework 4.7, three new events allow you to programmatically handle dynamic DPI changes:</span></span>

- <span data-ttu-id="1af77-135"><xref:System.Windows.Forms.Control.DpiChangedAfterParent>는 부모 컨트롤 또는 폼에 대 한 DPI 변경 이벤트가 발생 한 후 컨트롤의 DPI 설정이 프로그래밍 방식으로 변경 될 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="1af77-135"><xref:System.Windows.Forms.Control.DpiChangedAfterParent>, which is fired when the DPI setting for a control is changed programmatically after a DPI change event for it's parent control or form has occurred.</span></span>
- <span data-ttu-id="1af77-136"><xref:System.Windows.Forms.Control.DpiChangedBeforeParent>-부모 컨트롤이 나 폼에 대 한 DPI 변경 이벤트가 발생 하기 전에 컨트롤의 DPI 설정이 프로그래밍 방식으로 변경 될 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="1af77-136"><xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, which is fired when the DPI setting for a control is changed programmatically before a DPI change event for its parent control or form has occurred.</span></span>
- <span data-ttu-id="1af77-137"><xref:System.Windows.Forms.Form.DpiChanged>-폼이 현재 표시 되는 디스플레이 장치에서 DPI 설정이 변경 될 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="1af77-137"><xref:System.Windows.Forms.Form.DpiChanged>, which is fired when the DPI setting changes on the display device where the form is currently displayed.</span></span>

## <a name="new-helper-methods-and-properties"></a><span data-ttu-id="1af77-138">새 도우미 메서드 및 속성</span><span class="sxs-lookup"><span data-stu-id="1af77-138">New helper methods and properties</span></span>

<span data-ttu-id="1af77-139">또한 .NET Framework 4.7은 DPI 크기 조정에 대 한 정보를 제공 하 고 DPI 크기 조정을 수행할 수 있도록 하는 여러 가지 새로운 도우미 메서드 및 속성을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1af77-139">The .NET Framework 4.7 also adds a number of new helper methods and properties that provide information about DPI scaling and allow you to perform DPI scaling.</span></span> <span data-ttu-id="1af77-140">이러한 개체는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1af77-140">These include:</span></span>

- <span data-ttu-id="1af77-141"><xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>-값을 논리적에서 장치 픽셀로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1af77-141"><xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>, which converts a value from logical to device pixels.</span></span>

- <span data-ttu-id="1af77-142"><xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>-비트맵 이미지를 장치에 대 한 논리 DPI로 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="1af77-142"><xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>, which scales a bitmap image to the logical DPI for a device.</span></span>

- <span data-ttu-id="1af77-143"><xref:System.Windows.Forms.Control.DeviceDpi%2A>-현재 장치에 대 한 DPI를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1af77-143"><xref:System.Windows.Forms.Control.DeviceDpi%2A>, which returns the DPI for the current device.</span></span>

## <a name="versioning-considerations"></a><span data-ttu-id="1af77-144">버전 관리 고려 사항</span><span class="sxs-lookup"><span data-stu-id="1af77-144">Versioning considerations</span></span>

<span data-ttu-id="1af77-145">.NET Framework 4.7 및 Windows 10 크리에이터 업데이트를 실행 하는 것 외에도 응용 프로그램은 높은 DPI의 향상 된 기능과 호환 되지 않는 환경에서 실행 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1af77-145">In addition to running on .NET Framework 4.7 and Windows 10 Creators Update, your application may also run in an environment in which it isn't compatible with high DPI improvements.</span></span> <span data-ttu-id="1af77-146">이 경우에는 응용 프로그램에 대 한 대체 (fallback)를 개발 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1af77-146">In this case, you'll need to develop a fallback for your application.</span></span> <span data-ttu-id="1af77-147">이 작업을 수행 하 여 [사용자 지정 그리기](./controls/user-drawn-controls.md) 를 수행 하 여 크기 조정을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1af77-147">You can do this to perform [custom drawing](./controls/user-drawn-controls.md) to handle scaling.</span></span>

<span data-ttu-id="1af77-148">이렇게 하려면 앱이 실행 되는 운영 체제도 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1af77-148">To do this, you also need to determine the operating system on which your app is running.</span></span> <span data-ttu-id="1af77-149">다음과 같은 코드를 사용 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1af77-149">You can do that with code like the following:</span></span>

```csharp
// Create a reference to the OS version of Windows 10 Creators Update.
Version OsMinVersion = new Version(10, 0, 15063, 0);

// Access the platform/version of the current OS.
Console.WriteLine(Environment.OSVersion.Platform.ToString());
Console.WriteLine(Environment.OSVersion.VersionString);

// Compare the current version to the minimum required version.
Console.WriteLine(Environment.OSVersion.Version.CompareTo(OsMinVersion));
```

<span data-ttu-id="1af77-150">응용 프로그램은 응용 프로그램 매니페스트에서 지원 되는 운영 체제로 나열 되지 않은 경우 Windows 10을 성공적으로 검색 하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="1af77-150">Note that your application won't successfully detect Windows 10 if it wasn't listed as a supported operating system in the application manifest.</span></span>

<span data-ttu-id="1af77-151">응용 프로그램을 빌드한 .NET Framework 버전을 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1af77-151">You can also check the version of the .NET Framework that the application was built against:</span></span>

```csharp
Console.WriteLine(AppDomain.CurrentDomain.SetupInformation.TargetFrameworkName);
```

## <a name="see-also"></a><span data-ttu-id="1af77-152">참조</span><span class="sxs-lookup"><span data-stu-id="1af77-152">See also</span></span>

- [<span data-ttu-id="1af77-153">구성 요소 Windows Forms 추가</span><span class="sxs-lookup"><span data-stu-id="1af77-153">Windows Forms Add Configuration Element</span></span>](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)
- [<span data-ttu-id="1af77-154">Windows Forms의 크기 및 배율 조정</span><span class="sxs-lookup"><span data-stu-id="1af77-154">Adjusting the Size and Scale of Windows Forms</span></span>](adjusting-the-size-and-scale-of-windows-forms.md)
