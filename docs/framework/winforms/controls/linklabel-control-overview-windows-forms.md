---
title: LinkLabel 컨트롤 개요
ms.date: 03/30/2017
f1_keywords:
- LinkLabel
helpviewer_keywords:
- links [Windows Forms], LinkLabel control
- Label control [Windows Forms], about Label control
- LinkLabel control [Windows Forms], about LinkLabel control
ms.assetid: 9e248549-10ca-43a3-bb5e-60f583d369f1
ms.openlocfilehash: 9837902bf56a402d623adbcf41558dcc568b7105
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745216"
---
# <a name="linklabel-control-overview-windows-forms"></a>LinkLabel 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.LinkLabel> 컨트롤을 사용 하면 Windows Forms 응용 프로그램에 웹 스타일 링크를 추가할 수 있습니다. <xref:System.Windows.Forms.Label> 컨트롤을 사용할 수 있는 모든 항목에 대해 <xref:System.Windows.Forms.LinkLabel> 컨트롤을 사용할 수 있습니다. 텍스트의 일부를 파일, 폴더 또는 웹 페이지에 대 한 링크로 설정할 수도 있습니다.  
  
## <a name="what-you-can-do-with-the-linklabel-control"></a>LinkLabel 컨트롤을 사용 하 여 수행할 수 있는 작업  
 <xref:System.Windows.Forms.Label> 컨트롤의 모든 속성, 메서드 및 이벤트 외에도 <xref:System.Windows.Forms.LinkLabel> 컨트롤에는 하이퍼링크 및 링크 색에 대 한 속성이 있습니다. <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 속성은 링크를 활성화 하는 텍스트 영역을 설정 합니다. <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>및 <xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A> 속성은 링크의 색을 설정 합니다. <xref:System.Windows.Forms.LinkLabel.LinkClicked> 이벤트는 링크 텍스트가 선택 될 때 수행 되는 작업을 결정 합니다.  
  
 <xref:System.Windows.Forms.LinkLabel> 컨트롤을 가장 간단 하 게 사용 하는 것은 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 속성을 사용 하 여 단일 링크를 표시 하는 것 이지만 <xref:System.Windows.Forms.LinkLabel.Links%2A> 속성을 사용 하 여 여러 하이퍼링크를 표시할 수도 있습니다. <xref:System.Windows.Forms.LinkLabel.Links%2A> 속성을 사용 하 여 링크 컬렉션에 액세스할 수 있습니다. 각 개별 <xref:System.Windows.Forms.LinkLabel.Link> 개체의 <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> 속성에 데이터를 지정할 수도 있습니다. <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> 속성의 값을 사용 하 여 표시할 파일의 위치를 저장 하거나 웹 사이트의 주소를 저장할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.LinkLabel>
- [Label 컨트롤 개요](label-control-overview-windows-forms.md)
- [방법: Windows Forms LinkLabel 컨트롤을 사용하여 개체 또는 웹 페이지에 연결](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [방법: Windows Forms LinkLabel 컨트롤의 모양 변경](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
