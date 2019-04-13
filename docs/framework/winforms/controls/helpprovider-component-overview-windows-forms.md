---
title: HelpProvider 구성 요소 개요(Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- HelpProvider
helpviewer_keywords:
- HelpProvider component [Windows Forms], about HelpProvider component
- Help [Windows Forms], adding to Windows applications
- F1 Help [Windows Forms], adding to Windows Forms
- dialog boxes [Windows Forms], context-sensitive Help
- Windows Forms, context-sensitive Help
ms.assetid: 6b10c2cc-c577-4cb5-9669-e37b33416af9
ms.openlocfilehash: 177b61cab99d21a844298632020244fa424d8d2a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59176581"
---
# <a name="helpprovider-component-overview-windows-forms"></a>HelpProvider 구성 요소 개요(Windows Forms)
Windows Forms [HelpProvider](helpprovider-component-windows-forms.md) 구성 요소는 Windows 응용 프로그램을 사용 하 여 HTML 도움말 1.x 도움말 파일 (HTML Help Workshop으로 생성 된.chm 파일 또는.htm 파일)를 연결할 때 사용 됩니다. 다양 한 방법에에서 대 한 도움말을 제공할 수 있습니다.  
  
-   Windows Forms에서 컨트롤에 대 한 상황에 맞는 도움말을 제공 합니다.  
  
-   특정 대화 상자 또는 대화 상자에서 특정 컨트롤에서 상황에 맞는 도움말을 제공 합니다.  
  
-   도움말 파일을 목차, 색인 또는 검색 기능을의 기본 페이지 등의 특정 영역을 엽니다.  
  
## <a name="using-the-help-provider"></a>Help Provider를 사용 하 여  
 추가 <xref:System.Windows.Forms.HelpProvider> Windows 폼에 구성 요소에는 다른 컨트롤의 도움말 속성을 노출 하는 폼에 허용 된 <xref:System.Windows.Forms.HelpProvider> 구성 요소입니다. 이 옵션을 사용 하면 Windows 폼의 컨트롤에 대 한 도움말을 제공할 수 있습니다. 사용 하 여 도움말 파일을 연결할 수 있습니다 합니다 <xref:System.Windows.Forms.HelpProvider> 구성 요소를 사용 하 여는 <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> 속성입니다. 호출 하 여 제공 된 도움말의 형식을 지정할 <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> 의 값을 제공 하는 <xref:System.Windows.Forms.HelpNavigator> 지정된 된 컨트롤에 대 한 열거형입니다. 호출 하 여 도움말에 대 한 키워드 또는 항목을 제공 합니다 <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> 메서드.  
  
 필요에 따라 다른 컨트롤을 사용 하 여 특정 도움말 문자열을 연결 하려면 사용 된 <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> 메서드. 이 메서드를 사용 하는 컨트롤을 사용 하 여 연결 하는 문자열은 컨트롤에 포커스가 있는 동안 사용자가 F1 키를 누를 때 팝업 창에 표시 됩니다.  
  
 하는 경우 <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> 를 사용 해야 설정 되지 않은 <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> 도움말 텍스트를 제공 합니다. 모두 설정한 경우 <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> 도움말 문자열에 따라 도움말 및 <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> 우선 적용 됩니다.  
  
> [!NOTE]
>  도움말 파일의 경로를 지정 하는 경우에 상대 경로 사용 하 여 문제를 발생할 수 있습니다는 <xref:System.Windows.Forms.Help.ShowHelp%2A> 메서드 또는 <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> 의 속성을 <xref:System.Windows.Forms.HelpProvider> 컨트롤입니다. 이와 같이 절대 파일 경로 사용 하 여 도움말 파일을 지정 해야 합니다.  
  
## <a name="see-also"></a>참고자료

- [Windows Forms 응용 프로그램의 도움말 시스템](../advanced/help-systems-in-windows-forms-applications.md)
