---
title: PrintDialog 구성 요소 개요
ms.date: 03/30/2017
f1_keywords:
- PrintDialog
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], about PrintDialog component
ms.assetid: 8327b8ac-1017-4b5e-a88b-fea9dd56999c
ms.openlocfilehash: 0ed7f7a1f9770f71b75ae744a056b6943335c852
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728673"
---
# <a name="printdialog-component-overview-windows-forms"></a>PrintDialog 구성 요소 개요(Windows Forms)

Windows Forms [PrintDialog](printdialog-component-windows-forms.md) 구성 요소는 프린터를 선택 하 고, 인쇄할 페이지를 선택 하 고, Windows 기반 응용 프로그램에서 다른 인쇄 관련 설정을 결정 하는 데 사용 되는 미리 구성 된 대화 상자입니다. 고유한 대화 상자를 구성하는 대신 이 대화 상자를 프린터 및 인쇄 관련 설정 선택을 위한 간단한 솔루션으로 사용합니다. 사용자가 문서를 모두 인쇄 하거나 선택한 페이지 범위를 인쇄 하거나 선택 항목을 인쇄할 수 있도록 설정할 수 있습니다. 표준 Windows 대화 상자를 사용하여 기본 기능이 사용자에게 익숙한 애플리케이션을 만듭니다. <xref:System.Windows.Forms.PrintDialog> 구성 요소는 <xref:System.Windows.Forms.CommonDialog> 클래스에서 상속 됩니다.

## <a name="working-with-the-component"></a>구성 요소 작업

런타임에 대화 상자를 표시 하려면 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 메서드를 사용 합니다. 이 구성 요소에는 단일 인쇄 작업 (<xref:System.Drawing.Printing.PrintDocument> 클래스) 또는 개별 프린터의 설정 (<xref:System.Drawing.Printing.PrinterSettings> 클래스)과 관련 된 속성이 있습니다. 그 중 하나는 여러 프린터에서 공유 될 수 있습니다.

폼에 추가 되 면 <xref:System.Windows.Forms.PrintDialog> 구성 요소가 Visual Studio의 Windows Forms 디자이너 아래쪽에 있는 트레이에 표시 됩니다.

## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.PrintDialog>
- [PrintDialog 구성 요소](printdialog-component-windows-forms.md)
