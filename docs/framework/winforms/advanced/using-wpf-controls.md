---
title: WPF 컨트롤 사용
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
ms.openlocfilehash: 24b88e456628c5a0bdc3cded60b0e52a92057851
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61747617"
---
# <a name="using-wpf-controls"></a>WPF 컨트롤 사용
Windows Forms 기반 응용 프로그램에서 Windows Presentation Foundation (WPF) 컨트롤을 사용할 수 있습니다. 이러한 옵션은 두 가지 서로 다른 뷰 기술, 상호 운용 될 원활 하 게 합니다.  
  
 Windows Forms 디자이너에는 Windows Presentation Foundation 컨트롤을 호스팅하기 위한 시각적 디자인 환경을 제공 합니다. WPF 컨트롤 이라고 하는 특수 한 Windows Forms 컨트롤에서 호스팅하는 <xref:System.Windows.Forms.Integration.ElementHost>합니다. 이 컨트롤을 WPF 컨트롤을 폼의 레이아웃에 관여 하는 데 키보드 및 마우스 메시지를 받을 수 있습니다. 디자인 타임에 정렬할 수 있습니다는 <xref:System.Windows.Forms.Integration.ElementHost> 방법과 마찬가지로 모든 Windows Forms 컨트롤을 제어 합니다.  
  
 또한 WPF 기반 응용 프로그램에서 Windows Forms 컨트롤을 사용할 수 있습니다. 자세한 내용은 [Visual Studio에서 XAML 디자인](/visualstudio/designers/designing-xaml-in-visual-studio)합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [방법: 복사 하 고 디자인 타임에 ElementHost 컨트롤을 붙여 넣습니다.](how-to-copy-and-paste-an-elementhost-control-at-design-time.md)  
 Windows Form에 Windows Presentation Foundation 컨트롤을 복사 하는 방법을 보여 줍니다.  
  
 [연습: 디자인 타임에 Windows Forms에서 WPF 콘텐츠 정렬](walkthrough-arranging-wpf-content-on-windows-forms-at-design-time.md)  
 Windows Presentation Foundation 컨트롤을 정렬 하려면 고정 및 맞춤선 등의 Windows Forms 레이아웃 기능을 사용 하는 방법을 보여 줍니다.
  
 [연습: 디자인 타임에 Windows Forms에서 새 WPF 콘텐츠 만들기](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)  
 Windows Forms 기반 응용 프로그램에서 사용 하기 위해 Windows Presentation Foundation 컨트롤을 만드는 방법을 보여 줍니다.
  
 [연습: 디자인 타임에 Windows Forms에서 WPF 콘텐츠 할당](walkthrough-assigning-wpf-content-on-windows-forms-at-design-time.md)  
 폼에 표시 하려는 Windows Presentation Foundation 컨트롤 유형을 선택 하는 방법을 보여 줍니다.  
  
 [연습: WPF 콘텐츠 스타일 지정](walkthrough-styling-wpf-content.md)  
 Windows Forms 디자이너 간의 워크플로 보여 줍니다. 및 [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] Windows Presentation Foundation 컨트롤에 스타일을 적용 합니다.  
  
## <a name="reference"></a>참조  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 Windows Forms 기반 응용 프로그램에서 호스트 Windows Presentation Foundation 컨트롤에 사용할 수 있는 클래스를 설명 합니다.  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 Windows Presentation Foundation 기반 응용 프로그램에서 호스트 Windows Forms 컨트롤에 사용할 수 있는 클래스를 설명 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [마이그레이션 및 상호 운용성](../../wpf/advanced/migration-and-interoperability.md)  
 Windows Presentation Foundation 및 Windows Forms 기술 간의 상호 운용성을 설명합니다.  
  
 [Visual Studio에서 XAML 디자인](/visualstudio/designers/designing-xaml-in-visual-studio)  
 Visual Studio에서 Windows Presentation Foundation 컨트롤을 디자인 하는 방법에 설명 합니다.
