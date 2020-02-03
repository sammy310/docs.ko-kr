---
title: DataGridView 컨트롤 시나리오
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], displaying in tabular format
- data grids [Windows Forms], about data grids
- DataGridView control [Windows Forms], scenarios
ms.assetid: 09a5fd05-3447-47ec-a4ec-6082a2b7f0dd
ms.openlocfilehash: 160d967c6445fb753cb6c73babfb02a734a07e28
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742466"
---
# <a name="datagridview-control-scenarios-windows-forms"></a>DataGridView 컨트롤 시나리오(Windows Forms)
<xref:System.Windows.Forms.DataGridView> 컨트롤을 사용 하면 다양 한 데이터 원본에서 테이블 형식 데이터를 표시할 수 있습니다. 간단한 사용을 위해 <xref:System.Windows.Forms.DataGridView>를 수동으로 채우고 컨트롤을 통해 직접 데이터를 조작할 수 있습니다. 그러나 일반적으로는 데이터를 외부 데이터 원본에 저장 하 고 <xref:System.Windows.Forms.BindingSource> 구성 요소를 통해 컨트롤을 바인딩할 수 있습니다.  
  
 이 항목에서는 <xref:System.Windows.Forms.DataGridView> 컨트롤과 관련 된 몇 가지 일반적인 시나리오에 대해 설명 합니다.  
  
## <a name="scenario-1-displaying-small-amounts-of-data"></a>시나리오 1: 소량의 데이터 표시  
 데이터를 외부 데이터 원본에 저장 하 여 <xref:System.Windows.Forms.DataGridView> 컨트롤에 표시할 필요가 없습니다. 적은 양의 데이터로 작업 하는 경우 컨트롤을 직접 채우고 컨트롤을 통해 데이터를 조작할 수 있습니다. 이를 *바인딩되지 않은 모드*라고 합니다. 자세한 내용은 [방법: 바인딩되지 않은 Windows Forms DataGridView 컨트롤 만들기](how-to-create-an-unbound-windows-forms-datagridview-control.md)를 참조 하세요.  
  
### <a name="scenario-key-points"></a>시나리오 주요 사항  
  
- 바인딩되지 않은 모드에서는 컨트롤을 수동으로 채웁니다.  
  
- 바인딩되지 않은 모드는 읽기 전용 데이터의 양이 적은 경우에 특히 적합 합니다.  
  
- 바인딩되지 않은 모드는 스프레드시트와 유사 하거나 부족 한 테이블에도 적합 합니다.  
  
## <a name="scenario-2-viewing-and-updating-data-stored-in-an-external-data-source"></a>시나리오 2: 외부 데이터 원본에 저장 된 데이터 보기 및 업데이트  
 사용자가 데이터베이스 테이블이 나 비즈니스 개체 컬렉션과 같은 데이터 원본에 저장 된 데이터에 액세스할 수 있는 UI (사용자 인터페이스)로 <xref:System.Windows.Forms.DataGridView> 컨트롤을 사용할 수 있습니다. 자세한 내용은 [방법: Windows Forms DataGridView 컨트롤에 데이터 바인딩](how-to-bind-data-to-the-windows-forms-datagridview-control.md)을 참조 하세요.  
  
### <a name="scenario-key-points"></a>시나리오 주요 사항  
  
- 바인딩 모드를 사용 하면 데이터 원본에 연결 하 고, 데이터 원본 속성 또는 데이터베이스 열을 기반으로 열을 자동으로 생성 하 고, 컨트롤을 자동으로 채울 수 있습니다.  
  
- 바인딩된 모드는 데이터와의 사용자 상호 작용에 적합 합니다. 데이터를 표시 하기 위해 형식을 지정할 수 있으며 사용자 지정 데이터는 데이터 원본에 필요한 형식으로 구문 분석할 수 있습니다. 사용자에 게 경고를 표시 하 고 잘못 된 셀을 수정할 수 있도록 데이터 입력 형식 지정 오류 및 데이터베이스 제약 조건 오류가 검색 될 수 있습니다.  
  
- 열 정렬, 고정 및 다시 정렬과 같은 추가 기능을 통해 사용자는 자신의 워크플로에 가장 편리한 방식으로 데이터를 볼 수 있습니다.  
  
- 클립보드 지원을 통해 사용자는 응용 프로그램에서 다른 응용 프로그램으로 데이터를 복사할 수 있습니다.  
  
## <a name="scenario-3-advanced-data"></a>시나리오 3: 고급 데이터  
 표준 데이터 바인딩 모델에서 해결 하지 않아도 되는 특별 한 요구 사항이 있는 경우 *가상 모드*를 구현 하 여 컨트롤과 데이터 간의 상호 작용을 관리할 수 있습니다. 가상 모드 구현 이란 컨트롤이 정보를 필요로 하는 것으로 셀에 대 한 정보를 요청할 수 있도록 하는 하나 이상의 이벤트 처리기를 구현 한다는 의미입니다.  
  
 예를 들어 많은 양의 데이터로 작업 하는 경우 최적의 효율성을 위해 가상 모드를 구현할 수 있습니다. 또한 가상 모드는 다른 데이터 원본에서 검색 한 열과 함께 표시 되는 바인딩되지 않은 열의 값을 유지 하는 데 유용 합니다.  
  
 가상 모드에 대 한 자세한 내용은 [연습: Windows Forms DataGridView 컨트롤에서 가상 모드 구현](implementing-virtual-mode-wf-datagridview-control.md)을 참조 하세요.  
  
### <a name="scenario-key-points"></a>시나리오 주요 사항  
  
- 가상 모드는 성능을 미세 조정 해야 할 때 매우 많은 양의 데이터를 표시 하는 데 적합 합니다.  
  
## <a name="scenario-4-automatically-resizing-rows-and-columns"></a>시나리오 4: 행 및 열의 크기 자동 조정  
 정기적으로 업데이트 되는 데이터를 표시 하는 경우 모든 내용이 표시 되도록 행과 열의 크기를 자동으로 조정할 수 있습니다. <xref:System.Windows.Forms.DataGridView> 컨트롤은 수동 크기 조정을 활성화 또는 비활성화 하 고, 특정 시간에 프로그래밍 방식으로 크기를 조정 하거나, 콘텐츠가 변경 될 때마다 자동으로 크기를 조정할 수 있는 몇 가지 옵션을 제공 자세한 내용은 [Windows Forms DataGridView 컨트롤의 크기 조정 옵션](sizing-options-in-the-windows-forms-datagridview-control.md)을 참조 하세요.  
  
### <a name="scenario-key-points"></a>시나리오 주요 사항  
  
- 수동 크기 조정을 통해 사용자는 셀 높이와 너비를 조정할 수 있습니다.  
  
- 자동 크기 조정을 사용 하면 셀 내용이 잘리지 않도록 셀 크기를 유지할 수 있습니다.  
  
- 프로그래밍 방식으로 크기를 조정 하면 연속 자동 크기 조정의 성능 저하를 방지 하기 위해 특정 시간에 셀 크기를 조정할 수 있습니다.  
  
## <a name="scenario-5-simple-customization"></a>시나리오 5: 간단한 사용자 지정  
 <xref:System.Windows.Forms.DataGridView> 컨트롤은 기본 모양과 동작을 변경할 수 있는 여러 가지 방법을 제공 합니다. 자세한 내용은 [Windows Forms DataGridView 컨트롤의 셀 스타일](cell-styles-in-the-windows-forms-datagridview-control.md)을 참조 하세요.  
  
### <a name="scenario-key-points"></a>시나리오 주요 사항  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle> 개체를 사용 하 여 여러 수준 및 컨트롤의 개별 요소에 색, 글꼴, 서식 및 위치 정보를 제공할 수 있습니다.  
  
- 셀 스타일을 여러 요소에서 계층화 하 고 공유할 수 있으므로 코드를 다시 사용할 수 있습니다.  
  
## <a name="scenario-6-advanced-customization"></a>시나리오 6: 고급 사용자 지정  
 <xref:System.Windows.Forms.DataGridView> 컨트롤은 모양 및 동작을 사용자 지정 하는 다양 한 방법을 제공 합니다.  
  
### <a name="scenario-key-points"></a>시나리오 주요 사항  
  
- 사용자 고유의 셀 그리기 코드를 제공할 수 있습니다. 자세한 내용은 [방법: Windows Forms DataGridView 컨트롤에서 셀 모양 사용자 지정](customize-the-appearance-of-cells-in-the-datagrid.md)합니다.  
  
- 사용자 고유의 행 그리기를 제공할 수 있습니다. 예를 들어 여러 열에 걸쳐 있는 내용이 포함 된 행을 만드는 데 유용 합니다. 자세한 내용은 [방법: DataGridView 컨트롤 Windows Forms에서 행 모양 사용자 지정](customize-the-appearance-of-rows-in-the-datagrid.md)을 참조 하세요.  
  
- 사용자 고유의 셀 및 열 클래스를 구현 하 여 셀 모양을 사용자 지정할 수 있습니다. 자세한 내용은 [방법: 동작 및 모양을 확장 하 여 Windows Forms DataGridView 컨트롤에서 셀 및 열 사용자 지정을](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)참조 하세요.  
  
- 사용자 고유의 셀 및 열 클래스를 구현 하 여 기본 제공 열 형식에서 제공 하는 컨트롤 이외의 컨트롤을 호스팅할 수 있습니다. 자세한 내용은 [방법: Windows Forms DataGridView 셀의 호스트 컨트롤](how-to-host-controls-in-windows-forms-datagridview-cells.md)을 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.DataGridView>
- [DataGridView 컨트롤 개요](datagridview-control-overview-windows-forms.md)
