---
title: '방법: 디자이너를 사용하여 Windows Forms DataGridView 열의 형식 변경'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], types
- DataGridView control [Windows Forms], changing column type
- data [Windows Forms], displaying
ms.assetid: 7f994d45-600d-4190-a187-35803214b40c
ms.openlocfilehash: e87017f3698bc88a123d8a0ba0df5dbe2b7bbfd9
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59314869"
---
# <a name="how-to-change-the-type-of-a-windows-forms-datagridview-column-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms DataGridView 열의 형식 변경
Windows Forms에 이미 추가 된 열의 형식을 변경 하는 경우가 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 예를 들어, 다음 유형의 데이터 원본에 컨트롤을 바인딩하는 경우 자동으로 생성 되는 열 중 일부를 수정 하는 것이 좋습니다. 표시할 테이블에 열이 관련된 테이블의 행에 외래 키가 포함 된 경우에 유용 합니다. 이 경우 다음 관련된 테이블에서 보다 의미 있는 값을 표시 하는 콤보 상자 열을 사용 하 여 이러한 외래 키는 표시 되는 텍스트 상자 열을 대체 하는 것이 좋습니다.  
  
 다음 절차를 수행 하려면을 **Windows 응용 프로그램** 포함 하는 양식을 사용 하 여 프로젝트를 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 이러한 프로젝트 설정에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트를 만듭니다](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 고 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-change-the-type-of-a-column-using-the-designer"></a>디자이너를 사용 하 여 열 유형을 변경 하려면  
  
1. 스마트 태그 문자 모양을 클릭 (![스마트 태그 문자 모양](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))의 오른쪽 위 모서리에는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 선택한 후 **열 편집**합니다.  
  
2. 열을 선택 합니다 **선택한 열** 목록입니다.  
  
3. 에 **열 속성** 표에서 설정 합니다 `ColumnType` 속성을 새 열 형식입니다.  
  
    > [!NOTE]
    >  `ColumnType` 속성은 열 형식을 나타내는 클래스를 나타내는 디자인 타임 전용 속성입니다. 열 클래스에서 정의 하는 실제 속성이 아닙니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- [방법: Windows Forms 응용 프로그램 프로젝트 만들기](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)
