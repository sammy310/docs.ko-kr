---
description: '자세한 정보: 작업 3: 도구 상자 및 PropertyGrid 창 만들기'
title: '작업 3: 도구 상자 및 PropertyGrid 창 만들기'
ms.date: 03/30/2017
ms.assetid: 72c1546a-eed5-4f0f-a616-719a163414f4
ms.openlocfilehash: c07bfc2f974018cb0d789a6cc1181f9bed861382
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755164"
---
# <a name="task-3-create-the-toolbox-and-propertygrid-panes"></a>작업 3: 도구 상자 및 PropertyGrid 창 만들기

이 작업에서는 **도구 상자** 및 **PropertyGrid** 창을 만든 후 다시 호스트 된 Windows 워크플로 디자이너에 추가 합니다.

참조를 위해 MainWindow.xaml.cs 파일에 있어야 하는 코드는 [워크플로 디자이너 재호스팅](rehosting-the-workflow-designer.md) 의 3 가지 작업을 완료 한 후이 항목의 끝에 제공 됩니다.

## <a name="to-create-the-toolbox-and-add-it-to-the-grid"></a>도구 상자를 만들어 표에 추가하려면

1. [작업 2: 호스트 워크플로 디자이너](task-2-host-the-workflow-designer.md)에 설명 된 절차에 따라 가져온 HostingApplication 프로젝트를 엽니다.

2. **솔루션 탐색기** 창에서 *mainwindow.xaml* 파일을 마우스 오른쪽 단추로 클릭 하 고 **코드 보기** 를 선택 합니다.

3. 를 `GetToolboxControl` `MainWindow` 만들고 <xref:System.Activities.Presentation.Toolbox.ToolboxControl> , **도구 상자** 에 새 **도구 상자** 범주를 추가 하 고, <xref:System.Activities.Statements.Assign> 및 <xref:System.Activities.Statements.Sequence> 활동 형식을 해당 범주에 할당 하는 메서드를 클래스에 추가 합니다.

    ```csharp
    private ToolboxControl GetToolboxControl()
    {
        // Create the ToolBoxControl.
        var ctrl = new ToolboxControl();

        // Create a category.
        var category = new ToolboxCategory("category1");

        // Create Toolbox items.
        var tool1 =
            new ToolboxItemWrapper("System.Activities.Statements.Assign",
            typeof(Assign).Assembly.FullName, null, "Assign");

        var tool2 = new ToolboxItemWrapper("System.Activities.Statements.Sequence",
            typeof(Sequence).Assembly.FullName, null, "Sequence");

        // Add the Toolbox items to the category.
        category.Add(tool1);
        category.Add(tool2);

        // Add the category to the ToolBox control.
        ctrl.Categories.Add(category);
        return ctrl;
    }
    ```

4. `AddToolbox` `MainWindow` 모눈의 왼쪽 열에 **도구 상자** 를 배치 하는 전용 메서드를 클래스에 추가 합니다.

    ```csharp
    private void AddToolBox()
    {
        ToolboxControl tc = GetToolboxControl();
        Grid.SetColumn(tc, 0);
        grid1.Children.Add(tc);
    }
    ```

5. `AddToolBox` `MainWindow()` 다음 코드와 같이 클래스 생성자에 메서드에 대 한 호출을 추가 합니다.

    ```csharp
    public MainWindow()
    {
        InitializeComponent();
        this.RegisterMetadata();
        this.AddDesigner();

        this.AddToolBox();
    }
    ```

6. <kbd>F5</kbd> 키를 눌러 솔루션을 빌드하고 실행 합니다. 및 활동을 포함 하는 **도구 상자가** <xref:System.Activities.Statements.Assign> <xref:System.Activities.Statements.Sequence> 표시 됩니다.

## <a name="to-create-the-propertygrid"></a>PropertyGrid를 만들려면

1. **솔루션 탐색기** 창에서 *mainwindow.xaml* 파일을 마우스 오른쪽 단추로 클릭 하 고 **코드 보기** 를 선택 합니다.

2. `AddPropertyInspector`클래스에 메서드를 추가 `MainWindow` 하 여 **PropertyGrid** 창을 표의 맨 오른쪽 열에 놓습니다.

    ```csharp
    private void AddPropertyInspector()
    {
        Grid.SetColumn(wd.PropertyInspectorView, 2);
        grid1.Children.Add(wd.PropertyInspectorView);
    }
    ```

3. `AddPropertyInspector` `MainWindow()` 다음 코드와 같이 클래스 생성자에 메서드에 대 한 호출을 추가 합니다.

    ```csharp
    public MainWindow()
    {
        InitializeComponent();
        this.RegisterMetadata();
        this.AddDesigner();
        this.AddToolBox();

        this.AddPropertyInspector();
    }
    ```

4. <kbd>F5</kbd> 키를 눌러 솔루션을 빌드하고 실행 합니다. **도구 상자**, 워크플로 디자인 캔버스 및 **PropertyGrid** 창이 모두 표시 되어야 하며, <xref:System.Activities.Statements.Assign> 활동 또는 <xref:System.Activities.Statements.Sequence> 활동을 디자인 캔버스로 끌어 오면 강조 표시 된 활동에 따라 속성 표가 업데이트 됩니다.

## <a name="example"></a>예제

*MainWindow.xaml.cs* 파일에는 이제 다음 코드가 포함 됩니다.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Windows;
using System.Windows.Controls;
using System.Windows.Data;
using System.Windows.Documents;
using System.Windows.Input;
using System.Windows.Media;
using System.Windows.Media.Imaging;
using System.Windows.Navigation;
using System.Windows.Shapes;
// dlls added.
using System.Activities;
using System.Activities.Core.Presentation;
using System.Activities.Presentation;
using System.Activities.Presentation.Metadata;
using System.Activities.Presentation.Toolbox;
using System.Activities.Statements;
using System.ComponentModel;

namespace HostingApplication
{
    /// <summary>
    /// Interaction logic for MainWindow.xaml
    /// </summary>
    public partial class MainWindow : Window
    {
        private WorkflowDesigner wd;

        public MainWindow()
        {
            InitializeComponent();
            RegisterMetadata();
            AddDesigner();
            this.AddToolBox();
            this.AddPropertyInspector();
        }

        private void AddDesigner()
        {
            // Create an instance of WorkflowDesigner class.
            this.wd = new WorkflowDesigner();

            // Place the designer canvas in the middle column of the grid.
            Grid.SetColumn(this.wd.View, 1);

            // Load a new Sequence as default.
            this.wd.Load(new Sequence());

            // Add the designer canvas to the grid.
            grid1.Children.Add(this.wd.View);
        }

        private void RegisterMetadata()
        {
            var dm = new DesignerMetadata();
            dm.Register();
        }

        private ToolboxControl GetToolboxControl()
        {
            // Create the ToolBoxControl.
            var ctrl = new ToolboxControl();

            // Create a category.
            var category = new ToolboxCategory("category1");

            // Create Toolbox items.
            var tool1 =
                new ToolboxItemWrapper("System.Activities.Statements.Assign",
                typeof(Assign).Assembly.FullName, null, "Assign");

            var tool2 = new ToolboxItemWrapper("System.Activities.Statements.Sequence",
                typeof(Sequence).Assembly.FullName, null, "Sequence");

            // Add the Toolbox items to the category.
            category.Add(tool1);
            category.Add(tool2);

            // Add the category to the ToolBox control.
            ctrl.Categories.Add(category);
            return ctrl;
        }

        private void AddToolBox()
        {
            ToolboxControl tc = GetToolboxControl();
            Grid.SetColumn(tc, 0);
            grid1.Children.Add(tc);
        }

        private void AddPropertyInspector()
        {
            Grid.SetColumn(wd.PropertyInspectorView, 2);
            grid1.Children.Add(wd.PropertyInspectorView);
        }

    }
}
```

## <a name="see-also"></a>참고 항목

- [Workflow Designer 재호스팅](rehosting-the-workflow-designer.md)
- [작업 1: 새 Windows Presentation Foundation 애플리케이션 만들기](task-1-create-a-new-wpf-app.md)
- [작업 2: 워크플로 디자이너 호스트](task-2-host-the-workflow-designer.md)
