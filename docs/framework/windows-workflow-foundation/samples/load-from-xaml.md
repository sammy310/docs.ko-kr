---
description: '자세히 알아보기: XAML에서 로드'
title: Load From XAML
ms.date: 03/30/2017
ms.assetid: 1f103ef6-7bed-4f16-ae52-9e665c5a43d7
ms.openlocfilehash: fd0eca487c0245c7bfa46ca80c06f2adfa577353
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99742032"
---
# <a name="load-from-xaml"></a><span data-ttu-id="1e3f8-103">Load From XAML</span><span class="sxs-lookup"><span data-stu-id="1e3f8-103">Load From XAML</span></span>

<span data-ttu-id="1e3f8-104">이 샘플에서는 XamlBuildTask 도구를 실행할 필요 없이 XAML 워크플로를 동적으로 로드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1e3f8-104">This sample demonstrates how to dynamically load a XAML workflow without having to run the XamlBuildTask tool.</span></span> <span data-ttu-id="1e3f8-105">이 샘플에서는 대신 <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1e3f8-105">Instead, the sample calls the <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> method.</span></span> <span data-ttu-id="1e3f8-106">이 샘플은 클래스를 사용 하 여 XAML 워크플로를 로드 하 고 실행 하는 Windows Presentation Foundation (WPF) 클라이언트 응용 프로그램입니다 <xref:System.Activities.XamlIntegration.ActivityXamlServices> .</span><span class="sxs-lookup"><span data-stu-id="1e3f8-106">The sample is a Windows Presentation Foundation (WPF) client application that loads XAML workflows using the <xref:System.Activities.XamlIntegration.ActivityXamlServices> class and executes them.</span></span> <span data-ttu-id="1e3f8-107"><xref:System.Activities.XamlIntegration.ActivityXamlServices> 클래스를 사용하여 XAML 워크플로를 로드한 후에는 실행할 수 있는 <xref:System.Activities.DynamicActivity%601>가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e3f8-107">After they have been loaded using the <xref:System.Activities.XamlIntegration.ActivityXamlServices> class, a <xref:System.Activities.DynamicActivity%601> is returned that can be executed.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="1e3f8-108">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="1e3f8-108">To use this sample</span></span>

1. <span data-ttu-id="1e3f8-109">Visual Studio 2010을 사용 하 여 LoadFromXAML 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1e3f8-109">Using Visual Studio 2010, open the LoadFromXAML.sln solution file.</span></span>

2. <span data-ttu-id="1e3f8-110">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="1e3f8-110">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="1e3f8-111">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1e3f8-111">To run the solution, press CTRL+F5.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1e3f8-112">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e3f8-112">The samples may already be installed on your machine.</span></span> <span data-ttu-id="1e3f8-113">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="1e3f8-113">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="1e3f8-114">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e3f8-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1e3f8-115">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e3f8-115">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\DynamicActivity\LoadFromXAML`
