---
title: '방법: Windows Forms BindingNavigator 컨트롤에 로드, 저장 및 취소 단추 추가'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], manipulating
- BindingNavigator control [Windows Forms], adding buttons
ms.assetid: faa33042-186e-4bb2-8798-17ceb987ec62
ms.openlocfilehash: 4d5cc91ca8bf71b2d5893f591652d777041e1a4d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757375"
---
# <a name="how-to-add-load-save-and-cancel-buttons-to-the-windows-forms-bindingnavigator-control"></a>방법: Windows Forms BindingNavigator 컨트롤에 로드, 저장 및 취소 단추 추가
합니다 <xref:System.Windows.Forms.BindingNavigator> 컨트롤은 특수 한 용도의 <xref:System.Windows.Forms.ToolStrip> 컨트롤 이동 및 데이터에 바인딩된 폼의 컨트롤을 조작 하기 위한 것입니다.  
  
 이기 때문에 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 <xref:System.Windows.Forms.BindingNavigator> 구성 요소는 사용자에 대 한 추가 또는 대체 명령 포함 하도록 쉽게 수정할 수 있습니다.  
  
 다음 절차에는 <xref:System.Windows.Forms.TextBox> 컨트롤이 데이터에 바인딩되는 <xref:System.Windows.Forms.ToolStrip> 폼에 추가 되는 컨트롤 및 취소 단추를 저장, 로드를 포함 하도록 수정 됩니다.  
  
### <a name="to-add-load-save-and-cancel-buttons-to-the-bindingnavigator-component"></a>부하를 추가 하려면 저장 및 취소 단추가 BindingNavigator 구성 요소  
  
1. 폼에 <xref:System.Windows.Forms.TextBox> 컨트롤을 추가합니다.  
  
2. 에 바인딩하는 <xref:System.Windows.Forms.BindingSource>, 데이터 원본에 바인딩된 합니다. 예를 들어를 <xref:System.Windows.Forms.BindingSource> 데이터베이스에 바인딩되어 있습니다.  
  
3. 데이터 집합 및 테이블 어댑터를 생성 한 후 끌어서를 <xref:System.Windows.Forms.BindingNavigator> 컨트롤을 폼입니다.  
  
4. 설정 된 <xref:System.Windows.Forms.BindingNavigator> 컨트롤의 <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> 속성을는 <xref:System.Windows.Forms.BindingSource> 폼에서 컨트롤에 바인딩되어 있는 합니다.  
  
5. <xref:System.Windows.Forms.BindingNavigator> 컨트롤을 선택합니다.  
  
6. 스마트 태그 문자 모양을 클릭 (![스마트 태그 문자 모양](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) 하므로 **BindingNavigator 태스크** 대화 상자가 나타나고 선택 **항목편집**.  
  
     합니다 **항목 컬렉션 편집기** 나타납니다.  
  
7. 에 **항목 컬렉션 편집기**, 다음 단계를 완료 합니다.  
  
    1. 추가 <xref:System.Windows.Forms.ToolStripSeparator> 및 3 <xref:System.Windows.Forms.ToolStripButton> 적절 한 형식을 선택 하 여 항목 <xref:System.Windows.Forms.ToolStripItem> 를 클릭 하 고는 **추가** 단추입니다.  
  
    2. 설정 된 <xref:System.Windows.Forms.ToolStripItem.Name%2A> 단추 중 속성 **LoadButton**, **저장 단추**, 및 **CancelButton**각각.  
  
    3. 설정 합니다 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 단추 중 속성 **부하**를 **저장**, 및 **취소**합니다.  
  
    4. 설정 된 <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> 각 단추에 대 한 속성 **텍스트**합니다. 또는이 속성 설정할 수 있습니다 **이미지** 또는 **ImageAndText**에 표시할 이미지를 설정 하 고는 <xref:System.Windows.Forms.ToolStripItem.Image%2A> 속성입니다.  
  
    5. 클릭 **확인** 대화 상자를 닫습니다. 단추에 추가 되는 <xref:System.Windows.Forms.ToolStrip>합니다.  
  
8. 폼을 마우스 오른쪽 단추로 클릭 하 고 선택 **코드 보기**합니다.  
  
9. 코드 편집기에서 데이터 테이블 어댑터를 로드 하는 코드 줄을 찾습니다. 이 코드는 2 단계에서 데이터 바인딩을 설정할 때 생성 되었습니다. 코드는 다음과 유사 해야 합니다.: `TableAdapterName.Fill(DataSetName.TableName)`합니다. 양식의 포함 될 가능성이 <xref:System.Windows.Forms.Form.Load> 이벤트입니다.  
  
10. 이벤트 처리기를 만듭니다는 <xref:System.Windows.Forms.ToolStripItem.Click> 의 이벤트를 **부하** <xref:System.Windows.Forms.ToolStripButton> 이전에 만든이 데이터 로딩 코드를 이동 합니다.  
  
     이제 코드가 다음과 비슷하게 표시 됩니다.  
  
    ```vb  
    Private Sub LoadButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles LoadButton.Click  
        TableAdapterName.Fill(DataSetName.TableName)  
    End Sub  
    ```  
  
    ```csharp  
    private void LoadButton_Click(System.Object sender,   
        System.EventArgs e)  
    {  
        TableAdapterName.Fill(DataSetName.TableName);  
    }  
    ```  
  
11. 이벤트 처리기를 만듭니다는 <xref:System.Windows.Forms.ToolStripItem.Click> 의 이벤트를 **저장** <xref:System.Windows.Forms.ToolStripButton> 이전에 만든 및 테이블 컨트롤 내에서 데이터를 업데이트 하는 코드 작성에 바인딩되어 합니다.  
  
    ```vb  
    Private Sub SaveButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles SaveButton.Click  
        TableAdapterName.Update(DataSetName.TableName)  
    End Sub  
    ```  
  
    ```csharp  
    private void SaveButton_Click(System.Object sender,   
        System.EventArgs e)  
    {  
        TableAdapterName.Update(DataSetName.TableName);  
    }  
    ```  
  
    > [!NOTE]
    > 일부 경우에는 <xref:System.Windows.Forms.BindingNavigator> 구성 요소는 이미를 **저장** 단추에만 코드 없이 생성 된 Windows Forms 디자이너에서 합니다. 이 경우에 앞의 코드를 배치할 수 있습니다 합니다 <xref:System.Windows.Forms.ToolStripItem.Click> 에서 새 단추를 만드는 대신 해당 단추에 대 한 이벤트 처리기는 <xref:System.Windows.Forms.ToolStrip>합니다. 그러나 설정 해야 하므로 기본적으로 단추가 비활성화 되는 합니다 <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> 단추 속성 `true` 단추 함수를 올바르게 있어야 합니다.
  
12. 이벤트 처리기를 만듭니다는 <xref:System.Windows.Forms.ToolStripItem.Click> 의 이벤트를 **취소** <xref:System.Windows.Forms.ToolStripButton> 이전에 만든 및 표시 되는 데이터 레코드의 모든 변경 내용을 취소 하는 코드를 작성 합니다.  
  
    ```vb  
    Private Sub CancelButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles CancelButton.Click  
        BindingSourceName.CancelEdit()  
    End Sub  
    ```  
  
    ```csharp  
    private void CancelButton_Click(System.Object sender, System.EventArgs e)  
    {  
        BindingSourceName.CancelEdit();  
    }  
    ```  
  
    > [!NOTE]
    >  <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> 메서드는 데이터의 행에 범위가 지정 됩니다. 다음 레코드로 이동 하기 전에 해당 개별 레코드를 보고 하는 동안 수행한 모든 변경 내용 저장 합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.ToolStrip>
- [BindingNavigator 컨트롤](bindingnavigator-control-windows-forms.md)
- [BindingSource 구성 요소 개요](bindingsource-component-overview.md)
