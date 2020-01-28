---
title: DataGridView 컨트롤의 기본 기능
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], default functionality in DataGridView control
- DataGridView control [Windows Forms], default functionality
ms.assetid: 4405f697-cad1-4839-9bcd-8ddb09d9f00e
ms.openlocfilehash: b695883ac7ec3fb0c459adb66214b0eceab3a128
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746125"
---
# <a name="default-functionality-in-the-windows-forms-datagridview-control"></a>Windows Forms DataGridView 컨트롤의 기본 기능
Windows Forms <xref:System.Windows.Forms.DataGridView> 컨트롤은 많은 양의 기본 기능을 사용자에 게 제공 합니다.  
  
## <a name="default-functionality"></a>기본 기능  
 기본적으로 <xref:System.Windows.Forms.DataGridView> 컨트롤은 다음과 같습니다.  
  
- 테이블이 세로로 스크롤 될 때 계속 표시 되는 열 머리글 및 행 머리글을 자동으로 표시 합니다.  
  
- 현재 행에 대 한 선택 표시기를 포함 하는 행 머리글을 포함 합니다.  
  
- 첫 번째 셀에 선택 사각형이 있습니다.  
  
- 사용자가 열 구분선을 두 번 클릭할 때 자동으로 크기를 조정할 수 있는 열을 포함 합니다.  
  
- 는 응용 프로그램의 `Main` 메서드에서 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> 메서드를 호출할 때 Windows XP 및 Windows Server 2003 제품군의 비주얼 스타일을 자동으로 지원 합니다.  
  
 또한 <xref:System.Windows.Forms.DataGridView> 컨트롤의 내용은 기본적으로 편집할 수 있습니다.  
  
- 사용자가 셀에서 F2 키를 두 번 클릭 하거나 누르면 컨트롤이 자동으로 셀을 편집 모드로 전환 하 고 셀의 내용을 사용자 형식으로 업데이트 합니다.  
  
- 사용자가 표 끝으로 스크롤하면 새 레코드를 추가 하는 행이 표시 됩니다. 사용자가이 행을 클릭 하면 새 행이 기본값을 사용 하 여 <xref:System.Windows.Forms.DataGridView> 컨트롤에 추가 됩니다. 사용자가 ESC 키를 누르면이 새 행이 사라집니다.  
  
- 사용자가 행 머리글을 클릭 하면 전체 행이 선택 됩니다.  
  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A> 속성을 설정 하 여 <xref:System.Windows.Forms.DataGridView> 컨트롤을 데이터 소스에 바인딩하는 경우 컨트롤은 다음과 같습니다.  
  
- 에서는 자동으로 데이터 원본의 열 이름을 열 머리글 텍스트로 사용 합니다.  
  
- 데이터 소스의 콘텐츠로 채워집니다. 데이터 원본의 각 열에 대해 <xref:System.Windows.Forms.DataGridView> 열이 자동으로 생성 됩니다.  
  
- 테이블에서 표시 되는 각 행에 대 한 행을 만듭니다.  
  
- 사용자가 열 머리글을 클릭할 때 기본 데이터를 기준으로 행을 자동으로 정렬 합니다.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.DataGridView>
- [DataGridView 컨트롤](datagridview-control-windows-forms.md)
