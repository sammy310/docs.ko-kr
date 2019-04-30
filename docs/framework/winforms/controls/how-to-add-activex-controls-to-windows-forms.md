---
title: '방법: Windows Forms에 ActiveX 컨트롤 추가'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
ms.openlocfilehash: 780411949c543a2178de5e7c531bd2202703f27a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011156"
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a>방법: Windows Forms에 ActiveX 컨트롤 추가
Windows Forms 디자이너는 호스트 Windows Forms 컨트롤을 최적화 하는 동안에 Windows Forms에서 ActiveX 컨트롤을 배치할 수 있습니다.  
  
> [!CAUTION]
>  ActiveX 컨트롤에 추가 되 면 Windows Forms에 대 한 성능 제한이 있습니다.  
  
 ActiveX 컨트롤을 폼에 추가한 해당 도구 상자에 추가 해야 합니다. 자세한 내용은 [사용자 지정 도구 상자 대화 상자, COM 구성 요소](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100))합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 클릭합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-add-an-activex-control-to-your-windows-form"></a>Windows 폼에 ActiveX 컨트롤을 추가 하려면  
  
- 도구 상자 컨트롤을 두 번 클릭 합니다.  
  
     Visual Studio 프로젝트에서 컨트롤에 대 한 모든 참조를 추가합니다. Windows Forms에서 ActiveX 컨트롤을 사용 하 여 때 염두 할 사항에 대 한 자세한 내용은 참조 하세요. [Windows Form에서 ActiveX 컨트롤을 호스팅할 때의 고려 사항](considerations-when-hosting-an-activex-control-on-a-windows-form.md)합니다.  
  
    > [!NOTE]
    >  Windows Forms ActiveX 컨트롤 가져오기 (AxImp.exe) ActiveX 동적 링크 라이브러리 가져오기 시 예상 보다 다른 형식의 이벤트 인수를 만듭니다. AxImp.exe에서 만든 인수는 다음과 유사한: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`때 `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` 예상 됩니다. 주의이 불일치로 해도 코드는 정상적으로 작동 합니다. 자세한 내용은 참조 하세요 [Windows Forms ActiveX 컨트롤 가져오기 (Aximp.exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md)합니다.  
  
## <a name="see-also"></a>참고자료

- [Windows Forms 컨트롤](index.md)
- [여러 언어 및 라이브러리에서 사용되는 컨트롤 및 프로그래밍 가능한 개체 비교](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))
- [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)
- [Windows Forms에서 컨트롤 정렬](arranging-controls-on-windows-forms.md)
- [개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Windows Forms에 사용할 수 있는 컨트롤](controls-to-use-on-windows-forms.md)
- [기능별 Windows Forms 컨트롤](windows-forms-controls-by-function.md)
