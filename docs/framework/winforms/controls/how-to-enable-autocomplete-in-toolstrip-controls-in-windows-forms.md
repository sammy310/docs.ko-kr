---
title: '방법: ToolStrip 컨트롤에 자동 완성 기능 활성화'
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
ms.openlocfilehash: 18b17aaea9d2354c03bb43f3fdd8d3779697cf58
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142020"
---
# <a name="how-to-enable-autocomplete-in-toolstrip-controls-in-windows-forms"></a>방법: Windows Forms의 ToolStrip 컨트롤에 자동 완성 기능 활성화
다음 절차는 최근에 <xref:System.Windows.Forms.ToolStripLabel> 방문한 <xref:System.Windows.Forms.ToolStripComboBox> 웹 사이트와 같은 항목 목록을 표시하기 위해 삭제할 수 있는 a와 결합합니다. 사용자가 목록의 항목 중 하나의 첫 번째 문자와 일치하는 문자를 입력하면 항목이 즉시 표시됩니다.  
  
> [!NOTE]
> 자동 완성은 `ToolStrip` <xref:System.Windows.Forms.ComboBox> 와 같은 기존 컨트롤과 동일한 방식으로 <xref:System.Windows.Forms.TextBox>컨트롤과 함께 작동합니다.  
  
### <a name="to-enable-autocomplete-in-a-toolstrip-control"></a>도구 스트립 컨트롤에서 자동 완성을 사용하려면  
  
1. 컨트롤을 <xref:System.Windows.Forms.ToolStrip> 만들고 컨트롤에 항목을 추가합니다.  
  
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
  
2. 양식의 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> 크기에 관계없이 목록을 항상 사용할 <xref:System.Windows.Forms.ToolStripItemOverflow.Never> 수 있도록 레이블및 콤보 상자의 속성을 설정합니다.  
  
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
  
3. 컨트롤의 Items 컬렉션에 <xref:System.Windows.Forms.ToolStripComboBox> 단어를 추가합니다.  
  
    ```vb  
    ToolStripComboBox1.Items.AddRange(New Object() {"First Item", _  
        "Second Item", "Third Item"})  
    ```  
  
    ```csharp  
    toolStripComboBox1.Items.AddRange(new object[] {"First item", "Second item", "Third item"});  
    ```  
  
4. 콤보 <xref:System.Windows.Forms.ComboBox.AutoCompleteMode%2A> 상자의 속성을 <xref:System.Windows.Forms.AutoCompleteMode.Append>으로 설정합니다.  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteMode = _  
        System.Windows.Forms.AutoCompleteMode.Append  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteMode = System.Windows.Forms.AutoCompleteMode.Append;  
    ```  
  
5. 콤보 <xref:System.Windows.Forms.ComboBox.AutoCompleteSource%2A> 상자의 속성을 <xref:System.Windows.Forms.AutoCompleteSource.ListItems>으로 설정합니다.  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteSource = _  
        System.Windows.Forms.AutoCompleteSource.ListItems  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteSource = System.Windows.Forms.AutoCompleteSource.ListItems;  
    ```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripLabel>
- <xref:System.Windows.Forms.ToolStripComboBox>
- <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteMode%2A>
- <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteSource%2A>
- [ToolStrip 컨트롤 개요](toolstrip-control-overview-windows-forms.md)
- [ToolStrip 컨트롤 아키텍처](toolstrip-control-architecture.md)
- [ToolStrip 기술 요약](toolstrip-technology-summary.md)
