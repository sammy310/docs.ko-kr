---
description: '자세한 정보: PeerTransportBindingElement'
title: PeerTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
ms.openlocfilehash: b1ca8020f51a5f9b121f7d238d82b9971d13cdd4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757334"
---
# <a name="peertransportbindingelement"></a><span data-ttu-id="757eb-103">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="757eb-103">PeerTransportBindingElement</span></span>

<span data-ttu-id="757eb-104">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="757eb-104">PeerTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="757eb-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="757eb-105">Syntax</span></span>  
  
```csharp
class PeerTransportBindingElement : TransportBindingElement  
{  
  string ListenIPAddress;  
  sint32 Port;  
  PeerSecuritySettings Security;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="757eb-106">메서드</span><span class="sxs-lookup"><span data-stu-id="757eb-106">Methods</span></span>  

 <span data-ttu-id="757eb-107">PeerTransportBindingElement 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="757eb-107">The PeerTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="757eb-108">속성</span><span class="sxs-lookup"><span data-stu-id="757eb-108">Properties</span></span>  

 <span data-ttu-id="757eb-109">PeerTransportBindingElement 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="757eb-109">The PeerTransportBindingElement class has the following properties:</span></span>  
  
### <a name="listenipaddress"></a><span data-ttu-id="757eb-110">ListenIPAddress</span><span class="sxs-lookup"><span data-stu-id="757eb-110">ListenIPAddress</span></span>  

 <span data-ttu-id="757eb-111">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="757eb-111">Data type: string</span></span>  
  
 <span data-ttu-id="757eb-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="757eb-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="757eb-113">피어 노드가 메시지를 수신하는 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="757eb-113">The IP address on which the peer node listens for messages.</span></span>  
  
### <a name="port"></a><span data-ttu-id="757eb-114">포트</span><span class="sxs-lookup"><span data-stu-id="757eb-114">Port</span></span>  

 <span data-ttu-id="757eb-115">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="757eb-115">Data type: sint32</span></span>  
  
 <span data-ttu-id="757eb-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="757eb-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="757eb-117">이 바인딩이 피어 채널 메시지를 처리할 네트워크 인터페이스 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="757eb-117">The network interface port on which this binding processes peer channel messages.</span></span>  
  
### <a name="security"></a><span data-ttu-id="757eb-118">보안</span><span class="sxs-lookup"><span data-stu-id="757eb-118">Security</span></span>  

 <span data-ttu-id="757eb-119">데이터 형식: PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="757eb-119">Data type: PeerSecuritySettings</span></span>  
  
 <span data-ttu-id="757eb-120">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="757eb-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="757eb-121">피어 전송 보안 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="757eb-121">Peer transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="757eb-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="757eb-122">Requirements</span></span>  
  
|<span data-ttu-id="757eb-123">MOF</span><span class="sxs-lookup"><span data-stu-id="757eb-123">MOF</span></span>|<span data-ttu-id="757eb-124">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="757eb-124">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="757eb-125">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="757eb-125">Namespace</span></span>|<span data-ttu-id="757eb-126">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="757eb-126">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="757eb-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="757eb-127">See also</span></span>

- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
