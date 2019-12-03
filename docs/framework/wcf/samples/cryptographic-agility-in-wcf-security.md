---
title: WCF 보안의 암호화 민첩성
ms.date: 03/30/2017
ms.assetid: c2c549e5-ac19-40c5-b686-8f67f52b6dbf
ms.openlocfilehash: 2dbacd53876ded76ea212dd5656cd2dded4a6e48
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74714931"
---
# <a name="cryptographic-agility-in-wcf-security"></a><span data-ttu-id="16701-102">WCF 보안의 암호화 민첩성</span><span class="sxs-lookup"><span data-stu-id="16701-102">Cryptographic agility in WCF security</span></span>

<span data-ttu-id="16701-103">이 샘플에서는 Windows Communication Foundation (WCF) 클라이언트 및 서비스에서 암호화 agile 구현을 제공 하도록 표준/사용자 지정 알고리즘을 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="16701-103">This sample shows how to specify in a standard/custom algorithm to provide a cryptographic agile implementation in a Windows Communication Foundation (WCF) client and service.</span></span> <span data-ttu-id="16701-104">이 샘플은 다음 프로젝트로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16701-104">The sample is composed of the following projects:</span></span>

<span data-ttu-id="16701-105">**Service**</span><span class="sxs-lookup"><span data-stu-id="16701-105">**Service**</span></span>

<span data-ttu-id="16701-106">이는 `ICalculator` 인터페이스를 구현 하 고 보안 세션과 신뢰할 수 있는 세션을 사용 하지 않는 <xref:System.ServiceModel.WSHttpBinding>를 사용 하 여 끝점을 보호 하는 자체 호스팅 WCF 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="16701-106">This is a self-hosted WCF service that implements the `ICalculator` interface and secures the endpoint using the <xref:System.ServiceModel.WSHttpBinding> with secure session and reliable session disabled.</span></span> <span data-ttu-id="16701-107">이 서비스는 사용자 지정 `SecurityAlgorithmSuite` 클래스를 정의하여 메시지 보안에 사용할 암호화 알고리즘을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="16701-107">The service defines a custom `SecurityAlgorithmSuite` class to specify the cryptographic algorithms to be used for message security.</span></span>

<span data-ttu-id="16701-108">**클라이언트**</span><span class="sxs-lookup"><span data-stu-id="16701-108">**Client**</span></span>

<span data-ttu-id="16701-109">인증에 성공 하면 서비스에 액세스 하는 WCF 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="16701-109">This is a WCF client that accesses the service after successful authentication.</span></span> <span data-ttu-id="16701-110">이 클라이언트는 `ICalculator` 인터페이스에 의해 노출되고 서비스에 의해 구현된 작업을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="16701-110">It invokes the operations exposed by the `ICalculator` interface and implemented by the service.</span></span> <span data-ttu-id="16701-111">또한 클라이언트는 동일한 사용자 지정 `SecurityAlgorithmSuite` 클래스를 정의하여 메시지 보안에 사용할 암호화 알고리즘을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="16701-111">The client also defines the same custom `SecurityAlgorithmSuite` class to specify the cryptographic algorithms to be used for message security.</span></span>

## <a name="to-use-this-sample"></a><span data-ttu-id="16701-112">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="16701-112">To use this sample</span></span>

1. <span data-ttu-id="16701-113">Visual Studio 2012에서 CryptoAgility 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="16701-113">Open the CryptoAgility.sln solution in Visual Studio 2012.</span></span>

2. <span data-ttu-id="16701-114">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="16701-114">Press CTRL+SHIFT+B to build the solution.</span></span>

3. <span data-ttu-id="16701-115">파일 탐색기를 열고 \WCF\Basic\Security\CryptoAgility\Service\bin 디렉터리로 이동 하 고 setup.exe를 마우스 오른쪽 단추로 클릭 한 다음 **관리자 권한으로 실행**을 선택 하 여 관리자 권한으로 서비스 .exe 파일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="16701-115">Open File Explorer and navigate to the \WCF\Basic\Security\CryptoAgility\Service\bin directory and run the service.exe file with administrator privileges by right-clicking service.exe and selecting **Run as administrator**.</span></span>

4. <span data-ttu-id="16701-116">\WCF\Basic\Security\CryptoAgility\Client\bin 디렉터리로 이동하고 client.exe 파일을 정상적으로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="16701-116">Navigate to \WCF\Basic\Security\CryptoAgility\Client\bin directory and run the client.exe file normally.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="16701-117">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16701-117">The samples may already be installed on your machine.</span></span> <span data-ttu-id="16701-118">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="16701-118">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="16701-119">이 디렉터리가 없으면 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="16701-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="16701-120">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16701-120">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Security\CryptoAgility`

## <a name="see-also"></a><span data-ttu-id="16701-121">참조</span><span class="sxs-lookup"><span data-stu-id="16701-121">See also</span></span>

- [<span data-ttu-id="16701-122">Windows Communication Foundation 보안</span><span class="sxs-lookup"><span data-stu-id="16701-122">Windows Communication Foundation Security</span></span>](../feature-details/security.md)
