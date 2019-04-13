---
title: Windows Forms DataGridView 컨트롤에서 Just-In-Time 데이터 로드를 사용하여 가상 모드 구현
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], just-in-time data loading
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- just-in-time data loading
- DataGridView control [Windows Forms], large data sets
- virtual mode [Windows Forms], just-in-time data loading
ms.assetid: c2a052b9-423c-4ff7-91dc-d8c7c79345f6
ms.openlocfilehash: 641db19cc6493a20c9f9a34622f466e3623c32ad
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59088654"
---
# <a name="implementing-virtual-mode-with-just-in-time-data-loading-in-the-windows-forms-datagridview-control"></a>Windows Forms DataGridView 컨트롤에서 Just-In-Time 데이터 로드를 사용하여 가상 모드 구현
가상 모드 구현 하는 이유는 <xref:System.Windows.Forms.DataGridView> 컨트롤 필요할 때에 데이터를 검색 하는 것입니다. 이 이라고 *-just-in-time 데이터 로드*합니다.  
  
 원격 데이터베이스에서 매우 큰 테이블을 사용 하는 경우 예를 들어 좋습니다 표시 하기 위해 필요한 데이터를 검색 하 고 사용자가 새 행을 뷰로 스크롤할 경우에 추가 데이터를 검색 하 여 시작 지연 되지 않도록 합니다. 응용 프로그램을 실행 하는 클라이언트 컴퓨터 데이터를 저장 하는 데 사용 가능한 메모리 양이 제한 되어 있으면 데이터베이스에서 새 값을 검색할 때 사용 되지 않는 데이터를 삭제할 수도 있습니다.  
  
 다음 섹션을 사용 하는 방법에 설명 된 <xref:System.Windows.Forms.DataGridView> 적시에 캐시를 사용 하 여 컨트롤입니다.  
  
 이 항목의 코드를 단일 목록으로 복사하려면 [방법: Forms DataGridView 컨트롤의 Windows에서-Just-in-time 데이터 로드를 사용 하 여 가상 모드 구현](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)합니다.  
  
## <a name="the-form"></a>폼  
 다음 코드 예제에서는 정의 읽기 전용을 포함 하는 폼 <xref:System.Windows.Forms.DataGridView> 상호 작용 하는 컨트롤을 `Cache` 개체를 통해를 <xref:System.Windows.Forms.DataGridView.CellValueNeeded> 이벤트 처리기입니다. `Cache` 개체는 로컬에 저장 된 값을 관리 하 고 사용 하는 `DataRetriever` Northwind 샘플 데이터베이스의 Orders 테이블에서 값을 검색 하는 개체입니다. `DataRetriever` 구현 하는 개체를 `IDataPageRetriever` 에 필요한 인터페이스는 `Cache` 클래스를 초기화 하는 또한는 <xref:System.Windows.Forms.DataGridView> 행과 열을 제어 합니다.  
  
 합니다 `IDataPageRetriever`, `DataRetriever`, 및 `Cache` 형식은이 항목의 뒷부분에 설명 됩니다.  
  
> [!NOTE]
>  암호와 같은 중요한 정보를 연결 문자열 내에 저장하면 애플리케이션 보안 문제가 발생할 수 있습니다. 데이터베이스 액세스를 제어할 경우에는 통합 보안이라고도 하는 Windows 인증을 사용하는 방법이 더 안전합니다. 자세한 내용은 [연결 정보 보호](../../data/adonet/protecting-connection-information.md)를 참조하세요.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#100)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#100)]  
  
## <a name="the-idatapageretriever-interface"></a>IDataPageRetriever 인터페이스  
 다음 코드 예제에서는 정의 `IDataPageRetriever` 에서 구현 하는 인터페이스를 `DataRetriever` 클래스입니다. 이 인터페이스에서 선언 된 유일한 메서드는는 `SupplyPageOfData` 메서드는 초기 행 인덱스 및 데이터의 단일 페이지에 있는 행의 수가 필요 합니다. 이러한 값은 데이터 원본에서 데이터의 하위 집합을 검색 구현자에 의해 사용 됩니다.  
  
 `Cache` 개체 데이터의 첫 두 페이지가 로드 생성 하는 동안이 인터페이스의 구현을 사용 합니다. 캐시 되지 않은 값을 필요할 때마다 캐시 이러한 페이지 중 하나를 삭제 하 고에서 값이 포함 된 새 페이지를 요청 합니다 `IDataPageRetriever`합니다.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#201)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#201)]  
  
## <a name="the-dataretriever-class"></a>DataRetriever 클래스  
 다음 코드 예제에서는 정의 `DataRetriever` 클래스를 구현 하는 `IDataPageRetriever` 서버에서 데이터 페이지를 검색 하는 인터페이스입니다. `DataRetriever` 클래스도 제공 `Columns` 및 `RowCount` 속성을는 합니다 <xref:System.Windows.Forms.DataGridView> 제어 사용 하 여 필요한 열을 만드는 빈 행의 적절 한 수를 추가 하는 <xref:System.Windows.Forms.DataGridView.Rows%2A> 컬렉션입니다. 빈 행을 추가 하는 데 필요 컨트롤은 테이블의 모든 데이터를 포함 하는 것 처럼 동작 합니다. 즉, 스크롤 막대의 스크롤 상자에 적절 한 크기를 해야 합니다. 사용자 테이블의 모든 행에 액세스할 수 없게 됩니다. 행으로 채워질는 <xref:System.Windows.Forms.DataGridView.CellValueNeeded> 뷰로 스크롤할 때에 이벤트 처리기입니다.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#200)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#200)]  
  
## <a name="the-cache-class"></a>캐시 클래스  
 다음 코드 예제에서는 정의 `Cache` 를 통해 입력 데이터의 두 페이지를 관리 하는 클래스는 `IDataPageRetriever` 구현 합니다. `Cache` 클래스 정의 내부 `DataPage` 포함 된 구조를 <xref:System.Data.DataTable> 페이지 및 행 인덱스를 계산 하는 나타내는 페이지의 상한 및 하 한 경계 값을 단일 캐시에 저장 하 합니다.  
  
 `Cache` 클래스 생성 시 데이터의 두 페이지를 로드 합니다. 때마다 합니다 <xref:System.Windows.Forms.DataGridView.CellValueNeeded> 값을 요청 하는 이벤트를 `Cache` 개체 값에 표시 되 면 두 가지 페이지 및 결정, 그렇다면 반환 합니다. 값을 로컬에서 사용할 수 없는 경우는 `Cache` 개체 결정 두 페이지의 현재 표시 된 행에서 가장 먼 이며 그런 다음 반환 하는 요청 된 값이 포함 된 새 리소스를 사용 하 여 페이지를 대체 합니다.  
  
 데이터 페이지의 행 수가 한 번에 화면에 표시 될 수 있는 행의 수와 동일 인을 만든다고 가정이 모델에는 테이블을 통해 페이징 사용자를 게 가장 최근에 열어 본 페이지를 효율적으로 반환할 수 있습니다.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#300)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#300)]  
  
## <a name="additional-considerations"></a>추가 고려 사항  
 이전 코드 예제에서는-just-in-time 데이터 로드의 데모로 제공 됩니다. 효율성을 극대화 하기 위해 고유의 요구 사항에 대 한 코드를 수정 해야 합니다. 최소한, 캐시에 데이터 페이지당 행 수에 대 한 적절 한 값을 선택 해야 합니다. 이 값에 전달 되는 `Cache` 생성자입니다. 페이지당 행 수는 같거나 더 높아야 동시에 표시 될 수 있는 행의 수에 <xref:System.Windows.Forms.DataGridView> 제어 합니다.  
  
 최상의 결과 위해 성능 테스트 및 사용 편의성 테스트 시스템 및 사용자의 요구 사항을 확인 하려면 수행 해야 합니다. 고려해 야 할 여러 요인이 응용 프로그램, 사용, 네트워크 연결의 사용 가능한 대역폭 및 대기 시간 사용 하는 서버를 실행 하는 클라이언트 컴퓨터에 메모리의 양을 포함 합니다. 대역폭 및 대기 시간에 최대 사용량의 결정 되어야 합니다.  
  
 응용 프로그램의 스크롤 성능 향상을 위해 로컬로 저장 된 데이터의 크기를 늘릴 수 있습니다. 그러나 시작 시간을 향상 시키려면 하지 않도록 해야 처음에 너무 많은 데이터를 로드 합니다. 수정 하려는 경우는 `Cache` 클래스를 저장할 수 있는 데이터 페이지 수를 늘립니다. 더 많은 데이터 페이지를 사용 하 여 스크롤의 효율성을 향상 시킬 수 있지만 서버 대기 시간 및 사용 가능한 대역폭에 따라 데이터 페이지에서 행의 이상적인 개수를 확인 해야 합니다. 더 작은 페이지를 사용 하 여 서버에 자주 액세스 하지만 요청 된 데이터를 반환 하는 시간이 적게 걸립니다. 대기 시간 보다 대역폭 문제에 대 한 자세한 내용은 인 경우에 더 큰 데이터 페이지를 사용 하는 것이 좋습니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- [Windows Forms DataGridView 컨트롤의 성능 조정](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Windows Forms DataGridView 컨트롤의 크기 조정에 대한 모범 사례](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [Windows Forms DataGridView 컨트롤의 가상 모드](virtual-mode-in-the-windows-forms-datagridview-control.md)
- [연습: Windows Forms DataGridView 컨트롤에서 가상 모드 구현](implementing-virtual-mode-wf-datagridview-control.md)
- [방법: Windows Forms DataGridView 컨트롤에서 Just-In-Time 데이터 로드를 사용하여 가상 모드 구현](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)
