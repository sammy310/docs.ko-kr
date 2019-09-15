---
title: '방법: 사용자 지정 작업 템플릿 만들기'
ms.date: 03/30/2017
ms.assetid: 6760a5cc-6eb8-465f-b4fa-f89b39539429
ms.openlocfilehash: 4ec84658dbe3039a4d7d714f8da183e6a5eb6ca4
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2019
ms.locfileid: "70989706"
---
# <a name="how-to-create-a-custom-activity-template"></a><span data-ttu-id="3fcb0-102">방법: 사용자 지정 작업 템플릿 만들기</span><span class="sxs-lookup"><span data-stu-id="3fcb0-102">How to: Create a Custom Activity Template</span></span>

<span data-ttu-id="3fcb0-103">사용자 지정 활동 템플릿은 사용자가 각 활동을 개별적으로 만들지 않고 속성 및 기타 설정을 수동으로 구성하지 않아도 되도록 사용자 지정 복합 활동을 비롯한 여러 활동의 구성을 사용자 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-103">Custom activity templates are used to customize the configuration of activities, including custom composite activities, so that users do not have to create each activity individually and configure their properties and other settings manually.</span></span> <span data-ttu-id="3fcb0-104">이러한 사용자 지정 템플릿은의 [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] **도구 상자** 또는 다시 호스팅된 디자이너에서 사용할 수 있으며, 사용자가 미리 구성 된 디자인 화면으로 끌어 올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-104">These custom templates can be made available in the **Toolbox** on the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] or from a rehosted designer, from which users can drag them onto the preconfigured design surface.</span></span> [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]<span data-ttu-id="3fcb0-105">에는 [메시징 활동 디자이너](/visualstudio/workflow-designer/messaging-activity-designers) 범주의 [SendAndReceiveReply 템플릿 디자이너](/visualstudio/workflow-designer/sendandreceivereply-template-designer) 와 [ReceiveAndSendReply 템플릿 디자이너](/visualstudio/workflow-designer/receiveandsendreply-template-designer) 와 같은 템플릿의 좋은 예가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-105">ships with good examples of such templates: the [SendAndReceiveReply Template Designer](/visualstudio/workflow-designer/sendandreceivereply-template-designer) and the [ReceiveAndSendReply Template Designer](/visualstudio/workflow-designer/receiveandsendreply-template-designer) in the [Messaging Activity Designers](/visualstudio/workflow-designer/messaging-activity-designers) category.</span></span>

 <span data-ttu-id="3fcb0-106">이 항목의 첫 번째 절차에서는 **Delay** 활동에 대 한 사용자 지정 활동 템플릿을 만드는 방법에 대해 설명 하 고, [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] 두 번째 절차에서는에서 사용자 지정 템플릿이 작동 하는지 확인 하는 데 사용할 수 있도록 하는 방법을 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-106">The first procedure in this topic describes how to create a custom activity template for a **Delay** activity and the second procedure describes briefly how to make it available in a [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] to verify that the custom template works.</span></span>

 <span data-ttu-id="3fcb0-107">사용자 지정 활동 템플릿은 <xref:System.Activities.Presentation.IActivityTemplateFactory>를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-107">Custom activity templates must implement the <xref:System.Activities.Presentation.IActivityTemplateFactory>.</span></span> <span data-ttu-id="3fcb0-108">인터페이스에는 템플릿에 사용되는 활동 인스턴스를 만들고 구성할 수 있는 단일 <xref:System.Activities.Presentation.IActivityTemplateFactory.Create%2A> 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-108">The interface has a single <xref:System.Activities.Presentation.IActivityTemplateFactory.Create%2A> method with which you can create and configure the activity instances used in the template.</span></span>

## <a name="to-create-a-template-for-the-delay-activity"></a><span data-ttu-id="3fcb0-109">Delay 활동에 대한 템플릿을 만들려면</span><span class="sxs-lookup"><span data-stu-id="3fcb0-109">To create a template for the Delay activity</span></span>

1. <span data-ttu-id="3fcb0-110">Visual Studio 2010을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-110">Start Visual Studio 2010.</span></span>

2. <span data-ttu-id="3fcb0-111">**파일** 메뉴에서 **새로 만들기**를 가리킨 다음, **프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-111">On the **File** menu, point to **New**, and then select **Project**.</span></span>

     <span data-ttu-id="3fcb0-112">**새 프로젝트** 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-112">The **New Project** dialog box opens.</span></span>

3. <span data-ttu-id="3fcb0-113">**프로젝트 형식** 창에서 언어 기본 설정에 따라  **C# 시각적** 프로젝트 또는 **Visual Basic** 그룹에서 **워크플로** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-113">In the **Project Types** pane, select **Workflow** from either the **Visual C#** projects or **Visual Basic** groupings depending on your language preference.</span></span>

4. <span data-ttu-id="3fcb0-114">**템플릿** 창에서 **활동 라이브러리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-114">In the **Templates** pane, select **Activity Library**.</span></span>

5. <span data-ttu-id="3fcb0-115">**이름** 상자에을 입력 `DelayActivityTemplate`합니다.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-115">In the **Name** box, enter `DelayActivityTemplate`.</span></span>

6. <span data-ttu-id="3fcb0-116">**위치** 및 **솔루션 이름** 텍스트 상자에서 기본값을 그대로 적용 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-116">Accept the defaults in the **Location** and **Solution name** text boxes, and then click **OK**.</span></span>

7. <span data-ttu-id="3fcb0-117">**솔루션 탐색기** 에서 DelayActivityTemplate 프로젝트의 References 디렉터리를 마우스 오른쪽 단추로 클릭 하 고 **참조 추가** 를 선택 하 여 **참조 추가** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-117">Right-click the References directory of the DelayActivityTemplate project in **Solution Explorer** and choose **Add Reference** to open the **Add Reference** dialog box.</span></span>

8. <span data-ttu-id="3fcb0-118">**.Net** 탭으로 이동 하 고 왼쪽의 **구성 요소 이름** 열에서 **PresentationFramework** 를 선택 하 고 **확인** 을 클릭 하 여 PresentationFramework 파일에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-118">Go to the **.NET** tab and select **PresentationFramework** from the **Component Name** column on the left and click **OK** to add a reference to the PresentationFramework.dll file.</span></span>

9. <span data-ttu-id="3fcb0-119">이 절차를 반복하여 System.Activities.Presentation.dll 및 WindowsBase.dll 파일에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-119">Repeat this procedure to add references to the System.Activities.Presentation.dll and the WindowsBase.dll files.</span></span>

10. <span data-ttu-id="3fcb0-120">**솔루션 탐색기** 에서 DelayActivityTemplate 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **추가** 를 선택한 다음 **새 항목** 을 선택 하 여 **새 항목 추가** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-120">Right-click the DelayActivityTemplate project in **Solution Explorer** and choose **Add** and then **New Item** to open the **Add New Item** dialog box.</span></span>

11. <span data-ttu-id="3fcb0-121">**클래스** 템플릿을 선택 하 고 이름을 MyDelayTemplate으로 지정한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-121">Select the **Class** template, name it MyDelayTemplate, and then click **OK**.</span></span>

12. <span data-ttu-id="3fcb0-122">MyDelayTemplate.cs 파일을 열고 다음 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-122">Open the MyDelayTemplate.cs file and add the following statements.</span></span>

    ```csharp
    //Namespaces added
    using System.Activities;
    using System.Activities.Statements;
    using System.Activities.Presentation;
    using System.Windows;
    ```

13. <span data-ttu-id="3fcb0-123">다음 코드를 사용하여 <xref:System.Activities.Presentation.IActivityTemplateFactory> 클래스를 통해 `MyDelayActivity`를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-123">Implement the <xref:System.Activities.Presentation.IActivityTemplateFactory> with the `MyDelayActivity` class with the following code.</span></span> <span data-ttu-id="3fcb0-124">그러면 지연 기간이 10초로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-124">This configures the delay to have a duration of 10 seconds.</span></span>

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

14. <span data-ttu-id="3fcb0-125">**빌드** 메뉴에서 **솔루션 빌드** 를 선택 하 여 delayactivitytemplate .dll 파일을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-125">Select **Build Solution** from the **Build** menu to generate the DelayActivityTemplate.dll file.</span></span>

### <a name="to-make-the-template-available-in-a-workflow-designer"></a><span data-ttu-id="3fcb0-126">워크플로 디자이너에서 템플릿을 사용할 수 있도록 하려면</span><span class="sxs-lookup"><span data-stu-id="3fcb0-126">To make the template available in a Workflow Designer</span></span>

1. <span data-ttu-id="3fcb0-127">**솔루션 탐색기** 에서 DelayActivityTemplate 솔루션을 마우스 오른쪽 단추로 클릭 하 고 **추가** 를 선택한 다음 **새 프로젝트** 를 선택 하 여 **새 프로젝트 추가** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-127">Right-click the DelayActivityTemplate solution in **Solution Explorer** and choose **Add** and then **New Project** to open the **Add New Project** dialog box.</span></span>

2. <span data-ttu-id="3fcb0-128">**워크플로 콘솔 응용 프로그램** 템플릿을 선택 하 고 이름을 `CustomActivityTemplateApp`로 지정한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-128">Select the **Workflow Console Application** template, name it `CustomActivityTemplateApp`, and then click **OK**.</span></span>

3. <span data-ttu-id="3fcb0-129">**솔루션 탐색기** 에서 Customactivity템플릿 앱 프로젝트의 References 디렉터리를 마우스 오른쪽 단추로 클릭 하 고 **참조 추가** 를 선택 하 여 **참조 추가** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-129">Right-click the References directory of the CustomActivityTemplateApp project in **Solution Explorer** and choose **Add Reference** to open the **Add Reference** dialog box.</span></span>

4. <span data-ttu-id="3fcb0-130">**프로젝트** 탭으로 이동 하 여 왼쪽의 **프로젝트 이름** 열에서 **Delayactivitytemplate** 을 선택 하 고 **확인** 을 클릭 하 여 첫 번째 절차에서 만든 delayactivitytemplate .dll 파일에 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-130">Go to the **Projects** tab and select **DelayActivityTemplate** from the **Project Name** column on the left and click **OK** to add a reference to the DelayActivityTemplate.dll file that you created in the first procedure.</span></span>

5. <span data-ttu-id="3fcb0-131">**솔루션 탐색기** 에서 Customactivity템플릿 앱 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **빌드** 를 선택 하 여 응용 프로그램을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-131">Right-click the CustomActivityTemplateApp project in **Solution Explorer** and choose **Build** to compile the application.</span></span>

6. <span data-ttu-id="3fcb0-132">**솔루션 탐색기** 에서 Customactivity템플릿 앱 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **시작 프로젝트로 설정**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-132">Right-click the CustomActivityTemplateApp project in **Solution Explorer** and choose **Set as Startup Project**.</span></span>

7. <span data-ttu-id="3fcb0-133">**디버그** 메뉴에서 **디버깅 하지 않고 시작** 을 선택 하 고 cmd.exe 창에서 메시지가 표시 되 면 아무 키나 눌러 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-133">Select **Start Without Debugging** from the **Debug** menu and press any key to continue when prompted from the cmd.exe window.</span></span>

8. <span data-ttu-id="3fcb0-134">Workflow1.vb 파일을 열고 **도구 상자**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-134">Open the Workflow1.xaml file and open the **Toolbox**.</span></span>

9. <span data-ttu-id="3fcb0-135">**Delayactivitytemplate** 범주에서 **mydelayactivity** 템플릿을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-135">Locate the **MyDelayActivity** template in the **DelayActivityTemplate** category.</span></span> <span data-ttu-id="3fcb0-136">디자인 화면으로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-136">Drag it onto the design surface.</span></span> <span data-ttu-id="3fcb0-137">`Duration` **속성 창에서** 속성이 10 초로 설정 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-137">Confirm in the **Properties** window that the `Duration` property has been set to 10 seconds.</span></span>

## <a name="example"></a><span data-ttu-id="3fcb0-138">예제</span><span class="sxs-lookup"><span data-stu-id="3fcb0-138">Example</span></span>
 <span data-ttu-id="3fcb0-139">MyDelayActivity.cs 파일에 다음 코드가 들어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-139">The MyDelayActivity.cs file should contain the following code.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="3fcb0-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="3fcb0-140">See also</span></span>

- <xref:System.Activities.Presentation.IActivityTemplateFactory>
- [<span data-ttu-id="3fcb0-141">워크플로 디자인 환경 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="3fcb0-141">Customizing the Workflow Design Experience</span></span>](customizing-the-workflow-design-experience.md)
