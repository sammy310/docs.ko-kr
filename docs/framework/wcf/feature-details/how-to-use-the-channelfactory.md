---
title: '방법: ChannelFactory 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d48f01b5-582b-4c8b-b547-8adddae7e371
ms.openlocfilehash: 7d542a3dcae514e75194b49c23a8dec5dd7e8c3b
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59298853"
---
# <a name="how-to-use-the-channelfactory"></a><span data-ttu-id="4c636-102">방법: ChannelFactory 사용</span><span class="sxs-lookup"><span data-stu-id="4c636-102">How to: Use the ChannelFactory</span></span>
<span data-ttu-id="4c636-103">제네릭 <xref:System.ServiceModel.ChannelFactory%601> 클래스는 둘 이상의 채널을 만드는 데 사용할 수 있는 채널 팩터리를 만들어야 하는 고급 시나리오에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c636-103">The generic <xref:System.ServiceModel.ChannelFactory%601> class is used in advanced scenarios that require the creation of a channel factory that can be used to create more than one channel.</span></span>  
  
### <a name="to-create-and-use-the-channelfactory-class"></a><span data-ttu-id="4c636-104">ChannelFactory 클래스를 만들고 사용하려면</span><span class="sxs-lookup"><span data-stu-id="4c636-104">To create and use the ChannelFactory class</span></span>  
  
1. <span data-ttu-id="4c636-105">빌드하고 Windows Communication Foundation (WCF) 서비스를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c636-105">Build and run an Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="4c636-106">자세한 내용은 [서비스 디자인 및 구현](../../../../docs/framework/wcf/designing-and-implementing-services.md)를 [서비스 구성](../../../../docs/framework/wcf/configuring-services.md), 및 [호스팅 서비스](../../../../docs/framework/wcf/hosting-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4c636-106">For more information, see [Designing and Implementing Services](../../../../docs/framework/wcf/designing-and-implementing-services.md), [Configuring Services](../../../../docs/framework/wcf/configuring-services.md), and [Hosting Services](../../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
2. <span data-ttu-id="4c636-107">사용 합니다 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 클라이언트에 대 한 계약 (인터페이스)를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c636-107">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the contract (interface) for the client.</span></span>  
  
3. <span data-ttu-id="4c636-108">클라이언트 코드에서 <xref:System.ServiceModel.ChannelFactory%601> 클래스를 사용하여 여러 개의 엔드포인트 수신기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4c636-108">In the client code, use the <xref:System.ServiceModel.ChannelFactory%601> class to create multiple endpoint listeners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c636-109">예제</span><span class="sxs-lookup"><span data-stu-id="4c636-109">Example</span></span>  
 [!code-csharp[c_HowToUseChannelFactory#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtousechannelfactory/cs/source.cs#1)]
 [!code-vb[c_HowToUseChannelFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtousechannelfactory/vb/source.vb#1)]
