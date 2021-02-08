---
description: '자세히 알아보기: NamedPipeConnectionPoolSettings'
title: NamedPipeConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 079bccb8-54b5-4436-a43d-5567763f72ce
ms.openlocfilehash: 8d724c7a24f62a8d48797125528eb8a194ece660
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803115"
---
# <a name="namedpipeconnectionpoolsettings"></a><span data-ttu-id="96c34-103">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="96c34-103">NamedPipeConnectionPoolSettings</span></span>

<span data-ttu-id="96c34-104">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="96c34-104">NamedPipeConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96c34-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="96c34-105">Syntax</span></span>  
  
```csharp
class NamedPipeConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="96c34-106">메서드</span><span class="sxs-lookup"><span data-stu-id="96c34-106">Methods</span></span>  

 <span data-ttu-id="96c34-107">NamedPipeConnectionPoolSettings 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96c34-107">The NamedPipeConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="96c34-108">속성</span><span class="sxs-lookup"><span data-stu-id="96c34-108">Properties</span></span>  

 <span data-ttu-id="96c34-109">NamedPipeConnectionPoolSettings 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96c34-109">The NamedPipeConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="96c34-110">GroupName</span><span class="sxs-lookup"><span data-stu-id="96c34-110">GroupName</span></span>  

 <span data-ttu-id="96c34-111">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="96c34-111">Data type: string</span></span>  
  
 <span data-ttu-id="96c34-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="96c34-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="96c34-113">바인딩 요소가 사용하는 연결 풀의 그룹 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="96c34-113">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="96c34-114">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="96c34-114">IdleTimeout</span></span>  

 <span data-ttu-id="96c34-115">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="96c34-115">Data type: datetime</span></span>  
  
 <span data-ttu-id="96c34-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="96c34-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="96c34-117">연결이 끊어지기 전에 유휴 상태일 수 있는 최대 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="96c34-117">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="96c34-118">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="96c34-118">MaxOutboundConnectionsPerEndpoint</span></span>  

 <span data-ttu-id="96c34-119">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="96c34-119">Data type: sint32</span></span>  
  
 <span data-ttu-id="96c34-120">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="96c34-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="96c34-121">클라이언트에서 각 엔드포인트에 대한 최대 아웃바운드 연결 수입니다.</span><span class="sxs-lookup"><span data-stu-id="96c34-121">The maximum number of outbound connections for each endpoint on the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96c34-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="96c34-122">Requirements</span></span>  
  
|<span data-ttu-id="96c34-123">MOF</span><span class="sxs-lookup"><span data-stu-id="96c34-123">MOF</span></span>|<span data-ttu-id="96c34-124">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96c34-124">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="96c34-125">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="96c34-125">Namespace</span></span>|<span data-ttu-id="96c34-126">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96c34-126">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="96c34-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="96c34-127">See also</span></span>

- <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
