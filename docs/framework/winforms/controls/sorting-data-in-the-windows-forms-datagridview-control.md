---
title: DataGridView 컨트롤의 데이터 정렬
ms.date: 02/13/2018
helpviewer_keywords:
- data [Windows Forms], sorting in grids
- data grids [Windows Forms], sorting data
- DataGridView control [Windows Forms], sorting data
ms.assetid: c1d4f24c-d961-4181-809d-5a5caa6122e4
ms.openlocfilehash: 1fcd5a5f5c6d690c573c4c2c5fa7c32aa0292441
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742950"
---
# <a name="sorting-data-in-the-windows-forms-datagridview-control"></a>Windows Forms DataGridView 컨트롤의 데이터 정렬

기본적으로 사용자는 입력란 열의 머리글을 클릭 하 여 <xref:System.Windows.Forms.DataGridView> 컨트롤의 데이터를 정렬 하거나 텍스트 상자 셀이 .NET Framework 4.7.2 이상 버전에 초점을 맞춘 경우 F3 키를 눌러 데이터를 정렬할 수 있습니다. 특정 열의 <xref:System.Windows.Forms.DataGridViewColumn.SortMode> 속성을 수정 하 여 사용자가이 작업을 수행 하는 데 적합 한 경우 다른 열 형식으로 정렬할 수 있습니다. 열 또는 여러 열을 기준으로 프로그래밍 방식으로 데이터를 정렬할 수도 있습니다.

## <a name="in-this-section"></a>섹션 내용

[Windows Forms DataGridView 컨트롤의 열 정렬 모드](column-sort-modes-in-the-windows-forms-datagridview-control.md)  
컨트롤의 데이터를 정렬 하기 위한 옵션에 대해 설명 합니다.

[방법: Windows Forms DataGridView 컨트롤의 열 정렬 모드 설정](set-the-sort-modes-for-columns-wf-datagridview-control.md)  
기본적으로 정렬할 수 없는 열을 기준으로 정렬할 수 있도록 하는 방법을 설명 합니다.

[방법: Windows Forms DataGridView 컨트롤에서 정렬 사용자 지정](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)  
프로그래밍 방식으로 데이터를 정렬 하는 방법과 <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> 이벤트를 사용 하거나 <xref:System.Collections.IComparer> 인터페이스를 구현 하 여 정렬을 사용자 지정 하는 방법을 설명 합니다.

## <a name="reference"></a>참조

<xref:System.Windows.Forms.DataGridView>  
<xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.  

<xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>  
<xref:System.Windows.Forms.DataGridView.Sort%2A> 메서드에 대 한 참조 설명서를 제공 합니다.

<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> 속성에 대 한 참조 설명서를 제공 합니다.

<xref:System.Windows.Forms.DataGridViewColumnSortMode>  
<xref:System.Windows.Forms.DataGridViewColumnSortMode> 열거형에 대 한 참조 설명서를 제공 합니다.

## <a name="see-also"></a>참고 항목

- [DataGridView 컨트롤](datagridview-control-windows-forms.md)
- [Windows Forms DataGridView 컨트롤의 열 형식](column-types-in-the-windows-forms-datagridview-control.md)
