---
description: '에 대 한 자세한 정보: TcpTransportBindingElement'
title: TcpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 33bbc1e5-44e4-4ee3-b7b5-801dc78956e4
ms.openlocfilehash: b52bb2eb4b40648808459f76e068a6f72f9476a4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99715147"
---
# <a name="tcptransportbindingelement"></a><span data-ttu-id="5208b-103">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="5208b-103">TcpTransportBindingElement</span></span>

<span data-ttu-id="5208b-104">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="5208b-104">TcpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5208b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5208b-105">Syntax</span></span>  
  
```csharp
class TcpTransportBindingElement : ConnectionOrientedTransportBindingElement  
{  
  TcpConnectionPoolSettings ConnectionPoolSettings;  
  sint32 ListenBacklog;  
  boolean PortSharingEnabled;  
  boolean TeredoEnabled;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="5208b-106">메서드</span><span class="sxs-lookup"><span data-stu-id="5208b-106">Methods</span></span>  

 <span data-ttu-id="5208b-107">TcpTransportBindingElement 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5208b-107">The TcpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="5208b-108">속성</span><span class="sxs-lookup"><span data-stu-id="5208b-108">Properties</span></span>  

 <span data-ttu-id="5208b-109">TcpTransportBindingElement 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5208b-109">The TcpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="connectionpoolsettings"></a><span data-ttu-id="5208b-110">ConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="5208b-110">ConnectionPoolSettings</span></span>  

 <span data-ttu-id="5208b-111">데이터 형식: TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="5208b-111">Data type: TcpConnectionPoolSettings</span></span>  
  
 <span data-ttu-id="5208b-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="5208b-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5208b-113">연결 풀 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="5208b-113">The connection pool settings.</span></span>  
  
### <a name="listenbacklog"></a><span data-ttu-id="5208b-114">ListenBacklog</span><span class="sxs-lookup"><span data-stu-id="5208b-114">ListenBacklog</span></span>  

 <span data-ttu-id="5208b-115">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="5208b-115">Data type: sint32</span></span>  
  
 <span data-ttu-id="5208b-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="5208b-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5208b-117">보류할 수 있는 최대 대기 중인 연결 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="5208b-117">The maximum number of queued connection requests that can be pending.</span></span>  
  
### <a name="portsharingenabled"></a><span data-ttu-id="5208b-118">PortSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="5208b-118">PortSharingEnabled</span></span>  

 <span data-ttu-id="5208b-119">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="5208b-119">Data type: boolean</span></span>  
  
 <span data-ttu-id="5208b-120">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="5208b-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5208b-121">이 연결에서 TCP 포트 공유를 사용하는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5208b-121">A boolean value that specifies whether TCP port sharing is enabled for this connection.</span></span>  
  
### <a name="teredoenabled"></a><span data-ttu-id="5208b-122">TeredoEnabled</span><span class="sxs-lookup"><span data-stu-id="5208b-122">TeredoEnabled</span></span>  

 <span data-ttu-id="5208b-123">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="5208b-123">Data type: boolean</span></span>  
  
 <span data-ttu-id="5208b-124">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="5208b-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5208b-125">Teredo(방화벽으로 보호되는 클라이언트의 주소를 지정하는 기술)의 사용 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5208b-125">A boolean value that specifies whether Teredo (a technology for addressing clients that are behind firewalls) is enabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5208b-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5208b-126">Requirements</span></span>  
  
|<span data-ttu-id="5208b-127">MOF</span><span class="sxs-lookup"><span data-stu-id="5208b-127">MOF</span></span>|<span data-ttu-id="5208b-128">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5208b-128">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="5208b-129">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="5208b-129">Namespace</span></span>|<span data-ttu-id="5208b-130">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5208b-130">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5208b-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5208b-131">See also</span></span>

- <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
