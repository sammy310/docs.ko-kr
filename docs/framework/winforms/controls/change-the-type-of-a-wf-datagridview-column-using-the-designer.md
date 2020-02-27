---
title: 디자이너를 사용 하 여 DataGridView 열의 형식 변경
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], types
- DataGridView control [Windows Forms], changing column type
- data [Windows Forms], displaying
ms.assetid: 7f994d45-600d-4190-a187-35803214b40c
ms.openlocfilehash: 470f350a4791a3db39d08ab7992d86eb7b2e270a
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628620"
---
# <a name="how-to-change-the-type-of-a-windows-forms-datagridview-column-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤의 형식 변경
경우에 따라 Windows Forms <xref:System.Windows.Forms.DataGridView> 컨트롤에 이미 추가 된 열의 형식을 변경 하는 것이 좋습니다. 예를 들어 데이터 소스에 컨트롤을 바인딩할 때 자동으로 생성 되는 일부 열의 형식을 수정할 수 있습니다. 이 기능은 표시 하는 테이블에 관련 테이블의 행에 대 한 외래 키가 포함 된 열이 있는 경우에 유용 합니다. 이 경우 이러한 외래 키를 표시 하는 입력란 열을 관련 테이블의 의미 있는 값을 표시 하는 콤보 상자 열로 바꿀 수 있습니다.

 다음 절차에는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 포함 하는 폼을 포함 하는 **Windows 응용 프로그램** 프로젝트가 필요 합니다. 이러한 프로젝트를 설정 하는 방법에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트 만들기](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 및 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)를 참조 하세요.

### <a name="to-change-the-type-of-a-column-using-the-designer"></a>디자이너를 사용 하 여 열의 형식을 변경 하려면

1. <xref:System.Windows.Forms.DataGridView> 컨트롤의 오른쪽 위 모퉁이에 있는 디자이너 작업 문자 모양 (![작은 검은색 화살표](./media/designer-actions-glyph.gif))을 클릭 한 다음 **열 편집**을 선택 합니다.

2. **선택한 열** 목록에서 열을 선택 합니다.

3. **열 속성** 표에서 `ColumnType` 속성을 새 열 유형으로 설정 합니다.

    > [!NOTE]
    > `ColumnType` 속성은 열 유형을 나타내는 클래스를 나타내는 디자인 타임 전용 속성입니다. 열 클래스에 정의 된 실제 속성이 아닙니다.

## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- [방법: Windows Forms 응용 프로그램 프로젝트 만들기](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)
