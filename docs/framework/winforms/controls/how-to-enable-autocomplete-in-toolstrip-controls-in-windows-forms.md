---
title: '방법: Windows Forms의 ToolStrip 컨트롤에 자동 완성 기능 활성화'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- AutoComplete [Windows Forms], examples
- toolbars [Windows Forms], AutoComplete
- examples [Windows Forms], toolbars
- AutoComplete [Windows Forms], enabling in toolbars
- ToolStripComboBox class [Windows Forms], examples
- ToolStrip control [Windows Forms], AutoComplete
ms.assetid: fd66d085-1af1-45d4-930a-cde944da2e16
ms.openlocfilehash: d7919bf87444ef6c4a64ee236356e762da14853f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59307901"
---
# <a name="how-to-enable-autocomplete-in-toolstrip-controls-in-windows-forms"></a>방법: Windows Forms의 ToolStrip 컨트롤에 자동 완성 기능 활성화
다음 절차를 결합 한 <xref:System.Windows.Forms.ToolStripLabel> 사용 하 여를 <xref:System.Windows.Forms.ToolStripComboBox> 는 삭제할 수 있습니다 표시할 항목의 목록을 같은 최근에 방문한 웹 사이트. 목록의 항목 중 첫 번째 문자를 일치 하는 문자를 입력 하는 경우 항목이 즉시 표시 됩니다.  
  
> [!NOTE]
>  자동 완성이 작동 `ToolStrip` 컨트롤 같은 일반적인 컨트롤에서 작동 하는 동일한 방식 <xref:System.Windows.Forms.ComboBox> 고 <xref:System.Windows.Forms.TextBox>입니다.  
  
### <a name="to-enable-autocomplete-in-a-toolstrip-control"></a>ToolStrip 컨트롤의 자동 완성을 사용 하도록 설정 하려면  
  
1. 만들기는 <xref:System.Windows.Forms.ToolStrip> 제어 하 고 항목을 추가 합니다.  
  
    ```vb  
    ToolStrip1 = New System.Windows.Forms.ToolStrip  
    ToolStrip1.Items.AddRange(New System.Windows.Forms.ToolStripItem()_  
        {ToolStripLabel1, ToolStripComboBox1})  
    ```  
  
    ```csharp  
    toolStrip1 = new System.Windows.Forms.ToolStrip();  
    toolStrip1.Items.AddRange(new System.Windows.Forms.ToolStripItem[]   
        {toolStripLabel1, toolStripComboBox1});  
    ```  
  
2. 설정 된 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> 레이블과 콤보 상자는 속성 <xref:System.Windows.Forms.ToolStripItemOverflow.Never> 목록은 항상 폼의 크기에 관계 없이 사용할 수 있도록 합니다.  
  
    ```vb  
    ToolStripLabel1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    ToolStripComboBox1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    ```  
  
    ```csharp  
    toolStripLabel1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    toolStripComboBox1.Overflow = System.Windows.Forms.ToolStripItemOverflow.Never  
    ```  
  
3. 단어의 Items 컬렉션에 추가 된 <xref:System.Windows.Forms.ToolStripComboBox> 제어 합니다.  
  
    ```vb  
    ToolStripComboBox1.Items.AddRange(New Object() {"First Item", _  
        "Second Item", "Third Item"})  
    ```  
  
    ```csharp  
    toolStripComboBox1.Items.AddRange(new object[] {"First item", "Second item", "Third item"});  
    ```  
  
4. 설정 된 <xref:System.Windows.Forms.ComboBox.AutoCompleteMode%2A> 콤보 상자의 속성 <xref:System.Windows.Forms.AutoCompleteMode.Append>합니다.  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteMode = _  
        System.Windows.Forms.AutoCompleteMode.Append  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteMode = System.Windows.Forms.AutoCompleteMode.Append;  
    ```  
  
5. 설정 된 <xref:System.Windows.Forms.ComboBox.AutoCompleteSource%2A> 콤보 상자의 속성 <xref:System.Windows.Forms.AutoCompleteSource.ListItems>합니다.  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteSource = _  
        System.Windows.Forms.AutoCompleteSource.ListItems  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteSource = System.Windows.Forms.AutoCompleteSource.ListItems;  
    ```  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripLabel>
- <xref:System.Windows.Forms.ToolStripComboBox>
- <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteMode%2A>
- <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteSource%2A>
- [ToolStrip 컨트롤 개요](toolstrip-control-overview-windows-forms.md)
- [ToolStrip 컨트롤 아키텍처](toolstrip-control-architecture.md)
- [ToolStrip 기술 요약](toolstrip-technology-summary.md)
