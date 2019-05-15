---
title: '방법: 사용자 지정 작업 템플릿 만들기'
ms.date: 03/30/2017
ms.assetid: 6760a5cc-6eb8-465f-b4fa-f89b39539429
ms.openlocfilehash: f54a625fbe5497406645ea29f824d361c0392eb3
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65637723"
---
# <a name="how-to-create-a-custom-activity-template"></a>방법: 사용자 지정 작업 템플릿 만들기

사용자 지정 활동 템플릿은 사용자가 각 활동을 개별적으로 만들지 않고 속성 및 기타 설정을 수동으로 구성하지 않아도 되도록 사용자 지정 복합 활동을 비롯한 여러 활동의 구성을 사용자 지정하는 데 사용됩니다. 이러한 사용자 지정 서식 파일에서 사용할 수 있습니다 합니다 **도구 상자** 에 [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] 또는 재 호스트 된 디자이너는 사용자가 끌어 놓을 수는 미리 구성 된 디자인 화면에서 합니다. [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] 이러한 템플릿의 좋은 예제 인와 함께 제공 되: 합니다 [SendAndReceiveReply 템플릿 디자이너](/visualstudio/workflow-designer/sendandreceivereply-template-designer) 하며 [ReceiveAndSendReply 템플릿 디자이너](/visualstudio/workflow-designer/receiveandsendreply-template-designer) 에 [메시징 활동 디자이너](/visualstudio/workflow-designer/messaging-activity-designers) 범주입니다.

 이 항목의 첫 번째 절차에 대 한 사용자 지정 활동 템플릿을 만드는 방법에 설명 합니다는 **지연** 활동과 두 번째 절차에서 사용할 수 있도록 하는 방법을 설명 간단 하 게는 [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] 사용자 지정 템플릿을 작동 하는지 확인 합니다.

 사용자 지정 활동 템플릿은 <xref:System.Activities.Presentation.IActivityTemplateFactory>를 구현해야 합니다. 인터페이스에는 템플릿에 사용되는 활동 인스턴스를 만들고 구성할 수 있는 단일 <xref:System.Activities.Presentation.IActivityTemplateFactory.Create%2A> 메서드가 있습니다.

## <a name="to-create-a-template-for-the-delay-activity"></a>Delay 활동에 대한 템플릿을 만들려면

1. Visual Studio 2010을 시작합니다.

2. **파일** 메뉴에서 **새로 만들기**를 가리킨 다음, **프로젝트**를 선택합니다.

     **새 프로젝트** 대화 상자가 열립니다.

3. 에 **프로젝트 형식** 창 **워크플로** 에서 합니다 **Visual C#** 프로젝트 또는 **Visual Basic** 그룹화에 따라 프로그램 언어 기본 설정 합니다.

4. 에 **템플릿을** 창 **활동 라이브러리**합니다.

5. 에 **이름을** 상자에 입력 `DelayActivityTemplate`합니다.

6. 기본값을 그대로 합니다 **위치** 하 고 **솔루션 이름** 텍스트 상자 및 클릭 한 다음 **확인**합니다.

7. DelayActivityTemplate 프로젝트의 References 디렉터리를 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 선택한 **참조 추가** 열려는 합니다 **참조 추가** 대화 상자.

8. 로 이동 합니다 **.NET** 탭을 선택한 **PresentationFramework** 에서 합니다 **구성 요소 이름** 클릭 왼쪽에 열 **확인** 참조를 추가 하려면 PresentationFramework.dll 파일입니다.

9. 이 절차를 반복하여 System.Activities.Presentation.dll 및 WindowsBase.dll 파일에 대한 참조를 추가합니다.

10. DelayActivityTemplate 프로젝트를 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 선택한 **추가** 차례로 **새 항목** 여는 **새 항목 추가**대화 상자.

11. 선택 된 **클래스** 템플릿 이름을 mydelaytemplate으로 지정한 및 클릭 **확인**합니다.

12. MyDelayTemplate.cs 파일을 열고 다음 문을 추가합니다.

    ```
    //Namespaces added
    using System.Activities;
    using System.Activities.Statements;
    using System.Activities.Presentation;
    using System.Windows;
    ```

13. 다음 코드를 사용하여 <xref:System.Activities.Presentation.IActivityTemplateFactory> 클래스를 통해 `MyDelayActivity`를 구현합니다. 그러면 지연 기간이 10초로 구성됩니다.

    ```
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

14. 선택 **솔루션 빌드** 에서 합니다 **빌드** DelayActivityTemplate.dll 파일을 생성 하는 메뉴입니다.

### <a name="to-make-the-template-available-in-a-workflow-designer"></a>워크플로 디자이너에서 템플릿을 사용할 수 있도록 하려면

1. DelayActivityTemplate 솔루션을 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 선택한 **추가** 차례로 **새 프로젝트** 여는 **새 프로젝트 추가** 대화 상자.

2. 선택 합니다 **워크플로 콘솔 응용 프로그램** 템플릿 이름을 `CustomActivityTemplateApp`를 클릭 하 고 **확인**합니다.

3. CustomActivityTemplateApp 프로젝트의 References 디렉터리를 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 선택한 **참조 추가** 열려는 합니다 **참조 추가** 대화 상자 상자입니다.

4. 로 이동 합니다 **프로젝트** 탭을 선택한 **DelayActivityTemplate** 에서 **프로젝트 이름** 열 왼쪽에 클릭 **확인** 추가할를 첫 번째 절차에서 만든 DelayActivityTemplate.dll 파일에 대 한 참조입니다.

5. CustomActivityTemplateApp 프로젝트를 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 선택한 **빌드** 응용 프로그램을 컴파일할 수 있습니다.

6. CustomActivityTemplateApp 프로젝트를 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 선택한 **시작 프로젝트로 설정**합니다.

7. 선택 **디버깅 하지 않고 시작** 에서 합니다 **디버그** cmd.exe 창에서 메시지가 표시 되 면 계속 하려면 아무 키나 메뉴 및 키를 누릅니다.

8. Workflow1.xaml 파일을 열고 엽니다는 **도구 상자**합니다.

9. 찾을 합니다 **MyDelayActivity** 에서 서식 파일을 **DelayActivityTemplate** 범주. 디자인 화면으로 끌어 옵니다. 확인 합니다 **속성** 창은를 `Duration` 속성이 10 초로 설정 되어 있습니다.

## <a name="example"></a>예제
 MyDelayActivity.cs 파일에 다음 코드가 들어 있어야 합니다.

```
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

## <a name="see-also"></a>참고자료

- <xref:System.Activities.Presentation.IActivityTemplateFactory>
- [워크플로 디자인 환경 사용자 지정](customizing-the-workflow-design-experience.md)
