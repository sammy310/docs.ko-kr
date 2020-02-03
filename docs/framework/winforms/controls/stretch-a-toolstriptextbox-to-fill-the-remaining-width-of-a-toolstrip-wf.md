---
title: '방법: ToolStripTextBox를 늘려 ToolStrip의 나머지 너비 채우기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text boxes [Windows Forms], stretching in ToolStrip control [Windows Forms]
- ToolStrip control [Windows Forms], stretching a text box
ms.assetid: 0e610fbf-85fe-414c-900c-9704a5dd5cc6
ms.openlocfilehash: c60cc2a377f08a73159f25b2ab5f2812d41f0c10
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742847"
---
# <a name="how-to-stretch-a-toolstriptextbox-to-fill-the-remaining-width-of-a-toolstrip-windows-forms"></a>방법: ToolStripTextBox를 늘려 ToolStrip의 나머지 너비 채우기(Windows Forms)
<xref:System.Windows.Forms.ToolStrip> 컨트롤의 <xref:System.Windows.Forms.ToolStrip.Stretch%2A> 속성을 `true`로 설정 하는 경우 컨트롤은 해당 컨테이너를 끝에서 끝까지 채우고 컨테이너의 크기가 조정 될 때 크기를 조정 합니다. 이 구성에서는 <xref:System.Windows.Forms.ToolStripTextBox>와 같은 컨트롤의 항목을 확장 하 여 사용 가능한 공간을 채우고 컨트롤의 크기를 조정할 때 크기를 조정 하는 것이 유용할 수 있습니다. 예를 들어이 확장은 Microsoft® Internet Explorer의 주소 표시줄과 비슷한 모양 및 동작을 수행 하려는 경우에 유용 합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 `ToolStripSpringTextBox`이라는 <xref:System.Windows.Forms.ToolStripTextBox>에서 파생 된 클래스를 제공 합니다. 이 클래스는 <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> 메서드를 재정의 하 여 다른 모든 항목의 전체 너비를 뺀 후의 부모 <xref:System.Windows.Forms.ToolStrip> 컨트롤의 사용 가능한 너비를 계산 합니다. 이 코드 예제에서는 <xref:System.Windows.Forms.Form> 클래스 및 `Program` 클래스를 제공 하 여 새 동작을 보여 줍니다.  
  
 [!code-csharp[ToolStripSpringTextBox#00](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripSpringTextBox/cs/ToolStripSpringTextBox.cs#00)]
 [!code-vb[ToolStripSpringTextBox#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripSpringTextBox/vb/ToolStripSpringTextBox.vb#00)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
- System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.Stretch%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripTextBox>
- <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A?displayProperty=nameWithType>
- [ToolStrip 컨트롤 아키텍처](toolstrip-control-architecture.md)
- [방법: StatusStrip에서 대화형으로 Spring 속성 사용](how-to-use-the-spring-property-interactively-in-a-statusstrip.md)
