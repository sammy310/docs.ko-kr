---
title: '방법: ChannelFactory 사용'
description: WCF 클라이언트를 사용 하 여 서비스에 액세스 하기 위해 채널 팩터리를 만드는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d48f01b5-582b-4c8b-b547-8adddae7e371
ms.openlocfilehash: dd767443fefb16ebc02300bffa4264357f12c3ae
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280587"
---
# <a name="how-to-use-the-channelfactory"></a><span data-ttu-id="fe63e-103">방법: ChannelFactory 사용</span><span class="sxs-lookup"><span data-stu-id="fe63e-103">How to: Use the ChannelFactory</span></span>

<span data-ttu-id="fe63e-104">제네릭 <xref:System.ServiceModel.ChannelFactory%601> 클래스는 둘 이상의 채널을 만드는 데 사용할 수 있는 채널 팩터리를 만들어야 하는 고급 시나리오에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe63e-104">The generic <xref:System.ServiceModel.ChannelFactory%601> class is used in advanced scenarios that require the creation of a channel factory that can be used to create more than one channel.</span></span>  
  
### <a name="to-create-and-use-the-channelfactory-class"></a><span data-ttu-id="fe63e-105">ChannelFactory 클래스를 만들고 사용하려면</span><span class="sxs-lookup"><span data-stu-id="fe63e-105">To create and use the ChannelFactory class</span></span>  
  
1. <span data-ttu-id="fe63e-106">WCF (Windows Communication Foundation) 서비스를 빌드하고 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe63e-106">Build and run an Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="fe63e-107">자세한 내용은 [서비스 디자인 및 구현](../designing-and-implementing-services.md), [서비스 구성](../configuring-services.md)및 [서비스 호스팅](../hosting-services.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fe63e-107">For more information, see [Designing and Implementing Services](../designing-and-implementing-services.md), [Configuring Services](../configuring-services.md), and [Hosting Services](../hosting-services.md).</span></span>  
  
2. <span data-ttu-id="fe63e-108">[ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) 를 사용 하 여 클라이언트에 대 한 계약 (인터페이스)을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe63e-108">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the contract (interface) for the client.</span></span>  
  
3. <span data-ttu-id="fe63e-109">클라이언트 코드에서 <xref:System.ServiceModel.ChannelFactory%601> 클래스를 사용하여 여러 개의 엔드포인트 수신기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fe63e-109">In the client code, use the <xref:System.ServiceModel.ChannelFactory%601> class to create multiple endpoint listeners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe63e-110">예제</span><span class="sxs-lookup"><span data-stu-id="fe63e-110">Example</span></span>  

 [!code-csharp[c_HowToUseChannelFactory#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtousechannelfactory/cs/source.cs#1)]
 [!code-vb[c_HowToUseChannelFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtousechannelfactory/vb/source.vb#1)]
