---
title: 디자이너를 사용 하 여 DataGridView 컨트롤에서 열 순서 변경
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], order of
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- data [Windows Forms], displaying
ms.assetid: 7fe52a98-75d6-448c-97a5-65ca2c568c1a
ms.openlocfilehash: be4f67ca6530b74fc90cb50a10463b2378edb933
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743149"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 순서 변경

Windows Forms <xref:System.Windows.Forms.DataGridView> 컨트롤을 데이터 원본에 바인딩하는 경우 자동으로 생성 되는 열의 표시 순서는 데이터 원본에 의해 결정 됩니다. 이 순서가 원하는 항목이 아닌 경우 디자이너를 사용 하 여 열의 순서를 변경할 수 있습니다. 컨트롤에 바인딩되지 않은 열을 추가 하 고 표시 순서를 변경할 수도 있습니다. 프로그래밍 방식으로 열 순서를 변경 하는 방법에 대 한 자세한 내용은 [방법: DataGridView 컨트롤 Windows Forms에서 열 순서 변경](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)을 참조 하세요.

다음 절차에는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 포함 하는 폼을 포함 하는 **Windows 응용 프로그램** 프로젝트가 필요 합니다. 이러한 프로젝트를 설정 하는 방법에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트 만들기](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 및 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)를 참조 하세요.

## <a name="to-change-the-column-order-using-the-designer"></a>디자이너를 사용 하 여 열 순서를 변경 하려면

1. <xref:System.Windows.Forms.DataGridView> 컨트롤의 오른쪽 위 모퉁이에 있는 스마트 태그 문자 모양 (![스마트 태그 문자 모양](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))을 클릭 한 다음 **열 편집**을 선택 합니다.

2. **선택한 열** 목록에서 열을 선택 합니다.

3. 선택한 열이 원하는 위치에 있을 때까지 **선택한 열** 목록 오른쪽에 있는 위쪽 또는 아래쪽 화살표를 클릭 합니다.

## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.DataGridView>
- [방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 추가 및 제거](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [방법: Windows Forms 응용 프로그램 프로젝트 만들기](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)
