---
title: Windows Forms 구성 요소를 추가합니다.
ms.date: 04/07/2017
helpviewer_keywords:
- Windows Forms Add configuration element
- configuring Windows Forms applications
ms.assetid: 3e3e04de-99d1-4658-b716-44cb669d9589
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 107de172e523758474bafb3b86a2960b926a010a
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57371374"
---
# <a name="windows-forms-add-configuration-element"></a>Windows Forms 구성 요소를 추가합니다.

`<add>` 요소는 Windows Form 앱.NET Framework 4.7 이상 버전의 Windows Forms 앱에 추가 된 기능을 지원 하는지 여부를 지정 하는 미리 정의 된 키를 추가 합니다.

## <a name="syntax"></a>구문

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="key-name" value="key-value" />
</System.Windows.Forms.ApplicationConfigurationSection>
```

## <a name="attributes-and-elements"></a>특성 및 요소

다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.

### <a name="attributes"></a>특성

| 특성 | 설명 |
| --------- | ----------- |
| `key`     | 필수 특성입니다. 특정 Windows Forms 사용자 지정 가능한 기능에 해당 하는 미리 정의 된 키 이름입니다. |
| `value`   | 필수 특성입니다. `key`에 할당할 값입니다. |

### <a name="key-attribute-names-and-associated-values"></a>`key` 특성 이름 및 연결 된 값

| `key` 이름 | 값 | 설명 |
| ---------- | ------ | ----------- |
| "AnchorLayout.DisableSinglePassControlScaling" | "true"&#124;"false" | 고정 된 컨트롤은 단일 패스에서 배율 조정 여부를 나타냅니다. 크기 조정, 단일을 사용 하지 않도록 설정 하려면 "true" 전달 그렇지 않으면 false입니다. "단일 확장 전달 하는 데 사용" 섹션을 참조 합니다 [주의](#Remarks) 자세한 내용은 합니다. |
| "DpiAwareness" | "PerMonitorV2"&#124;"false" | 응용 프로그램의 DPI 인식 여부를 나타냅니다. Dpi 인식;를 지원 하기 위해 "PerMonitorV2" 키를 설정 합니다. 그렇지 않으면 "false"로 설정 합니다. DPI 인식은 옵트인 기능입니다. Windows Forms의 높은 DPI 지원을 이용 하려면 "PerMonitorV2" 값을 설정 해야 합니다. 참조 된 [주의](#remarks) 자세한 내용은 섹션입니다. |
| "CheckedListBox.DisableHighDpiImprovements" | "true"&#124;"false" | 나타냅니다 여부는 <xref:System.Windows.Forms.CheckedListBox> 컨트롤은.NET Framework 4.7에서 도입 된 크기 조정 및 레이아웃 개선 사항 활용 합니다. caling 및 레이아웃 개선; 옵트아웃 하려면 "true" 그렇지 않으면, "false"입니다. |
| "DataGridView.DisableHighDpiImprovements" | "true"&#124;"false" | 나타냅니다 여부는 <xref:System.Windows.Forms.DataGridView> .NET Framework 4.7에 도입 된 크기 조정 및 레이아웃 향상 된 기능을 제어 합니다. DPI 인식; 옵트아웃 하려면 "true" "false" 그렇지 않은 경우. |
| "DisableDpiChangedMessageHandling" | "true"&#124;"false" | DPI 배율을 변경;와 관련 된 메시지 수신을 옵트아웃 하려면 "true" "false" 그렇지 않은 경우. 참조 된 [주의](#remarks) 자세한 내용은 섹션입니다. |
| "EnableWindowsFormsHighDpiAutoResizing" | "true"&#124;"false" | Windows Forms 응용 프로그램을 자동으로 DPI 배율 변경으로 인해 크기 조정 여부를 나타냅니다. 자동 크기 조정을 사용 하도록 설정 하려면 "true" 그렇지 않으면 false입니다. |
| "Form.DisableSinglePassControlScaling" | "true"&#124;"false" | 나타냅니다 여부는 <xref:System.Windows.Forms.Form> 단일 패스에서 확장 됩니다. 크기 조정, 사용 하지 않도록 설정 하려면 "true" 한 번 통과 그렇지 않으면 false입니다. "단일 확장 전달 하는 데 사용" 섹션을 참조 합니다 [주의](#Remarks) 자세한 내용은 합니다. |
| "MonthCalendar.DisableSinglePassControlScaling" | "true"&#124;"false" | 나타냅니다 여부는 <xref:System.Windows.Forms.MonthCalendar> 단일 패스에서 컨트롤의 크기가 조정 됩니다. 크기 조정, 사용 하지 않도록 설정 하려면 "true" 한 번 통과 그렇지 않으면 false입니다. "단일 확장 전달 하는 데 사용" 섹션을 참조 합니다 [주의](#Remarks) 자세한 내용은 합니다. |
| "Toolstrip.DisableHighDpiImprovements" | "true"&#124;"false" | 나타냅니다 여부는 <xref:System.Windows.Forms.ToolStrip> 컨트롤은.NET Framework 4.7에서 도입 된 크기 조정 및 레이아웃 개선 사항 활용 합니다. DPI 인식; 옵트아웃 하려면 "true" "false" 그렇지 않은 경우. |

### <a name="child-elements"></a>자식 요소

없음

### <a name="parent-elements"></a>부모 요소

| 요소 | 설명 |
| ------- | ----------- |
| [`<System.Windows.Forms.ApplicationConfigurationSection>`](../../../../../docs/framework/configure-apps/file-schema/winforms/index.md) | 새 Windows Forms 응용 프로그램 기능에 대 한 지원을 구성합니다. |

## <a name="a-nameremarks--remarks"></a><a name="remarks" /> 설명

.NET Framework 4.7부터는 `<System.Windows.Forms.ApplicationConfigurationSection>` 요소를 사용하여 Windows Forms 애플리케이션을 구성해 최신 .NET Framework 릴리스에 추가된 기능을 활용할 수 있습니다.

`<System.Windows.Forms.ApplicationConfigurationSection>` 요소를 사용 하면 하나 이상의 자식에 추가할 `<add>` 요소를 각각 특정 구성 설정을 정의 합니다.

Windows Forms의 높은 DPI 지원의 개요를 보려면 [Windows Forms의 높은 DPI 지원](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md)합니다.

### <a name="dpiawareness"></a>DpiAwareness

.NET Framework에 도입 된 높은 DPI 개선 사항을 활용 하려면.NET Framework 4.7부터 Windows 10 크리에이터 버전 및.NET Framework의 대상 버전부터 Windows 버전에서 실행 되는 Windows Forms 응용 프로그램을 구성할 수 있습니다. 4.7입니다. 여기에는 다음이 포함됩니다.

- 사용자가 변경할 DPI 또는 확장 비율을 Windows Forms 응용 프로그램을 실행 된 후 동적 DPI 시나리오를 지원 합니다.

- 와 같은 크기 조정 및 레이아웃의 다양 한 Windows Forms의 향상 된 컨트롤을 <xref:System.Windows.Forms.MonthCalendar> 컨트롤 및 <xref:System.Windows.Forms.CheckedListBox> 제어 합니다.

높은 DPI 인식은 옵트인 기능입니다. 기본적으로 값 `DpiAwareness` 는 `false`합니다. 이 키의 값을 설정 하 여 DPI 인식에 대 한 Windows Forms 지원을 선택할 수 `PerMonitorV2` 응용 프로그램 구성 파일에서입니다. DPI 인식 설정 된 경우 모든 개별 DPI 기능 활성화 됩니다. 여기에는 다음이 포함됩니다.

- DPI 변경에 의해 제어 되는 메시지는 `DisableDpiChangedMessageHandling` 키입니다.

- 동적 DPI 지원을 의해 제어 되는 `EnableWindowsFormsHighDpiAutoResizing` 키입니다.

- 단일 패스 컨트롤 크기 조정에 의해 제어 되는 `Form.DisableSinglePassControlScaling` 개인에 대 한 <xref:System.Windows.Forms.Form> 컨트롤을 여는 `AnchorLayout.DisableSinglePassControlScaling` 및 고정 된 컨트롤에 대 한 키를 `MonthCalendar.DisableSinglePassControlScaling` 키를 <xref:System.Windows.Forms.MonthCalendar> 컨트롤

- 높은 DPI 크기 조정 및 레이아웃 향상 된 기능을 제어 하는 `CheckListBox.DisableHighDpiImprovements` 키를 <xref:System.Windows.Forms.CheckedListBox> 컨트롤에서 `DataGridView.DisableHighDpiImprovements` 키를 <xref:System.Windows.Forms.DataGridView> 컨트롤 및를 `Toolstrip.DisableHighDpiImprovements` 키를 <xref:System.Windows.Forms.ToolStrip> 컨트롤입니다.

제공 하는 단일 기본 옵트인 설정을 설정 하 여 `DpiAwareness` 에 `PerMonitorV2` 새 Windows Forms 응용 프로그램에 일반적으로 적합 합니다. 그러나 옵트아웃할 수 있습니다 다음 개별 높은 DPI 향상 된 응용 프로그램 구성 파일에 해당 키를 추가 합니다. 예를 들어 동적 DPI 지원 제외 하 고 모든 새 DPI 기능을 활용 하는 다음에 추가한 응용 프로그램 구성 파일:

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
   <add key="DpiAwareness" value="PerMonitorV2" />
   <!-- Disable dynamic DPI support -->
   <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" />
</System.Windows.Forms.ApplicationConfigurationSection>
```
일반적으로 있습니다 옵트아웃 특정 기능을 프로그래밍 방식으로 처리 하도록 선택한 때문입니다.

Windows Forms 응용 프로그램의 높은 DPI 지원의 활용에 자세한 내용은 참조 하세요. [Windows Forms의 높은 DPI 지원](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md)합니다.

### <a name="disabledpichangedmessagehandling"></a>DisableDpiChangedMessageHandling

.NET Framework 4.7부터 Windows Forms 컨트롤 수를의 DPI 배율에서 변경과 관련 된 이벤트를 발생 시킵니다. 여기에 포함 된 <xref:System.Windows.Forms.Control.DpiChangedAfterParent>, <xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, 및 <xref:System.Windows.Forms.Form.DpiChanged> 이벤트. 값을 `DisableDpiChangedMessageHandling` 키는 Windows Forms 응용 프로그램에서 이러한 이벤트가 발생 하는지 여부를 결정 합니다.

### <a name="single-pass-scaling"></a>단일 패스 크기 조정

단일 또는 다중 전달 확장에 영향을 줍니다 사용자 인터페이스의 체감된 응답성 및 사용자 인터페이스 요소의 모양을으로 크기가 조정 됩니다. .NET Framework 4.7부터 Windows Forms 크기 조정 단일 패스로 사용 합니다. .NET Framework의 이전 버전에서는 크기 조정 필요 하는 것 보다 몇 가지 컨트롤 확장을 발생 하는 여러 패스를 통해 수행 되었습니다. 크기 조정 단일 패스는 사용할 수 응용 프로그램이 이전 동작에 종속 하는 경우.

## <a name="see-also"></a>참고자료

- [Windows Forms 구성 섹션](../../../../../docs/framework/configure-apps/file-schema/winforms/index.md)
- [Windows Forms의 높은 DPI 지원](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md)
