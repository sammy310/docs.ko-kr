---
title: PrintPreviewDialog 컨트롤 개요(Windows Forms)
ms.date: 01/08/2018
f1_keywords:
- PrintPreviewDialog
helpviewer_keywords:
- PrintPreviewDialog control (using designer), about PrintPreviewDialog
ms.assetid: efd4ee8d-6edd-47ec-88e4-4a4759bd2384
ms.openlocfilehash: 670886956e1b348895862c117ccf9cf586bde8bb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141225"
---
# <a name="printpreviewdialog-control-overview-windows-forms"></a>PrintPreviewDialog 컨트롤 개요 (Windows Forms)

Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤은 인쇄 시 [PrintDocument](printdocument-component-windows-forms.md) 표시 되는 방식을 표시 하는 데 사용 되는 미리 구성 된 대화 상자입니다. 사용자 고유의 대화 상자를 구성 하는 대신 Windows 기반 응용 프로그램 내에서 간단한 솔루션으로 사용 합니다. 컨트롤에는 인쇄, 확대, 한 페이지 또는 여러 페이지 표시 및 대화 상자 닫기 단추가 포함되어 있습니다.

## <a name="key-properties-and-methods"></a>키 속성 및 메서드

컨트롤의 키 속성은 미리 볼 문서를 설정 하는 <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>입니다. 문서는 <xref:System.Drawing.Printing.PrintDocument> 개체 여야 합니다. 대화 상자를 표시 하려면 <xref:System.Windows.Forms.Form.ShowDialog%2A> 메서드를 호출 해야 합니다. 앤티앨리어싱을 사용 하면 텍스트가 더 부드럽게 표시 될 수 있지만 더 느리게 표시 될 수도 있습니다. 이를 사용 하려면 <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> 속성을 `true`로 설정 합니다.

특정 속성은 <xref:System.Windows.Forms.PrintPreviewDialog> 포함 된 <xref:System.Windows.Forms.PrintPreviewControl>를 통해 사용할 수 있습니다. 이 <xref:System.Windows.Forms.PrintPreviewControl> 폼에 추가할 필요는 없습니다. 폼에 대화 상자를 추가할 때 <xref:System.Windows.Forms.PrintPreviewDialog>에 자동으로 포함 됩니다. <xref:System.Windows.Forms.PrintPreviewControl>를 통해 사용할 수 있는 속성의 예로는 컨트롤에서 가로 및 세로로 표시 되는 페이지 수를 결정 하는 <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> 및 <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> 속성이 있습니다. <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> 속성은 Visual Basic, 시각적 개체 C#`printPreviewDialog1.PrintPreviewControl.Columns` 또는 시각적 개체 C++`printPreviewDialog1->PrintPreviewControl->Columns`에서 `PrintPreviewDialog1.PrintPreviewControl.Columns`으로 액세스할 수 있습니다.

## <a name="printpreviewdialog-performance"></a>PrintPreviewDialog 성능

다음 조건에서는 <xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤이 매우 느리게 초기화 됩니다.

- 네트워크 프린터가 사용 됩니다.
- 이 프린터에 대 한 사용자 기본 설정 (예: 이중 설정)이 수정 되었습니다.

.NET Framework 4.5.2에서 실행 되는 앱의 경우 구성 파일의 \<appSettings > 섹션에 다음 키를 추가 하 여 <xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤 초기화의 성능을 향상 시킬 수 있습니다.

```xml
<appSettings>
   <add key="EnablePrintPreviewOptimization" value="true" />
</appSettings>
```

`EnablePrintPreviewOptimization` 키가 다른 값으로 설정 된 경우 또는 키가 없는 경우 최적화가 적용 되지 않습니다.

.NET Framework 4.6 이상 버전에서 실행 되는 앱의 경우, 앱 구성 파일의 [\<runtime >](../../configure-apps/file-schema/runtime/index.md) 섹션에서 [\<AppContextSwitchOverrides >](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 요소에 다음 스위치를 추가할 수 있습니다.

```xml
<runtime >
   <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false -->
   <AppContextSwitchOverrides value = "Switch.System.Drawing.Printing.OptimizePrintPreview=true" />
</runtime >
```

스위치가 없거나 다른 값으로 설정 된 경우에는 최적화가 적용 되지 않습니다.

<xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> 이벤트를 사용 하 여 프린터 설정을 수정 하는 경우 최적화 구성 스위치를 설정한 경우에도 <xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤의 성능이 향상 되지 않습니다.

## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.PrintPreviewDialog>
- [PrintPreviewControl 컨트롤 개요](printpreviewcontrol-control-overview-windows-forms.md)
- [PrintPreviewDialog 컨트롤](printpreviewdialog-control-windows-forms.md)
- [대화 상자 컨트롤 및 구성 요소](dialog-box-controls-and-components-windows-forms.md)
