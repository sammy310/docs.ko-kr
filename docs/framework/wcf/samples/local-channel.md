---
title: 로컬 채널
ms.date: 03/30/2017
ms.assetid: fa1917a4-f701-4e82-a439-14a16282c7cc
ms.openlocfilehash: 6bc1fac22f6eed3c9acb6b86f7611cbfb4e1d371
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74714892"
---
# <a name="local-channel"></a><span data-ttu-id="4fb8f-102">로컬 채널</span><span class="sxs-lookup"><span data-stu-id="4fb8f-102">Local Channel</span></span>
<span data-ttu-id="4fb8f-103">로컬 채널은 동일한 응용 프로그램 도메인 내에서 통신 하는 데 사용 되는 WCF (Windows Communication Foundation) 전송 채널입니다.</span><span class="sxs-lookup"><span data-stu-id="4fb8f-103">Local Channel is a Windows Communication Foundation (WCF) transport channel that is used for communication within the same application domain.</span></span> <span data-ttu-id="4fb8f-104">로컬 채널은 클라이언트와 서비스가 동일한 애플리케이션 도메인에서 실행 중이고 일반적인 WCF 채널 스택(메시지의 serialization 및 deserialization)의 오버헤드를 방지해야 하는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb8f-104">This is useful for scenarios where the client and the service are running in the same application domain and the overhead of the typical WCF channel stack (serialization and deserialization of messages) must be avoided.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="4fb8f-105">데모</span><span class="sxs-lookup"><span data-stu-id="4fb8f-105">Demonstrates</span></span>  
 <span data-ttu-id="4fb8f-106">로컬 채널</span><span class="sxs-lookup"><span data-stu-id="4fb8f-106">Local Channel</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="4fb8f-107">토론</span><span class="sxs-lookup"><span data-stu-id="4fb8f-107">Discussion</span></span>  
 <span data-ttu-id="4fb8f-108">이 샘플은 다음의 두 프로젝트 파일로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb8f-108">The sample consists of two project files:</span></span>  
  
- <span data-ttu-id="4fb8f-109">**Localchannel**: 현재 응용 프로그램 도메인 내에서 로컬 채널의 프로그래밍 방식 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="4fb8f-109">**LocalChannel**: The programmatic representation of the local channel within the current application domain.</span></span> <span data-ttu-id="4fb8f-110">이 프로젝트에서 보내기 구성 요소는 메시지를 메모리 내 큐에 넣고 받기 구성 요소는 메시지를 큐에서 꺼내 해당 메시지를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb8f-110">In this project, the sending component places the message in an in-memory queue and the receiving component de-queues the message to receive it.</span></span>  
  
- <span data-ttu-id="4fb8f-111">**Clientandservice**:이 프로젝트는 콘솔 응용 프로그램에서 서비스를 호스팅하고 클라이언트를 실행 하 여 동일한 응용 프로그램 도메인 내에서 서비스를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb8f-111">**ClientAndService**: This project hosts a service in a console application and then runs a client to call the service from within the same application domain.</span></span>  
  
 <span data-ttu-id="4fb8f-112">로컬 채널 디자인은 채널 스택과 serialization 프로세스를 모두 건너뛰므로 속도가 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="4fb8f-112">The local channel design skips both the channel stack and the serialization process to increase speed.</span></span> <span data-ttu-id="4fb8f-113">로컬 전송 채널은 클라이언트의 서비스 호출을 서비스로 전송하고 값을 클라이언트에 다시 반환하는 큐를 사용하여 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fb8f-113">The local transport channel is implemented using a queue to transport service calls from the client to the service and to return back the value to the client.</span></span> <span data-ttu-id="4fb8f-114">매개 변수 및 반환 값을 serialize하는 대신 이 샘플에서는 해당 개체를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb8f-114">Rather than serializing parameters and return values, the sample copies the objects.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="4fb8f-115">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="4fb8f-115">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="4fb8f-116">LocalChannel 솔루션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb8f-116">Build and run the LocalChannel solution.</span></span>  
  
2. <span data-ttu-id="4fb8f-117">서비스 호스트가 시작되고 클라이언트가 로컬 채널을 사용하여 서비스를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb8f-117">The service host is started and the client calls the service using the local channel.</span></span> <span data-ttu-id="4fb8f-118">콘솔 창에 서비스 호출 결과가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fb8f-118">A console window appears to display the results of the service call.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="4fb8f-119">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb8f-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="4fb8f-120">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="4fb8f-120">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="4fb8f-121">이 디렉터리가 없으면 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb8f-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4fb8f-122">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb8f-122">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\LocalChannel`
