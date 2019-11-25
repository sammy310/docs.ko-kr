---
title: Visual Basic 애플리케이션 모델 확장
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic Application Model, extending
ms.assetid: e91d3bed-4c27-40e3-871d-2be17467c72c
ms.openlocfilehash: 46c18ab540c90c4147514685c2acc824755b435f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976858"
---
# <a name="extending-the-visual-basic-application-model"></a>Visual Basic 애플리케이션 모델 확장

<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> 클래스의 `Overridable` 멤버를 재정의 하 여 응용 프로그램 모델에 기능을 추가할 수 있습니다. 이 방법을 사용 하면 응용 프로그램을 시작 하 고 종료할 때 응용 프로그램 모델의 동작을 사용자 지정 하 고 사용자 고유의 메서드에 대 한 호출을 추가할 수 있습니다.

## <a name="visual-overview-of-the-application-model"></a>응용 프로그램 모델의 시각적 개요

이 섹션에서는 Visual Basic 응용 프로그램 모델에서 함수 호출의 시퀀스를 시각적으로 표시 합니다. 다음 섹션에서는 각 함수의 용도에 대해 자세히 설명 합니다.

다음 그래픽은 일반적인 Visual Basic Windows Forms 응용 프로그램의 응용 프로그램 모델 호출 시퀀스를 보여 줍니다. 시퀀스는 `Sub Main` 프로시저가 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> 메서드를 호출할 때 시작 됩니다.

![응용 프로그램 모델 호출 시퀀스를 보여 주는 다이어그램입니다.](./media/extending-the-visual-basic-application-model/application-model-call-sequence.gif)

또한 Visual Basic 응용 프로그램 모델은 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> 및 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> 이벤트를 제공 합니다. 다음 그래픽에서는 이러한 이벤트를 발생 시키는 메커니즘을 보여 줍니다.

![StartupNextInstance 이벤트를 발생 시키는 OnStartupNextInstance 메서드를 보여 주는 다이어그램입니다.](./media/extending-the-visual-basic-application-model/raise-startupnextinstance-event.gif)

![UnhandledException 이벤트를 발생 시키는 OnUnhandledException 메서드를 보여 주는 다이어그램입니다.](./media/extending-the-visual-basic-application-model/raise-unhandledexception-event.gif)

## <a name="overriding-the-base-methods"></a>기본 메서드 재정의

<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> 메서드는 `Application` 메서드를 실행 하는 순서를 정의 합니다. 기본적으로 Windows Forms 응용 프로그램에 대 한 `Sub Main` 프로시저는 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> 메서드를 호출 합니다.

응용 프로그램이 일반적인 응용 프로그램 (다중 인스턴스 응용 프로그램) 이거나 단일 인스턴스 응용 프로그램의 첫 번째 인스턴스인 경우 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> 메서드는 다음 순서로 `Overridable` 메서드를 실행 합니다.

1. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> 기본적으로이 메서드 비주얼 스타일, 텍스트 표시 스타일 및 (애플리케이션에는 Windows 인증 사용) 하는 경우 기본 애플리케이션 스레드의 현재 보안 주체를 설정 및 호출 `ShowSplashScreen` 모두 `/nosplash` 도 `-nosplash` 로 사용 되는 명령줄 인수입니다.

     이 함수가 `False` 반환 하는 경우 응용 프로그램 시작 시퀀스가 취소 됩니다. 이는 응용 프로그램을 실행 하지 않아야 하는 상황이 있는 경우에 유용할 수 있습니다.

     <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> 메서드는 다음 메서드를 호출 합니다.

    1. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A> 응용 프로그램에 시작 화면이 정의 되어 있는지 여부를 확인 하 고, 표시 되는 경우 별도의 스레드에 시작 화면을 표시 합니다.

         <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A> 메서드는 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A> 속성으로 지정 된 최소 시간 (밀리초) 동안 시작 화면을 표시 하는 코드를 포함 합니다. 이 기능을 사용 하려면 `My.Application.MinimumSplashScreenDisplayTime` 속성을 2 초로 설정 하는 **프로젝트 디자이너** 를 사용 하 여 응용 프로그램에 시작 화면을 추가 하거나 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> 또는 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A> 메서드를 재정의 하는 메서드에서 `My.Application.MinimumSplashScreenDisplayTime` 속성을 설정 해야 합니다. 자세한 내용은 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A>를 참조하세요.

    2. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A> 디자이너가 시작 화면을 초기화 하는 코드를 내보낼 수 있도록 합니다.

         기본적으로 이 메서드는 아무것도 수행하지 않습니다. Visual Basic에서 애플리케이션에 대 한 시작 화면을 선택 하면 **프로젝트 디자이너**, 디자이너 재정의 합니다 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A> 설정 하는 메서드를 사용 하 여 메서드를 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A> 시작 화면 폼의 새 인스턴스 속성 .

2. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartup%2A> `Startup` 이벤트를 발생 시키는 확장 지점을 제공 합니다. 이 함수가 `False` 반환 하는 경우 응용 프로그램 시작 시퀀스는 중지 됩니다.

     기본적으로이 메서드는 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> 이벤트를 발생 시킵니다. 이벤트 처리기가 이벤트 인수의 <xref:System.ComponentModel.CancelEventArgs.Cancel> 속성을 `True`로 설정 하면이 메서드는 `False`를 반환 하 여 응용 프로그램 시작을 취소 합니다.

3. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnRun%2A> 초기화가 완료된 후 기본 애플리케이션 실행을 시작할 준비가 되면 시작 지점을 제공합니다.

     기본적으로 Windows Forms 메시지 루프에 들어가기 전에이 메서드를 호출 합니다 `OnCreateMainForm` (애플리케이션의 기본 폼 만들려면) 및 `HideSplashScreen` (시작 화면 닫기)를 메서드:

    1. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> 디자이너에서 기본 폼을 초기화 하는 코드를 내보낼 수 있는 방법을 제공 합니다.

         기본적으로 이 메서드는 아무것도 수행하지 않습니다. 그러나 선택 하면 기본 폼에서 Visual Basic 애플리케이션에 대 한 **프로젝트 디자이너**, 디자이너 재정의 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> 설정 하는 메서드를 사용 하 여 메서드를 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> 기본 폼의 새 인스턴스에 대 한 속성입니다.

    2. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.HideSplashScreen%2A> 응용 프로그램에 시작 화면이 정의 되어 있고 열려 있는 경우이 메서드는 시작 화면을 닫습니다.

         기본적으로이 메서드는 시작 화면을 닫습니다.

4. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A> 응용 프로그램의 다른 인스턴스가 시작 될 때 단일 인스턴스 응용 프로그램이 동작 하는 방식을 사용자 지정 하는 방법을 제공 합니다.

     기본적으로이 메서드는 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> 이벤트를 발생 시킵니다.

5. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnShutdown%2A> `Shutdown` 이벤트를 발생 시키는 확장 지점을 제공 합니다. 이 메서드는 기본 애플리케이션에서 처리 되지 않은 예외가 발생할 경우 실행 되지 않습니다.

     기본적으로이 메서드는 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> 이벤트를 발생 시킵니다.

6. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnUnhandledException%2A> 위의 나열 된 방법 중 하나에서 처리 되지 않은 예외가 발생 하는 경우 실행 됩니다.

     기본적으로이 메서드는 디버거가 연결 되어 있지 않고 응용 프로그램에서 `UnhandledException` 이벤트를 처리 하는 동안 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> 이벤트를 발생 시킵니다.

 응용 프로그램이 단일 인스턴스 응용 프로그램이 고 응용 프로그램이 이미 실행 중인 경우에는 응용 프로그램의 후속 인스턴스가 응용 프로그램의 원본 인스턴스에서 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A> 메서드를 호출한 다음 종료 됩니다.

 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance(Microsoft.VisualBasic.ApplicationServices.StartupNextInstanceEventArgs)> 생성자는 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> 속성을 호출 하 여 응용 프로그램의 폼에 사용할 텍스트 렌더링 엔진을 결정 합니다. 기본적으로 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> 속성은 Visual Basic 2005 이상 버전의 기본값인 GDI 텍스트 렌더링 엔진을 사용 함을 나타내는 `False`을 반환 합니다. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> 속성을 재정의 하 여 GDI + 텍스트 렌더링 엔진이 사용 됨을 나타내는 `True`를 반환할 수 있습니다 .이는 Visual Basic .NET 2002 및 Visual Basic .NET 2003의 기본값입니다.

## <a name="configuring-the-application"></a>응용 프로그램 구성

 Visual Basic 응용 프로그램 모델의 일부로 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> 클래스는 응용 프로그램을 구성 하는 보호 된 속성을 제공 합니다. 이러한 속성은 구현 하는 클래스의 생성자에서 설정 해야 합니다.

 기본 Windows Forms 프로젝트에서 **프로젝트 디자이너** 는 디자이너 설정을 사용 하 여 속성을 설정 하는 코드를 만듭니다. 속성은 응용 프로그램을 시작 하는 경우에만 사용 됩니다. 응용 프로그램이 시작 된 후이를 설정 해도 아무런 영향을 주지 않습니다.

|속성|방식이|프로젝트 디자이너의 응용 프로그램 창에서 설정|
|---|---|---|
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.IsSingleInstance%2A>|응용 프로그램이 단일 인스턴스 응용 프로그램이 나 다중 인스턴스 응용 프로그램으로 실행 되는지 여부입니다.|**단일 인스턴스 응용 프로그램 만들기** 확인란|
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.EnableVisualStyles%2A>|응용 프로그램에서 Windows XP와 일치 하는 비주얼 스타일을 사용 하는 경우입니다.|**XP 비주얼 스타일 사용** 확인란|
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SaveMySettingsOnExit%2A>|응용 프로그램이 종료 될 때 응용 프로그램에서 응용 프로그램의 사용자 설정 변경 내용을 자동으로 저장 하는 경우|**종료 시 설정 저장** 확인란|
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShutdownStyle%2A>|시작 폼을 닫거나 마지막 폼을 닫을 때 처럼 응용 프로그램이 종료 되는 원인입니다.|**종료 모드** 목록|

## <a name="see-also"></a>참조

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>
- [Visual Basic 애플리케이션 모델 개요](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)
- [프로젝트 디자이너, 애플리케이션 페이지(Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
