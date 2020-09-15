---
ms.openlocfilehash: c8e1c91f4fee8aa896b6617c815fe2a4b6d22f2a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614890"
---
### <a name="accessibility-improvements-in-windows-forms-controls"></a>Windows Forms 콘트롤의 서비스 효율성 개선 사항

#### <a name="details"></a>설명

Windows Forms는 Windows Forms 고객을 더욱 효과적으로 지원하도록 서비스 효율성 기술로 작업하는 방법을 개선합니다. .NET Framework 4.7.1부터 다음 변경 내용을 포함합니다.

- 고대비 모드 중에 표시를 개선하기 위한 변경 내용
- 속성 브라우저 환경을 개선하기 위한 변경 내용 속성 브라우저 개선 사항은 다음과 같습니다.
- 다양한 드롭다운 선택 창을 통한 향상된 키보드 탐색
- 불필요한 탭 중단 감소
- 컨트롤 형식의 향상된 보고
- 향상된 내레이터 동작
- 컨트롤에서 누락된 UI 서비스 효율성 패턴을 구현하기 위한 변경 내용

#### <a name="suggestion"></a>제안 해결 방법

**이러한 변경을 옵트인 또는 옵트아웃하는 방법**: 애플리케이션이 이러한 변경의 이점을 활용하도록 하기 위해 .NET Framework 4.7.1 이상에서 실행해야 합니다. 애플리케이션은 다음과 같은 방법으로 이러한 변경의 이점을 활용할 수 있습니다.

- 컴파일되어 .NET Framework 4.7.1을 대상으로 지정합니다. 이러한 서비스 효율성 변경 내용은 .NET Framework 4.7.1 이상을 대상으로 하는 Windows Forms 애플리케이션에서 기본적으로 활성화됩니다.
- 다음 예제와 같이 app.config 파일의 `<runtime>` 섹션에 [AppContext 스위치](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)를 추가하고 이를 `false`로 설정하여 레거시 접근성 동작을 옵트아웃합니다.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <startup>
    <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7"/>
  </startup>
  <runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true/false;key2=true/false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
  </runtime>
</configuration>
```

.NET Framework 4.7.1 이상을 대상으로 하고 레거시 액세스 가능성 동작을 유지하려는 애플리케이션은 이 AppContext 스위치를 `true`로 명확하게 설정하여 레거시 액세스 가능성 기능 사용을 옵트인할 수 있습니다.<p/>UI 자동화 개요는 [UI Automation 개요](~/docs/framework/ui-automation/ui-automation-overview.md)를 참조하세요.<p/>**UI Automation 패턴 및 속성에 대한 추가된 지원**<br/>접근성 클라이언트는 일반적이고 공개적으로 설명된 호출 패턴을 사용하여 새로운 WinForms 접근성 기능을 활용할 수 있습니다. 이러한 패턴은 WinForms에 특정되지 않습니다. 예를 들어 접근성 클라이언트가 IAccessible 인터페이스(MAAS)의 QueryInterface 메서드를 호출하여 IServiceProvider 인터페이스를 가져올 수 있습니다. 이 인터페이스가 지원되면 클라이언트는 QueryService 메서드를 사용하여 IAccessibleEx 인터페이스를 요청할 수 있습니다. 자세한 내용은 [클라이언트에서 IAccessibleEx 사용](https://docs.microsoft.com/windows/desktop/WinAuto/using-iaccessibleex-from-a-client)을 참조하세요. .NET Framework 4.7.1, IServiceProvider 및 [IAccessibleEx](https://docs.microsoft.com/windows/desktop/WinAuto/iaccessibleex)(적용 가능한 경우)부터는 WinForms 접근성 개체에 지원됩니다.<p/>.NET Framework 4.7.1은 다음 UI 자동화 패턴 및 속성에 대한 지원을 추가합니다.

- <xref:System.Windows.Forms.ToolStripSplitButton> 및 <xref:System.Windows.Forms.ComboBox> 컨트롤은 [확장/축소 패턴](~/docs/framework/ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md)을 지원합니다.
- <xref:System.Windows.Forms.ToolStripMenuItem> 컨트롤에는 [ControlType](~/docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md) 속성 값 <xref:System.Windows.Automation.ControlType.MenuItem?displayProperty=nameWithType>이 있습니다.
- <xref:System.Windows.Forms.ToolStripItem> 컨트롤은 <xref:System.Windows.Automation.AutomationElement.NameProperty> 속성 및 [확장/축소 패턴](~/docs/framework/ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md)을 지원합니다.
- <xref:System.Windows.Forms.ToolStripDropDownItem> 컨트롤은 드롭다운이 확장되거나 축소될 때 StateChange 및 NameChange를 나타내는 <xref:System.Windows.Forms.AccessibleEvents>를 지원합니다.
- <xref:System.Windows.Forms.ToolStripDropDownButton> 컨트롤에는 <xref:System.Windows.Automation.ControlType.MenuItem?displayProperty=nameWithType>이라는 [ControlType](~/docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md) 속성 값이 있습니다.
- <xref:System.Windows.Forms.DataGridViewCheckBoxCell> 컨트롤은 <xref:System.Windows.Automation.TogglePattern>을 지원합니다.
- <xref:System.Windows.Forms.NumericUpDown> 및 <xref:System.Windows.Forms.DomainUpDown> 컨트롤은 <xref:System.Windows.Automation.AutomationElement.NameProperty> 속성을 지원하고 <xref:System.Windows.Automation.ControlType.Spinner?displayProperty=nameWithType>의 [ControlType](~/docs/framework/ui-automation/ui-automation-support-for-the-spinner-control-type.md)을 포함합니다.</p>
**PropertyGrid 컨트롤의 개선 사항** .NET Framework 4.7.1은 PropertyBrowser 컨트롤에 다음과 같은 개선 사항을 추가합니다.

- 사용자가 <xref:System.Windows.Forms.PropertyGrid> 컨트롤에서 잘못된 값을 입력할 때 표시되는 오류 대화 상자의 **세부 정보** 단추는 <xref:System.Windows.Automation.ControlType.MenuItem?displayProperty=nameWithType> 값을 사용하여 [확장/축소 패턴](~/docs/framework/ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md), 상태 및 이름 변경 알림 및 [ControlType](~/docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md) 속성을 지원합니다.
- 오류 대화 상자의 **세부 정보** 단추가 확장될 때 표시되는 메시지 창은 이제 바로 가기에 액세스할 수 있으며 내레이터가 오류 메시지의 콘텐츠를 알리도록 합니다.
- <xref:System.Windows.Forms.PropertyGrid> 컨트롤에서 행의 <xref:System.Windows.Forms.AccessibleRole>은 &quot;행&quot;에서 &quot;셀&quot;로 변경되었습니다. 셀이 UIA ControlType &quot;DataItem&quot;에 매핑됩니다. 그러면 적절한 바로 가기 키 및 내레이터 공지를 지원할 수 있습니다.
- <xref:System.Windows.Forms.PropertyGrid> 컨트롤에 <xref:System.Windows.Forms.PropertyGrid.PropertySort> 속성이 <xref:System.Windows.Forms.PropertySort.Categorized?displayProperty=nameWithType>로 설정된 경우 헤더 항목을 나타내는 <xref:System.Windows.Forms.PropertyGrid> 컨트롤 행에는 <xref:System.Windows.Automation.ControlType.Button?displayProperty=nameWithType>이라는 [ControlType](~/docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md) 속성 값이 있습니다.
- <xref:System.Windows.Forms.PropertyGrid> 컨트롤에 <xref:System.Windows.Forms.PropertyGrid.PropertySort> 속성이 <xref:System.Windows.Forms.PropertySort.Categorized?displayProperty=nameWithType>로 설정된 경우 헤더 항목을 나타내는 <xref:System.Windows.Forms.PropertyGrid> 컨트롤 행은 [확장/축소 패턴](~/docs/framework/ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md)을 지원합니다.
- 그리드와 그 위의 도구 모음 간에 바로 가기 탐색 개선 &quot;Shift + Tab&quot; 키를 누르면 전체 도구 모음 대신 첫 번째 도구 모음 단추를 선택합니다.
- 고대비 모드에 표시되는 <xref:System.Windows.Forms.PropertyGrid> 컨트롤은 이제 현재 <xref:System.Windows.Forms.PropertyGrid.PropertySort> 속성 값에 해당하는 도구 모음 단추 주위에 포커스 사각형을 그립니다.
- 고대비 모드에서 표시되고 <xref:System.Windows.Forms.PropertyGrid.PropertySort> 속성이 <xref:System.Windows.Forms.PropertySort.Categorized?displayProperty=nameWithType>로 설정된 <xref:System.Windows.Forms.PropertyGrid> 컨트롤은 대비가 높은 색으로 범주 헤더의 배경을 표시합니다.
- <xref:System.Windows.Forms.PropertyGrid> 컨트롤은 포커스가 있는 도구 모음 항목과 현재 <xref:System.Windows.Forms.PropertyGrid.PropertySort> 속성 값을 나타내는 도구 모음 항목의 차이점을 잘 구분할 수 있습니다. 이 수정은 고대비 변경 내용 및 고대비가 아닌 시나리오에 대한 변경 내용으로 이루어져 있습니다.
- <xref:System.Windows.Forms.PropertyGrid.PropertySort> 속성의 현재 값을 나타내는 <xref:System.Windows.Forms.PropertyGrid> 컨트롤 도구 모음 항목은 <xref:System.Windows.Automation.TogglePattern>을 지원합니다.
- 맞춤 선택에서 선택한 맞춤을 구별하기 위한 내레이터 지원 개선
- 양식에 비어 있는 <xref:System.Windows.Forms.PropertyGrid> 컨트롤이 표시되는 경우 이전에 못한 포커스를 사용할 수 있습니다.

**고대비 테마에서 OS 정의 색 사용**

- 기본 스타일인 <xref:System.Windows.Forms.FlatStyle.System?displayProperty=nameWithType>로 설정된 <xref:System.Windows.Forms.ButtonBase.FlatStyle> 속성을 사용하는 <xref:System.Windows.Forms.Button> 및 <xref:System.Windows.Forms.CheckBox> 컨트롤은 선택된 경우 고대비 테마에서 OS 정의 색을 사용합니다. 이전에 텍스트 및 배경색이 대비되지 않았고 읽기가 어려웠습니다.
- **false**로 설정된 해당 <xref:System.Windows.Forms.Control.Enabled> 속성을 사용한 <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.CheckBox>, <xref:System.Windows.Forms.RadioButton>, <xref:System.Windows.Forms.Label>, <xref:System.Windows.Forms.LinkLabel> 및 <xref:System.Windows.Forms.GroupBox> 컨트롤은 음영이 있는 색을 사용하여 고대비 테마의 텍스트를 렌더링합니다. 따라서 배경에서 대비가 낮아집니다. 이제 이러한 컨트롤은 OS에서 정의된 &quot;비활성 텍스트&quot; 색을 사용합니다. 이 수정 사항은 `FlatStyle` 속성이 <xref:System.Windows.Forms.FlatStyle.System?displayProperty=nameWithType> 이외의 값으로 설정된 컨트롤에 적용됩니다. 두 번째 컨트롤은 OS에서 렌더링됩니다.
- 이제 <xref:System.Windows.Forms.DataGridView>는 현재 포커스가 있는 셀의 컨텐츠 주위에 표시 가능한 사각형을 렌더링합니다. 이전에는 특정 고대비 테마에 표시되지 않았습니다.
- 이제 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled> 속성이 **false**로 설정된 <xref:System.Windows.Forms.ToolStripMenuItem> 컨트롤은 OS에서 정의한 &quot;비활성 텍스트&quot; 색을 사용합니다.
- 이제 <xref:System.Windows.Forms.ToolStripMenuItem.Checked> 속성이 **true**로 설정된 <xref:System.Windows.Forms.ToolStripMenuItem> 컨트롤은 대비 시스템 색에서 연결된 확인 표시를 렌더링합니다.  이전에는 확인 표시 색이 충분히 대비되지 않고 고대비 테마에서 표시되지 않습니다.
참고:  Windows 10은 일부 고대비 시스템 색에 대한 값을 변경했습니다. Windows Forms Framework는 Win32 프레임워크를 기반으로 합니다. 환경을 최적화하기 위해 테스트 애플리케이션에 app.manifest 파일을 추가하고 다음과 같은 코드의 주석을 제거하여 최신 버전의 Windows에서 실행하고 최신 OS 변경 사항을 옵트인합니다.

```xml
<!-- Windows 10 -->
<supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
```

**바로 가기 탐색 개선**

- <xref:System.Windows.Forms.ComboBox> 컨트롤에 <xref:System.Windows.Forms.ComboBox.DropDownStyle> 속성이 <xref:System.Windows.Forms.ComboBoxStyle.DropDownList?displayProperty=nameWithType>로 설정되고 해당 컨트롤이 양식의 탭 순서에서 첫 번째 컨트롤인 경우 바로 가기를 사용하여 부모 양식을 열 때 포커스 사각형을 표시합니다. 이러한 변경 전에 키보드 포커스는 이 컨트롤에 적용되었지만 포커스 표시기가 렌더링되지 않았습니다.

**향상된 내레이터 지원**

- <xref:System.Windows.Forms.MonthCalendar> 컨트롤에서는 이전에 수행하지 못할 경우 내레이터가 컨트롤의 값을 읽는 기능을 비롯하여 컨트롤에 액세스하는 보조 기술에 대한 지원을 추가했습니다.

- 이제 <xref:System.Windows.Forms.CheckBox.CheckState?displayProperty=nameWithType> 속성이 변경된 경우 <xref:System.Windows.Forms.CheckedListBox> 컨트롤은 내레이터에게 알림을 보냅니다. 이전에는 내레이터가 알림을 수신하지 않았고 결과적으로 사용자가 <xref:System.Windows.Forms.CheckBox.CheckState> 속성이 업데이트되었음을 알지 못했습니다.
- <xref:System.Windows.Forms.LinkLabel> 컨트롤이 컨트롤에서 텍스트를 내레이터에 알리는 방식으로 변경되었습니다. 이전에는 내레이터가 이 텍스트를 두 번 공지하고, 사용자에게 표시되지 않는 경우에도 &quot;&amp;&quot; 기호를 실제 텍스트로 읽었습니다. 불필요한 &quot;&amp;&quot; 기호뿐만 아니라 중복된 텍스트도 내레이터 공지에서 제거되었습니다.
- 이제 <xref:System.Windows.Forms.DataGridViewCell> 컨트롤 형식은 내레이터에 대한 읽기 전용 상태 및 기타 보조 기술을 올바르게 보고합니다.
- 내레이터는 이제 [Multiple-Document Interface]~/docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md) 애플리케이션에서 자식 창의 시스템 메뉴를 읽을 수 있습니다.
- 이제 내레이터는 <xref:System.Windows.Forms.ToolStripItem.Enabled?displayProperty=nameWithType> 속성이 **false**로 설정된 <xref:System.Windows.Forms.ToolStripMenuItem> 컨트롤을 읽을 수 있습니다. 이전에는 내레이터가 콘텐츠를 읽기 위해 비활성화된 메뉴 항목에 초점을 맞출 수 없었습니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   | 주요함       |
| 버전 | 4.8         |
| 형식    | 대상 변경 |

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Windows.Forms.ToolStripDropDownButton.CreateAccessibilityInstance?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownAccessibleObject.Name?displayProperty=nameWithType>
- [MonthCalendar.AccessibilityObject](xref:System.Windows.Forms.Control.AccessibilityObject)
