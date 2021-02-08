---
description: '자세한 정보: Windows Forms 애플리케이션 기초(Visual Basic)'
title: Windows Forms 응용 프로그램의 기본 사항
ms.date: 07/20/2015
helpviewer_keywords:
- Windows applications
- Windows Forms, Visual Basic
ms.assetid: 0b919d30-7fd6-42db-85c8-543d15312441
ms.openlocfilehash: 04f360a0262e08fa018f19577b0e950c15a7253a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99675327"
---
# <a name="windows-forms-application-basics-visual-basic"></a>Windows Forms 애플리케이션 기초(Visual Basic)

Visual Basic의 중요한 부분은 사용자 컴퓨터에서 로컬로 실행되는 Windows Forms 애플리케이션을 만드는 기능입니다. Visual Studio를 통해 Windows Forms를 사용하여 애플리케이션 및 사용자 인터페이스를 만들 수 있습니다. Windows Forms 애플리케이션은 <xref:System.Windows.Forms> 네임스페이스의 클래스를 기반으로 빌드됩니다.

## <a name="designing-windows-forms-applications"></a>Windows Forms 애플리케이션 디자인

Visual Studio를 사용하여 Windows Forms 및 Windows 서비스 애플리케이션을 만들 수 있습니다. 자세한 내용은 다음 항목을 참조하세요.

- [Windows Forms 시작](/dotnet/desktop/winforms/getting-started-with-windows-forms). Windows Forms를 만들고 프로그래밍하는 방법에 관한 정보를 제공합니다.

- [Windows Forms 컨트롤](/dotnet/desktop/winforms/controls/). Windows Forms 컨트롤 사용을 자세히 설명하는 항목 컬렉션입니다.

- [Windows 서비스 애플리케이션](../../../framework/windows-services/index.md). Windows 서비스를 만드는 방법을 설명하는 항목을 나열합니다.

## <a name="building-rich-interactive-user-interfaces"></a>풍부한 대화형 사용자 인터페이스 빌드

Windows Forms는 .NET Framework 및 .NET Core(.NET Core 3.0 이상)의 스마트 클라이언트 구성 요소입니다. 또한 파일 시스템 읽기 및 쓰기와 같은 일반적인 애플리케이션 작업을 지원하는 관리형 라이브러리 세트입니다. Visual Studio와 같은 개발 환경을 사용하면 정보를 표시하고, 사용자 입력을 요청하고, 네트워크를 통해 원격 컴퓨터와 통신하는 Windows Forms 애플리케이션을 만들 수 있습니다.

Windows Forms에서 양식은 사용자에게 정보를 표시하는 시각적 표면입니다. 일반적으로 양식에 컨트롤을 배치하고 마우스 클릭이나 키 누름과 같은 사용자 동작에 대한 응답을 개발하여 Windows Forms 애플리케이션을 빌드합니다. *컨트롤* 은 데이터를 표시하거나 데이터 입력을 수락하는 고유한 UI(사용자 인터페이스) 요소입니다.

### <a name="events"></a>이벤트

사용자가 양식이나 컨트롤 중 하나에 작업을 수행하면 이벤트가 생성됩니다. 애플리케이션은 코드를 사용하여 이러한 이벤트에 대응하고, 발생 시 이벤트를 처리합니다. 자세한 내용은 [Windows Forms에서 이벤트 처리기 만들기](/dotnet/desktop/winforms/creating-event-handlers-in-windows-forms)를 참조하세요.

### <a name="controls"></a>컨트롤

Windows Forms에는 텍스트 상자, 단추, 드롭다운 상자, 라디오 단추 및 웹 페이지를 표시하는 컨트롤 등 양식에 배치할 수 있는 다양한 컨트롤이 포함되어 있습니다. 폼에서 사용할 수 있는 모든 컨트롤의 목록은 [Windows Forms에서 사용할 수 있는 컨트롤](/dotnet/desktop/winforms/controls/controls-to-use-on-windows-forms)을 참조하세요. 기존 컨트롤이 요구를 충족하지 않는 경우 Windows Forms에서 <xref:System.Windows.Forms.UserControl> 클래스를 사용하여 고유한 사용자 지정 컨트롤을 만들 수도 있습니다.

Windows Forms에는 Microsoft Office와 같은 고급 애플리케이션의 기능을 에뮬레이트하는 풍부한 UI 컨트롤이 있습니다. <xref:System.Windows.Forms.ToolStrip> 및 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 사용하면 텍스트와 이미지를 포함하고, 하위 메뉴를 표시하며, 텍스트 상자 및 콤보 상자와 같은 기타 컨트롤을 호스트하는 도구 모음과 메뉴를 만들 수 있습니다.

Visual Studio 끌어서 놓기 양식 디자이너를 사용하여 Windows Forms 애플리케이션을 쉽게 만들 수 있습니다. 커서로 컨트롤을 선택하고 양식에서 원하는 위치에 배치하면 됩니다. 디자이너는 컨트롤을 쉽게 배치하기 위한 눈금선 및 “맞춤선”과 같은 도구를 제공합니다. 또한 Visual Studio를 사용하든, 명령줄에서 컴파일하든 <xref:System.Windows.Forms.FlowLayoutPanel>, <xref:System.Windows.Forms.TableLayoutPanel> 및 <xref:System.Windows.Forms.SplitContainer> 컨트롤을 사용하여 최소한의 시간과 노력으로 고급 양식 레이아웃을 만들 수 있습니다.

### <a name="custom-ui-elements"></a>사용자 지정 UI 요소

끝으로, 고유한 사용자 지정 UI 요소를 만들어야 하는 경우 <xref:System.Drawing> 네임스페이스에는 양식에서 선, 원 및 기타 도형을 렌더링하는 데 필요한 모든 클래스가 포함되어 있습니다.

해당 기능을 사용하는 방법에 관한 단계별 정보는 다음 도움말 항목을 참조하세요.

|대상|참조 항목|
|--------|---------|
|Visual Studio를 사용하여 새 Windows Forms 애플리케이션 만들기|[자습서 1: 사진 뷰어 만들기](/visualstudio/ide/tutorial-1-create-a-picture-viewer)|
|양식에서 컨트롤 사용|[방법: Windows Forms에 컨트롤 추가](/dotnet/desktop/winforms/controls/how-to-add-controls-to-windows-forms)|
|<xref:System.Drawing>을 사용하여 그래픽 만들기|[그래픽 프로그래밍 시작](/dotnet/desktop/winforms/advanced/getting-started-with-graphics-programming)|
|사용자 지정 컨트롤 만들기|[방법: UserControl 클래스에서 상속](/dotnet/desktop/winforms/controls/how-to-inherit-from-the-usercontrol-class)|

## <a name="displaying-and-manipulating-data"></a>데이터 표시 및 조작

많은 애플리케이션은 데이터베이스, XML 파일, XML Web services 또는 기타 데이터 소스의 데이터를 표시해야 합니다. Windows Forms는 각 데이터 조각이 해당 셀을 사용하도록 해당 테이블 형식 데이터를 기존 행 및 열 형식으로 렌더링하기 위해 <xref:System.Windows.Forms.DataGridView>라는 유연한 컨트롤을 제공합니다. <xref:System.Windows.Forms.DataGridView>를 사용하면 다른 기능 중에서도 개별 셀의 모양을 사용자 지정하고, 임의의 행과 열을 제자리에 잠그고, 셀 안에 복잡한 컨트롤을 표시할 수 있습니다.

네트워크를 통해 데이터 소스에 연결하는 것은 Windows Forms 스마트 클라이언트에서 간단한 작업입니다. Visual Studio 2005 및 .NET Framework 2.0의 Windows Forms에 새로 추가된 <xref:System.Windows.Forms.BindingSource> 구성 요소는 데이터 소스에 대한 연결을 나타내며 데이터를 컨트롤에 바인딩하고, 이전 및 다음 레코드로 이동하고, 레코드를 편집하고, 변경 내용을 다시 원래 소스에 저장하기 위한 메서드를 공개합니다. <xref:System.Windows.Forms.BindingNavigator> 컨트롤은 <xref:System.Windows.Forms.BindingSource> 구성 요소를 통해 사용자가 레코드를 탐색하기 위한 간단한 인터페이스를 제공합니다.

### <a name="data-bound-controls"></a>데이터 바인딩 컨트롤

데이터베이스, 웹 서비스 및 개체와 같은 데이터 소스를 프로젝트에 표시하는 데이터 소스 창을 사용하여 데이터 바인딩 컨트롤을 쉽게 만들 수 있습니다. 이 창에서 프로젝트의 폼으로 항목을 끌어 데이터 바인딩된 컨트롤을 만들 수 있습니다. 데이터 소스 창에서 기존 컨트롤로 개체를 끌어 기존 컨트롤을 데이터에 바인딩할 수도 있습니다.

### <a name="settings"></a>설정

Windows Forms에서 관리할 수 있는 다른 형식의 데이터 바인딩은 설정입니다. 대부분의 스마트 클라이언트 애플리케이션은 마지막으로 알려진 양식 크기와 같은 런타임 상태에 대한 일부 정보를 유지하고 저장된 파일의 기본 위치와 같은 사용자 기본 설정 데이터를 유지해야 합니다. 두 가지 설정을 모두 클라이언트 컴퓨터에 쉽게 저장할 수 있는 애플리케이션 설정 기능은 이 요구 사항을 충족합니다. Visual Studio 또는 코드 편집기를 사용하여 이 설정을 정의하면 설정이 XML로 유지되며 런타임에 자동으로 다시 메모리로 읽어옵니다.

해당 기능을 사용하는 방법에 관한 단계별 정보는 다음 도움말 항목을 참조하세요.

|대상|참조 항목|
|--------|---------|
|<xref:System.Windows.Forms.BindingSource> 구성 요소 사용|[방법: 디자이너를 사용하여 Windows Forms 컨트롤에서 BindingSource 구성 요소 바인딩](/dotnet/desktop/winforms/controls/bind-wf-controls-with-the-bindingsource)|
|ADO.NET 데이터 소스 작업|[방법: Windows Forms BindingSource 구성 요소를 사용하여 ADO.NET 데이터 정렬 및 필터링](/dotnet/desktop/winforms/controls/sort-and-filter-ado-net-data-with-wf-bindingsource-component)|
|데이터 소스 창 사용|[연습: Windows Form에 데이터 표시](/visualstudio/data-tools/accessing-data-in-visual-studio)|

## <a name="deploying-applications-to-client-computers"></a>클라이언트 컴퓨터에 애플리케이션 배포

애플리케이션을 작성한 후 해당 클라이언트 컴퓨터에 설치하고 실행할 수 있도록 사용자에게 보내야 합니다. ClickOnce 기술을 사용하는 경우 Visual Studio 내에서 마우스만 몇 번 클릭하여 애플리케이션을 배포하고 웹에서 해당 애플리케이션을 가리키는 URL을 사용자에게 제공할 수 있습니다. ClickOnce는 애플리케이션의 모든 요소와 종속성을 관리하고 클라이언트 컴퓨터에 애플리케이션이 적절하게 설치되었는지 확인합니다.

사용자가 네트워크에 연결된 경우에만 실행되거나 온라인 및 오프라인 둘 다에서 실행되도록 ClickOnce 애플리케이션을 구성할 수 있습니다. 애플리케이션이 오프라인 작업을 지원하도록 지정하면 ClickOnce는 사용자의 **시작** 메뉴에 애플리케이션의 링크를 추가하여 URL 없이도 링크를 열 수 있습니다.

애플리케이션을 업데이트하는 경우 새 배포 매니페스트와 애플리케이션의 새 복사본을 웹 서버에 게시합니다. ClickOnce에서 사용 가능한 업데이트가 있는지 검색하고 사용자 설치를 업그레이드합니다. 이전 어셈블리를 업데이트하는 데 사용자 지정 프로그래밍이 필요하지 않습니다.

ClickOnce에 대한 전체 개요는 [ClickOnce 보안 및 배포](/visualstudio/deployment/clickonce-security-and-deployment)를 참조하세요. 해당 기능을 사용하는 방법에 관한 단계별 정보는 다음 도움말 항목을 참조하세요.

|대상|참조 항목|
|--------|---------|
|ClickOnce를 사용하여 애플리케이션 배포|[방법: 게시 마법사를 사용하여 ClickOnce 애플리케이션 게시](/visualstudio/deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard)<br /><br /> [연습: 수동으로 ClickOnce 애플리케이션 배포](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)|
|ClickOnce 배포 업데이트|[방법: ClickOnce 애플리케이션에 대한 업데이트 관리](/visualstudio/deployment/how-to-manage-updates-for-a-clickonce-application)|
|ClickOnce를 사용하여 보안 관리|[방법: ClickOnce 보안 설정 사용](/visualstudio/deployment/how-to-enable-clickonce-security-settings)|

## <a name="other-controls-and-features"></a>기타 컨트롤 및 기능

Windows Forms에는 대화 상자 만들기, 인쇄, 설명서 추가 및 여러 언어로 애플리케이션 지역화 지원과 같이 일반적인 작업을 쉽고 빠르게 구현할 수 있게 해주는 다른 여러 기능이 있습니다. 또한 Windows Forms는 .NET의 강력한 보안 시스템을 사용하여 더 안전한 애플리케이션을 고객에게 릴리스할 수 있습니다.

해당 기능을 사용하는 방법에 관한 단계별 정보는 다음 도움말 항목을 참조하세요.

|대상|참조 항목|
|--------|---------|
|양식 콘텐츠 인쇄|[방법: Windows Forms에서 그래픽 인쇄](/dotnet/desktop/winforms/advanced/how-to-print-graphics-in-windows-forms)<br /><br /> [방법: Windows Forms에서 다중 페이지 텍스트 파일 인쇄](/dotnet/desktop/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms)|
|Windows Forms 보안에 대한 자세한 정보|[Windows Forms의 보안 개요](/dotnet/desktop/winforms/security-in-windows-forms-overview)|

## <a name="see-also"></a>참조

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- [Windows Forms 개요](/dotnet/desktop/winforms/windows-forms-overview)
- [My.Forms 개체](../../language-reference/objects/my-forms-object.md)
