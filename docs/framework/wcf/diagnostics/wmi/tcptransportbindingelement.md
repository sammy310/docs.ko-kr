---
title: TcpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 33bbc1e5-44e4-4ee3-b7b5-801dc78956e4
ms.openlocfilehash: 6af85d62fffada95537494692b8694f42d7a2932
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96290090"
---
# <a name="tcptransportbindingelement"></a><span data-ttu-id="60d1d-102">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="60d1d-102">TcpTransportBindingElement</span></span>

<span data-ttu-id="60d1d-103">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="60d1d-103">TcpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60d1d-104">구문</span><span class="sxs-lookup"><span data-stu-id="60d1d-104">Syntax</span></span>  
  
```csharp
class TcpTransportBindingElement : ConnectionOrientedTransportBindingElement  
{  
  TcpConnectionPoolSettings ConnectionPoolSettings;  
  sint32 ListenBacklog;  
  boolean PortSharingEnabled;  
  boolean TeredoEnabled;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="60d1d-105">메서드</span><span class="sxs-lookup"><span data-stu-id="60d1d-105">Methods</span></span>  

 <span data-ttu-id="60d1d-106">TcpTransportBindingElement 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="60d1d-106">The TcpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="60d1d-107">속성</span><span class="sxs-lookup"><span data-stu-id="60d1d-107">Properties</span></span>  

 <span data-ttu-id="60d1d-108">TcpTransportBindingElement 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60d1d-108">The TcpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="connectionpoolsettings"></a><span data-ttu-id="60d1d-109">ConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="60d1d-109">ConnectionPoolSettings</span></span>  

 <span data-ttu-id="60d1d-110">데이터 형식: TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="60d1d-110">Data type: TcpConnectionPoolSettings</span></span>  
  
 <span data-ttu-id="60d1d-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="60d1d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="60d1d-112">연결 풀 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="60d1d-112">The connection pool settings.</span></span>  
  
### <a name="listenbacklog"></a><span data-ttu-id="60d1d-113">ListenBacklog</span><span class="sxs-lookup"><span data-stu-id="60d1d-113">ListenBacklog</span></span>  

 <span data-ttu-id="60d1d-114">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="60d1d-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="60d1d-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="60d1d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="60d1d-116">보류할 수 있는 최대 대기 중인 연결 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="60d1d-116">The maximum number of queued connection requests that can be pending.</span></span>  
  
### <a name="portsharingenabled"></a><span data-ttu-id="60d1d-117">PortSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="60d1d-117">PortSharingEnabled</span></span>  

 <span data-ttu-id="60d1d-118">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="60d1d-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="60d1d-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="60d1d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="60d1d-120">이 연결에서 TCP 포트 공유를 사용하는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="60d1d-120">A boolean value that specifies whether TCP port sharing is enabled for this connection.</span></span>  
  
### <a name="teredoenabled"></a><span data-ttu-id="60d1d-121">TeredoEnabled</span><span class="sxs-lookup"><span data-stu-id="60d1d-121">TeredoEnabled</span></span>  

 <span data-ttu-id="60d1d-122">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="60d1d-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="60d1d-123">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="60d1d-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="60d1d-124">Teredo(방화벽으로 보호되는 클라이언트의 주소를 지정하는 기술)의 사용 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="60d1d-124">A boolean value that specifies whether Teredo (a technology for addressing clients that are behind firewalls) is enabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60d1d-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="60d1d-125">Requirements</span></span>  
  
|<span data-ttu-id="60d1d-126">MOF</span><span class="sxs-lookup"><span data-stu-id="60d1d-126">MOF</span></span>|<span data-ttu-id="60d1d-127">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60d1d-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="60d1d-128">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="60d1d-128">Namespace</span></span>|<span data-ttu-id="60d1d-129">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60d1d-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="60d1d-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="60d1d-130">See also</span></span>

- <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
