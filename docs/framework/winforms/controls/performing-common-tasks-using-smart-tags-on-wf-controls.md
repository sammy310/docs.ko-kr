---
title: '연습: Windows Forms 컨트롤에서 스마트 태그를 사용하여 일반 작업 수행'
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
ms.openlocfilehash: 3b20e903ce7eef7c69f55328f459d52537a1e85d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59132069"
---
# <a name="walkthrough-performing-common-tasks-using-smart-tags-on-windows-forms-controls"></a>연습: Windows Forms 컨트롤에서 스마트 태그를 사용하여 일반 작업 수행
Windows Forms 응용 프로그램에 대 한 폼 및 컨트롤을 구성할 때에 반복적으로 수행 하는 많은 작업이 있습니다. 다음은 발생 하는 일반적으로 수행된 하는 작업의 일부입니다.  
  
-   추가 또는 탭에서 제거 된 <xref:System.Windows.Forms.TabControl>합니다.  
  
-   부모 컨트롤을 도킹 합니다.  
  
-   방향 변경 된 <xref:System.Windows.Forms.SplitContainer> 제어 합니다.  
  
 개발 속도 높이려면, 많은 컨트롤 디자인 타임에 단일 제스처로에서 다음과 같은 일반적인 작업을 수행할 수 있도록 하는 상황에 맞는 메뉴가 있는 스마트 태그를 제공 합니다. 이러한 작업 이라고 *스마트 태그 동사*합니다.  
  
 스마트 태그의 수명 주기 동안 디자이너에서 컨트롤 인스턴스를 연결 된 상태로 유지 하며 항상 사용할 수입니다.  
  
 이 연습에서 설명하는 작업은 다음과 같습니다.  
  
-   Windows Forms 프로젝트 만들기  
  
-   스마트 태그를 사용 하 여  
  
-   사용 하도록 설정 하 고 스마트 태그를 사용 하지 않도록 설정  
  
 작업을 완료하면 이러한 중요한 레이아웃 기능이 수행하는 역할을 이해하게 됩니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
## <a name="creating-the-project"></a>프로젝트 만들기  
 첫 번째 단계는 프로젝트를 만들고 폼을 설정하는 것입니다.  
  
#### <a name="to-create-the-project"></a>프로젝트를 만들려면  
  
1.  "SmartTagsExample" 이라는 Windows 기반 응용 프로그램 프로젝트를 만듭니다 (**파일** > **새로 만들기** > **프로젝트**  >   **Visual C#** 나 **Visual Basic** > **클래식 바탕 화면** > **Windows Forms 응용 프로그램**).  
  
2.  폼을 선택 합니다 **Windows Forms 디자이너**합니다.  
  
## <a name="using-smart-tags"></a>스마트 태그를 사용 하 여  
 스마트 태그는 항상 사용자에 게 제공 하는 컨트롤에 디자인 타임에 사용할 수 있습니다.  
  
#### <a name="to-use-smart-tags"></a>스마트 태그를 사용 하려면  
  
1.  끌어서를 <xref:System.Windows.Forms.TabControl> 에서 합니다 **도구 상자** 폼입니다. 스마트 태그 문자 모양을 확인 (![스마트 태그 문자 모양](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))의 측면에 표시 되는 <xref:System.Windows.Forms.TabControl>합니다.  
  
2.  스마트 태그 문자 모양을 클릭 합니다. 문자 모양이 옆에 나타나는 바로 가기 메뉴에서 선택 합니다 **추가 탭** 항목입니다. 탭 페이지를 새로 추가할 관찰 된 <xref:System.Windows.Forms.TabControl>합니다.  
  
3.  <xref:System.Windows.Forms.TableLayoutPanel> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다.  
  
4.  스마트 태그 문자 모양을 클릭 합니다. 문자 모양이 옆에 나타나는 바로 가기 메뉴에서 선택 합니다 **열 추가** 항목입니다. 새 열을 추가할 관찰 된 <xref:System.Windows.Forms.TableLayoutPanel> 제어 합니다.  
  
5.  <xref:System.Windows.Forms.SplitContainer> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다.  
  
6.  스마트 태그 문자 모양을 클릭 합니다. 문자 모양이 옆에 나타나는 바로 가기 메뉴에서 선택 합니다 **가로 분할자 방향** 항목입니다. 확인 된 <xref:System.Windows.Forms.SplitContainer> 컨트롤의 분할 막대는 이제 가로 방향입니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
- [연습: Windows Forms 구성 요소에 스마트 태그 추가](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171829(v=vs.120))
