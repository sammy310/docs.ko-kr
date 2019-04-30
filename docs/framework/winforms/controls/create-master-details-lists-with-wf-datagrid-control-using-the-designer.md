---
title: '방법: 디자이너를 사용하여 Windows Forms DataGrid 컨트롤에 마스터-세부 목록 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 19438ba2-f687-4417-a2fb-ab1cd69d4ded
ms.openlocfilehash: f586572c850927ffe71566287986e6db6112c689
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61961362"
---
# <a name="how-to-create-master-details-lists-with-the-windows-forms-datagrid-control-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms DataGrid 컨트롤에 마스터-세부 목록 만들기

> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다. 자세한 내용은 [Windows Forms DataGridView 및 DataGrid 컨트롤의 차이점](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.  
  
 경우에 <xref:System.Data.DataSet> 계열이 관련된 테이블의 두 사용할 수 있습니다 <xref:System.Windows.Forms.DataGrid> 마스터-세부 형식으로 데이터를 표시 하는 컨트롤입니다. 하나의 <xref:System.Windows.Forms.DataGrid> 는 마스터 데이터에 지정 된 두 번째 지정 된 세부 정보 표 및 합니다. 목록에 항목을 선택 하면 관련된 자식 항목의 모든 세부 정보 목록에 표시 됩니다. 예를 들어, 경우에 <xref:System.Data.DataSet> 고객 테이블 및 관련된 Orders 테이블에 포함 되어는 마스터 데이터를 Customers 테이블과 Orders 테이블 세부 정보 표에서을 지정 합니다. 마스터 그리드에서 고객을 선택 하면 모든 주문을 Orders 테이블의 해당 고객과 관련 된 세부 정보 창에 표시 됩니다.  
  
 다음 절차를 수행 하려면을 **Windows 응용 프로그램** 프로젝트 (**파일** > **New** > **프로젝트**  >  **Visual C#** 하거나 **Visual Basic** > **클래식 데스크톱** > **Windows Forms 응용 프로그램**).  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-create-a-master-details-list-in-the-designer"></a>디자이너에서 마스터-세부 정보 목록을 만들려면  
  
1. 두 개의 추가 <xref:System.Windows.Forms.DataGrid> 폼에 컨트롤을 합니다. 자세한 내용은 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)합니다. Visual Studio 2005에는 <xref:System.Windows.Forms.DataGrid> 컨트롤에 없는 경우는 **도구 상자** 기본적으로. 자세한 내용은 [방법: 도구 상자 항목 추가](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100))합니다.  
  
    > [!NOTE]
    >  다음 단계를 사용 하는 Visual Studio 2005에 적용 되지 않습니다.는 **데이터 원본** 디자인 타임 데이터 바인딩에 대 한 창. 자세한 내용은 [Visual Studio에서 데이터에 컨트롤 바인딩](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio) 고 [방법: 관련 데이터에는 Windows Forms 응용 프로그램 표시](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/57tx3hhe(v=vs.120))합니다.  
  
2. 두 개 이상의 테이블을 끌어 **서버 탐색기** 폼입니다.  
  
3. **데이터** 메뉴에서 **데이터 집합 생성**합니다.  
  
4. XML 디자이너를 사용 하 여 테이블 간의 관계를 설정 합니다. 세부 정보를 참조 하세요. "방법: 만들 XML 스키마 및 데이터 집합에 일 대 다 관계 MSDN에서 ".  
  
5. 선택 하 여 관계를 저장할 **모두 저장** 에서 합니다 **파일** 메뉴.  
  
6. 구성 된 <xref:System.Windows.Forms.DataGrid> 는 마스터 데이터를 다음과 같이 지정 하려는 컨트롤:  
  
    1. 선택 된 <xref:System.Data.DataSet> 드롭 다운 목록에서를 <xref:System.Windows.Forms.DataGrid.DataSource%2A> 속성입니다.  
  
    2. 드롭다운 목록에서 마스터 테이블 (예: "고객")을 선택 합니다 <xref:System.Windows.Forms.DataGrid.DataMember%2A> 속성입니다.  
  
7. 구성 된 <xref:System.Windows.Forms.DataGrid> 세부 정보 표에서 다음과 같이 지정 하려는 컨트롤:  
  
    1. 선택 된 <xref:System.Data.DataSet> 드롭 다운 목록에서를 <xref:System.Windows.Forms.DataGrid.DataSource%2A> 속성입니다.  
  
    2. 드롭다운 목록에서 마스터 및 세부 테이블 간의 관계 (예: "Customers.CustOrd")를 선택 합니다 <xref:System.Windows.Forms.DataGrid.DataMember%2A> 속성입니다. 관계를 표시 하려면 더하기를 클릭 하 여 노드를 확장 (**+**) 드롭다운 목록에서 마스터 테이블 옆에 있는 기호입니다.  
  
## <a name="see-also"></a>참고자료

- [DataGrid 컨트롤](datagrid-control-windows-forms.md)
- [DataGrid 컨트롤 개요](datagrid-control-overview-windows-forms.md)
- [방법: 데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
- [Visual Studio에서 데이터에 컨트롤 바인딩](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
