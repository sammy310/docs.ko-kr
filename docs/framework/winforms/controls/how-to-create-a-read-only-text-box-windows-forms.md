---
title: '방법: 읽기 전용 텍스트 상자 (Windows Forms) 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 72dc188993474ad4b39f0cfa74cadffdb99ff46f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61746874"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a>방법: 읽기 전용 텍스트 상자 (Windows Forms) 만들기
읽기 전용 컨트롤에 편집 가능한 Windows Forms 텍스트 상자에 변환할 수 있습니다. 예를 들어, 텍스트 상자는 일반적으로 편집 되지만 아닐 현재 응용 프로그램의 상태로 인해 하는 값을 표시할 수 있습니다.  
  
### <a name="to-create-a-read-only-text-box"></a>읽기 전용 텍스트 상자를 만들려면  
  
1. 설정 된 <xref:System.Windows.Forms.TextBox> 컨트롤의 <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> 속성을 `true`입니다. 속성 집합을 사용 하 여 `true`, 사용자가 여전히 스크롤 및 변경을 허용 하지 않고 텍스트 상자에 텍스트를 강조 표시 합니다. **복사본** 명령은 텍스트 상자에서 작동 하지만 **잘라내기** 하 고 **붙여넣기** 명령을 가져오지 않습니다.  
  
    > [!NOTE]
    >  <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> 속성이 런타임 시 사용자 상호 작용에만 영향을 줍니다. 여전히 바꾸면 텍스트 상자의 내용을 프로그래밍 방식으로 런타임에 변경 하 여는 <xref:System.Windows.Forms.TextBox.Text%2A> 입력란의 속성입니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.TextBox>
- [TextBox 컨트롤 개요](textbox-control-overview-windows-forms.md)
- [방법: Windows Forms TextBox 컨트롤의 삽입 지점 제어](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [방법: Windows Forms TextBox 컨트롤을 사용 하 여 암호 텍스트 상자 만들기](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [방법: 문자열에 인용 부호 넣기](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [방법: Windows Forms TextBox 컨트롤에서 텍스트를 선택 합니다.](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [방법: Windows Forms TextBox 컨트롤에서 여러 줄 보기](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [TextBox 컨트롤](textbox-control-windows-forms.md)
