---
title: 높은 DPI 지원
ms.date: 05/16/2017
helpviewer_keywords:
- High DPI in Windows Forms
- Dynamic rescaling in Windows Forms
- Windows Forms layout
- Windows Forms dynamic resizing
ms.assetid: 075ea4c3-900c-4f8a-9dd2-13ea6804346b
ms.openlocfilehash: a5c3125475c2de2cf83a3d97e356b26c0acdde99
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741891"
---
# <a name="high-dpi-support-in-windows-forms"></a>Windows Forms의 높은 DPI 지원

.NET Framework 4.7부터 Windows Forms 일반적인 높은 DPI 및 동적 DPI 시나리오에 대 한 향상 된 기능이 포함 되어 있습니다. 여기에는 다음이 포함됩니다.

- <xref:System.Windows.Forms.MonthCalendar> 컨트롤 및 <xref:System.Windows.Forms.CheckedListBox> 컨트롤과 같은 여러 Windows Forms 컨트롤의 크기 조정 및 레이아웃이 개선 되었습니다.

- 단일 패스 크기 조정.  .NET Framework 4.6 이전 버전에서는 여러 패스를 통해 크기 조정을 수행 했습니다 .이로 인해 일부 컨트롤의 크기가 필요 이상으로 조정 되었습니다.

- 사용자가 Windows Forms 응용 프로그램이 시작 된 후 DPI 또는 배율 인수를 변경 하는 동적 DPI 시나리오에 대 한 지원.

.NET Framework 4.7부터 시작 하는 .NET Framework 버전에서는 향상 된 높은 DPI 지원이 옵트인 기능입니다. 응용 프로그램을 사용 하도록 구성 해야 합니다.

## <a name="configuring-your-windows-forms-app-for-high-dpi-support"></a>높은 DPI 지원을 위해 Windows Forms 앱 구성

높은 DPI 인식을 지 원하는 새로운 Windows Forms 기능은 .NET Framework 4.7를 대상으로 하 고 Windows 10 크리에이터 스 업데이트부터 Windows 운영 체제에서 실행 되는 응용 프로그램 에서만 사용할 수 있습니다.

또한 Windows Forms 응용 프로그램에서 높은 DPI 지원을 구성 하려면 다음을 수행 해야 합니다.

- Windows 10과의 호환성을 선언 합니다.

  이렇게 하려면 매니페스트 파일에 다음을 추가 합니다.

  ```xml
  <compatibility xmlns="urn:schemas-microsoft-com:compatibility.v1">
    <application>
      <!-- Windows 10 compatibility -->
      <supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
    </application>
  </compatibility>
  ```

- *App.config* 파일에서 모니터 단위 dpi 인식을 사용 하도록 설정 합니다.

  Windows Forms에서는 새 기능을 지원 하 고 .NET Framework 4.7부터 추가 된 사용자 지정을 지원 하기 위해 새로운 [`<System.Windows.Forms.ApplicationConfigurationSection>`](../configure-apps/file-schema/winforms/index.md) 요소를 소개 합니다. 높은 DPI를 지 원하는 새 기능을 활용 하려면 응용 프로그램 구성 파일에 다음을 추가 합니다.

  ```xml
  <System.Windows.Forms.ApplicationConfigurationSection>
    <add key="DpiAwareness" value="PerMonitorV2" />
  </System.Windows.Forms.ApplicationConfigurationSection>
  ```

  > [!IMPORTANT]
  > 이전 버전의 .NET Framework에서는 매니페스트를 사용 하 여 높은 DPI 지원을 추가 했습니다. 이 방법은 app.config 파일에 정의 된 설정을 재정의 하므로 더 이상 권장 되지 않습니다.

- 정적 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> 메서드를 호출 합니다.

  응용 프로그램 진입점의 첫 번째 메서드 호출 이어야 합니다. 예를 들면 다음과 같습니다.:

  ```csharp
  static void Main()
  {
      Application.EnableVisualStyles();
      Application.SetCompatibleTextRenderingDefault(false);
      Application.Run(new Form2());
  }
  ```

## <a name="opting-out-of-individual-high-dpi-features"></a>개별 높은 DPI 기능 옵트아웃

`DpiAwareness` 값을 `PerMonitorV2`로 설정 하면 .NET Framework 버전에서 지 원하는 모든 높은 DPI 인식 기능을 .NET Framework 4.7부터 사용할 수 있습니다. 일반적으로 대부분의 Windows Forms 응용 프로그램에 적합 합니다. 그러나 하나 이상의 개별 기능을 옵트아웃 (opt out) 할 수 있습니다. 이 작업을 수행 하는 가장 중요 한 이유는 기존 응용 프로그램 코드에서 해당 기능을 이미 처리 하는 것입니다.  예를 들어 응용 프로그램에서 자동 크기 조정을 처리 하는 경우 다음과 같이 자동 크기 조정 기능을 사용 하지 않도록 설정할 수 있습니다.

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="DpiAwareness" value="PerMonitorV2" />
  <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" />
</System.Windows.Forms.ApplicationConfigurationSection>
```

개별 키와 해당 값의 목록은 [Windows Forms Add Configuration 요소](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)를 참조 하세요.

## <a name="new-dpi-change-events"></a>새 DPI 변경 이벤트

.NET Framework 4.7부터 3 개의 새 이벤트를 사용 하 여 동적 DPI 변경을 프로그래밍 방식으로 처리할 수 있습니다.

- <xref:System.Windows.Forms.Control.DpiChangedAfterParent>는 부모 컨트롤 또는 폼에 대 한 DPI 변경 이벤트가 발생 한 후 컨트롤의 DPI 설정이 프로그래밍 방식으로 변경 될 때 발생 합니다.
- <xref:System.Windows.Forms.Control.DpiChangedBeforeParent>는 부모 컨트롤 또는 양식에 대 한 DPI 변경 이벤트가 발생 하기 전에 컨트롤의 DPI 설정이 프로그래밍 방식으로 변경 될 때 발생 합니다.
- <xref:System.Windows.Forms.Form.DpiChanged>-폼이 현재 표시 되는 디스플레이 장치에서 DPI 설정이 변경 될 때 발생 합니다.

## <a name="new-helper-methods-and-properties"></a>새 도우미 메서드 및 속성

또한 .NET Framework 4.7은 DPI 크기 조정에 대 한 정보를 제공 하 고 DPI 크기 조정을 수행할 수 있도록 하는 여러 가지 새로운 도우미 메서드 및 속성을 추가 합니다. 여기에는 다음이 포함됩니다.

- <xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>-값을 논리적에서 장치 픽셀로 변환 합니다.

- 비트맵 이미지를 장치에 대 한 논리 DPI로 크기를 조정 하는 <xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>.

- <xref:System.Windows.Forms.Control.DeviceDpi%2A>-현재 장치에 대 한 DPI를 반환 합니다.

## <a name="versioning-considerations"></a>버전 관리 고려 사항

.NET Framework 4.7 및 Windows 10 크리에이터 업데이트를 실행 하는 것 외에도 응용 프로그램은 높은 DPI의 향상 된 기능과 호환 되지 않는 환경에서 실행 될 수 있습니다. 이 경우에는 응용 프로그램에 대 한 대체 (fallback)를 개발 해야 합니다. 이 작업을 수행 하 여 [사용자 지정 그리기](./controls/user-drawn-controls.md) 를 수행 하 여 크기 조정을 처리할 수 있습니다.

이렇게 하려면 앱이 실행 되는 운영 체제도 확인 해야 합니다. 다음과 같은 코드를 사용 하 여이 작업을 수행할 수 있습니다.

```csharp
// Create a reference to the OS version of Windows 10 Creators Update.
Version OsMinVersion = new Version(10, 0, 15063, 0);

// Access the platform/version of the current OS.
Console.WriteLine(Environment.OSVersion.Platform.ToString());
Console.WriteLine(Environment.OSVersion.VersionString);

// Compare the current version to the minimum required version.
Console.WriteLine(Environment.OSVersion.Version.CompareTo(OsMinVersion));
```

응용 프로그램은 응용 프로그램 매니페스트에서 지원 되는 운영 체제로 나열 되지 않은 경우 Windows 10을 성공적으로 검색 하지 못합니다.

응용 프로그램을 빌드한 .NET Framework 버전을 확인할 수도 있습니다.

```csharp
Console.WriteLine(AppDomain.CurrentDomain.SetupInformation.TargetFrameworkName);
```

## <a name="see-also"></a>참조

- [구성 요소 Windows Forms 추가](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)
- [Windows Forms의 크기 및 배율 조정](adjusting-the-size-and-scale-of-windows-forms.md)
