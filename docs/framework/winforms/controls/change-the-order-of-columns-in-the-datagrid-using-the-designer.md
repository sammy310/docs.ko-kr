---
title: '방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 순서 변경'
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], order of
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- data [Windows Forms], displaying
ms.assetid: 7fe52a98-75d6-448c-97a5-65ca2c568c1a
ms.openlocfilehash: 131ef2a04caa17aa268c0e8d229a1070061c4373
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175307"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 순서 변경
Windows Forms 바인딩하면 <xref:System.Windows.Forms.DataGridView> 컨트롤을 데이터 소스를 자동으로 생성 된 열의 표시 순서는 데이터 원본에 의해 결정 됩니다. 이 순서를 원하는 경우에 디자이너를 사용 하 여 열의 순서를 변경할 수 있습니다. 컨트롤에 바인딩되지 않은 열을 추가 및 표시 순서를 변경할 수도 있습니다. 열 순서를 프로그래밍 방식으로 변경 하는 방법에 대 한 정보를 참조 하세요. [방법: Windows Forms DataGridView 컨트롤에서 열 순서를 변경할](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)합니다.  
  
 다음 절차를 수행 하려면을 **Windows 응용 프로그램** 포함 하는 양식을 사용 하 여 프로젝트를 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 이러한 프로젝트 설정에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트를 만듭니다](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 고 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 참조 하세요. [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)  
  
### <a name="to-change-the-column-order-using-the-designer"></a>디자이너를 사용 하 여 열 순서를 변경 하려면  
  
1.  스마트 태그 문자 모양을 클릭 (![스마트 태그 문자 모양](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))의 오른쪽 위 모서리에는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 선택한 후 **열 편집**합니다.  
  
2.  열을 선택 합니다 **선택한 열** 목록입니다.  
  
3.  위쪽 또는 아래쪽 화살표 오른쪽에는 **선택한 열** 원하는 위치에서 선택한 열을 나열 합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.DataGridView>
- [방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 추가 및 제거](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [방법: Windows Forms 응용 프로그램 프로젝트 만들기](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)
