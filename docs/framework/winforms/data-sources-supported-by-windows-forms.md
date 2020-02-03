---
title: 지원되는 데이터 원본
ms.date: 03/30/2017
helpviewer_keywords:
- collections [Windows Forms], binding to
- OLE DB providers [Windows Forms], Windows Forms
- DataTable class [Windows Forms], binding and Windows Forms
- Windows Forms, data binding
- DataView class [Windows Forms], binding and Windows Forms
- DataViewManager class [Windows Forms], binding and Windows Forms
- Windows Forms, source data
- arrays [Windows Forms]
- data sources [Windows Forms]
- data providers [Windows Forms]
- DataSet class [Windows Forms], binding and Windows Forms
- data [Windows Forms], data providers
ms.assetid: 3d2c43f6-462b-4d35-9c86-13e9afe012e1
ms.openlocfilehash: 83ce4bb0d6f0bf81bcad4e38af212dccc3483ca5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742305"
---
# <a name="data-sources-supported-by-windows-forms"></a>Windows Forms에서 지원하는 데이터 소스
일반적으로 데이터 바인딩은 응용 프로그램 내에서 데이터베이스에 저장 된 데이터를 활용 하는 데 사용 되었습니다. Windows Forms 데이터 바인딩을 사용 하면 최소한의 특정 요구 사항이 충족 되는 한, 배열 및 컬렉션과 같은 다른 구조의 데이터 뿐만 아니라 데이터베이스의 데이터에 액세스할 수 있습니다.  
  
## <a name="structures-to-bind-to"></a>바인딩할 구조체  
 Windows Forms에서는 단순 개체 (단순 바인딩)에서 ADO.NET data tables (복합 바인딩)와 같은 복합 목록으로 다양 한 구조에 바인딩할 수 있습니다. 단순 바인딩의 경우 Windows Forms 단순 개체의 공용 속성에 대 한 바인딩을 지원 합니다. 목록 기반 바인딩에는 일반적으로 개체가 <xref:System.Collections.IList> 인터페이스 또는 <xref:System.ComponentModel.IListSource> 인터페이스를 지원 해야 Windows Forms. 또한 <xref:System.Windows.Forms.BindingSource> 구성 요소를 통해에 바인딩하는 경우에는 <xref:System.Collections.IEnumerable> 인터페이스를 지 원하는 개체에 바인딩할 수 있습니다. 데이터 바인딩과 관련 된 인터페이스에 대 한 자세한 내용은 [데이터 바인딩과 관련 된 인터페이스](interfaces-related-to-data-binding.md)를 참조 하세요.  
  
 다음 목록에서는 Windows Forms에서 바인딩할 수 있는 구조를 보여 줍니다.  
  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.BindingSource>은 가장 일반적인 Windows Forms 데이터 소스 이며, 데이터 소스와 Windows Forms 컨트롤 간의 프록시 역할을 합니다. 일반적인 <xref:System.Windows.Forms.BindingSource> 사용 패턴은 <xref:System.Windows.Forms.BindingSource>에 컨트롤을 바인딩하고 <xref:System.Windows.Forms.BindingSource> 데이터 원본 (예: ADO.NET 데이터 테이블 또는 비즈니스 개체)에 바인딩하는 것입니다. <xref:System.Windows.Forms.BindingSource>는 데이터 바인딩 지원 수준을 설정 하 고 개선 하는 서비스를 제공 합니다. 예를 들어 <xref:System.Windows.Forms.DataGridView> 및 <xref:System.Windows.Forms.ComboBox>와 같은 Windows Forms 목록 기반 컨트롤은 <xref:System.Collections.IEnumerable> 데이터 원본에 대 한 바인딩을 직접 지원 하지 않지만 <xref:System.Windows.Forms.BindingSource>를 통해 바인딩하여이 시나리오를 사용 하도록 설정할 수 있습니다. 이 경우 <xref:System.Windows.Forms.BindingSource>는 데이터 원본을 <xref:System.Collections.IList>변환 합니다.  
  
 단순 개체  
 Windows Forms은 <xref:System.Windows.Forms.Binding> 유형을 사용 하 여 개체 인스턴스의 공용 속성에 대 한 데이터 바인딩 컨트롤 속성을 지원 합니다. Windows Forms는 <xref:System.Windows.Forms.BindingSource>를 사용할 때 개체 인스턴스에 대 한 <xref:System.Windows.Forms.ListControl>와 같은 목록 기반 컨트롤의 바인딩도 지원 합니다.  
  
 배열 또는 컬렉션  
 데이터 소스 역할을 하려면 목록에서 <xref:System.Collections.IList> 인터페이스를 구현 해야 합니다. 한 가지 예는 <xref:System.Array> 클래스의 인스턴스인 배열입니다. 배열에 대 한 자세한 내용은 [방법: 개체 배열 만들기 (Visual Basic)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/487y7874(v=vs.100))를 참조 하세요.  
  
 일반적으로 데이터 바인딩을 위한 개체 목록을 만들 때 <xref:System.ComponentModel.BindingList%601>를 사용 해야 합니다. <xref:System.ComponentModel.BindingList%601>은 <xref:System.ComponentModel.IBindingList> 인터페이스의 제네릭 버전입니다. <xref:System.ComponentModel.IBindingList> 인터페이스는 양방향 데이터 바인딩에 필요한 속성, 메서드 및 이벤트를 추가 하 여 <xref:System.Collections.IList> 인터페이스를 확장 합니다.  
  
 <xref:System.Collections.IEnumerable>  
 Windows Forms 컨트롤은 <xref:System.Windows.Forms.BindingSource> 구성 요소를 통해 바인딩되는 경우에만 <xref:System.Collections.IEnumerable> 인터페이스를 지 원하는 데이터 소스에 바인딩할 수 있습니다.  
  
 ADO.NET data 개체  
 ADO.NET는에 바인딩하는 데 적합 한 여러 데이터 구조를 제공 합니다. 각각은 복잡성과 복잡도에 따라 다릅니다.  
  
- <xref:System.Data.DataColumn>입니다. <xref:System.Data.DataColumn>은 테이블을 구성 하는 여러 열이 있는 <xref:System.Data.DataTable>의 필수 구성 요소입니다. 각 <xref:System.Data.DataColumn>에는 열이 보유 하는 데이터의 종류를 결정 하는 <xref:System.Data.DataColumn.DataType%2A> 속성이 있습니다. 예를 들어 자동차를 설명 하는 테이블의 자동차를 만듭니다. 컨트롤 (예: <xref:System.Windows.Forms.TextBox> 컨트롤의 <xref:System.Windows.Forms.Control.Text%2A> 속성)을 데이터 테이블 내의 열에 간단 하 게 바인딩할 수 있습니다.  
  
- <xref:System.Data.DataTable>입니다. <xref:System.Data.DataTable>는 ADO.NET의 행과 열이 있는 테이블의 표현입니다. 데이터 테이블에는 두 개의 컬렉션이 포함 되어 있습니다. 즉, 지정 된 테이블의 데이터 열 (궁극적으로는 해당 테이블에 입력할 수 있는 데이터의 종류를 결정 함)을 나타내고 지정 된 테이블의 데이터 행을 나타내는 <xref:System.Data.DataRow>를 <xref:System.Data.DataColumn>합니다. 데이터 테이블에 포함 된 정보에 컨트롤을 복잡 하 게 바인딩할 수 있습니다. 예를 들어 <xref:System.Windows.Forms.DataGridView> 컨트롤을 데이터 테이블에 바인딩할 수 있습니다. 그러나 <xref:System.Data.DataTable>에 바인딩하는 경우에는 테이블의 기본 뷰에 대 한 실제 바인딩입니다.  
  
- <xref:System.Data.DataView>입니다. <xref:System.Data.DataView>은 필터링 하거나 정렬할 수 있는 단일 데이터 테이블의 사용자 지정 된 뷰입니다. 데이터 뷰는 복합 바인딩된 컨트롤에서 사용 하는 데이터 "스냅숏"입니다. 데이터 뷰 내에서 데이터를 단순 하 게 바인딩하거나 복잡 하 게 바인딩할 수 있지만 데이터 원본이 깨끗 하 고 업데이트 되는 것이 아니라 데이터의 고정 "그림"에 바인딩합니다.  
  
- <xref:System.Data.DataSet>입니다. <xref:System.Data.DataSet>은 데이터베이스의 데이터에 대 한 테이블, 관계 및 제약 조건의 컬렉션입니다. 데이터 집합 내에서 데이터를 단순 하 게 바인딩하거나 복잡 하 게 바인딩할 수 있지만 <xref:System.Data.DataSet>의 기본 <xref:System.Data.DataViewManager>에 바인딩합니다 (다음 글머리 기호 참조).  
  
- <xref:System.Data.DataViewManager>입니다. <xref:System.Data.DataViewManager>은 <xref:System.Data.DataView>와 유사 하지만 관계가 포함 된 전체 <xref:System.Data.DataSet>의 사용자 지정 된 뷰입니다. <xref:System.Data.DataViewManager.DataViewSettings%2A> 컬렉션을 사용 하 여 지정 된 테이블에 대 한 <xref:System.Data.DataViewManager>에 있는 모든 뷰에 대해 기본 필터 및 정렬 옵션을 설정할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목

- [Windows Forms 데이터 바인딩의 변경 알림](change-notification-in-windows-forms-data-binding.md)
- [데이터 바인딩 및 Windows Forms](data-binding-and-windows-forms.md)
- [Windows Forms 데이터 바인딩](windows-forms-data-binding.md)
