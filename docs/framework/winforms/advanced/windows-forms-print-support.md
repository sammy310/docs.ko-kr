---
title: 인쇄 지원
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- forms [Windows Forms], printing (using designer)
- printing [Windows Forms], Windows Forms, support
- printing [Windows Forms], print support
ms.assetid: a4a2960c-eb70-48e2-b641-cfb222704e46
ms.openlocfilehash: d6e8f60db7afe2f1b04eaae6fe71aa93e5c22cae
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732497"
---
# <a name="windows-forms-print-support"></a>Windows Forms 인쇄 지원
Windows Forms 인쇄는 주로 [PrintDocument component](../controls/printdocument-component-windows-forms.md) 구성 요소를 사용 하 여 사용자가 인쇄할 수 있도록 하 고 [PrintPreviewDialog 컨트롤](../controls/printpreviewdialog-control-windows-forms.md) 컨트롤, [PrintDialog 구성](../controls/printdialog-component-windows-forms.md) 요소 및 [PageSetupDialog](../controls/pagesetupdialog-component-windows-forms.md) 구성 요소 구성 요소를 사용 하 여 Windows 운영 체제에 익숙한 사용자에 게 친숙 한 그래픽 인터페이스를 제공 하는 데 사용 됩니다.  
  
 일반적으로 <xref:System.Drawing.Printing.PrintDocument> 구성 요소의 새 인스턴스를 만들고, <xref:System.Drawing.Printing.PrinterSettings> 및 <xref:System.Drawing.Printing.PageSettings> 클래스를 사용 하 여 인쇄할 항목을 설명 하는 속성을 설정 하 고, <xref:System.Drawing.Printing.PrintDocument.Print%2A> 메서드를 호출 하 여 실제로 문서를 인쇄 합니다.  
  
 Windows 기반 응용 프로그램에서 인쇄 하는 과정에서 <xref:System.Drawing.Printing.PrintDocument> 구성 요소는 인쇄 중단 대화 상자를 표시 하 여 인쇄가 발생 하 고 인쇄 작업을 취소할 수 있음을 사용자에 게 알립니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [방법: 표준 Windows Forms 인쇄 작업 만들기](how-to-create-standard-windows-forms-print-jobs.md)  
 <xref:System.Drawing.Printing.PrintDocument> 구성 요소를 사용 하 여 Windows Form에서 인쇄 하는 방법을 설명 합니다.  
  
 [방법: 런타임에 PrintDialog에서 사용자 입력 캡처](how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 <xref:System.Windows.Forms.PrintDialog> 구성 요소를 사용 하 여 프로그래밍 방식으로 선택한 인쇄 옵션을 수정 하는 방법을 설명 합니다.  
  
 [방법: Windows Forms에서 사용자의 컴퓨터에 연결된 프린터 선택](how-to-choose-the-printers-attached-to-user-computer-in-windows-forms.md)  
 런타임에 <xref:System.Windows.Forms.PrintDialog> 구성 요소를 사용 하 여 인쇄 되도록 프린터를 변경 하는 방법을 설명 합니다.  
  
 [방법: Windows Forms의 그래픽 인쇄](how-to-print-graphics-in-windows-forms.md)  
 프린터에 그래픽을 보내는 방법을 설명 합니다.  
  
 [방법: Windows Forms에서 다중 페이지 텍스트 파일 인쇄](how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 프린터에 텍스트를 전송 하는 방법을 설명 합니다.  
  
 [방법: Windows Forms 인쇄 작업 완료](how-to-complete-windows-forms-print-jobs.md)  
 인쇄 작업이 완료 되었음을 사용자에 게 알리는 방법을 설명 합니다.  
  
 [방법: Windows Form 인쇄](how-to-print-a-windows-form.md)  
 현재 폼의 복사본을 인쇄 하는 방법을 보여 줍니다.  
  
 [방법: Windows Forms에서 인쇄 미리 보기를 사용하여 인쇄](how-to-print-in-windows-forms-using-print-preview.md)  
 문서를 인쇄 하는 데 <xref:System.Windows.Forms.PrintPreviewDialog>를 사용 하는 방법을 보여 줍니다.  
  
## <a name="related-sections"></a>관련 섹션  
 [PrintDocument 구성 요소](../controls/printdocument-component-windows-forms.md)  
 <xref:System.Drawing.Printing.PrintDocument> 구성 요소의 사용법을 설명 합니다.  
  
 [PrintDialog 구성 요소](../controls/printdialog-component-windows-forms.md)  
 <xref:System.Windows.Forms.PrintDialog> 구성 요소의 사용법을 설명 합니다.  
  
 [PrintPreviewDialog 컨트롤](../controls/printpreviewdialog-control-windows-forms.md)  
 <xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤의 사용법을 설명 합니다.  
  
 [PageSetupDialog 구성 요소](../controls/pagesetupdialog-component-windows-forms.md)  
 <xref:System.Windows.Forms.PageSetupDialog> 구성 요소의 사용법을 설명 합니다.  
  
 <xref:System.Drawing.Printing>  
 <xref:System.Drawing.Printing> 네임 스페이스의 클래스에 대해 설명 합니다.
