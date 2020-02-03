---
title: DataGridView 컨트롤 기술 요약
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], about DataGridView control
- data grids [Windows Forms], about data grids
ms.assetid: 094498c3-a126-4a3f-83fe-f69e96c7717b
ms.openlocfilehash: 18eebd067df9768e14cc81258184551d00dd1402
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742483"
---
# <a name="datagridview-control-technology-summary-windows-forms"></a>DataGridView 컨트롤 기술 요약(Windows Forms)
이 항목에서는 `DataGridView` 제어 및 이를 사용하도록 지원하는 클래스에 대한 정보를 요약하여 설명합니다.  
  
 데이터를 테이블 형식으로 표시 하는 작업은 자주 수행 해야 하는 작업입니다. `DataGridView` 컨트롤은 모눈에 데이터를 제공 하기 위한 완전 한 솔루션으로 설계 되었습니다.  
  
## <a name="keywords"></a>키워드가  
 DataGridView, BindingSource, 테이블, 셀, 데이터 바인딩, 가상 모드  
  
## <a name="namespaces"></a>네임스페이스  
 <xref:System.Windows.Forms?displayProperty=nameWithType>  
  
 <xref:System.Data?displayProperty=nameWithType>  
  
## <a name="related-technologies"></a>관련 기술  
 `BindingSource`  
  
## <a name="background"></a>배경  
 UI (사용자 인터페이스) 디자이너는 사용자에 게 테이블 형식 데이터를 표시 해야 하는 경우가 많습니다. .NET Framework는 테이블이 나 표에 데이터를 표시 하는 여러 가지 방법을 제공 합니다. `DataGridView` 컨트롤은 Windows Forms 응용 프로그램에 대 한이 기술의 최신 진화를 나타냅니다.  
  
 `DataGridView` 컨트롤은 데이터 저장소의 데이터 행을 표시할 수 있습니다. 많은 유형의 데이터 저장소가 지원 됩니다. 데이터 저장소는 1 차원 배열과 같은 단순 하 고 형식화 되지 않은 데이터를 보유할 수 있으며, <xref:System.Data.DataSet>등의 형식화 된 데이터를 저장할 수 있습니다. 자세한 내용은 [방법: Windows Forms DataGridView 컨트롤에 데이터 바인딩](how-to-bind-data-to-the-windows-forms-datagridview-control.md)을 참조 하세요.  
  
 `DataGridView` 컨트롤에서는 데이터를 표 형식으로 표시하는 강력하고 유연한 방법을 제공합니다. 컨트롤을 사용 하 여 작고 매우 큰 데이터 집합에 대 한 읽기 전용 또는 편집 가능한 뷰를 표시할 수 있습니다.  
  
 여러 가지 방법으로 `DataGridView` 컨트롤을 확장 하 여 응용 프로그램에 사용자 지정 동작을 빌드할 수 있습니다. 예를 들어 프로그래밍 방식으로 고유한 정렬 알고리즘을 지정하고 고유한 셀 형식을 만들 수도 있습니다. 여러 속성 중에서 선택하여 `DataGridView` 컨트롤의 모양을 쉽게 사용자 지정할 수 있습니다. 많은 유형의 데이터 저장소를 데이터 원본으로 사용할 수도 있고, 데이터 소스에 바인딩되지 않은 `DataGridView` 컨트롤을 작동할 수도 있습니다.  
  
## <a name="implementing-datagridview-classes"></a>DataGridView 클래스 구현  
 `DataGridView` 컨트롤의 확장성 기능을 활용 하는 데는 여러 가지 방법이 있습니다. 이벤트와 속성을 통해 컨트롤의 여러 측면을 사용자 지정할 수 있지만 일부 사용자 지정을 수행 하려면 기존 `DataGridView` 클래스에서 파생 된 새 클래스를 만들어야 합니다.  
  
 가장 일반적으로 사용 되는 기본 클래스는 `DataGridViewCell` 및 `DataGridViewColumn`입니다. `DataGridViewCell` 또는 해당 자식 클래스에서 사용자 고유의 셀 클래스를 파생할 수 있습니다. 모든 셀 형식을 열에 추가할 수 있지만 일반적으로 사용자 지정 셀 형식의 셀을 호스트 하는 `DataGridViewColumn`에서 함께 제공 되는 열 클래스를 기본적으로 파생 시킬 수 있습니다.  
  
 파생 셀 클래스에서 `IDataGridViewEditingCell` 인터페이스를 구현 하 여 편집 기능이 있지만 편집 모드에서 컨트롤을 호스팅하지 않는 셀 형식을 만들 수 있습니다. 편집 모드에서 셀에 호스팅할 수 있는 컨트롤을 만들려면 <xref:System.Windows.Forms.Control>에서 파생 된 클래스에 `IDataGridViewEditingControl` 인터페이스를 구현할 수 있습니다.  
  
 자세한 내용은 [방법: 동작 및 모양을 확장 하 여 Windows Forms DataGridView 컨트롤에서 셀 및 열 사용자 지정](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md) 및 [방법: Windows Forms DataGridView 셀에서 컨트롤 호스팅](how-to-host-controls-in-windows-forms-datagridview-cells.md)을 참조 하세요.  
  
## <a name="datagridview-classes-at-a-glance"></a>DataGridView 클래스 한눈에 보기  
 <xref:System.Windows.Forms>  
  
|기술 영역|클래스/인터페이스/구성 요소|  
|---------------------|-------------------------------------------------|  
|데이터 바인딩|<xref:System.Windows.Forms.BindingSource>|  
|데이터 프레젠테이션|<xref:System.Windows.Forms.DataGridView><br /><br /> <xref:System.Windows.Forms.DataGridViewCell> 및 파생 클래스<br /><br /> <xref:System.Windows.Forms.DataGridViewRow> 및 파생 클래스<br /><br /> <xref:System.Windows.Forms.DataGridViewColumn> 및 파생 클래스<br /><br /> <xref:System.Windows.Forms.DataGridViewCellStyle>|  
|<xref:System.Windows.Forms.DataGridView> 확장성|<xref:System.Windows.Forms.DataGridViewCell> 및 파생 클래스<br /><br /> <xref:System.Windows.Forms.DataGridViewColumn> 및 파생 클래스<br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingCell><br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingControl>|  
  
## <a name="whats-new"></a>What's New  
 <xref:System.Windows.Forms.DataGridView> 컨트롤은 Windows Forms를 사용 하 여 표 형식 데이터를 표시 하기 위한 완전 한 솔루션으로 설계 되었습니다. 새 응용 프로그램을 작성 하는 경우 <xref:System.Windows.Forms.DataGrid>같은 다른 솔루션 앞에 <xref:System.Windows.Forms.DataGridView> 컨트롤을 사용 하는 것이 좋습니다. 자세한 내용은 [Windows Forms DataGridView 및 DataGrid 컨트롤의 차이점](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.  
  
 <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.BindingSource> 구성 요소와 밀접 하 게 연동 하 여 작업할 수 있습니다. 이 구성 요소는 양식의 주 데이터 원본으로 설계 되었습니다. 데이터 원본 형식에 관계 없이 <xref:System.Windows.Forms.DataGridView> 컨트롤과 데이터 소스 간의 상호 작용을 관리할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목

- [DataGridView 컨트롤 개요](datagridview-control-overview-windows-forms.md)
- [DataGridView 컨트롤 아키텍처](datagridview-control-architecture-windows-forms.md)
- [연결 정보 보호](../../data/adonet/protecting-connection-information.md)
