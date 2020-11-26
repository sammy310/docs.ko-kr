---
title: 구성 채널 팩터리
ms.date: 03/30/2017
ms.assetid: 3b749493-bd8a-4ccb-893e-5948901a1486
ms.openlocfilehash: bebdd7e5913fd3bbc1ab88d32e6612b9bc951852
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96241150"
---
# <a name="configuration-channel-factory"></a><span data-ttu-id="4a4fc-102">구성 채널 팩터리</span><span class="sxs-lookup"><span data-stu-id="4a4fc-102">Configuration Channel Factory</span></span>

<span data-ttu-id="4a4fc-103">이 샘플에서는 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>의 사용법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4fc-103">This sample covers the usage of the <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>.</span></span> <span data-ttu-id="4a4fc-104">에서는 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> WCF 클라이언트 구성의 중앙 관리를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a4fc-104">The <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> allows central management of WCF client configuration.</span></span> <span data-ttu-id="4a4fc-105">애플리케이션 도메인의 로드 이후 구성이 선택되었거나 변경된 경우에도 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4fc-105">This can also be useful in scenarios in which configuration is selected or changed after the application domain load time.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="4a4fc-106">데모</span><span class="sxs-lookup"><span data-stu-id="4a4fc-106">Demonstrates</span></span>

 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>

## <a name="discussion"></a><span data-ttu-id="4a4fc-107">토론(Discussion)</span><span class="sxs-lookup"><span data-stu-id="4a4fc-107">Discussion</span></span>

 <span data-ttu-id="4a4fc-108">이 샘플에서는 기본 애플리케이션 구성 파일을 사용할 필요 없이 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>를 사용하여 클라이언트 애플리케이션에 특정 구성 파일을 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4a4fc-108">This sample shows how to use <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> to add a particular configuration file to a client application, without having to use the default application configuration file.</span></span>

 <span data-ttu-id="4a4fc-109">이 샘플은 두 프로젝트로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a4fc-109">The sample consists of two projects.</span></span> <span data-ttu-id="4a4fc-110">첫 번째 프로젝트는 클라이언트가 보내는 메시지에 회신하기 위해 실행되는 간단한 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="4a4fc-110">The first project is a simple service that runs to reply to messages coming from the clients.</span></span> <span data-ttu-id="4a4fc-111">두 번째 프로젝트는 Test.config 구성 파일에 대해 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>을 사용하여 두 개의 <xref:System.Configuration.ExeConfigurationFileMap> 개체를 빌드하고 이 개체를 사용하여 서비스와 통신하는 클라이언트 애플리케이션입니다.</span><span class="sxs-lookup"><span data-stu-id="4a4fc-111">The second project is a client application that builds two <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> objects using a <xref:System.Configuration.ExeConfigurationFileMap> for the Test.config configuration file and uses them to communicate with the service.</span></span> <span data-ttu-id="4a4fc-112">두 클라이언트 모두 Test.config에 지정된 구성을 사용하여 서비스와 통신합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4fc-112">Both clients communicate with the service using the configuration specified in Test.config.</span></span>

 <span data-ttu-id="4a4fc-113">다음 코드에서는 클라이언트 애플리케이션에 사용자 지정 구성 파일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4fc-113">The following code adds a custom configuration file to a client application.</span></span>

```csharp
ExeConfigurationFileMap fileMap = new ExeConfigurationFileMap();
fileMap.ExeConfigFilename = "Test.config";
Configuration newConfiguration = ConfigurationManager.OpenMappedExeConfiguration(fileMap, ConfigurationUserLevel.None);

ConfigurationChannelFactory<ICalculatorChannel> factory1 = new ConfigurationChannelFactory<ICalculatorChannel>("endpoint1", newConfiguration, new EndpointAddress("http://localhost:8000/servicemodelsamples/service"));
ICalculatorChannel client1 = factory1.CreateChannel();
```

#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="4a4fc-114">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="4a4fc-114">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="4a4fc-115">관리자 권한으로 Visual Studio 2012을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4a4fc-115">Open Visual Studio 2012 with administrator privileges.</span></span>

2. <span data-ttu-id="4a4fc-116">ConfigurationChannelFactory 솔루션 (프로젝트 2 개)을 마우스 오른쪽 단추로 클릭 한 다음 **속성** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4fc-116">Right-click the ConfigurationChannelFactory solution (2 projects) and then select **Properties**.</span></span>

3. <span data-ttu-id="4a4fc-117">**공용 속성** 에서 **시작 프로젝트** 를 선택한 다음 **여러 개의 시작 프로젝트** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4fc-117">In **Common Properties**, select **Startup Project**, and then click **Multiple startup projects**.</span></span>

4. <span data-ttu-id="4a4fc-118">**서비스 프로젝트** 를 **' start ' 작업** 을 사용 하 여 목록의 시작 부분으로 이동한 다음 **클라이언트** 프로젝트를 **' Start ' 작업** 을 사용 하 여 **서비스** 프로젝트 뒤로 이동 하 여 **서비스 프로젝트 이후에** **클라이언트** 프로젝트가 실행 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4fc-118">Move the **Service** project to the beginning of the list, with the **Action ‘Start’**, and then move the **Client** project after the **Service** project, also with the **Action ‘Start’**, so the **Client** project is executed after the **Service** project.</span></span>

5. <span data-ttu-id="4a4fc-119">**확인** 을 클릭 한 다음 F5 키 (또는 CTRL + F5)를 눌러 샘플을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4fc-119">Click **OK**, and then press F5 (or CTRL+F5) to run the sample.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4a4fc-120">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a4fc-120">The samples may already be installed on your machine.</span></span> <span data-ttu-id="4a4fc-121">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="4a4fc-121">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="4a4fc-122">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4fc-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4a4fc-123">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a4fc-123">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigurationChannelFactory`
