---
description: '다음에 대 한 자세한 정보: TcpConnectionPoolSettings'
title: TcpConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 19acfba3-c057-4dbc-bac7-8674d7844d83
ms.openlocfilehash: 927fcba7f94bcbfa80e06479e79bf20986a661e3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99715199"
---
# <a name="tcpconnectionpoolsettings"></a><span data-ttu-id="7f9ec-103">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="7f9ec-103">TcpConnectionPoolSettings</span></span>

<span data-ttu-id="7f9ec-104">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="7f9ec-104">TcpConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f9ec-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7f9ec-105">Syntax</span></span>  
  
```csharp
class TcpConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="7f9ec-106">메서드</span><span class="sxs-lookup"><span data-stu-id="7f9ec-106">Methods</span></span>  

 <span data-ttu-id="7f9ec-107">TcpConnectionPoolSettings 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7f9ec-107">The TcpConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="7f9ec-108">속성</span><span class="sxs-lookup"><span data-stu-id="7f9ec-108">Properties</span></span>  

 <span data-ttu-id="7f9ec-109">TcpConnectionPoolSettings 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f9ec-109">The TcpConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="7f9ec-110">GroupName</span><span class="sxs-lookup"><span data-stu-id="7f9ec-110">GroupName</span></span>  

 <span data-ttu-id="7f9ec-111">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="7f9ec-111">Data type: string</span></span>  
  
 <span data-ttu-id="7f9ec-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="7f9ec-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7f9ec-113">바인딩 요소가 사용하는 연결 풀의 그룹 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7f9ec-113">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="7f9ec-114">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="7f9ec-114">IdleTimeout</span></span>  

 <span data-ttu-id="7f9ec-115">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="7f9ec-115">Data type: datetime</span></span>  
  
 <span data-ttu-id="7f9ec-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="7f9ec-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7f9ec-117">연결이 끊어지기 전에 유휴 상태일 수 있는 최대 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="7f9ec-117">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="7f9ec-118">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="7f9ec-118">LeaseTimeout</span></span>  

 <span data-ttu-id="7f9ec-119">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="7f9ec-119">Data type: datetime</span></span>  
  
 <span data-ttu-id="7f9ec-120">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="7f9ec-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7f9ec-121">제한 시간을 초과하기 전에 대여 작업을 완료하기 위한 최대 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="7f9ec-121">The maximum time for the lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="7f9ec-122">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="7f9ec-122">MaxOutboundConnectionsPerEndpoint</span></span>  

 <span data-ttu-id="7f9ec-123">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="7f9ec-123">Data type: sint32</span></span>  
  
 <span data-ttu-id="7f9ec-124">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="7f9ec-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7f9ec-125">각 엔드포인트에 대한 최대 아웃바운드 연결 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7f9ec-125">The maximum outbound connections for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f9ec-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7f9ec-126">Requirements</span></span>  
  
|<span data-ttu-id="7f9ec-127">MOF</span><span class="sxs-lookup"><span data-stu-id="7f9ec-127">MOF</span></span>|<span data-ttu-id="7f9ec-128">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f9ec-128">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="7f9ec-129">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="7f9ec-129">Namespace</span></span>|<span data-ttu-id="7f9ec-130">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f9ec-130">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7f9ec-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7f9ec-131">See also</span></span>

- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
