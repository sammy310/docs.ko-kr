---
title: Windows Forms DataGridView 컨트롤의 셀 스타일
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], styles
- data grids [Windows Forms], cell styles
ms.assetid: dbb75ed6-8804-4232-8382-f9920c2e380c
ms.openlocfilehash: ec2a34deb25cd5f4cf492d92129ffc61d14001ab
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59171524"
---
# <a name="cell-styles-in-the-windows-forms-datagridview-control"></a>Windows Forms DataGridView 컨트롤의 셀 스타일
내에 있는 각 셀은 <xref:System.Windows.Forms.DataGridView> 컨트롤 고유한 스타일을 텍스트 형식으로, 배경색, 전경색, 글꼴 등을 가질 수 있습니다. 하지만 일반적으로 여러 셀은 특징이 있습니다. 특정 스타일입니다.  
  
 셀 스타일을 공유 하는 그룹 컨트롤에서 특정 행 또는 열, 특정 값에 포함 된 모든 셀 또는 모든 셀 내에 있는 모든 셀을 포함할 수 있습니다. 이러한 그룹은 겹칠, 때문에 각 셀 둘 이상의 위치에서 해당 스타일 정보를 가져올 수 있습니다. 예를 들어 좋습니다 모든 셀는 <xref:System.Windows.Forms.DataGridView> 및 사용 하는 동일한 글꼴 하지만 통화 형식을 사용 하려면 통화 열의 셀에에서 통화 셀만 음수를 사용 하 여 빨간 전경 색을 사용 하는 컨트롤입니다.  
  
## <a name="the-datagridviewcellstyle-class"></a>DataGridViewCellStyle 클래스  
 <xref:System.Windows.Forms.DataGridViewCellStyle> 클래스 비주얼 스타일에 관한 다음 속성을 포함 합니다.  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> 및 <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionBackColor%2A> 및 <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionForeColor%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A>  
  
 이 클래스에는 서식 지정 관련 된 다음 속성이 포함 됩니다.  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> 및 <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> 및 <xref:System.Windows.Forms.DataGridViewCellStyle.DataSourceNullValue%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Padding%2A>  
  
 다른 셀 스타일 속성과 이러한 속성에 대 한 자세한 내용은 참조는 <xref:System.Windows.Forms.DataGridViewCellStyle> 아래 참고 항목 섹션에 나열 된 참조 설명서 및 항목입니다.  
  
## <a name="using-datagridviewcellstyle-objects"></a>DataGridViewCellStyle 개체를 사용 하 여  
 검색할 수 있습니다 <xref:System.Windows.Forms.DataGridViewCellStyle> 의 다양 한 속성에서 개체를 <xref:System.Windows.Forms.DataGridView>를 <xref:System.Windows.Forms.DataGridViewColumn>, <xref:System.Windows.Forms.DataGridViewRow>, 및 <xref:System.Windows.Forms.DataGridViewCell> 클래스 및 파생된 클래스입니다. 이러한 속성 중 하나에 아직 설정 되지 경우 해당 값을 검색 만들어집니다 새 <xref:System.Windows.Forms.DataGridViewCellStyle> 개체입니다. 인스턴스화할 수도 있습니다 고유한 <xref:System.Windows.Forms.DataGridViewCellStyle> 개체 및 이러한 속성에 할당 합니다.  
  
 공유 하 여 스타일 정보가 불필요 한 중복을 방지할 수 있습니다 <xref:System.Windows.Forms.DataGridViewCellStyle> 여러 개체 <xref:System.Windows.Forms.DataGridView> 요소입니다. 스타일을 컨트롤, 열 및 행 수준 필터링을 통해 셀 수준으로 각 수준에서 설정 때문에 위의 수준을 다른 각 수준에서 스타일 속성만 설정 하 여도 스타일 중복을 방지할 수 있습니다. 이 스타일 상속 다음 섹션에서 자세히 설명 되어 있습니다.  
  
 다음 표에서 기본 속성을 get 또는 set <xref:System.Windows.Forms.DataGridViewCellStyle> 개체입니다.  
  
|속성|클래스|설명|  
|--------------|-------------|-----------------|  
|`DefaultCellStyle`|<xref:System.Windows.Forms.DataGridView>하십시오 <xref:System.Windows.Forms.DataGridViewColumn>, <xref:System.Windows.Forms.DataGridViewRow>, 및 파생 클래스|모든 컨트롤에서 셀 전체 (머리글 셀을 포함), 행 또는 열에 사용 되는 기본 스타일을 가져오거나 설정 합니다.|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|컨트롤의 모든 행에서 사용 하는 기본 셀 스타일을 가져오거나 설정 합니다. 여기에 머리글 셀 포함 되지 않습니다.|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|컨트롤의 행을 교대로 반복 되는 사용 되는 기본 셀 스타일을 가져오거나 설정 합니다. 장부와 비슷한 효과를 만들려면 사용 합니다.|  
|<xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|컨트롤의 행 머리글에서 사용 하는 기본 셀 스타일을 가져오거나 설정 합니다. 비주얼 스타일을 사용 하는 경우 현재 테마도 재정의 합니다.|  
|<xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|컨트롤의 열 머리글에서 사용 하는 기본 셀 스타일을 가져오거나 설정 합니다. 비주얼 스타일을 사용 하는 경우 현재 테마도 재정의 합니다.|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A>|<xref:System.Windows.Forms.DataGridViewCell> 클래스와 파생된 클래스|셀 수준에서 지정 된 스타일을 가져오거나 설정 합니다. 이러한 스타일의 상위 수준에서 상속 무시 합니다.|  
|`InheritedStyle`|<xref:System.Windows.Forms.DataGridViewCell>하십시오 <xref:System.Windows.Forms.DataGridViewRow>, <xref:System.Windows.Forms.DataGridViewColumn>, 및 파생 클래스|현재 셀, 행 또는 상위 수준에서 상속 하는 스타일을 포함 하는 열에 적용 된 모든 스타일을 가져옵니다.|  
  
 위에서 설명한 대로 새 인스턴스화합니다 스타일 속성의 값을 자동으로 가져오고 <xref:System.Windows.Forms.DataGridViewCellStyle> 경우 속성에 이전에 설정 되지 개체입니다. 행 및 열 클래스에는 이러한 개체를 불필요 하 게 만들기를 방지 하려면를 <xref:System.Windows.Forms.DataGridViewBand.HasDefaultCellStyle%2A> 속성으로 결정을 확인할 수 있습니다 여부를 <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A> 속성이 설정 되어 있습니다. 셀 클래스에는 마찬가지로 <xref:System.Windows.Forms.DataGridViewCell.HasStyle%2A> 나타내는 속성이 있는지 여부를 <xref:System.Windows.Forms.DataGridViewCell.Style%2A> 속성이 설정 되어 합니다.  
  
 스타일 속성을 각각의 해당 *PropertyName* `Changed` 이벤트에는 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 행, 열 및 셀 속성, 이벤트의 이름으로 시작 "`Row`","`Column`", 또는 "`Cell`" (예를 들어 <xref:System.Windows.Forms.DataGridView.RowDefaultCellStyleChanged>). 해당 스타일 속성을 다른 설정 된 경우 발생 하는 이러한 각 이벤트 <xref:System.Windows.Forms.DataGridViewCellStyle> 개체입니다. 이러한 이벤트를 검색할 때 발생 하지는 <xref:System.Windows.Forms.DataGridViewCellStyle> 스타일 속성에서 개체 및 해당 속성 값을 수정 합니다. 셀 스타일 개체 자체가 변경에 응답 하려면 처리는 <xref:System.Windows.Forms.DataGridView.CellStyleContentChanged> 이벤트입니다.  
  
## <a name="style-inheritance"></a>스타일 상속  
 각 <xref:System.Windows.Forms.DataGridViewCell> 에서 모양을 가져옵니다 해당 <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> 속성입니다. 합니다 <xref:System.Windows.Forms.DataGridViewCellStyle> 이 속성에서 반환 된 개체 형식의 속성의 계층 구조에서 값을 상속 <xref:System.Windows.Forms.DataGridViewCellStyle>합니다. 순서에서이 속성은 아래 나열 된 <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> 머리글이 아닌 셀에 대 한 해당 값을 가져옵니다.  
  
1.  <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
  
2.  <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
3.  <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType> (홀수 인덱스 번호가 있는 행의 셀)에 해당  
  
4.  <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
  
5.  <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
6.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 행 및 열 머리글 셀에는 <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> 속성은 지정 된 순서로 원본 속성의 다음 목록에서 값으로 채워집니다.  
  
1.  <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
  
2.  <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A?displayProperty=nameWithType> 또는 <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A?displayProperty=nameWithType>  
  
3.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 다음 다이어그램에서는이 프로세스를 보여 줍니다.  
  
 ![DataGridViewCellStyle 형식의](./media/cell-styles-in-the-windows-forms-datagridview-control/datagridviewcells-inheritance-diagram.gif "DataGridViewCells 상속 다이어그램")  
  
 또한 특정 행과 열으로 상속 된 스타일을 액세스할 수 있습니다. 열 <xref:System.Windows.Forms.DataGridViewColumn.InheritedStyle%2A> 속성은 다음 속성에서 값을 상속 합니다.  
  
1.  <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
2.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 행 <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A> 속성은 다음 속성에서 값을 상속 합니다.  
  
1.  <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
2.  <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType> (홀수 인덱스 번호가 있는 행의 셀)에 해당  
  
3.  <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
  
4.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 각 속성에 대 한는 <xref:System.Windows.Forms.DataGridViewCellStyle> 에서 반환 된 개체를 `InheritedStyle` 속성 값을 해당 속성이 아닌 다른 값으로 설정 하는 적절 한 목록의 첫 번째 셀 스타일에서 가져온 속성을 <xref:System.Windows.Forms.DataGridViewCellStyle> 클래스가 기본적으로.  
  
 다음 표에서 설명 하는 방법을 <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> 예제 셀 속성 값은 해당 포함 된 열에서 상속 됩니다.  
  
|형식의 속성 `DataGridViewCellStyle`|예제 `ForeColor` 검색된 된 개체에 대 한 값|  
|----------------------------------------------|----------------------------------------------------|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Red%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.DarkBlue%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Black%2A?displayProperty=nameWithType>|  
  
 이 경우에 <xref:System.Drawing.Color.Red%2A?displayProperty=nameWithType> 셀의 행에서 값은 목록에서 첫 번째 실제 값입니다. 이것이 합니다 <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> 셀의 속성 값 <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A>합니다.  
  
 다음 다이어그램에서는 다양 한 <xref:System.Windows.Forms.DataGridViewCellStyle> 속성 다른 위치에서 해당 값을 상속할 수 있습니다.  
  
 ![DataGridView 속성&#45;값이 상속](./media/cell-styles-in-the-windows-forms-datagridview-control/datagridviewcells-value-inheritance-diagram.gif "DataGridViewCells 값 상속 다이어그램")  
  
 스타일 상속을 활용 하 여 여러 위치에서 동일한 정보를 지정 하지 않고 전체 컨트롤에 대 한 적절 한 스타일을 제공할 수 있습니다.  
  
 개체에서 반환 된 설명 된 대로 머리글 셀 스타일 상속에 참여 하지만 <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> 및 <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> 의 속성을 <xref:System.Windows.Forms.DataGridView> 컨트롤이 반환 하는 개체의 속성 값을 재정의 하는 초기 속성 값 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> 속성입니다. 속성에서 반환 된 개체에 대해 설정 하려는 경우는 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> 행 및 열 머리글에 적용할 속성에서 반환 된 개체의 해당 속성을 설정 해야 합니다 <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> 및 <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> 속성 기본값을 표시 에 대 한는 <xref:System.Windows.Forms.DataGridViewCellStyle> 클래스입니다.  
  
> [!NOTE]
>  비주얼 스타일을 사용 하는 경우 행 및 열 머리글 (제외 하 고는 <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>)는 이러한 속성에 지정 된 스타일을 재정의 하는 현재 테마에 따라 자동으로 스타일이 지정 합니다.  
  
 합니다 <xref:System.Windows.Forms.DataGridViewButtonColumn>, <xref:System.Windows.Forms.DataGridViewImageColumn>, 및 <xref:System.Windows.Forms.DataGridViewCheckBoxColumn> 유형 열을 기준으로 반환 되는 개체의 일부 값을 초기화할 수도 <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> 속성입니다. 자세한 내용은 이러한 형식에 대 한 참조 설명서를 참조 하세요.  
  
## <a name="setting-styles-dynamically"></a>스타일을 동적으로 설정  
 특정 값이 포함 된 셀 스타일을 사용자 지정 구현에 대 한 처리기를 <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> 이벤트입니다. 이 이벤트 처리기의 인수를 수신 합니다 <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> 형식입니다. 이 개체의 위치로 함께 서식이 지정 되는 셀의 값을 확인할 수 있도록 하는 속성이 포함 된 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 이 개체도 포함을 <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.CellStyle%2A> 속성의 값으로 초기화 되는 <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> 서식이 지정 되는 셀의 속성입니다. 셀 값과 위치에 적합 한 스타일 정보를 지정 하려면 셀 스타일 속성을 수정할 수 있습니다.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView.RowPrePaint> 하 고 <xref:System.Windows.Forms.DataGridView.RowPostPaint> 이벤트 권한도 <xref:System.Windows.Forms.DataGridViewCellStyle> 개체 데이터를 이벤트 이지만 경우에는 행의 복사본 <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A> 속성은 읽기 전용 모드로 변경 내용을 컨트롤 영향을 주지 않습니다.  
  
 수정할 수 있습니다 동적으로 이벤트에 대 한 응답에서 개별 셀의 스타일과 같은 합니다 <xref:System.Windows.Forms.DataGridView.CellMouseEnter?displayProperty=nameWithType> 고 <xref:System.Windows.Forms.DataGridView.CellMouseLeave> 이벤트입니다. 에 대 한 처리기에서 예를 들어 합니다 <xref:System.Windows.Forms.DataGridView.CellMouseEnter> 이벤트를 셀 배경색의 현재 값을 저장할 수 있습니다 (셀의 검색할 <xref:System.Windows.Forms.DataGridViewCell.Style%2A> 속성), 위로 마우스를 가져가면 셀을 강조 표시 되도록 새로운 색으로 설정한. 에 대 한 처리기에는 <xref:System.Windows.Forms.DataGridView.CellMouseLeave> 이벤트에 원래 값으로 다음 배경색을 복원할 수 있습니다.  
  
> [!NOTE]
>  셀에 저장 된 값을 캐시 <xref:System.Windows.Forms.DataGridViewCell.Style%2A> 속성은 특정 스타일 값이 설정 되어 있는지 여부에 관계 없이 중요 합니다. 스타일 설정을 일시적으로 바꿔야 하는 경우 원래 "설정 안 함" 상태로 복원 셀 스타일 설정 상위 수준에서 상속 하는 다시 이동 됩니다 것을 확인 합니다. 스타일의 상속 여부에 관계 없이 셀에 대해 적용할 실제 스타일을 결정 해야 할 경우 사용 하 여 셀의 <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> 속성입니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.InheritedStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.InheritedStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellStyleContentChanged?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>
- [Windows Forms DataGridView 컨트롤에서 기본 형식 및 스타일 지정](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [방법: Windows Forms DataGridView 컨트롤에 대한 기본 셀 스타일 설정](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)
- [Windows Forms DataGridView 컨트롤에서 데이터 형식 지정](data-formatting-in-the-windows-forms-datagridview-control.md)
