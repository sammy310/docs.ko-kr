---
title: '방법: 인쇄 대화 상자 호출'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- invoking print dialogs [WPF]
- print dialogs [WPF], invoking
ms.assetid: e3a2c84c-74fe-45a4-8501-5813f9dbfed2
ms.openlocfilehash: 2ced508eb83e2955fdcd1ad87fb6415e2052446f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59206046"
---
# <a name="how-to-invoke-a-print-dialog"></a>방법: 인쇄 대화 상자 호출
응용 프로그램에서 인쇄 하는 기능을 제공 하려면 있습니다 단순히 만들고 열 수는 <xref:System.Windows.Controls.PrintDialog> 개체입니다.  
  
## <a name="example"></a>예제  
 <xref:System.Windows.Controls.PrintDialog> 컨트롤은 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], 구성 및 [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] 작업 제출을 위한 단일 진입점을 제공합니다. 컨트롤을 쉽게 사용 하 고 사용 하 여 인스턴스화할 수 있습니다 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 태그나 코드입니다. 다음 예제에서는 인스턴스화하고 코드에서 컨트롤을 열고 방법에서 인쇄 하는 방법을 보여 줍니다. 또한는 대화 상자는 사용자에 게 제공 페이지의 특정 범위를 설정 하는 옵션을 확인 하는 방법을 보여 줍니다. 예제 코드를 c: 드라이브의 루트에 있는 파일 FixedDocumentSequence.xps 있다고 가정 합니다.  
  
 [!code-csharp[printdialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintDialog/CSharp/Window1.xaml.cs#1)]
 [!code-vb[printdialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintDialog/visualbasic/window1.xaml.vb#1)]  
  
 대화 상자를 연 후 사용자가 자신의 컴퓨터에 설치 된 프린터 중에서 선택할 수 있게 됩니다. 옵션을 선택 하는 단위도 합니다 [Microsoft XPS Document Writer](https://go.microsoft.com/fwlink/?LinkId=147319) 만들려면는 [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] 인쇄 하는 대신 파일.  
  
> [!NOTE]
>  합니다 <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> 제어 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)],이 항목에서 설명 하는 혼동 하지는 <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> Windows Forms 구성 요소입니다.  
  
 엄격히 말해, 사용할 수 있습니다는 <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> 적이 대화 상자를 열지 않고 메서드. 이런 의미에서 컨트롤이 보이지 않는 인쇄 구성 요소로 사용할 수 있습니다. 하지만 성능상의 이유로 사용 하 여 더 나은 것은 <xref:System.Printing.PrintQueue.AddJob%2A> 메서드 또는 다양 한 <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> 및 <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> 의 메서드는 <xref:System.Windows.Xps.XpsDocumentWriter>합니다. 이 대 한 자세한 내용은 참조 하세요 [프로그래밍 방식으로 XPS 파일 인쇄](how-to-programmatically-print-xps-files.md) 및 합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Controls.PrintDialog>
- [WPF의 문서](documents-in-wpf.md)
- [인쇄 개요](printing-overview.md)
- [Microsoft XPS Document Writer](https://go.microsoft.com/fwlink/?LinkId=147319)
