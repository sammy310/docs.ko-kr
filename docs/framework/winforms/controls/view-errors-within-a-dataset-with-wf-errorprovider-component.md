---
title: '방법: Windows Forms ErrorProvider 구성 요소를 사용하여 DataSet 내의 오류 보기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- errors [Windows Forms], dataset errors
- error messages [Windows Forms], viewing in datasets
- ErrorProvider component [Windows Forms], dataset errors
ms.assetid: cbae023f-d651-4210-bdea-bcc5f037e321
ms.openlocfilehash: 190b53a248a77f03dd5d8cb13cb59a439fa9960d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157627"
---
# <a name="how-to-view-errors-within-a-dataset-with-the-windows-forms-errorprovider-component"></a>방법: Windows Forms ErrorProvider 구성 요소를 사용하여 DataSet 내의 오류 보기
Windows Forms를 사용할 수 있습니다 <xref:System.Windows.Forms.ErrorProvider> 데이터 집합 또는 다른 데이터 원본 내 열 오류를 보려면 구성 요소입니다. 에 대 한는 <xref:System.Windows.Forms.ErrorProvider> 폼에서 데이터 오류를 표시 하려면 구성 요소 수 하지 않아도 컨트롤을 사용 하 여 직접 연결 합니다. 데이터 원본에 바인딩된 후 동일한 데이터 원본에 바인딩되는 컨트롤 옆에 오류 아이콘이 표시할 수 있습니다.  
  
> [!NOTE]
>  오류 공급자를 변경 하는 경우 <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> 하 고 <xref:System.Windows.Forms.ErrorProvider.DataMember%2A> 런타임에 속성을 사용할지는 <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A> 충돌을 방지 하는 방법입니다.  
  
### <a name="to-display-data-errors"></a>데이터 오류를 표시 하려면  
  
1.  데이터 테이블 내에서 특정 열으로 구성 요소를 바인딩하십시오.  
  
    ```vb  
    ' Assumes existence of DataSet1, DataTable1  
    TextBox1.DataBindings.Add("Text", DataSet1, "Customers.Name")  
    ErrorProvider1.DataSource = DataSet1  
    ErrorProvider1.DataMember = "Customers"  
    ```  
  
    ```csharp  
    // Assumes existence of DataSet1, DataTable1  
    textBox1.DataBindings.Add("Text", DataSet1, "Customers.Name");  
    errorProvider1.DataSource = DataSet1;  
    errorProvider1.DataMember = "Customers";  
    ```  
  
2.  설정 된 <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> 속성을 폼입니다.  
  
    ```vb  
    ErrorProvider1.ContainerControl = Me  
    ```  
  
    ```csharp  
    errorProvider1.ContainerControl = this;  
    ```  
  
3.  열 오류를 포함 하는 행을 현재 레코드의 위치를 설정 합니다.  
  
    ```vb  
    DataTable1.Rows(5).SetColumnError("Name", "Bad data in this row.")  
    Me.BindingContext(DataTable1).Position = 5  
    ```  
  
    ```csharp  
    DataTable1.Rows[5].SetColumnError("Name", "Bad data in this row.");  
    this.BindingContext [DataTable1].Position = 5;  
    ```  
  
## <a name="see-also"></a>참고자료

- [ErrorProvider 구성 요소 개요](errorprovider-component-overview-windows-forms.md)
- [방법: Windows Forms ErrorProvider 구성 요소를 사용하여 양식 유효성 오류 아이콘 표시](display-error-icons-for-form-validation-with-wf-errorprovider.md)
