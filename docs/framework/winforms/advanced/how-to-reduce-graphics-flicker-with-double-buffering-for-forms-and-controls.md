---
title: '방법: 양식과 컨트롤에 이중 버퍼링을 사용하여 그래픽 깜빡임 줄이기'
description: Windows Forms에 대 한 이중 버퍼링을 사용 하 여 그래픽 깜박임을 줄이고 그리기 작업과 관련 된 깜빡임 문제를 해결 하는 컨트롤을 사용 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing double-buffered flicker
ms.assetid: 91083d3a-653f-4f15-a467-0f37b2aa39d6
ms.openlocfilehash: f7c0425729f8a1a780124621788a1c49e06e0c4e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618131"
---
# <a name="how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls"></a>방법: 양식과 컨트롤에 이중 버퍼링을 사용하여 그래픽 깜빡임 줄이기
이중 버퍼링은 메모리 버퍼를 사용하여 여러 그리기 작업과 관련된 깜박임 문제를 해결합니다. 이중 버퍼링을 사용하면 모든 그리기 작업이 그리기 화면 대신 메모리 버퍼에 먼저 렌더링됩니다. 모든 그리기 작업이 완료되면 메모리 버퍼가 연결된 그리기 화면에 직접 복사됩니다. 화면에서 하나의 그래픽 작업만 수행 되므로 복잡 한 그리기 작업과 관련 된 이미지 깜박임이 제거 됩니다. 대부분의 응용 프로그램에서는 .NET Framework에서 제공 하는 기본 이중 버퍼링이 최상의 결과를 제공 합니다. 표준 Windows Forms 컨트롤은 기본적으로 이중 버퍼링 됩니다. 두 가지 방법으로 양식 및 제작 컨트롤에서 기본 이중 버퍼링을 사용 하도록 설정할 수 있습니다. <xref:System.Windows.Forms.Control.DoubleBuffered%2A>속성을로 설정 `true` 하거나, 메서드를 호출 하 여 플래그를 <xref:System.Windows.Forms.Control.SetStyle%2A> 로 설정할 수 있습니다 <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> `true` . 두 방법 모두 폼 이나 컨트롤에 대해 기본 이중 버퍼링을 사용 하 고 깜빡임 없는 그래픽 렌더링을 제공 합니다. <xref:System.Windows.Forms.Control.SetStyle%2A>모든 렌더링 코드를 작성 한 사용자 지정 컨트롤에만 메서드를 호출 하는 것이 좋습니다.  
  
 애니메이션 또는 고급 메모리 관리와 같은 고급 이중 버퍼링 시나리오의 경우 사용자 고유의 이중 버퍼링 논리를 구현할 수 있습니다. 자세한 내용은 [방법: 버퍼링 된 그래픽 수동 관리](how-to-manually-manage-buffered-graphics.md)를 참조 하세요.  
  
### <a name="to-reduce-flicker"></a>깜박임을 줄이려면  
  
- <xref:System.Windows.Forms.Control.DoubleBuffered%2A> 속성을 `true`으로 설정합니다.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#31)]  
  
 \- 또는 -  
  
- 메서드를 호출 <xref:System.Windows.Forms.Control.SetStyle%2A> 하 여 플래그를 <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> 로 설정 `true` 합니다.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#32)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#32)]  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.Control.DoubleBuffered%2A>
- <xref:System.Windows.Forms.Control.SetStyle%2A>
- [이중 버퍼링 그래픽](double-buffered-graphics.md)
- [Windows Forms의 그래픽 및 그리기](graphics-and-drawing-in-windows-forms.md)
