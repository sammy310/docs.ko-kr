---
title: Windows Forms 관련 호환성이 손상되는 변경
description: .NET Core용 Windows Forms 관련 호환성이 손상되는 변경 목록입니다.
ms.date: 01/08/2020
ms.openlocfilehash: 75d369c7fb999da81a50fe46716e125c3840eb7a
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158439"
---
# <a name="breaking-changes-in-windows-forms"></a>Windows Forms 관련 호환성이 손상되는 변경

Windows Forms 지원이 버전 3.0의 .NET Core에 추가되었습니다. 이 문서에서는 Windows Forms의 주요 변경 사항이 .NET Core 버전이 도입된 순서대로 표시됩니다. .NET Framework 또는 이전 버전의 .NET Core(3.0 이상)에서 Windows Forms 앱을 업그레이드하는 경우 이 문서가 적용됩니다.

이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.

| 주요 변경 내용 | 도입된 버전 |
| - | :-: |
| [상태 표시줄 컨트롤 제거](#removed-status-bar-controls) | 5.0 |
| [WinForms 메서드는 이제 ArgumentException을 throw함](#winforms-methods-now-throw-argumentexception) | 5.0 |
| [WinForms 메서드는 이제 ArgumentNullException을 throw함](#winforms-methods-now-throw-argumentnullexception) | 5.0 |
| [제거된 컨트롤](#removed-controls) | 3.1 |
| [도구 설명이 표시되면 CellFormatting 이벤트가 발생하지 않음](#cellformatting-event-not-raised-if-tooltip-is-shown) | 3.1 |
| [Control.DefaultFont가 맑은 고딕 9pt로 변경됨](#default-control-font-changed-to-segoe-ui-9-pt) | 3.0 |
| [FolderBrowserDialog의 현대화](#modernization-of-the-folderbrowserdialog) | 3.0 |
| [일부 Windows Forms 형식에서 SerializableAttribute 제거됨](#serializableattribute-removed-from-some-windows-forms-types) | 3.0 |
| [AllowUpdateChildControlIndexForTabControls 호환성 스위치가 지원되지 않음](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported) | 3.0 |
| [DomainUpDown.UseLegacyScrolling 호환성 스위치가 지원되지 않음](#domainupdownuselegacyscrolling-compatibility-switch-not-supported) | 3.0 |
| [DoNotLoadLatestRichEditControl 호환성 스위치가 지원되지 않음](#donotloadlatestricheditcontrol-compatibility-switch-not-supported) | 3.0 |
| [DoNotSupportSelectAllShortcutInMultilineTextBox 호환성 스위치가 지원되지 않음](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported) | 3.0 |
| [DontSupportReentrantFilterMessage 호환성 스위치가 지원되지 않음](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported) | 3.0 |
| [EnableVisualStyleValidation 호환성 스위치가 지원되지 않음](#enablevisualstylevalidation-compatibility-switch-not-supported) | 3.0 |
| [UseLegacyContextMenuStripSourceControlValue 호환성 스위치가 지원되지 않음](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported) | 3.0 |
| [UseLegacyImages 호환성 스위치가 지원되지 않음](#uselegacyimages-compatibility-switch-not-supported) | 3.0 |
| [AccessibleObject.RuntimeIDFirstItem에 대한 액세스 변경](#change-of-access-for-accessibleobjectruntimeidfirstitem) | 3.0 |
| [Windows Forms에서 중복된 API가 제거되었습니다.](#duplicated-apis-removed-from-windows-forms) | 3.0 |

## <a name="net-50"></a>.NET 5.0

[!INCLUDE [winforms-deprecated-controls](../../../includes/core-changes/windowsforms/5.0/winforms-deprecated-controls.md)]

***

[!INCLUDE [invalid-args-cause-argumentexception](../../../includes/core-changes/windowsforms/5.0/invalid-args-cause-argumentexception.md)]

***

[!INCLUDE [null-args-cause-argumentnullexception](../../../includes/core-changes/windowsforms/5.0/null-args-cause-argumentnullexception.md)]

***

## <a name="net-core-31"></a>.NET Core 3.1

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

## <a name="net-core-30"></a>.NET Core 3.0

[!INCLUDE[Control.DefaultFont changed to Segoe UI 9pt](~/includes/core-changes/windowsforms/3.0/control-defaultfont-changed.md)]

***

[!INCLUDE[Modernization of the FolderBrowserDialog](~/includes/core-changes/windowsforms/3.0/modernized-folderbrowserdialog.md)]

***

[!INCLUDE[SerializableAttribute removed from some Windows Forms types](~/includes/core-changes/windowsforms/3.0/remove-serializationattribute.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-allowupdatechildcontrolindexfortabcontrols.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyscrolling.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotloadlatestricheditcontrol.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotsupportselectallshortcutinmultilinetextbox.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DontSupportReentrantFilterMessage compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-dontsupportreentrantfiltermessage.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.EnableVisualStyleValidation compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-enablevisualstylevalidation.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacycontextmenustripsourcecontrolvalue.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyImages compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyimages.md)]

***

[!INCLUDE[Change of access for AccessibleObject.RuntimeIDFirstItem](~/includes/core-changes/windowsforms/3.0/changed-access-for-runtimeidfirstitem.md)]

***

[!INCLUDE[Duplicated APIs removed from Windows Forms](~/includes/core-changes/windowsforms/3.0/remove-duplicated-apis.md)]

***

## <a name="see-also"></a>참조

- [.NET Core에 Windows Forms 앱 포팅](../porting/winforms.md)
