---
title: 내용에 맞게 레이블 컨트롤 크기 조정
ms.date: 03/30/2017
helpviewer_keywords:
- captions [Windows Forms], sizing
- sizing controls
- size [Windows Forms], controls
- labels [Windows Forms], sizing to fit contents
- Label control [Windows Forms], sizing to fit contents
ms.assetid: 99648964-63b2-438c-980e-d24103ad602b
ms.openlocfilehash: 6a563693feaa5074f5d13f0b82cc4d0305a79c23
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743777"
---
# <a name="how-to-size-a-windows-forms-label-control-to-fit-its-contents"></a>방법: 내용에 맞게 Windows Forms Label 컨트롤 크기 조정
Windows Forms <xref:System.Windows.Forms.Label> 컨트롤은 한 줄 또는 여러 줄이 될 수 있으며, 크기가 고정 되거나 자동으로 크기를 조정 하 여 캡션을 수용할 수 있습니다. <xref:System.Windows.Forms.Label.AutoSize%2A> 속성을 사용 하면 컨트롤 크기를 조정 하 여 컨트롤의 크기를 조정할 수 있으며,이는 런타임에 캡션이 변경 될 경우 특히 유용 합니다.  
  
### <a name="to-make-a-label-control-resize-dynamically-to-fit-its-contents"></a>레이블 컨트롤의 내용에 맞게 동적으로 크기를 조정 하려면  
  
1. <xref:System.Windows.Forms.Label.AutoSize%2A> 속성을 `true`로 설정 합니다.  
  
 <xref:System.Windows.Forms.Label.AutoSize%2A>을 `false`로 설정 하면 <xref:System.Windows.Forms.Label.Text%2A> 속성에 지정 된 단어가 가능한 경우 다음 줄로 줄 바꿈됩니다. 그러나 컨트롤이 확장 되지 않습니다.  
  
## <a name="see-also"></a>참조

- [방법: Windows Forms Label 컨트롤을 사용하여 선택키 만들기](how-to-create-access-keys-with-windows-forms-label-controls.md)
- [Label 컨트롤 개요](label-control-overview-windows-forms.md)
- [레이블 컨트롤](label-control-windows-forms.md)
