---
title: Windows Forms 응용 프로그램의 기본 사항
ms.date: 07/20/2015
helpviewer_keywords:
- Windows applications
- Windows Forms, Visual Basic
ms.assetid: 0b919d30-7fd6-42db-85c8-543d15312441
ms.openlocfilehash: 1aa1edf0130e388c6cc87662d83591f41a8e2325
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349159"
---
# <a name="windows-forms-application-basics-visual-basic"></a>Windows Forms 애플리케이션 기초(Visual Basic)

An important part of Visual Basic is the ability to create Windows Forms applications that run locally on users' computers. You can use Visual Studio to create the application and user interface using Windows Forms. A Windows Forms application is built on classes from the <xref:System.Windows.Forms> namespace.

## <a name="designing-windows-forms-applications"></a>Designing Windows Forms Applications

You can create Windows Forms and Windows service applications with Visual Studio. 자세한 내용은 다음 항목을 참조하세요.

- [Getting Started with Windows Forms](../../../framework/winforms/getting-started-with-windows-forms.md). Provides information on how to create and program Windows Forms.

- [Windows Forms Controls](../../../framework/winforms/controls/index.md). Collection of topics detailing the use of Windows Forms controls.

- [Windows Service Applications](../../../framework/windows-services/index.md). Lists topics that explain how to create Windows services.

## <a name="building-rich-interactive-user-interfaces"></a>풍부한 대화형 사용자 인터페이스 빌드

Windows Forms is the smart-client component of the .NET Framework, a set of managed libraries that enable common application tasks such as reading and writing to the file system. Using a development environment like Visual Studio, you can create Windows Forms applications that display information, request input from users, and communicate with remote computers over a network.

In Windows Forms, a form is a visual surface on which you display information to the user. You commonly build Windows Forms applications by placing controls on forms and developing responses to user actions, such as mouse clicks or key presses. *컨트롤*은 데이터를 표시하거나 데이터 입력을 수락하는 고유한 UI(사용자 인터페이스) 요소입니다.

### <a name="events"></a>이벤트

When a user does something to your form or one of its controls, it generates an event. 애플리케이션은 코드를 사용하여 이러한 이벤트에 대응하고, 발생 시 이벤트를 처리합니다. 자세한 내용은 [Windows Forms에서 이벤트 처리기 만들기](../../../framework/winforms/creating-event-handlers-in-windows-forms.md)를 참조하세요.

### <a name="controls"></a>컨트롤

Windows Forms contains a variety of controls that you can place on forms: controls that display text boxes, buttons, drop-down boxes, radio buttons, and even Web pages. 폼에서 사용할 수 있는 모든 컨트롤의 목록은 [Windows Forms에서 사용할 수 있는 컨트롤](../../../framework/winforms/controls/controls-to-use-on-windows-forms.md)을 참조하세요. 기존 컨트롤이 요구를 충족하지 않는 경우 Windows Forms에서 <xref:System.Windows.Forms.UserControl> 클래스를 사용하여 고유한 사용자 지정 컨트롤을 만들 수도 있습니다.

Windows Forms에는 Microsoft Office와 같은 고급 애플리케이션의 기능을 에뮬레이트하는 풍부한 UI 컨트롤이 있습니다. Using the <xref:System.Windows.Forms.ToolStrip> and <xref:System.Windows.Forms.MenuStrip> control, you can create toolbars and menus that contain text and images, display submenus, and host other controls such as text boxes and combo boxes.

With the Visual Studio drag-and-drop forms designer, you can easily create Windows Forms applications: just select the controls with your cursor and place them where you want on the form. The designer provides tools such as grid lines and "snap lines" to take the hassle out of aligning controls. And whether you use Visual Studio or compile at the command line, you can use the <xref:System.Windows.Forms.FlowLayoutPanel>, <xref:System.Windows.Forms.TableLayoutPanel> and <xref:System.Windows.Forms.SplitContainer> controls to create advanced form layouts with minimal time and effort.

### <a name="custom-ui-elements"></a>Custom UI Elements

Finally, if you must create your own custom UI elements, the <xref:System.Drawing> namespace contains all of the classes you need to render lines, circles, and other shapes directly on a form.

For step-by-step information about using these features, see the following Help topics.

|대상|참조 항목|
|--------|---------|
|Create a new Windows Forms application with Visual Studio|[Tutorial 1: Create a picture viewer](/visualstudio/ide/tutorial-1-create-a-picture-viewer)|
|Use controls on forms|[방법: Windows Forms에 컨트롤 추가](../../../framework/winforms/controls/how-to-add-controls-to-windows-forms.md)|
|Create graphics with <xref:System.Drawing>|[그래픽 프로그래밍 시작](../../../framework/winforms/advanced/getting-started-with-graphics-programming.md)|
|Create custom controls|[방법: UserControl 클래스에서 상속](../../../framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)|

## <a name="displaying-and-manipulating-data"></a>데이터 표시 및 조작

많은 애플리케이션은 데이터베이스, XML 파일, XML Web services 또는 기타 데이터 소스의 데이터를 표시해야 합니다. Windows Forms provides a flexible control called the <xref:System.Windows.Forms.DataGridView> control for rendering such tabular data in a traditional row and column format, so that every piece of data occupies its own cell. Using <xref:System.Windows.Forms.DataGridView> you can customize the appearance of individual cells, lock arbitrary rows and columns in place, and display complex controls inside cells, among other features.

네트워크를 통해 데이터 소스에 연결하는 것은 Windows Forms 스마트 클라이언트에서 간단한 작업입니다. The <xref:System.Windows.Forms.BindingSource> component, new with Windows Forms in Visual Studio 2005 and the .NET Framework 2.0, represents a connection to a data source, and exposes methods for binding data to controls, navigating to the previous and next records, editing records, and saving changes back to the original source. <xref:System.Windows.Forms.BindingNavigator> 컨트롤은 <xref:System.Windows.Forms.BindingSource> 구성 요소를 통해 사용자가 레코드를 탐색하기 위한 간단한 인터페이스를 제공합니다.

### <a name="data-bound-controls"></a>Data-Bound Controls

You can create data-bound controls easily using the Data Sources window, which displays data sources such as databases, Web services, and objects in your project. 이 창에서 프로젝트의 폼으로 항목을 끌어 데이터 바인딩된 컨트롤을 만들 수 있습니다. 데이터 소스 창에서 기존 컨트롤로 개체를 끌어 기존 컨트롤을 데이터에 바인딩할 수도 있습니다.

### <a name="settings"></a>설정

Another type of data binding you can manage in Windows Forms is settings. Most smart-client applications must retain some information about their run-time state, such as the last-known size of forms, and retain user-preference data, such as default locations for saved files. The application-settings feature addresses these requirements by providing an easy way to store both types of settings on the client computer. Once defined using either Visual Studio or a code editor, these settings are persisted as XML and automatically read back into memory at run time.

For step-by-step information about using these features, see the following Help topics.

|대상|참조 항목|
|--------|---------|
|Use the <xref:System.Windows.Forms.BindingSource> component|[방법: 디자이너를 사용하여 Windows Forms 컨트롤에 BindingSource 구성 요소 바인딩](../../../framework/winforms/controls/bind-wf-controls-with-the-bindingsource.md)|
|Work with ADO.NET data sources|[방법: Windows Forms BindingSource 구성 요소를 사용하여 ADO.NET 데이터 정렬 및 필터링](../../../framework/winforms/controls/sort-and-filter-ado-net-data-with-wf-bindingsource-component.md)|
|Use the Data Sources window|[연습: Windows Form에 데이터 표시](/visualstudio/data-tools/accessing-data-in-visual-studio)|

## <a name="deploying-applications-to-client-computers"></a>클라이언트 컴퓨터에 애플리케이션 배포

Once you have written your application, you must send it to your users so that they can install and run it on their own client computers. Using the ClickOnce technology, you can deploy your applications from within Visual Studio by using just a few clicks and provide users with a URL pointing to your application on the Web. ClickOnce manages all of the elements and dependencies in your application and ensures that the application is properly installed on the client computer.

ClickOnce applications can be configured to run only when the user is connected to the network, or to run both online and offline. When you specify that an application should support offline operation, ClickOnce adds a link to your application in the user's **Start** menu, so that the user can open it without using the URL.

애플리케이션을 업데이트하는 경우 새 배포 매니페스트와 애플리케이션의 새 복사본을 웹 서버에 게시합니다. ClickOnce detects that there is an update available and upgrades the user's installation; no custom programming is required to update old assemblies.

For a full introduction to ClickOnce, see [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment). For step-by-step information about using these features, see the following Help topics:

|대상|참조 항목|
|--------|---------|
|Deploy an application with ClickOnce|[방법: 게시 마법사를 사용하여 ClickOnce 애플리케이션 게시](/visualstudio/deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard)<br /><br /> [연습: ClickOnce 애플리케이션 수동 배포](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)|
|Update a ClickOnce deployment|[방법: ClickOnce 애플리케이션에 대한 업데이트 관리](/visualstudio/deployment/how-to-manage-updates-for-a-clickonce-application)|
|Manage security with ClickOnce|[방법: ClickOnce 보안 설정 사용](/visualstudio/deployment/how-to-enable-clickonce-security-settings)|

## <a name="other-controls-and-features"></a>기타 컨트롤 및 기능

Windows Forms에는 대화 상자 만들기, 인쇄, 도움말 및 설명서 추가 및 여러 언어로 애플리케이션 지역화 지원과 같이 일반적인 작업을 쉽고 빠르게 구현할 수 있게 해주는 다른 여러 기능이 있습니다. In addition, Windows Forms relies on the robust security system of the .NET Framework, enabling you to release more secure applications to your customers.

For step-by-step information about using these features, see the following Help topics:

|대상|참조 항목|
|--------|---------|
|Print the contents of a form|[방법: Windows Forms의 그래픽 인쇄](../../../framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)<br /><br /> [방법: Windows Forms에서 다중 페이지 텍스트 파일 인쇄](../../../framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)|
|Windows Forms 보안에 대한 자세한 정보|[Windows Forms의 보안 개요](../../../framework/winforms/security-in-windows-forms-overview.md)|

## <a name="see-also"></a>참조

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- [Windows Forms 개요](../../../framework/winforms/windows-forms-overview.md)
- [My.Forms 개체](../../../visual-basic/language-reference/objects/my-forms-object.md)
