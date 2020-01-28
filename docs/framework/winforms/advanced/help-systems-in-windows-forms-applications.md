---
title: 도움말 시스템
ms.date: 03/30/2017
helpviewer_keywords:
- Help [Windows Forms], adding to Windows applications
- Windows applications [Windows Forms], providing Help systems
- What's This? Help
- Help [Windows Forms], Windows Forms
- HelpProvider component [Windows Forms], providing Help in Windows applications
ms.assetid: 2a96a278-432c-41fc-9e3c-5bfedf5e1267
ms.openlocfilehash: c97a22dbdbdcc0eb282b52e16c4ef40914b1d9e7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742240"
---
# <a name="help-systems-in-windows-forms-applications"></a>Windows Forms 응용 프로그램의 도움말 시스템
응용 프로그램 개발자로 서 가장 중요 한 courtesies 중 하나는 사용자에 게 특정 조항이 불법 도움말 시스템을 제공할 수 있다는 것입니다. 이것이 혼동 되거나 disoriented 될 때 설정 되는 위치입니다. Windows 기반 응용 프로그램에 도움말 시스템을 제공 하는 것은 [HelpProvider 구성 요소](../controls/helpprovider-component-windows-forms.md)를 사용 하 여 쉽게 수행할 수 있습니다.  
  
## <a name="different-types-of-help"></a>다양 한 형식의 도움말  
 Windows Forms <xref:System.Windows.Forms.HelpProvider> 구성 요소는 HTML 도움말 1.x 도움말 파일(HTML Help Workshop으로 생성된 .chm 파일 또는 .htm 파일)을 Windows 기반 애플리케이션에 연결하는 데 사용됩니다. <xref:System.Windows.Forms.HelpProvider> 구성 요소를 사용 하 여 Windows Forms 또는 특정 컨트롤의 컨트롤에 대 한 상황에 맞는 도움말을 제공할 수 있습니다. 또한 <xref:System.Windows.Forms.HelpProvider> 구성 요소는 목차, 인덱스 또는 검색 함수의 기본 페이지와 같은 특정 영역에 대 한 도움말 파일을 열 수 있습니다. <xref:System.Windows.Forms.HelpProvider> 구성 요소에 대 한 일반 정보는 [HelpProvider 구성 요소 개요](../controls/helpprovider-component-overview-windows-forms.md)를 참조 하세요. <xref:System.Windows.Forms.HelpProvider> 구성 요소를 사용 하 여 Windows Forms에 대 한 팝업 도움말을 표시 하는 방법에 대 한 자세한 내용은 [방법: 팝업 도움말 표시](how-to-display-pop-up-help.md)를 참조 하세요. <xref:System.Windows.Forms.ToolTip> 구성 요소를 사용 하 여 컨트롤별 도움말을 표시 하는 방법에 대 한 자세한 내용은 [도구 설명을 사용 하 여 컨트롤 도움말](control-help-using-tooltips.md)을 참조 하세요.  
  
 Html 도움말 워크샵을 사용 하 여 HTML 도움말 1.x 파일을 생성할 수 있습니다. HTML 도움말에 대 한 자세한 내용은 MSDN의 "HTML 도움말 워크숍" 또는 기타 "HTML 도움말" 항목을 참조 하십시오.  
  
## <a name="see-also"></a>참조

- [Windows Forms에 사용자 도움말 통합](integrating-user-help-in-windows-forms.md)
- [HelpProvider 구성 요소](../controls/helpprovider-component-windows-forms.md)
- [ToolTip 구성 요소](../controls/tooltip-component-windows-forms.md)
- [Windows Forms 개요](../windows-forms-overview.md)
- [Windows Forms](../index.md)
