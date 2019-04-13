---
title: Load From XAML
ms.date: 03/30/2017
ms.assetid: 1f103ef6-7bed-4f16-ae52-9e665c5a43d7
ms.openlocfilehash: 5a3b3673812c0b5500a13ae9ce79ce8206aa4834
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59300972"
---
# <a name="load-from-xaml"></a>Load From XAML
이 샘플에서는 XamlBuildTask 도구를 실행할 필요 없이 XAML 워크플로를 동적으로 로드하는 방법을 보여 줍니다. 이 샘플에서는 대신 <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> 메서드를 호출합니다. 샘플은 Windows Presentation Foundation (WPF) 클라이언트 응용 프로그램을 사용 하 여 XAML 워크플로 로드 합니다 <xref:System.Activities.XamlIntegration.ActivityXamlServices> 클래스 및 실행 합니다. <xref:System.Activities.XamlIntegration.ActivityXamlServices> 클래스를 사용하여 XAML 워크플로를 로드한 후에는 실행할 수 있는 <xref:System.Activities.DynamicActivity%601>가 반환됩니다.

#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면

1. LoadFromXAML.sln 솔루션 파일을 열고 Visual Studio 2010을 사용 합니다.

2. Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.

3. Ctrl+F5를 눌러 솔루션을 실행합니다.

> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\DynamicActivity\LoadFromXAML`