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
# <a name="load-from-xaml"></a><span data-ttu-id="5725d-102">Load From XAML</span><span class="sxs-lookup"><span data-stu-id="5725d-102">Load From XAML</span></span>
<span data-ttu-id="5725d-103">이 샘플에서는 XamlBuildTask 도구를 실행할 필요 없이 XAML 워크플로를 동적으로 로드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5725d-103">This sample demonstrates how to dynamically load a XAML workflow without having to run the XamlBuildTask tool.</span></span> <span data-ttu-id="5725d-104">이 샘플에서는 대신 <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="5725d-104">Instead, the sample calls the <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> method.</span></span> <span data-ttu-id="5725d-105">샘플은 Windows Presentation Foundation (WPF) 클라이언트 응용 프로그램을 사용 하 여 XAML 워크플로 로드 합니다 <xref:System.Activities.XamlIntegration.ActivityXamlServices> 클래스 및 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5725d-105">The sample is a Windows Presentation Foundation (WPF) client application that loads XAML workflows using the <xref:System.Activities.XamlIntegration.ActivityXamlServices> class and executes them.</span></span> <span data-ttu-id="5725d-106"><xref:System.Activities.XamlIntegration.ActivityXamlServices> 클래스를 사용하여 XAML 워크플로를 로드한 후에는 실행할 수 있는 <xref:System.Activities.DynamicActivity%601>가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="5725d-106">After they have been loaded using the <xref:System.Activities.XamlIntegration.ActivityXamlServices> class, a <xref:System.Activities.DynamicActivity%601> is returned that can be executed.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="5725d-107">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="5725d-107">To use this sample</span></span>

1. <span data-ttu-id="5725d-108">LoadFromXAML.sln 솔루션 파일을 열고 Visual Studio 2010을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5725d-108">Using Visual Studio 2010, open the LoadFromXAML.sln solution file.</span></span>

2. <span data-ttu-id="5725d-109">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="5725d-109">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="5725d-110">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5725d-110">To run the solution, press CTRL+F5.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="5725d-111">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5725d-111">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5725d-112">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="5725d-112">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5725d-113">이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="5725d-113">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5725d-114">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5725d-114">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\DynamicActivity\LoadFromXAML`