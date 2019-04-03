---
title: 시작 폼이 지정되지 않았습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_NoStartupForm
ms.assetid: 8e04af49-4bef-49de-a7ec-e407e9873da7
ms.openlocfilehash: 9af95b397bef4a19654510619cf0864c8ab7b76f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58833570"
---
# <a name="a-startup-form-has-not-been-specified"></a><span data-ttu-id="3a78c-102">시작 폼이 지정되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="3a78c-102">A startup form has not been specified</span></span>
<span data-ttu-id="3a78c-103">응용 프로그램을 사용 합니다 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> 클래스 하지만 시작 폼을 지정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a78c-103">The application uses the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> class but does not specify the startup form.</span></span>  
  
 <span data-ttu-id="3a78c-104">하는 경우 발생할 수 있습니다 합니다 **응용 프로그램 프레임 워크 사용** 프로젝트 디자이너에서 확인란을 선택 하지만 **시작 폼** 지정 하지 않으면.</span><span class="sxs-lookup"><span data-stu-id="3a78c-104">This can occur if the **Enable application framework** check box is selected in the project designer but the **Startup form** is not specified.</span></span> <span data-ttu-id="3a78c-105">자세한 내용은 [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a78c-105">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3a78c-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="3a78c-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="3a78c-107">응용 프로그램에 대 한 시작 개체를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a78c-107">Specify a startup object for the application.</span></span>  
  
     <span data-ttu-id="3a78c-108">자세한 내용은 [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a78c-108">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
2.  <span data-ttu-id="3a78c-109">재정의 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> 설정 하는 방법의 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> 속성을 시작 폼입니다.</span><span class="sxs-lookup"><span data-stu-id="3a78c-109">Override the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> method to set the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> property to the startup form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a78c-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="3a78c-110">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>
- [<span data-ttu-id="3a78c-111">Visual Basic 응용 프로그램 모델 개요</span><span class="sxs-lookup"><span data-stu-id="3a78c-111">Overview of the Visual Basic Application Model</span></span>](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)
