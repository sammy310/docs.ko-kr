---
title: Windows 양식 접근성 개선 사항
description: .NET 코어 Windows Forms에서 .NET 프레임워크 Windows 양식과 비교하여 접근성을 향상시키려는 방법에 대해 알아봅니다.
ms.date: 04/20/2020
helpviewer_keywords:
- Windows Forms accessibility
- accessibility
author: M-Lipin
ms.openlocfilehash: 30eb8b3bd0aaf646ea23f4f036e822f9bba78dc4
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739765"
---
# <a name="accessibility-improvements-in-windows-forms-controls-for-net-core-30"></a>.NET 코어 3.0에 대한 Windows 양식 컨트롤의 접근성 향상

Windows Forms는 Windows Forms 고객을 더 잘 지원하기 위해 내게 필요한 옵션 기술과 함께 작동하는 방식을 지속적으로 개선하고 있습니다. 개선 사항에는 다음과 같은 변경 내용이 포함됩니다.

- 내레이터를 포함하여 내게 필요한 옵션 클라이언트 응용 프로그램과의 다양한 상호 작용 영역의 변경
- 액세스 가능한 계층 구조의 변경 내용(UI Automation 트리를 통한 탐색 개선).
- 키보드 탐색의 변경 내용입니다.

> [!IMPORTANT]
> .NET Framework 4.7.1에서 .NET Framework 4.8을 통해 변경한 액세스 가능 변경 사항은 .NET Core 3.0 이상에 포함되며 기본적으로 활성화됩니다. .NET Framework는 응용 프로그램이 새 내게 필요한 옵션 동작을 옵트아웃할 수 있도록 하는 호환성 스위치를 지원했습니다. 반면 .NET Core는 이러한 설정을 지원하지 않으며 응용 프로그램이 내게 필요한 옵션 동작을 옵트아웃할 수 없습니다.
  
.NET Core 3.0부터 Windows Forms 응용 프로그램은 추가 구성 없이 모든 새로운 내게 필요한 옵션 기능(.NET Framework 4.7.1 - 4.8에 도입)의 이점을 누릴 수 있습니다.

## <a name="listbox-accessibility-support"></a>리스트박스 접근성 지원

컨트롤에는 다음 변경 <xref:System.Windows.Forms.ListBox> 사항이 적용됩니다.

- 제어를 위한 `ListBox` UI 자동화 지원 지원.
- 항목에 추가하고 `ListBox` <xref:System.Windows.Automation.ScrollItemPattern> 항목을 통해 접근성 이벤트 올리기 및 처리 및 내레이터 탐색을 향상시켜 접근성 지원을 개선했습니다(캡 잠금 탐색이 올바르지 않으며 의도치 않게 컨트롤 외부로 탐색을 던지지 않습니다). `ListBox`

## <a name="checkedlistbox-accessibility-support"></a>선택 목록상자 접근성 지원

컨트롤에는 다음 변경 <xref:System.Windows.Forms.CheckedListBox> 사항이 적용됩니다.

- 항목에 `CheckedListBox` 대한 내게 필요한 옵션 속성에서 제공하는 수정된 경계입니다.
- 전반적인 `ListBox` `CheckedListBox` 및 접근성 개선: 속성 값 및 이벤트 모델 수정.

## <a name="combobox-accessibility-support"></a>콤보박스 접근성 지원

컨트롤에는 다음 변경 <xref:System.Windows.Forms.ComboBox> 사항이 적용됩니다.

- 함수가 재정의될 경우 안전하지 않을 수 있는 항목에서 해시 코드를 가져오는 대신 항목에 대한 암호를 생성할 수 있도록 항목의 접근성 개체를 가져오는 `ComboBox` 프로세스를 <xref:System.Object.GetHashCode%2A> 업데이트했습니다.

## <a name="datagridview-accessibility-support"></a>데이터그리드뷰 접근성 지원

컨트롤에는 다음 변경 <xref:System.Windows.Forms.DataGridView> 사항이 적용됩니다.

- 열, `DataGridView.Bounds` 행, 셀 및 해당 헤더에 대한 내게 필요한 옵션 속성에서 제공하는 수정, 경계 사각형 계산의 성능 향상. 모든 접근성 경계는 뷰포트와 함께 전체 컨트롤의 경계를 고려하여 올바르게 표시됩니다.
- 액세스 `Value.IsReadOnly` 가능한 클라이언트 응용 프로그램에 대해 제공하는 속성 값을 수정했습니다. 이제 속성에 `IsReadOnly` 셀에 대 한 올바른 상태가 표시 됩니다.
- 첫 번째 <xref:System.Windows.Forms.DataGridView.CellParsing> 셀 변경에 대한 이벤트 발생 문제를 수정했습니다. 셀 값은 제1 `DataGridView` 대조군 상호작용을 포함하는 어떠한 문제도 없이 변경될 수 있다.
- Windows `DataGridView` 고대비 테마를 사용할 때 배경 색 대비가 개선되었습니다. HC#1, HC#2 및 HC 검정 테마를 사용할 때 기본 백 색상을 변경했습니다. `DataGridView`

## <a name="propertygrid-accessibility-support"></a>속성 그리드 내게 필요한 옵션 지원

컨트롤에는 다음 변경 <xref:System.Windows.Forms.PropertyGrid> 사항이 적용됩니다.

- 그리드 `PropertyGrid.Bounds` 항목에 대한 내게 필요한 옵션 속성에서 제공하는 수정, 경계 사각형 계산의 성능 향상. 지금은 모든 접근성 경계가 뷰포트와 함께 전체 컨트롤의 경계를 고려하여 올바르게 표시됩니다.
- 컨트롤 형식 이름을 포함하지 않고 컨트롤 형식 이름에 대한 이중 발표를 피하기 위해 액세스 가능한 이름 및 하위 컨트롤 설명을 수정했습니다.

## <a name="toolstrip-accessibility-support"></a>툴스트립 접근성 지원

컨트롤에는 다음 변경 <xref:System.Windows.Forms.ToolStrip> 사항이 적용됩니다.

- 을 `ToolStrip` `MenuStrip`통한 탐색이 `StatusStrip` 향상되었습니다. `ToolStrip` 시프트 탭 위쪽 화살표를 누르면 메뉴 항목을 뒤로 반복하여 아래쪽 메뉴 요소로 이동합니다. `MenuStrip`
- 'MenuItem' 대신 '메뉴'의 하위 메뉴를 만들기 위해 하위 메뉴에 대한 접근성 탐색, 수정된 메뉴 접근 형 제어 유형이 개선되었습니다. `MenuStrip`

## <a name="printpreviewcontrol-and-printpreviewdialog-accessibility-support"></a>PrintPreviewControl 및 인쇄미리보기대화언성 액세스 가능 지원

다음 변경 사항은 인쇄 컨트롤에 적용됩니다.

- 메뉴 항목을 통해 액세스 가능한 탐색(내레이터 탐색 포함)이 개선되었습니다.
- 향상된 고대비 테마 지원 및 컨트롤 요소를 더욱 대조적으로 만들었습니다.

## <a name="stringcollectioneditor-accessibility-support"></a>스트링컬렉션편집기 내게 필요한 옵션 지원

이제 Windows Forms 디자이너는 향상된 접근성 지원을 통해 문자열 컬렉션 편집기를 사용합니다.

## <a name="monthcalendar-accessibility-support-available-in-net-core-31"></a>월별 캘린더 내게 필요한 옵션 지원(.NET 코어 3.1에서 사용 가능)

컨트롤에는 다음 변경 <xref:System.Windows.Forms.MonthCalendar> 사항이 적용됩니다.

- 제어할 UI 자동화 `MonthCalendar` 서버 공급자를 추가하고 UI 자동화 그리드 패턴 및 테이블 패턴 공급자를 추가했습니다.
- Changed _table_ accessible control type to _calendar_ accessible control type for `MonthCalendar` except the case when the control has a preceding label control that defines `MonthCalendar` control accessible name, in this specific case accessible control type becomes _table_.
- 제어를 위해 선택한 `MonthCalendar` 날짜의 공지가 개선되었습니다.
- 화면 `MonthCalendar` 판독기 및 기타 내게 필요한 옵션 도구에 대한 향상된 제어 지원. 이 시점에서 사용자는 컨트롤 요소를 탐색하고 키보드 전용 입력을 사용하여 이러한 요소와 상호 작용할 수 있습니다. 내레이터를 사용하면 CAPS + 화살표 키를 사용하여 컨트롤 요소를 탐색하고 CAPS + Enter를 사용하여 요소 기본 작업을 호출합니다.
- 내레이터의 파란색 `MonthCalendar` 초점 사각형인 포커스 사각형이 있는 자식 요소 에서 화살표 키 탐색이 개선되었습니다.
- 제공된 좌표로 자식 액세스 요소를 `MonthCalendar` 얻을 수 있도록 컨트롤 요소에 대한 적중 테스트 작업에 대한 `MonthCalendar` 접근성이 향상되었습니다.

## <a name="tooltips-accessibility-available-in-net-core-31"></a>도구 팁 내게 필요한 옵션(.NET 코어 3.1에서 사용 가능)

- NVDA 및 내레이터와 같은 화면 판독기 응용 프로그램에서 도구 설명 텍스트를 발표할 수 있는 기능이 추가되었습니다. 이제 화면 판독기 응용 프로그램은 도구 설명팁을 표시하도록 구성된 Windows Forms 컨트롤의 키보드 또는 마우스 도구 설명의 텍스트를 발표할 수 있습니다.

## <a name="ui-automation-support-for-datagridview-propertygrid-listbox-combobox-toolstrip-and-other-controls"></a>DataGridView, 속성 그리드, 리스트 박스, 콤보 박스, 도구 스트립 및 기타 컨트롤에 대한 UI 자동화 지원

UI 자동화 지원은 런타임에 컨트롤에 사용할 수 있지만 디자인 타임에는 사용되지 않습니다. UI 자동화 개요는 [UI Automation 개요](https://docs.microsoft.com/dotnet/framework/ui-automation/ui-automation-overview)를 참조하세요.

## <a name="see-also"></a>참고 항목

- [내게 필요한 옵션 모범 사례.](../ui-automation/accessibility-best-practices.md)
