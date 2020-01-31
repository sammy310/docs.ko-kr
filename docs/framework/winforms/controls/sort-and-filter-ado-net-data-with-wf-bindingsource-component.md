---
title: BindingSource 구성 요소를 사용 하 여 ADO.NET 데이터 정렬 및 필터링
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
ms.openlocfilehash: cf1da3bb94b26449eb72b0e4930b262236487acc
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742967"
---
# <a name="how-to-sort-and-filter-adonet-data-with-the-windows-forms-bindingsource-component"></a>방법: Windows Forms BindingSource 구성 요소를 사용하여 ADO.NET 데이터 정렬 및 필터링
<xref:System.Windows.Forms.BindingSource.Sort%2A> 및 <xref:System.Windows.Forms.BindingSource.Filter%2A> 속성을 통해 <xref:System.Windows.Forms.BindingSource> 컨트롤의 정렬 및 필터링 기능을 노출할 수 있습니다. 기본 데이터 원본이 <xref:System.ComponentModel.IBindingList>경우 단순 정렬을 적용할 수 있으며, 데이터 원본이 <xref:System.ComponentModel.IBindingListView>인 경우 필터링 및 고급 정렬을 적용할 수 있습니다. <xref:System.Windows.Forms.BindingSource.Sort%2A> 속성에는 표준 ADO.NET 구문이 필요 합니다. 즉, 데이터 원본에 있는 데이터 열의 이름을 나타내는 문자열 뒤에 `ASC` 또는 `DESC` 목록을 오름차순으로 정렬할지 또는 내림차순으로 정렬할지를 나타냅니다. 쉼표 구분 기호를 사용 하 여 각 열을 구분 하 여 고급 정렬 또는 다중 열 정렬을 설정할 수 있습니다. <xref:System.Windows.Forms.BindingSource.Filter%2A> 속성은 문자열 식을 사용 합니다.  
  
> [!NOTE]
> 암호와 같은 중요한 정보를 연결 문자열 내에 저장하면 애플리케이션 보안 문제가 발생할 수 있습니다. 데이터베이스 액세스를 제어할 경우에는 통합 보안이라고도 하는 Windows 인증을 사용하는 방법이 더 안전합니다. 자세한 내용은 [연결 정보 보호](../../data/adonet/protecting-connection-information.md)를 참조하세요.  
  
### <a name="to-filter-data-with-the-bindingsource"></a>BindingSource를 사용 하 여 데이터를 필터링 하려면  
  
- <xref:System.Windows.Forms.BindingSource.Filter%2A> 속성을 원하는 식으로 설정 합니다.  
  
     다음 코드 예제에서 식은 열 이름 뒤에 열에 대해 원하는 값을 입력 합니다.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### <a name="to-sort-data-with-the-bindingsource"></a>BindingSource를 사용 하 여 데이터를 정렬 하려면  
  
1. <xref:System.Windows.Forms.BindingSource.Sort%2A> 속성을 원하는 열 이름으로 설정 하 고 `ASC` 또는 `DESC`를 입력 하 여 오름차순 이나 내림차순으로 지정 합니다.  
  
2. 여러 열을 쉼표로 구분 합니다.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## <a name="example"></a>예  
 다음 코드 예제에서는 Northwind 샘플 데이터베이스의 Customers 테이블에서 <xref:System.Windows.Forms.DataGridView> 컨트롤로 데이터를 로드 하 고 표시 된 데이터를 필터링 및 정렬 합니다.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제를 실행 하려면 `BindingSource1` 라는 <xref:System.Windows.Forms.BindingSource> 포함 된 양식에 코드를 붙여넣고 이름이 `dataGridView1`<xref:System.Windows.Forms.DataGridView> 합니다. 폼에 대 한 <xref:System.Windows.Forms.Form.Load> 이벤트를 처리 하 고 load 이벤트 처리기 메서드에서 `InitializeSortedFilteredBindingSource`를 호출 합니다.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.BindingSource.Sort%2A>
- <xref:System.Windows.Forms.BindingSource.Filter%2A>
- [방법: 샘플 데이터베이스 설치](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/8b6y4c7s(v=vs.120))
- [BindingSource 구성 요소](bindingsource-component.md)
