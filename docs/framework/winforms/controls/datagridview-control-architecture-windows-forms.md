---
title: DataGridView 컨트롤 아키텍처
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], architecture
ms.assetid: 1c6cabf0-02ee-4bbc-9574-b54bb7f5b19e
ms.openlocfilehash: 2e1884383cca87f8d4ff84f486e2b29761a0c55d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742533"
---
# <a name="datagridview-control-architecture-windows-forms"></a>DataGridView 컨트롤 아키텍처(Windows Forms)
<xref:System.Windows.Forms.DataGridView> 컨트롤과 관련 클래스는 테이블 형식 데이터를 표시 하 고 편집 하기 위한 유연 하 고 확장 가능한 시스템으로 설계 되었습니다. 이러한 클래스는 모두 <xref:System.Windows.Forms?displayProperty=nameWithType> 네임 스페이스에 포함 되며 모두 "DataGridView" 접두사를 사용 하 여 이름이 지정 됩니다.  
  
## <a name="architecture-elements"></a>아키텍처 요소  
 기본 <xref:System.Windows.Forms.DataGridView> 동반 클래스는 <xref:System.Windows.Forms.DataGridViewElement>에서 파생 됩니다. 다음 개체 모델은 <xref:System.Windows.Forms.DataGridViewElement> 상속 계층 구조를 보여 줍니다.  
  
 ![DataGridViewElement 개체 모델 계층 구조를 표시 하는 다이어그램입니다.](./media/datagridview-control-architecture-windows-forms/datagridviewelement-object-model.gif)  
  
 <xref:System.Windows.Forms.DataGridViewElement> 클래스는 부모 <xref:System.Windows.Forms.DataGridView> 컨트롤에 대 한 참조를 제공 하 고 <xref:System.Windows.Forms.DataGridViewElementStates> 열거형의 값 조합을 나타내는 값을 포함 하는 <xref:System.Windows.Forms.DataGridViewElement.State%2A> 속성을 포함 합니다.  
  
 다음 섹션에서는 <xref:System.Windows.Forms.DataGridView> 동반 클래스에 대해 자세히 설명 합니다.  
  
### <a name="datagridviewelementstates"></a>DataGridViewElementStates  
 <xref:System.Windows.Forms.DataGridViewElementStates> 열거는 다음 값을 포함합니다.  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.None>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.ReadOnly>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Resizable>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Selected>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Visible>  
  
 이 열거형의 값은 비트 논리 연산자와 함께 사용할 수 있으므로 <xref:System.Windows.Forms.DataGridViewElement.State%2A> 속성은 한 번에 둘 이상의 상태를 표현할 수 있습니다. 예를 들어 <xref:System.Windows.Forms.DataGridViewElement>은 동시에 <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>, <xref:System.Windows.Forms.DataGridViewElementStates.Selected>및 <xref:System.Windows.Forms.DataGridViewElementStates.Visible>수 있습니다.  
  
### <a name="cells-and-bands"></a>셀 및 밴드  
 <xref:System.Windows.Forms.DataGridView> 컨트롤은 두 가지 기본 개체인 셀과 밴드를 구성 합니다. 모든 셀은 <xref:System.Windows.Forms.DataGridViewCell> 기본 클래스에서 파생 됩니다. 두 종류의 밴드, <xref:System.Windows.Forms.DataGridViewColumn> 및 <xref:System.Windows.Forms.DataGridViewRow>는 모두 <xref:System.Windows.Forms.DataGridViewBand> 기본 클래스에서 파생 됩니다.  
  
 <xref:System.Windows.Forms.DataGridView> 컨트롤은 여러 클래스와 상호 운용 되지만 가장 일반적으로 발생 하는 것은 <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn>및 <xref:System.Windows.Forms.DataGridViewRow>입니다.  
  
### <a name="datagridviewcell"></a>DataGridViewCell  
 셀은 <xref:System.Windows.Forms.DataGridView>의 기본 상호 작용 단위입니다. 표시는 셀 가운데에 표시 되 고 데이터 항목은 종종 셀을 통해 수행 됩니다. <xref:System.Windows.Forms.DataGridViewRow> 클래스의 <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> 컬렉션을 사용 하 여 셀에 액세스할 수 있으며, <xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> 컬렉션을 사용 하 여 선택한 셀에 액세스할 수 있습니다. 다음 개체 모델에서는이 사용법을 보여 주고 <xref:System.Windows.Forms.DataGridViewCell> 상속 계층 구조를 보여 줍니다.  
  
 ![DataGridViewCell 개체 모델 계층 구조를 표시 하는 다이어그램입니다.](./media/datagridview-control-architecture-windows-forms/datagridviewcell-object-model.gif)  
  
 <xref:System.Windows.Forms.DataGridViewCell> 형식은 모든 셀 형식이 파생 되는 추상 기본 클래스입니다. <xref:System.Windows.Forms.DataGridViewCell> 및 파생 된 형식은 Windows Forms 컨트롤이 아니지만 일부 호스트 Windows Forms 컨트롤입니다. 셀에서 지원 되는 모든 편집 기능은 일반적으로 호스팅된 컨트롤에 의해 처리 됩니다.  
  
 <xref:System.Windows.Forms.DataGridViewCell> 개체는 Windows Forms 컨트롤과 같은 방식으로 자체 모양과 그리기 기능을 제어 하지 않습니다. 대신 <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.DataGridViewCell> 개체의 모양을 담당 합니다. <xref:System.Windows.Forms.DataGridView> 컨트롤의 속성 및 이벤트와 상호 작용 하 여 셀의 모양과 동작에 크게 영향을 줄 수 있습니다. <xref:System.Windows.Forms.DataGridView> 컨트롤의 기능을 벗어나는 사용자 지정 항목에 대 한 특별 한 요구 사항이 있는 경우 <xref:System.Windows.Forms.DataGridViewCell> 또는 해당 자식 클래스 중 하나에서 파생 되는 고유한 클래스를 구현할 수 있습니다.  
  
 다음 목록에서는 <xref:System.Windows.Forms.DataGridViewCell>에서 파생 된 클래스를 보여 줍니다.  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewButtonCell>  
  
- <xref:System.Windows.Forms.DataGridViewLinkCell>  
  
- <xref:System.Windows.Forms.DataGridViewCheckBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewImageCell>  
  
- <xref:System.Windows.Forms.DataGridViewHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewRowHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewColumnHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewTopLeftHeaderCell>  
  
- 사용자 지정 셀 형식  
  
### <a name="datagridviewcolumn"></a>DataGridViewColumn  
 <xref:System.Windows.Forms.DataGridView> 컨트롤의 연결 된 데이터 저장소의 스키마는 <xref:System.Windows.Forms.DataGridView> 컨트롤의 열에 표시 됩니다. <xref:System.Windows.Forms.DataGridView.Columns%2A> 컬렉션을 사용 하 여 <xref:System.Windows.Forms.DataGridView> 컨트롤의 열에 액세스할 수 있습니다. <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> 컬렉션을 사용 하 여 선택한 열에 액세스할 수 있습니다. 다음 개체 모델에서는이 사용법을 보여 주고 <xref:System.Windows.Forms.DataGridViewColumn> 상속 계층 구조를 보여 줍니다.  
  
 ![DataGridViewColumn 개체 모델 계층 구조를 표시 하는 다이어그램입니다.](./media/datagridview-control-architecture-windows-forms/datagridviewcolumn-object-model.gif)  
  
 일부 키 셀 형식에는 해당 하는 열 형식이 있습니다. 이러한 클래스는 <xref:System.Windows.Forms.DataGridViewColumn> 기본 클래스에서 파생 됩니다.  
  
 다음 목록에서는 <xref:System.Windows.Forms.DataGridViewColumn>에서 파생 된 클래스를 보여 줍니다.  
  
- <xref:System.Windows.Forms.DataGridViewButtonColumn>  
  
- <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewImageColumn>  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewLinkColumn>  
  
- 사용자 지정 열 형식  
  
### <a name="datagridview-editing-controls"></a>DataGridView 편집 컨트롤  
 고급 편집 기능을 지 원하는 셀은 일반적으로 Windows Forms 컨트롤에서 파생 된 호스트 된 컨트롤을 사용 합니다. 이러한 컨트롤은 <xref:System.Windows.Forms.IDataGridViewEditingControl> 인터페이스도 구현 합니다. 다음 개체 모델에서는 이러한 컨트롤을 사용 하는 방법을 보여 줍니다.  
  
 ![DataGridView 편집 컨트롤 개체 모델 계층 구조를 보여 주는 다이어그램입니다.](./media/datagridview-control-architecture-windows-forms/datagridviewediting-object-model.gif)  
  
 다음 편집 컨트롤은 <xref:System.Windows.Forms.DataGridView> 컨트롤과 함께 제공 됩니다.  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>  
  
 사용자 고유의 편집 컨트롤을 만드는 방법에 대 한 자세한 내용은 [방법: Windows Forms DataGridView 셀의 호스트 컨트롤](how-to-host-controls-in-windows-forms-datagridview-cells.md)을 참조 하세요.  
  
 다음 표에서는 셀 형식, 열 형식 및 편집 컨트롤 간의 관계를 보여 줍니다.  
  
|셀 형식|호스팅된 컨트롤|열 유형|  
|---------------|--------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewButtonCell>|N/A|<xref:System.Windows.Forms.DataGridViewButtonColumn>|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxCell>|N/A|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewComboBoxCell>|<xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewImageCell>|N/A|<xref:System.Windows.Forms.DataGridViewImageColumn>|  
|<xref:System.Windows.Forms.DataGridViewLinkCell>|N/A|<xref:System.Windows.Forms.DataGridViewLinkColumn>|  
|<xref:System.Windows.Forms.DataGridViewTextBoxCell>|<xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|  
  
### <a name="datagridviewrow"></a>DataGridViewRow  
 <xref:System.Windows.Forms.DataGridViewRow> 클래스는 <xref:System.Windows.Forms.DataGridView> 컨트롤이 연결 된 데이터 저장소에서 레코드의 데이터 필드를 표시 합니다. <xref:System.Windows.Forms.DataGridView.Rows%2A> 컬렉션을 사용 하 여 <xref:System.Windows.Forms.DataGridView> 컨트롤의 행에 액세스할 수 있습니다. <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> 컬렉션을 사용 하 여 선택 된 행에 액세스할 수 있습니다. 다음 개체 모델에서는이 사용법을 보여 주고 <xref:System.Windows.Forms.DataGridViewRow> 상속 계층 구조를 보여 줍니다.  
  
 ![DataGridViewRow 개체 모델 계층 구조를 표시 하는 다이어그램입니다.](./media/datagridview-control-architecture-windows-forms/datagridviewrow-object-model.gif)
  
 일반적으로 필요 하지는 않지만 <xref:System.Windows.Forms.DataGridViewRow> 클래스에서 고유한 형식을 파생할 수 있습니다. <xref:System.Windows.Forms.DataGridView> 컨트롤에는 <xref:System.Windows.Forms.DataGridViewRow> 개체의 동작을 사용자 지정 하기 위한 몇 가지 행 관련 이벤트와 속성이 있습니다.  
  
 <xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> 속성을 사용 하도록 설정 하면 새 행을 추가 하는 특수 행이 마지막 행으로 표시 됩니다. 이 행은 <xref:System.Windows.Forms.DataGridView.Rows%2A> 컬렉션의 일부 이지만 주의가 필요한 특수 기능이 있습니다. 자세한 내용은 [Windows Forms DataGridView 컨트롤에서 새 레코드에 행 사용](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)을 참조 하세요.  
  
## <a name="see-also"></a>참조

- [DataGridView 컨트롤 개요](datagridview-control-overview-windows-forms.md)
- [Windows Forms DataGridView 컨트롤 사용자 지정](customizing-the-windows-forms-datagridview-control.md)
- [Windows Forms DataGridView 컨트롤에서 새 레코드에 행 사용](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
