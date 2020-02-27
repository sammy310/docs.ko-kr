---
title: 디자이너를 사용 하 여 DataGridView 컨트롤에서 행 추가 및 삭제 방지
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], preventing row addition or deletion
ms.assetid: a17722bd-9400-41e6-8dcc-c9c151f0a749
ms.openlocfilehash: cca497aeaedd0c9f988241092eed707ecc259859
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628893"
---
# <a name="how-to-prevent-row-addition-and-deletion-in-the-windows-forms-datagridview-control-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 행 추가 및 삭제 금지
때때로 사용자가 <xref:System.Windows.Forms.DataGridView> 컨트롤에서 새 데이터 행을 입력하거나 기존 행을 삭제하지 않도록 방지하려고 합니다. 새 행은 컨트롤의 맨 아래에 있는 새 레코드의 특수 행에 입력 됩니다. 행 추가를 사용 하지 않도록 설정 하면 새 레코드의 행이 표시 되지 않습니다. 그런 다음 행 삭제 및 셀 편집을 사용 하지 않도록 설정 하 여 컨트롤을 완전히 읽기 전용으로 만들 수 있습니다.

 다음 절차에는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 포함 하는 폼을 포함 하는 **Windows 응용 프로그램** 프로젝트가 필요 합니다. 이러한 프로젝트를 설정 하는 방법에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트 만들기](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 및 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)를 참조 하세요.

## <a name="to-prevent-row-addition-and-deletion"></a>행 추가 및 삭제를 방지 하려면

- <xref:System.Windows.Forms.DataGridView> 컨트롤의 오른쪽 위 모퉁이에 있는 디자이너 작업 문자 모양 (![작은 검은색 화살표](./media/designer-actions-glyph.gif))을 클릭 한 다음 **추가 사용** 및 **삭제 사용** 확인란의 선택을 취소 합니다.

    > [!NOTE]
    > 컨트롤을 완전히 읽기 전용으로 설정 하려면 **편집 사용** 확인란의 선택을 취소 합니다.

## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>
- [방법: Windows Forms 응용 프로그램 프로젝트 만들기](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)
