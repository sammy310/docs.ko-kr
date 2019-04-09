---
title: '방법: Windows Forms에서 컨트롤 잠금'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, locking
- controls [Windows Forms], locking
ms.assetid: 94efe0d2-c14e-4d14-b903-63ea9b07e290
ms.openlocfilehash: ac02e825218f14f8479e67a79da0c86e1c9ffe11
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117925"
---
# <a name="how-to-lock-controls-to-windows-forms"></a>방법: Windows Forms에서 컨트롤 잠금
Windows 응용 프로그램의 사용자 인터페이스 (UI)를 디자인할 때 수행 하지 않도록 이동 하거나 다른 속성을 설정 하는 경우 크기를 조정할 수 있도록 올바르게 배치 되 면 컨트롤을 잠글 수 있습니다.  
  
 또한 잠금 및 폼에 한 번에 여러 컨트롤을 사용 하 여 양식을 하는 데 도움이 되는 모든 컨트롤을 잠금 해제 하거나 개별 컨트롤을 잠금 해제할 수 있습니다. 하려는 양식의 모든 컨트롤을 배치 했으면, 잘못 된 이동을 방지 하기 위해 모든에서 잠급니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-lock-a-control"></a>컨트롤을 잠그려면  
  
1.  에 **속성** 창 클릭 합니다 **잠금** 속성을 선택 `true`합니다. (이름을 두 번의 속성 설정을 전환 합니다.)  
  
     또는 컨트롤을 마우스 오른쪽 단추로 클릭 하 고 선택 **잠금 컨트롤**합니다.  
  
    > [!NOTE]
    >  컨트롤을 잠그면 디자인 화면에서 새 크기 또는 위치를 끌어 올 하 수 없습니다. 그러나 변경할 수 있습니다 크기를 이용 하 여 컨트롤의 위치를 **속성** 창 또는 코드입니다.  
  
### <a name="to-lock-all-the-controls-on-a-form"></a>양식의 모든 컨트롤을 잠그려면  
  
1.  **형식** 메뉴 선택 **잠금 컨트롤**합니다.  
  
    > [!NOTE]
    >  이 명령은 폼 컨트롤 이므로 폼의 크기를 뿐만 잠급니다.  
  
### <a name="to-unlock-all-locked-controls-on-a-form"></a>모두 잠금 해제 하려면 잠긴 폼의 컨트롤  
  
1.  **형식** 메뉴 선택 **잠금 컨트롤**합니다.  
  
     양식에서 이전에 잠긴된 모든 컨트롤은 이제 잠금 해제 합니다.  
  
### <a name="to-unlock-locked-controls-individually"></a>잠긴된 컨트롤을 개별적으로 잠금을 해제 하려면  
  
1.  에 **속성** 창 클릭 합니다 **잠금** 속성을 선택 `false`합니다. (이름을 두 번의 속성 설정을 전환 합니다.)  
  
## <a name="see-also"></a>참고자료

- [Windows Forms 컨트롤](index.md)
- [Windows Forms에서 컨트롤 정렬](arranging-controls-on-windows-forms.md)
- [개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Windows Forms에 사용할 수 있는 컨트롤](controls-to-use-on-windows-forms.md)
- [기능별 Windows Forms 컨트롤](windows-forms-controls-by-function.md)
