---
title: '방법: 바인딩되지 않은 Windows Forms DataGridView 컨트롤 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], unbound data
- DataGridView control [Windows Forms], displaying data without binding to a data source
- data [Windows Forms], unbound
ms.assetid: b5d4b47d-9a28-4d88-9dba-0a3c90fba71d
ms.openlocfilehash: 9bfffac3d6970aceea3842df95f4bcae970b42e7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61747491"
---
# <a name="how-to-create-an-unbound-windows-forms-datagridview-control"></a>방법: 바인딩되지 않은 Windows Forms DataGridView 컨트롤 만들기
다음 코드 예제에서는 데이터 소스에 바인딩하지 않고 프로그래밍 방식으로 <xref:System.Windows.Forms.DataGridView> 컨트롤을 채우는 방법을 보여 줍니다. 적은 양의 데이터를 테이블 형식으로 표시하려는 경우에 유용합니다.  
  
 에 대 한 전체 설명은이 코드 예제를 참조 하세요. [연습: 만들기는 바인딩되지 않은 Windows Forms DataGridView 컨트롤](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)합니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#00)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
- System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조  
  
 Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다. 또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.  

## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.DataGridView>
- [연습: 만들기는 바인딩되지 않은 Windows Forms DataGridView 컨트롤](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)
- [Windows Forms DataGridView 컨트롤에서 데이터 표시](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Windows Forms DataGridView 컨트롤의 데이터 디스플레이 모드](data-display-modes-in-the-windows-forms-datagridview-control.md)
