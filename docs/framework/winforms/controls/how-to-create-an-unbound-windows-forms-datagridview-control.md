---
title: 바인딩되지 않은 DataGridView 컨트롤 만들기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], unbound data
- DataGridView control [Windows Forms], displaying data without binding to a data source
- data [Windows Forms], unbound
ms.assetid: b5d4b47d-9a28-4d88-9dba-0a3c90fba71d
ms.openlocfilehash: 0b477eba6d8455554d72dc7ec8cfce68a91add38
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731000"
---
# <a name="how-to-create-an-unbound-windows-forms-datagridview-control"></a>방법: 바인딩되지 않은 Windows Forms DataGridView 컨트롤 만들기
다음 코드 예제에서는 데이터 소스에 바인딩하지 않고 프로그래밍 방식으로 <xref:System.Windows.Forms.DataGridView> 컨트롤을 채우는 방법을 보여 줍니다. 적은 양의 데이터를 테이블 형식으로 표시하려는 경우에 유용합니다.  
  
 이 코드 예제에 대한 전체적인 설명은 [연습: 바인딩되지 않은 Windows Forms DataGridView 컨트롤 만들기](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)를 참조하세요.  
  
## <a name="example"></a>예  
 [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#00)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
- System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.DataGridView>
- [연습: 바인딩되지 않은 Windows Forms DataGridView 컨트롤 만들기](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)
- [Windows Forms DataGridView 컨트롤에서 데이터 표시](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Windows Forms DataGridView 컨트롤의 데이터 디스플레이 모드](data-display-modes-in-the-windows-forms-datagridview-control.md)
