---
description: '자세한 정보: WCF 보안의 암호화 민첩성'
title: WCF 보안의 암호화 민첩성
ms.date: 03/30/2017
ms.assetid: c2c549e5-ac19-40c5-b686-8f67f52b6dbf
ms.openlocfilehash: ab46034b16a846f7399220480fc928655d931be0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99778349"
---
# <a name="cryptographic-agility-in-wcf-security"></a><span data-ttu-id="fd71a-103">WCF 보안의 암호화 민첩성</span><span class="sxs-lookup"><span data-stu-id="fd71a-103">Cryptographic agility in WCF security</span></span>

<span data-ttu-id="fd71a-104">이 샘플에서는 Windows Communication Foundation (WCF) 클라이언트 및 서비스에서 암호화 agile 구현을 제공 하도록 표준/사용자 지정 알고리즘을 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fd71a-104">This sample shows how to specify in a standard/custom algorithm to provide a cryptographic agile implementation in a Windows Communication Foundation (WCF) client and service.</span></span> <span data-ttu-id="fd71a-105">이 샘플은 다음 프로젝트로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd71a-105">The sample is composed of the following projects:</span></span>

<span data-ttu-id="fd71a-106">**서비스**</span><span class="sxs-lookup"><span data-stu-id="fd71a-106">**Service**</span></span>

<span data-ttu-id="fd71a-107">이는 인터페이스를 구현 하 `ICalculator` 고 <xref:System.ServiceModel.WSHttpBinding> 보안 세션 및 신뢰할 수 있는 세션을 사용 하 여 끝점을 보호 하는 자체 호스팅 WCF 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="fd71a-107">This is a self-hosted WCF service that implements the `ICalculator` interface and secures the endpoint using the <xref:System.ServiceModel.WSHttpBinding> with secure session and reliable session disabled.</span></span> <span data-ttu-id="fd71a-108">이 서비스는 사용자 지정 `SecurityAlgorithmSuite` 클래스를 정의하여 메시지 보안에 사용할 암호화 알고리즘을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fd71a-108">The service defines a custom `SecurityAlgorithmSuite` class to specify the cryptographic algorithms to be used for message security.</span></span>

<span data-ttu-id="fd71a-109">**클라이언트**</span><span class="sxs-lookup"><span data-stu-id="fd71a-109">**Client**</span></span>

<span data-ttu-id="fd71a-110">인증에 성공 하면 서비스에 액세스 하는 WCF 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="fd71a-110">This is a WCF client that accesses the service after successful authentication.</span></span> <span data-ttu-id="fd71a-111">이 클라이언트는 `ICalculator` 인터페이스에 의해 노출되고 서비스에 의해 구현된 작업을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="fd71a-111">It invokes the operations exposed by the `ICalculator` interface and implemented by the service.</span></span> <span data-ttu-id="fd71a-112">또한 클라이언트는 동일한 사용자 지정 `SecurityAlgorithmSuite` 클래스를 정의하여 메시지 보안에 사용할 암호화 알고리즘을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fd71a-112">The client also defines the same custom `SecurityAlgorithmSuite` class to specify the cryptographic algorithms to be used for message security.</span></span>

## <a name="to-use-this-sample"></a><span data-ttu-id="fd71a-113">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="fd71a-113">To use this sample</span></span>

1. <span data-ttu-id="fd71a-114">Visual Studio 2012에서 CryptoAgility 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="fd71a-114">Open the CryptoAgility.sln solution in Visual Studio 2012.</span></span>

2. <span data-ttu-id="fd71a-115">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="fd71a-115">Press CTRL+SHIFT+B to build the solution.</span></span>

3. <span data-ttu-id="fd71a-116">파일 탐색기를 열고 \WCF\Basic\Security\CryptoAgility\Service\bin 디렉터리로 이동한 후 service.exe을 마우스 오른쪽 단추로 클릭 하 고 **관리자 권한으로 실행** 을 선택 하 여 관리자 권한으로 service.exe 파일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd71a-116">Open File Explorer and navigate to the \WCF\Basic\Security\CryptoAgility\Service\bin directory and run the service.exe file with administrator privileges by right-clicking service.exe and selecting **Run as administrator**.</span></span>

4. <span data-ttu-id="fd71a-117">\WCF\Basic\Security\CryptoAgility\Client\bin 디렉터리로 이동하고 client.exe 파일을 정상적으로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fd71a-117">Navigate to \WCF\Basic\Security\CryptoAgility\Client\bin directory and run the client.exe file normally.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fd71a-118">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd71a-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="fd71a-119">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="fd71a-119">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="fd71a-120">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd71a-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="fd71a-121">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd71a-121">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Security\CryptoAgility`

## <a name="see-also"></a><span data-ttu-id="fd71a-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fd71a-122">See also</span></span>

- [<span data-ttu-id="fd71a-123">Windows Communication Foundation 보안</span><span class="sxs-lookup"><span data-stu-id="fd71a-123">Windows Communication Foundation Security</span></span>](../feature-details/security.md)
