---
title: ComboBox 또는 ListBox 컨트롤을 데이터에 바인딩
description: Windows Forms ComboBox 및 ListBox를 데이터에 바인딩하는 방법에 대해 설명 하 여 데이터베이스에서 데이터를 검색 하거나, 새 데이터를 입력 하거나, 기존 데이터를 편집 하는 등의 작업을 수행 합니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [Windows Forms], binding to controls
- list boxes [Windows Forms], data binding
- ComboBox control [Windows Forms], data binding
- data binding [Windows Forms], combo boxes
- ListBox control [Windows Forms], data binding
- combo boxes [Windows Forms], data binding
- bound controls [Windows Forms], combo boxes
- Windows Forms controls, data binding
- data-bound controls [Windows Forms], Windows Forms
ms.assetid: dfd7f081-8bea-4a41-86a3-86a1934828ef
ms.openlocfilehash: 0c07dc90ddc91061c5f34b5a237082cb444e89d9
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324070"
---
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a>방법: 데이터에 Windows Forms ComboBox 또는 ListBox 컨트롤 바인딩
<xref:System.Windows.Forms.ComboBox>및를 <xref:System.Windows.Forms.ListBox> 데이터에 바인딩하여 데이터베이스의 데이터 검색, 새 데이터 입력, 기존 데이터 편집 등의 작업을 수행할 수 있습니다.  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a>ComboBox 또는 ListBox 컨트롤을 바인딩하려면  
  
1. 속성을 `DataSource` 데이터 원본 개체로 설정 합니다. 가능한 데이터 원본에는 <xref:System.Windows.Forms.BindingSource> 데이터에 바인딩된 데이터, 데이터 테이블, 데이터 뷰, 데이터 집합, 데이터 뷰 관리자, 배열 또는 인터페이스를 구현 하는 클래스가 포함 됩니다 <xref:System.Collections.IList> . 자세한 내용은 [Windows Forms에서 지 원하는 데이터 원본](../data-sources-supported-by-windows-forms.md)을 참조 하세요.  
  
2. 테이블에 바인딩하는 경우 `DisplayMember` 속성을 데이터 원본의 열 이름으로 설정 합니다.  
  
     \- 또는 -  
  
     에 바인딩하는 경우 <xref:System.Collections.IList> 표시 멤버를 목록에 있는 형식의 public 속성으로 설정 합니다.  
  
    ```vb  
    Private Sub BindComboBox()  
      ComboBox1.DataSource = DataSet1.Tables("Suppliers")  
      ComboBox1.DisplayMember = "ProductName"  
    End Sub  
    ```  
  
    ```csharp  
    private void BindComboBox()  
    {  
      comboBox1.DataSource = dataSet1.Tables["Suppliers"];  
      comboBox1.DisplayMember = "ProductName";  
    }  
    ```  
  
    > [!NOTE]
    > 인터페이스를 구현 하지 않는 데이터 소스 (예:)에 바인딩되는 경우 <xref:System.ComponentModel.IBindingList> <xref:System.Collections.ArrayList> 데이터 소스가 업데이트 될 때 바인딩된 컨트롤의 데이터가 업데이트 되지 않습니다. 예를 들어에 바인딩된 콤보 상자가 있고 데이터를에 추가 하는 경우 <xref:System.Collections.ArrayList> <xref:System.Collections.ArrayList> 이러한 새 항목은 콤보 상자에 표시 되지 않습니다. 그러나 <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> 컨트롤이 바인딩되는 클래스의 인스턴스에서 및 메서드를 호출 하 여 콤보 상자를 강제로 업데이트할 수 있습니다 <xref:System.Windows.Forms.BindingContext> .  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [Windows Forms 데이터 바인딩](../windows-forms-data-binding.md)
- [데이터 바인딩 및 Windows Forms](../data-binding-and-windows-forms.md)
- [옵션 목록 표시에 사용하는 Windows Forms 컨트롤](windows-forms-controls-used-to-list-options.md)
