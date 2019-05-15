---
title: NetTcpBinding 응용 프로그램을 피어 채널 응용 프로그램으로 변환
ms.date: 03/30/2017
ms.assetid: d4137292-a923-4b8f-8594-42276f2d3ce2
ms.openlocfilehash: b89afbe59b73288ba357fa55ec5d55c1fb18352b
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65582791"
---
# <a name="converting-a-nettcpbinding-application-to-a-peer-channel-application"></a><span data-ttu-id="87d5c-102">NetTcpBinding 응용 프로그램을 피어 채널 응용 프로그램으로 변환</span><span class="sxs-lookup"><span data-stu-id="87d5c-102">Converting a NetTcpBinding Application to a Peer Channel Application</span></span>
<span data-ttu-id="87d5c-103">연결 매개 변수를 설명하는 바인딩을 사용하여 [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]에서 클라이언트 간의 연결을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87d5c-103">You can create connections between clients using the [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] by using bindings that describe the parameters of the connection.</span></span> <span data-ttu-id="87d5c-104">클라이언트 연결을 만들 때이 기술을 지 원하는 바인딩이 필요 피어-투-피어 연결을 사용 하려면.NET Framework 응용 프로그램을 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="87d5c-104">Converting a .NET Framework application to use peer-to-peer connections requires a binding that supports this technology when making client connections.</span></span> <span data-ttu-id="87d5c-105">피어 채널은 <xref:System.ServiceModel.NetPeerTcpBinding>과 유사한 방식으로 사용할 수 있는 <xref:System.ServiceModel.NetTcpBinding>이라는 바인딩을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="87d5c-105">Peer Channel provides a binding called <xref:System.ServiceModel.NetPeerTcpBinding>, which you can use in a similar way to the <xref:System.ServiceModel.NetTcpBinding>.</span></span> <span data-ttu-id="87d5c-106">주요 차이점에는 확인자 서비스 지정과 보안 설정 정의가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="87d5c-106">Key differences include specifying a resolver service and defining security settings.</span></span>  
  
 <span data-ttu-id="87d5c-107">응용 프로그램에서 기본 확인자와 보안 설정을 사용하는 경우 피어 채널을 사용하도록 일반 클라이언트/서버 기반 응용 프로그램을 변환하려면 응용 프로그램 구성 파일에서 바인딩의 이름을 "NetTcpBinding"에서 "NetPeerTcpBinding"으로 변경해야 합니다. 응용 프로그램 코드베이스는 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="87d5c-107">If an application is using the default resolver and security settings, converting a normal client/server-based application to use Peer Channel entails changing the name of the binding from "NetTcpBinding" to "NetPeerTcpBinding" in the application’s configuration file—you do not have to change the application code base.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87d5c-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="87d5c-108">See also</span></span>

- [<span data-ttu-id="87d5c-109">피어 채널 응용 프로그램 빌드</span><span class="sxs-lookup"><span data-stu-id="87d5c-109">Building a Peer Channel Application</span></span>](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md)
- [<span data-ttu-id="87d5c-110">시스템 제공 바인딩</span><span class="sxs-lookup"><span data-stu-id="87d5c-110">System-Provided Bindings</span></span>](../../../../docs/framework/wcf/system-provided-bindings.md)
