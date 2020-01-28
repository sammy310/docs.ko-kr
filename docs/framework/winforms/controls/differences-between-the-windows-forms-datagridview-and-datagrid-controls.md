---
title: DataGridView 컨트롤과 DataGrid 컨트롤의 차이점
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms
- DataGrid control [Windows Forms], DataGridView control compared
- DataGridView control [Windows Forms], DataGrid control compared
ms.assetid: d412c786-140e-4210-8a56-a68467530a55
ms.openlocfilehash: 3552abe55d8e2c1cb4ae372ca64c7ca21f1fed0e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745962"
---
# <a name="differences-between-the-windows-forms-datagridview-and-datagrid-controls"></a>Windows Forms DataGridView 컨트롤과 DataGrid 컨트롤의 차이점
<xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체 하는 새 컨트롤입니다. <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤에 없는 다양 한 기본 및 고급 기능을 제공 합니다. 또한 <xref:System.Windows.Forms.DataGridView> 컨트롤의 아키텍처를 사용 하 여 <xref:System.Windows.Forms.DataGrid> 컨트롤 보다 더 쉽게 확장 하 고 사용자 지정할 수 있습니다.  
  
 다음 표에서는 <xref:System.Windows.Forms.DataGrid> 컨트롤에서 누락 된 <xref:System.Windows.Forms.DataGridView> 컨트롤에서 사용할 수 있는 몇 가지 주요 기능에 대해 설명 합니다.  
  
|DataGridView 컨트롤 기능|설명|  
|----------------------------------|-----------------|  
|여러 열 형식|<xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤 보다 더 많은 기본 제공 열 형식을 제공 합니다. 이러한 열 유형은 가장 일반적인 시나리오의 요구를 충족 하지만 <xref:System.Windows.Forms.DataGrid> 컨트롤의 열 유형과 확장 하거나 대체 하기도 쉽습니다. 자세한 내용은 [Windows Forms DataGridView 컨트롤의 열 형식](column-types-in-the-windows-forms-datagridview-control.md)을 참조 하세요.|  
|데이터를 표시 하는 여러 가지 방법|<xref:System.Windows.Forms.DataGrid> 컨트롤은 외부 데이터 원본의 데이터를 표시 하는 것으로 제한 됩니다. 그러나 <xref:System.Windows.Forms.DataGridView> 컨트롤은 컨트롤에 저장 된 바인딩되지 않은 데이터, 바인딩된 데이터 소스의 데이터 또는 바인딩된 데이터와 바인딩되지 않은 데이터를 함께 표시할 수 있습니다. 사용자 지정 데이터 관리를 제공 하는 <xref:System.Windows.Forms.DataGridView> 컨트롤에서 가상 모드를 구현할 수도 있습니다. 자세한 내용은 [Windows Forms DataGridView 컨트롤의 데이터 디스플레이 모드](data-display-modes-in-the-windows-forms-datagridview-control.md)합니다.|  
|데이터 표시를 사용자 지정 하는 여러 가지 방법|<xref:System.Windows.Forms.DataGridView> 컨트롤은 데이터의 서식을 지정 하 고 표시 하는 방법을 지정 하는 데 사용할 수 있는 많은 속성과 이벤트를 제공 합니다. 예를 들어, 셀에 포함 된 데이터에 따라 셀, 행 및 열의 모양을 변경 하거나 한 데이터 형식의 데이터를 다른 형식의 동등한 데이터로 바꿀 수 있습니다. 자세한 내용은 [Windows Forms DataGridView 컨트롤의 데이터 형식 지정](data-formatting-in-the-windows-forms-datagridview-control.md)을 참조 하세요.|  
|셀, 행, 열, 머리글 모양 및 동작을 변경 하는 여러 옵션|<xref:System.Windows.Forms.DataGridView> 컨트롤을 사용 하면 여러 가지 방법으로 개별 그리드 구성 요소를 사용할 수 있습니다. 예를 들어 행과 열을 고정 하 여 스크롤을 방지할 수 있습니다. 행, 열 및 머리글 숨기기 행, 열 및 헤더 크기가 조정 되는 방식을 변경 합니다. 사용자가 선택 하는 방식을 변경 합니다. 및는 개별 셀, 행 및 열에 대 한 도구 설명 및 바로 가기 메뉴를 제공 합니다.|  
  
 <xref:System.Windows.Forms.DataGrid> 컨트롤은 이전 버전과의 호환성을 위해 유지 되며 특별 한 요구 사항에 따라 유지 됩니다. 거의 모든 용도로 <xref:System.Windows.Forms.DataGridView> 컨트롤을 사용 해야 합니다. <xref:System.Windows.Forms.DataGridView> 컨트롤에서 사용할 수 없는 <xref:System.Windows.Forms.DataGrid> 컨트롤에서 사용할 수 있는 유일한 기능은 관련 된 두 테이블의 정보를 단일 컨트롤로 계층적으로 표시 하는 것입니다. 두 개의 <xref:System.Windows.Forms.DataGridView> 컨트롤을 사용 하 여 마스터/세부 관계에 있는 두 테이블의 정보를 표시 해야 합니다.  
  
## <a name="upgrading-to-the-datagridview-control"></a>DataGridView 컨트롤로 업그레이드  
 사용자 지정 없이 간단한 데이터 바인딩된 시나리오에서 <xref:System.Windows.Forms.DataGrid> 컨트롤을 사용 하는 기존 응용 프로그램이 있는 경우 이전 컨트롤을 새 컨트롤로 바꿀 수 있습니다. 두 컨트롤 모두 표준 Windows Forms 데이터 바인딩 아키텍처를 사용 하기 때문에 <xref:System.Windows.Forms.DataGridView> 컨트롤은 추가 구성 없이 바인딩된 데이터를 표시 합니다. 데이터 바인딩 향상을 활용 하는 것이 좋습니다. 그러나 데이터를 <xref:System.Windows.Forms.BindingSource> 구성 요소에 바인딩한 다음 <xref:System.Windows.Forms.DataGridView> 컨트롤에 바인딩할 수도 있습니다. 자세한 내용은 [BindingSource 구성 요소](bindingsource-component.md)를 참조 하세요.  
  
 <xref:System.Windows.Forms.DataGridView> 컨트롤에는 완전히 새로운 아키텍처가 있으므로 <xref:System.Windows.Forms.DataGridView> 컨트롤을 사용 하 <xref:System.Windows.Forms.DataGrid> 사용자 지정을 사용할 수 있도록 하는 간단한 변환 경로가 없습니다. 그러나 새 컨트롤에서 사용할 수 있는 기본 제공 기능 때문에 <xref:System.Windows.Forms.DataGridView> 컨트롤에서는 많은 <xref:System.Windows.Forms.DataGrid> 사용자 지정이 필요 하지 않습니다. <xref:System.Windows.Forms.DataGridView> 컨트롤에서 사용 하려는 <xref:System.Windows.Forms.DataGrid> 컨트롤에 대 한 사용자 지정 열 형식을 만든 경우 새 아키텍처를 사용 하 여 다시 구현 해야 합니다. 자세한 내용은 [Windows Forms DataGridView 컨트롤 사용자 지정](customizing-the-windows-forms-datagridview-control.md)을 참조 하세요.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGrid>
- <xref:System.Windows.Forms.BindingSource>
- [DataGridView 컨트롤](datagridview-control-windows-forms.md)
- [DataGrid 컨트롤](datagrid-control-windows-forms.md)
- [BindingSource 구성 요소](bindingsource-component.md)
- [Windows Forms DataGridView 컨트롤의 열 형식](column-types-in-the-windows-forms-datagridview-control.md)
- [Windows Forms DataGridView 컨트롤의 셀 스타일](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Windows Forms DataGridView 컨트롤의 데이터 디스플레이 모드](data-display-modes-in-the-windows-forms-datagridview-control.md)
- [Windows Forms DataGridView 컨트롤의 데이터 형식 지정](data-formatting-in-the-windows-forms-datagridview-control.md)
- [Windows Forms DataGridView 컨트롤의 크기 조정 옵션](sizing-options-in-the-windows-forms-datagridview-control.md)
- [Windows Forms DataGridView 컨트롤의 열 정렬 모드](column-sort-modes-in-the-windows-forms-datagridview-control.md)
- [Windows Forms DataGridView 컨트롤의 선택 모드](selection-modes-in-the-windows-forms-datagridview-control.md)
- [Windows Forms DataGridView 컨트롤 사용자 지정](customizing-the-windows-forms-datagridview-control.md)
