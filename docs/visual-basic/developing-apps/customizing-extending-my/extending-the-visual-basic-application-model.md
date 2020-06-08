---
title: Visual Basic 애플리케이션 모델 확장
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic Application Model, extending
ms.assetid: e91d3bed-4c27-40e3-871d-2be17467c72c
ms.openlocfilehash: e707f034f05aababdc70d5d6e1f9e1da0ed558bc
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410233"
---
# <a name="extending-the-visual-basic-application-model"></a>Visual Basic 애플리케이션 모델 확장

<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> 클래스의 `Overridable` 멤버를 재정의하여 애플리케이션 모델에 기능을 추가할 수 있습니다. 이 방법을 사용하면 애플리케이션이 시작하고 종료할 때 애플리케이션 모델의 동작을 사용자 지정하고 사용자 고유의 메서드에 대한 호출을 추가할 수 있습니다.

## <a name="visual-overview-of-the-application-model"></a>애플리케이션 모델의 시각적 개요

이 섹션에서는 Visual Basic 애플리케이션 모델의 함수 호출 시퀀스를 시각적으로 표시합니다. 다음 섹션에서는 각 함수의 용도에 대해 자세히 설명합니다.

다음 그래픽은 일반적인 Visual Basic Windows Forms 애플리케이션의 애플리케이션 모델 호출 시퀀스를 보여 줍니다. 이 시퀀스는 `Sub Main` 프로시저가 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> 메서드를 호출할 때 시작됩니다.

![애플리케이션 모델 호출 시퀀스를 보여 주는 다이어그램.](./media/extending-the-visual-basic-application-model/application-model-call-sequence.gif)

또한 Visual Basic 애플리케이션 모델은 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> 및 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> 이벤트도 제공합니다. 다음 그래픽에서는 이러한 이벤트를 발생시키는 메커니즘을 보여 줍니다.

![StartupNextInstance 이벤트를 발생시키는 OnStartupNextInstance 메서드를 보여 주는 다이어그램.](./media/extending-the-visual-basic-application-model/raise-startupnextinstance-event.gif)

![UnhandledException 이벤트를 발생시키는 OnUnhandledException 메서드를 보여 주는 다이어그램.](./media/extending-the-visual-basic-application-model/raise-unhandledexception-event.gif)

## <a name="overriding-the-base-methods"></a>기본 메서드 재정의

<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> 메서드는 `Application` 메서드를 실행하는 순서를 정의합니다. 기본적으로 Windows Forms 애플리케이션에 대한 `Sub Main` 프로시저는 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> 메서드를 호출합니다.

애플리케이션이 일반적인 애플리케이션(다중 인스턴스 애플리케이션)이거나 단일 인스턴스 애플리케이션의 첫 번째 인스턴스인 경우 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> 메서드는 다음 순서로 `Overridable` 메서드를 실행합니다.

1. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A>. 기본적으로이 메서드 비주얼 스타일, 텍스트 표시 스타일 및 (애플리케이션에는 Windows 인증 사용) 하는 경우 기본 애플리케이션 스레드의 현재 보안 주체를 설정 및 호출 `ShowSplashScreen` 모두 `/nosplash` 도 `-nosplash` 로 사용 되는 명령줄 인수입니다.

     이 함수가 `False`를 반환하는 경우 애플리케이션 시작 시퀀스가 취소됩니다. 이는 애플리케이션을 실행하지 않아야 하는 상황이 있는 경우에 유용할 수 있습니다.

     <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> 메서드는 다음 메서드를 호출합니다.

    1. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A>. 애플리케이션에 시작 화면이 정의되어 있는지 여부를 확인하고, 시작 화면이 있는 경우 별도의 스레드에서 시작 화면을 표시합니다.

         <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A> 메서드는 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A> 속성으로 지정된 시간(밀리초) 이상 시작 화면을 표시하는 코드를 포함합니다. 이 기능을 사용하려면 **프로젝트 디자이너**(`My.Application.MinimumSplashScreenDisplayTime` 속성을 2초로 설정함)를 사용하여 애플리케이션에 시작 화면을 추가하거나 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> 또는 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A> 메서드를 재정의하는 메서드에서 `My.Application.MinimumSplashScreenDisplayTime` 속성을 설정해야 합니다. 자세한 내용은 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A>를 참조하세요.

    2. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A>. 디자이너가 시작 화면을 초기화하는 코드를 내보낼 수 있도록 합니다.

         기본적으로 이 메서드는 아무것도 수행하지 않습니다. Visual Basic에서 애플리케이션에 대 한 시작 화면을 선택 하면 **프로젝트 디자이너**, 디자이너 재정의 합니다 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A> 설정 하는 메서드를 사용 하 여 메서드를 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A> 시작 화면 폼의 새 인스턴스 속성 .

2. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartup%2A>. `Startup` 이벤트를 발생시키는 확장성 지점을 제공합니다. 이 함수가 `False`를 반환하는 경우 애플리케이션 시작 시퀀스가 중지합니다.

     기본적으로 이 메서드는 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> 이벤트를 발생시킵니다. 이벤트 처리기가 이벤트 인수의 <xref:System.ComponentModel.CancelEventArgs.Cancel> 속성을 `True`로 설정하면 이 메서드는 `False`를 반환하여 애플리케이션 시작을 취소합니다.

3. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnRun%2A>. 초기화가 완료된 후 기본 애플리케이션 실행을 시작할 준비가 되면 시작 지점을 제공합니다.

     기본적으로 Windows Forms 메시지 루프에 들어가기 전에이 메서드를 호출 합니다 `OnCreateMainForm` (애플리케이션의 기본 폼 만들려면) 및 `HideSplashScreen` (시작 화면 닫기)를 메서드:

    1. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>. 디자이너가 기본 폼을 초기화하는 코드를 내보내는 방법을 제공합니다.

         기본적으로 이 메서드는 아무것도 수행하지 않습니다. 그러나 선택 하면 기본 폼에서 Visual Basic 애플리케이션에 대 한 **프로젝트 디자이너**, 디자이너 재정의 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> 설정 하는 메서드를 사용 하 여 메서드를 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> 기본 폼의 새 인스턴스에 대 한 속성입니다.

    2. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.HideSplashScreen%2A>. 애플리케이션에 시작 화면이 정의되어 있으면 이 메서드는 시작 화면을 닫습니다.

         기본적으로 이 메서드는 시작 화면을 닫습니다.

4. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A>. 애플리케이션의 다른 인스턴스가 시작할 때 단일 인스턴스 애플리케이션이 동작하는 방식을 사용자 지정하는 방법을 제공합니다.

     기본적으로 이 메서드는 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> 이벤트를 발생시킵니다.

5. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnShutdown%2A>. `Shutdown` 이벤트를 발생시키는 확장성 지점을 제공합니다. 이 메서드는 기본 애플리케이션에서 처리 되지 않은 예외가 발생할 경우 실행 되지 않습니다.

     기본적으로 이 메서드는 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> 이벤트를 발생시킵니다.

6. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnUnhandledException%2A>. 위에 나열된 메서드 중 하나에서 처리되지 않은 예외가 발생하는 경우 실행됩니다.

     기본적으로 이 메서드는 디버거가 연결되지 않고 애플리케이션이 `UnhandledException` 이벤트를 처리하는 동안 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> 이벤트를 발생시킵니다.

 애플리케이션이 단일 인스턴스 애플리케이션이고 애플리케이션이 이미 실행 중인 경우에는 애플리케이션의 후속 인스턴스가 애플리케이션의 원래 인스턴스에 대한 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A> 메서드를 호출한 다음 종료됩니다.

 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance(Microsoft.VisualBasic.ApplicationServices.StartupNextInstanceEventArgs)> 생성자는 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> 속성을 호출하여 애플리케이션의 폼에 사용할 텍스트 렌더링 엔진을 결정합니다. 기본적으로 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> 속성은 Visual Basic 2005 이상 버전의 기본값인 GDI 텍스트 렌더링 엔진을 사용해야 함을 나타내는 `False`를 반환합니다. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> 속성을 재정의하여 Visual Basic .NET 2002 및 Visual Basic .NET 2003의 기본값인 GDI + 텍스트 렌더링 엔진을 사용해야 함을 나타내는 `True`를 반환할 수 있습니다.

## <a name="configuring-the-application"></a>애플리케이션 구성

 Visual Basic 애플리케이션 모델의 일부로 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> 클래스는 애플리케이션을 구성하는 보호된 속성을 제공합니다. 이러한 속성은 구현 클래스의 생성자에서 설정해야 합니다.

 기본 Windows Forms 프로젝트에서 **프로젝트 디자이너**는 디자이너 설정을 사용하여 속성을 설정하는 코드를 만듭니다. 속성은 애플리케이션이 시작할 때만 사용됩니다. 애플리케이션이 시작한 후 속성을 설정하면 아무런 영향을 주지 않습니다.

|속성|결정|프로젝트 디자이너의 애플리케이션 창에서의 설정|
|---|---|---|
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.IsSingleInstance%2A>|애플리케이션이 단일 인스턴스 애플리케이션 또는 다중 인스턴스 애플리케이션으로 실행되는지 여부.|**단일 인스턴스 애플리케이션 작성** 확인란|
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.EnableVisualStyles%2A>|애플리케이션이 Windows XP와 일치하는 비주얼 스타일을 사용할지 여부.|**XP 비주얼 스타일 사용** 확인란|
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SaveMySettingsOnExit%2A>|애플리케이션이 종료할 때 애플리케이션이 애플리케이션의 사용자 설정 변경 내용을 자동으로 저장하는지 여부.|**종료할 때 My.Settings 저장** 확인란|
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShutdownStyle%2A>|애플리케이션이 종료되는 원인(예: 시작 폼이 닫힘 또는 마지막 폼이 닫힘).|**종료 모드** 목록|

## <a name="see-also"></a>참조

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>
- [Visual Basic 애플리케이션 모델 개요](../development-with-my/overview-of-the-visual-basic-application-model.md)
- [프로젝트 디자이너, 애플리케이션 페이지(Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
