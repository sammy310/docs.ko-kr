---
title: '방법: Windows Forms BindingSource 구성 요소를 사용하여 ADO.NET 데이터 정렬 및 필터링'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting data
- data sorting [Windows Forms], ADO.NET
- data [Windows Forms], filtering
- BindingSource component [Windows Forms], sorting and filtering data
- filtering [Windows Forms], ADO.NET
- data [Windows Forms], sorting
- ADO.NET [Windows Forms]
ms.assetid: 6c206daf-d706-4602-9dbe-435343052063
ms.openlocfilehash: 8904eff39b7278b2a185cc5e2f738ece1e8e88e4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61903047"
---
# <a name="how-to-sort-and-filter-adonet-data-with-the-windows-forms-bindingsource-component"></a>방법: Windows Forms BindingSource 구성 요소를 사용하여 ADO.NET 데이터 정렬 및 필터링
정렬 및 필터링 기능을 노출할 수 있습니다 <xref:System.Windows.Forms.BindingSource> 를 통해 제어 합니다 <xref:System.Windows.Forms.BindingSource.Sort%2A> 및 <xref:System.Windows.Forms.BindingSource.Filter%2A> 속성입니다. 데이터 원본의 경우에 간단한 정렬을 적용할 수 있습니다는 <xref:System.ComponentModel.IBindingList>, 및 고급 데이터 원본의 경우 정렬 및 필터링을 적용할 수 있습니다는 <xref:System.ComponentModel.IBindingListView>합니다. 합니다 <xref:System.Windows.Forms.BindingSource.Sort%2A> 속성을 사용 하려면 표준 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 구문: 뒤에 데이터 원본에서 데이터의 열 이름을 나타내는 문자열입니다 `ASC` 또는 `DESC` 목록을 오름차순 또는 내림차순으로 정렬할지 여부를 나타냅니다. 고급 정렬 또는 쉼표 구분 기호를 사용 하 여 각 열을 구분 하 여 여러 열 정렬을 설정할 수 있습니다. <xref:System.Windows.Forms.BindingSource.Filter%2A> 속성은 문자열 식을 사용 합니다.  
  
> [!NOTE]
>  암호와 같은 중요한 정보를 연결 문자열 내에 저장하면 애플리케이션 보안 문제가 발생할 수 있습니다. 데이터베이스 액세스를 제어할 경우에는 통합 보안이라고도 하는 Windows 인증을 사용하는 방법이 더 안전합니다. 자세한 내용은 [연결 정보 보호](../../data/adonet/protecting-connection-information.md)를 참조하세요.  
  
### <a name="to-filter-data-with-the-bindingsource"></a>BindingSource 사용 하 여 데이터를 필터링 하려면  
  
-   설정 된 <xref:System.Windows.Forms.BindingSource.Filter%2A> 속성을 원하는 식입니다.  
  
     다음 코드 예제에서는 식에는 다음 열에 대해 원하는 값 열 이름입니다.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### <a name="to-sort-data-with-the-bindingsource"></a>BindingSource 사용 하 여 데이터를 정렬 하려면  
  
1. 설정 합니다 <xref:System.Windows.Forms.BindingSource.Sort%2A> 속성을 원하는 열 이름 뒤에 `ASC` 또는 `DESC` 를 오름차순 또는 내림차순을 나타내는입니다.  
  
2. 여러 열을 쉼표로 구분 합니다.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## <a name="example"></a>예제  
 다음 코드 예제에 Northwind 샘플 데이터베이스의 Customers 테이블에서 데이터를 로드는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 필터링 하 고 표시 된 데이터를 정렬 합니다.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제를 실행 하려면 코드를 포함 하는 폼에 붙여 넣습니다를 <xref:System.Windows.Forms.BindingSource> 라는 `BindingSource1` 와 <xref:System.Windows.Forms.DataGridView> 라는 `dataGridView1`합니다. 처리를 <xref:System.Windows.Forms.Form.Load> 양식과 호출에 대 한 이벤트 `InitializeSortedFilteredBindingSource` load 이벤트 처리기 메서드에서 합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.BindingSource.Sort%2A>
- <xref:System.Windows.Forms.BindingSource.Filter%2A>
- [방법: 예제 데이터베이스 설치](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/8b6y4c7s(v=vs.120))
- [BindingSource 구성 요소](bindingsource-component.md)
