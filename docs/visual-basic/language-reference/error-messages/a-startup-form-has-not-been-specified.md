---
description: '에 대 한 자세한 정보: 시작 폼이 지정 되지 않았습니다.'
title: 시작 폼이 지정되지 않았습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_NoStartupForm
ms.assetid: 8e04af49-4bef-49de-a7ec-e407e9873da7
ms.openlocfilehash: 4b00890f07121ef55ce49978842010cc54aba29b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797187"
---
# <a name="a-startup-form-has-not-been-specified"></a><span data-ttu-id="8bf8c-103">시작 폼이 지정되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="8bf8c-103">A startup form has not been specified</span></span>

<span data-ttu-id="8bf8c-104">응용 프로그램에서 클래스를 사용 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> 하지만 시작 폼을 지정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8bf8c-104">The application uses the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> class but does not specify the startup form.</span></span>  
  
 <span data-ttu-id="8bf8c-105">프로젝트 디자이너에서 **응용 프로그램 프레임 워크 사용** 확인란이 선택 되어 있지만 **시작 폼** 이 지정 되지 않은 경우이 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bf8c-105">This can occur if the **Enable application framework** check box is selected in the project designer but the **Startup form** is not specified.</span></span> <span data-ttu-id="8bf8c-106">자세한 내용은 [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8bf8c-106">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8bf8c-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="8bf8c-107">To correct this error</span></span>  
  
1. <span data-ttu-id="8bf8c-108">응용 프로그램에 대 한 시작 개체를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bf8c-108">Specify a startup object for the application.</span></span>  
  
     <span data-ttu-id="8bf8c-109">자세한 내용은 [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8bf8c-109">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
2. <span data-ttu-id="8bf8c-110">메서드를 재정의 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> 하 여 속성을 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> 시작 폼으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bf8c-110">Override the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> method to set the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> property to the startup form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bf8c-111">참조</span><span class="sxs-lookup"><span data-stu-id="8bf8c-111">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>
- [<span data-ttu-id="8bf8c-112">Visual Basic 애플리케이션 모델 개요</span><span class="sxs-lookup"><span data-stu-id="8bf8c-112">Overview of the Visual Basic Application Model</span></span>](../../developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)
