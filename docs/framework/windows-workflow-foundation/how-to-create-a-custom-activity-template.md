---
description: '자세히 알아보기: 방법: 사용자 지정 활동 템플릿 만들기'
title: '방법: 사용자 지정 작업 템플릿 만들기'
ms.date: 03/30/2017
ms.assetid: 6760a5cc-6eb8-465f-b4fa-f89b39539429
ms.openlocfilehash: 06fda953110e36e46a91fda8697aadbcd6e6bf59
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99742110"
---
# <a name="how-to-create-a-custom-activity-template"></a><span data-ttu-id="3d471-103">방법: 사용자 지정 작업 템플릿 만들기</span><span class="sxs-lookup"><span data-stu-id="3d471-103">How to: Create a Custom Activity Template</span></span>

<span data-ttu-id="3d471-104">사용자 지정 활동 템플릿은 사용자가 각 활동을 개별적으로 만들지 않고 속성 및 기타 설정을 수동으로 구성하지 않아도 되도록 사용자 지정 복합 활동을 비롯한 여러 활동의 구성을 사용자 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d471-104">Custom activity templates are used to customize the configuration of activities, including custom composite activities, so that users do not have to create each activity individually and configure their properties and other settings manually.</span></span> <span data-ttu-id="3d471-105">이러한 사용자 지정 템플릿은 Windows 워크플로 디자이너 또는 다시 호스팅된 **디자이너에서 사용할** 수 있으며, 사용자가 미리 구성 된 디자인 화면으로 끌어 올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d471-105">These custom templates can be made available in the **Toolbox** on the Windows Workflow Designer or from a rehosted designer, from which users can drag them onto the preconfigured design surface.</span></span> <span data-ttu-id="3d471-106">워크플로 디자이너는 [메시징 활동 디자이너](/visualstudio/workflow-designer/messaging-activity-designers) 범주의 [SendAndReceiveReply 템플릿 디자이너](/visualstudio/workflow-designer/sendandreceivereply-template-designer) 와 [ReceiveAndSendReply 템플릿 디자이너](/visualstudio/workflow-designer/receiveandsendreply-template-designer) 와 같은 템플릿의 좋은 예를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d471-106">Workflow Designer ships with good examples of such templates: the [SendAndReceiveReply Template Designer](/visualstudio/workflow-designer/sendandreceivereply-template-designer) and the [ReceiveAndSendReply Template Designer](/visualstudio/workflow-designer/receiveandsendreply-template-designer) in the [Messaging Activity Designers](/visualstudio/workflow-designer/messaging-activity-designers) category.</span></span>

 <span data-ttu-id="3d471-107">이 항목의 첫 번째 절차에서는 **Delay** 활동에 대 한 사용자 지정 활동 템플릿을 만드는 방법에 대해 설명 하 고, 두 번째 절차에서는 워크플로 디자이너에서 사용 가능 하도록 설정 하 여 사용자 지정 템플릿이 작동 하는지 확인 하는 방법을 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d471-107">The first procedure in this topic describes how to create a custom activity template for a **Delay** activity and the second procedure describes briefly how to make it available in a Workflow Designer to verify that the custom template works.</span></span>

 <span data-ttu-id="3d471-108">사용자 지정 활동 템플릿은 <xref:System.Activities.Presentation.IActivityTemplateFactory>를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d471-108">Custom activity templates must implement the <xref:System.Activities.Presentation.IActivityTemplateFactory>.</span></span> <span data-ttu-id="3d471-109">인터페이스에는 템플릿에 사용되는 활동 인스턴스를 만들고 구성할 수 있는 단일 <xref:System.Activities.Presentation.IActivityTemplateFactory.Create%2A> 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d471-109">The interface has a single <xref:System.Activities.Presentation.IActivityTemplateFactory.Create%2A> method with which you can create and configure the activity instances used in the template.</span></span>

## <a name="to-create-a-template-for-the-delay-activity"></a><span data-ttu-id="3d471-110">Delay 활동에 대한 템플릿을 만들려면</span><span class="sxs-lookup"><span data-stu-id="3d471-110">To create a template for the Delay activity</span></span>

1. <span data-ttu-id="3d471-111">Visual Studio 2010을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3d471-111">Start Visual Studio 2010.</span></span>

2. <span data-ttu-id="3d471-112">**파일** 메뉴에서 **새로 만들기** 를 가리킨 다음 **프로젝트** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3d471-112">On the **File** menu, point to **New**, and then select **Project**.</span></span>

     <span data-ttu-id="3d471-113">**새 프로젝트** 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="3d471-113">The **New Project** dialog box opens.</span></span>

3. <span data-ttu-id="3d471-114">**프로젝트 형식** 창에서 **Visual c #** 프로젝트 또는 언어 기본 설정에 따라 그룹화 **Visual Basic** 에서 **워크플로** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d471-114">In the **Project Types** pane, select **Workflow** from either the **Visual C#** projects or **Visual Basic** groupings depending on your language preference.</span></span>

4. <span data-ttu-id="3d471-115">**템플릿** 창에서 **활동 라이브러리** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d471-115">In the **Templates** pane, select **Activity Library**.</span></span>

5. <span data-ttu-id="3d471-116">**이름** 상자에서 `DelayActivityTemplate`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3d471-116">In the **Name** box, enter `DelayActivityTemplate`.</span></span>

6. <span data-ttu-id="3d471-117">**위치** 및 **솔루션 이름** 텍스트 상자에서 기본값을 그대로 적용 하 고 **확인** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d471-117">Accept the defaults in the **Location** and **Solution name** text boxes, and then click **OK**.</span></span>

7. <span data-ttu-id="3d471-118">**솔루션 탐색기** 에서 DelayActivityTemplate 프로젝트의 References 디렉터리를 마우스 오른쪽 단추로 클릭 하 고 **참조 추가** 를 선택 하 여 **참조 추가** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3d471-118">Right-click the References directory of the DelayActivityTemplate project in **Solution Explorer** and choose **Add Reference** to open the **Add Reference** dialog box.</span></span>

8. <span data-ttu-id="3d471-119">**.Net** 탭으로 이동 하 고 왼쪽의 **구성 요소 이름** 열에서 **PresentationFramework** 를 선택 하 고 **확인** 을 클릭 하 여 PresentationFramework.dll 파일에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d471-119">Go to the **.NET** tab and select **PresentationFramework** from the **Component Name** column on the left and click **OK** to add a reference to the PresentationFramework.dll file.</span></span>

9. <span data-ttu-id="3d471-120">이 절차를 반복하여 System.Activities.Presentation.dll 및 WindowsBase.dll 파일에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3d471-120">Repeat this procedure to add references to the System.Activities.Presentation.dll and the WindowsBase.dll files.</span></span>

10. <span data-ttu-id="3d471-121">**솔루션 탐색기** 에서 DelayActivityTemplate 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **추가** 를 선택한 다음 **새 항목** 을 선택 하 여 **새 항목 추가** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3d471-121">Right-click the DelayActivityTemplate project in **Solution Explorer** and choose **Add** and then **New Item** to open the **Add New Item** dialog box.</span></span>

11. <span data-ttu-id="3d471-122">**클래스** 템플릿을 선택 하 고 이름을 MyDelayTemplate으로 지정한 다음 **확인** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d471-122">Select the **Class** template, name it MyDelayTemplate, and then click **OK**.</span></span>

12. <span data-ttu-id="3d471-123">MyDelayTemplate.cs 파일을 열고 다음 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3d471-123">Open the MyDelayTemplate.cs file and add the following statements.</span></span>

    ```csharp
    //Namespaces added
    using System.Activities;
    using System.Activities.Statements;
    using System.Activities.Presentation;
    using System.Windows;
    ```

13. <span data-ttu-id="3d471-124">다음 코드를 사용하여 <xref:System.Activities.Presentation.IActivityTemplateFactory> 클래스를 통해 `MyDelayActivity`를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="3d471-124">Implement the <xref:System.Activities.Presentation.IActivityTemplateFactory> with the `MyDelayActivity` class with the following code.</span></span> <span data-ttu-id="3d471-125">그러면 지연 기간이 10초로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d471-125">This configures the delay to have a duration of 10 seconds.</span></span>

    ```csharp
    public sealed class MyDelayActivity : IActivityTemplateFactory
    {
        public Activity Create(System.Windows.DependencyObject target)
        {
            return new System.Activities.Statements.Delay
            {
                DisplayName = "DelayActivityTemplate",
                Duration = new TimeSpan(0, 0, 10)

            };
        }
    }
    ```

14. <span data-ttu-id="3d471-126">**빌드** 메뉴에서 **솔루션 빌드** 를 선택 하 여 DelayActivityTemplate.dll 파일을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d471-126">Select **Build Solution** from the **Build** menu to generate the DelayActivityTemplate.dll file.</span></span>

### <a name="to-make-the-template-available-in-a-workflow-designer"></a><span data-ttu-id="3d471-127">워크플로 디자이너에서 템플릿을 사용할 수 있도록 하려면</span><span class="sxs-lookup"><span data-stu-id="3d471-127">To make the template available in a Workflow Designer</span></span>

1. <span data-ttu-id="3d471-128">**솔루션 탐색기** 에서 DelayActivityTemplate 솔루션을 마우스 오른쪽 단추로 클릭 하 고 **추가** 를 선택한 다음 **새 프로젝트** 를 선택 하 여 **새 프로젝트 추가** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3d471-128">Right-click the DelayActivityTemplate solution in **Solution Explorer** and choose **Add** and then **New Project** to open the **Add New Project** dialog box.</span></span>

2. <span data-ttu-id="3d471-129">**워크플로 콘솔 응용 프로그램** 템플릿을 선택 하 고 이름을 `CustomActivityTemplateApp` 로 지정한 다음 **확인** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d471-129">Select the **Workflow Console Application** template, name it `CustomActivityTemplateApp`, and then click **OK**.</span></span>

3. <span data-ttu-id="3d471-130">**솔루션 탐색기** 에서 Customactivity템플릿 앱 프로젝트의 References 디렉터리를 마우스 오른쪽 단추로 클릭 하 고 **참조 추가** 를 선택 하 여 **참조 추가** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3d471-130">Right-click the References directory of the CustomActivityTemplateApp project in **Solution Explorer** and choose **Add Reference** to open the **Add Reference** dialog box.</span></span>

4. <span data-ttu-id="3d471-131">**프로젝트** 탭으로 이동 하 여 왼쪽의 **프로젝트 이름** 열에서 **Delayactivitytemplate** 을 선택 하 고 **확인** 을 클릭 하 여 첫 번째 절차에서 만든 DelayActivityTemplate.dll 파일에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d471-131">Go to the **Projects** tab and select **DelayActivityTemplate** from the **Project Name** column on the left and click **OK** to add a reference to the DelayActivityTemplate.dll file that you created in the first procedure.</span></span>

5. <span data-ttu-id="3d471-132">**솔루션 탐색기** 에서 Customactivity템플릿 앱 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **빌드** 를 선택 하 여 응용 프로그램을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="3d471-132">Right-click the CustomActivityTemplateApp project in **Solution Explorer** and choose **Build** to compile the application.</span></span>

6. <span data-ttu-id="3d471-133">**솔루션 탐색기** 에서 Customactivity템플릿 앱 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **시작 프로젝트로 설정** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d471-133">Right-click the CustomActivityTemplateApp project in **Solution Explorer** and choose **Set as Startup Project**.</span></span>

7. <span data-ttu-id="3d471-134">**디버그** 메뉴에서 **디버깅 하지 않고 시작** 을 선택 하 고 cmd.exe 창에서 메시지가 표시 되 면 아무 키나 눌러 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d471-134">Select **Start Without Debugging** from the **Debug** menu and press any key to continue when prompted from the cmd.exe window.</span></span>

8. <span data-ttu-id="3d471-135">Workflow1.vb 파일을 열고 **도구 상자** 를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3d471-135">Open the Workflow1.xaml file and open the **Toolbox**.</span></span>

9. <span data-ttu-id="3d471-136">**Delayactivitytemplate** 범주에서 **mydelayactivity** 템플릿을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d471-136">Locate the **MyDelayActivity** template in the **DelayActivityTemplate** category.</span></span> <span data-ttu-id="3d471-137">디자인 화면으로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="3d471-137">Drag it onto the design surface.</span></span> <span data-ttu-id="3d471-138">**속성 창에서** `Duration` 속성이 10 초로 설정 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d471-138">Confirm in the **Properties** window that the `Duration` property has been set to 10 seconds.</span></span>

## <a name="example"></a><span data-ttu-id="3d471-139">예제</span><span class="sxs-lookup"><span data-stu-id="3d471-139">Example</span></span>

 <span data-ttu-id="3d471-140">MyDelayActivity.cs 파일에 다음 코드가 들어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d471-140">The MyDelayActivity.cs file should contain the following code.</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;

//Namespaces added
using System.Activities;
using System.Activities.Statements;
using System.Activities.Presentation;
using System.Windows;

namespace DelayActivityTemplate
{
    public sealed class MyDelayActivity : IActivityTemplateFactory
    {
        public Activity Create(System.Windows.DependencyObject target)
        {
            return new System.Activities.Statements.Delay
            {
                DisplayName = "DelayActivityTemplate",
                Duration = new TimeSpan(0, 0, 10)

            };
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="3d471-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3d471-141">See also</span></span>

- <xref:System.Activities.Presentation.IActivityTemplateFactory>
- [<span data-ttu-id="3d471-142">워크플로 디자인 환경 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="3d471-142">Customizing the Workflow Design Experience</span></span>](customizing-the-workflow-design-experience.md)
