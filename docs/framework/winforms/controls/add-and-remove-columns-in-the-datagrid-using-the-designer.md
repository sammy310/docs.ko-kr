---
title: '방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 추가 및 제거'
ms.date: 03/30/2017
f1_keywords:
- vs.DataGridViewAddColumnDialog
helpviewer_keywords:
- DataGridView control [Windows Forms], adding columns
- DataGridView control [Windows Forms], removing columns
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
ms.openlocfilehash: 82bab7a42c7a8de131cc53d792cf2d372580af40
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078111"
---
# <a name="how-to-add-and-remove-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 추가 및 제거
Windows Forms <xref:System.Windows.Forms.DataGridView> 컨트롤 데이터를 표시 하기 위해 열을 포함 해야 합니다. 수동으로 컨트롤을 채우는 하려는 경우에 직접 열을 추가 해야 합니다. 또는 생성 되 고 열을 자동으로 채워지도록 데이터 원본에 컨트롤을 바인딩할 수 있습니다. 데이터 원본에 표시 하려는 것 보다 많은 열이 있으면 필요 없는 열을 제거할 수 있습니다.  
  
 다음 절차는 **Windows 응용 프로그램** 포함 하는 양식을 사용 하 여 프로젝트를 <xref:System.Windows.Forms.DataGridView> 컨트롤입니다. 이러한 프로젝트 설정에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트를 만듭니다](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 고 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-add-a-column-using-the-designer"></a>디자이너를 사용 하 여 열을 추가 하려면  
  
1.  스마트 태그 문자 모양을 클릭 (![스마트 태그 문자 모양](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))의 오른쪽 위 모서리에는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 선택한 후 **열 추가**합니다.  
  
2.  **열 추가** 대화 상자를 선택 합니다 **데이터 바인딩된 열** 옵션 및 데이터 원본에서 열을 선택 하거나 선택 합니다 **바인딩되지 않은 열** 옵션 및 해당 열을 정의 제공 된 필드를 사용 합니다.  
  
3.  클릭 합니다 **추가** 기존 열이 컨트롤의 표시 영역에 아직 채워지지 않은 경우 디자이너에 표시 하는 열을 추가 하려면 단추입니다.  
  
    > [!NOTE]
    >  열 속성을 수정할 수 있습니다는 **열 편집** 대화 상자에서 컨트롤의 스마트 태그에서 액세스할 수 있습니다.  
  
### <a name="to-remove-a-column-using-the-designer"></a>디자이너를 사용 하 여 열을 제거 하려면  
  
1.  선택할 **열 편집** 컨트롤의 스마트 태그입니다.  
  
2.  열을 선택 합니다 **선택한 열** 목록입니다.  
  
3.  클릭 합니다 **제거** 사라집니다 디자이너에서 열을 삭제 하려면 단추입니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.DataGridView>
- [방법: Windows Forms 응용 프로그램 프로젝트 만들기](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)
