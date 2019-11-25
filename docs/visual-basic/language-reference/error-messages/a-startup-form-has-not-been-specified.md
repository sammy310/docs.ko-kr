---
title: 시작 폼이 지정되지 않았습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_NoStartupForm
ms.assetid: 8e04af49-4bef-49de-a7ec-e407e9873da7
ms.openlocfilehash: 301f249e6222c929d2c513964ecbb21df5fbc47f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976187"
---
# <a name="a-startup-form-has-not-been-specified"></a>시작 폼이 지정되지 않았습니다.

응용 프로그램에서 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> 클래스를 사용 하지만 시작 폼을 지정 하지 않습니다.  
  
 프로젝트 디자이너에서 **응용 프로그램 프레임 워크 사용** 확인란이 선택 되어 있지만 **시작 폼** 이 지정 되지 않은 경우이 문제가 발생할 수 있습니다. 자세한 내용은 [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)을 참조하세요.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1. 응용 프로그램에 대 한 시작 개체를 지정 합니다.  
  
     자세한 내용은 [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)을 참조하세요.  
  
2. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> 메서드를 재정의 하 여 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> 속성을 시작 폼으로 설정 합니다.  
  
## <a name="see-also"></a>참조

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>
- [Visual Basic 애플리케이션 모델 개요](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)
