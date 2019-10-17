---
title: '방법: 데이터를 입력할 수 있는 크기 조정 가능한 Windows Form 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- layout [Windows Forms], resizing
- forms [Windows Forms], creating resizable
- Windows Forms, resizable
ms.assetid: babdf198-404c-485d-a914-ed370c6ecd99
ms.openlocfilehash: aeab1b506b9ded4c3c2ab527f07a8655a44cad2b
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72396017"
---
# <a name="how-to-create-a-resizable-windows-form-for-data-entry"></a>방법: 데이터를 입력할 수 있는 크기 조정 가능한 Windows Form 만들기
좋은 레이아웃은 부모 폼의 크기 변경에 제대로 대응합니다. <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 통해 폼의 레이아웃을 정렬하면 폼 크기가 변경될 때 일관된 방식으로 컨트롤의 크기를 조정하고 배치할 수 있습니다. <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤은 컨트롤의 콘텐츠 변경으로 인해 레이아웃이 변경되는 경우에도 유용합니다. 이 절차에서 설명하는 프로세스는 Visual Studio 환경 내에서 수행할 수 있습니다.  또한 [연습: 데이터를 입력할 수 있는 크기 조정 가능한 Windows Form 만들기](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))를 참조하세요.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 통해 사용자가 폼 크기를 조정할 때 제대로 대응하는 레이아웃을 작성하는 방법을 보여 줍니다. 또한 지역화에 제대로 대응하는 레이아웃을 보여 줍니다.  
  
 [!code-cpp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/cpp/basicdataentryform.cpp#1)]
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/CS/basicdataentryform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/VB/basicdataentryform.vb#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
- System, System.Data, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [방법: TableLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [방법: 지역화에 적합한 Windows Forms 레이아웃 디자인](how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)
