---
title: NamedPipeConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 079bccb8-54b5-4436-a43d-5567763f72ce
ms.openlocfilehash: 8422e1adf9a8914b631431eba5c9c0ed058cd0f3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96258025"
---
# <a name="namedpipeconnectionpoolsettings"></a><span data-ttu-id="d8ee6-102">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="d8ee6-102">NamedPipeConnectionPoolSettings</span></span>

<span data-ttu-id="d8ee6-103">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="d8ee6-103">NamedPipeConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8ee6-104">구문</span><span class="sxs-lookup"><span data-stu-id="d8ee6-104">Syntax</span></span>  
  
```csharp
class NamedPipeConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="d8ee6-105">메서드</span><span class="sxs-lookup"><span data-stu-id="d8ee6-105">Methods</span></span>  

 <span data-ttu-id="d8ee6-106">NamedPipeConnectionPoolSettings 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8ee6-106">The NamedPipeConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d8ee6-107">속성</span><span class="sxs-lookup"><span data-stu-id="d8ee6-107">Properties</span></span>  

 <span data-ttu-id="d8ee6-108">NamedPipeConnectionPoolSettings 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8ee6-108">The NamedPipeConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="d8ee6-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="d8ee6-109">GroupName</span></span>  

 <span data-ttu-id="d8ee6-110">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="d8ee6-110">Data type: string</span></span>  
  
 <span data-ttu-id="d8ee6-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="d8ee6-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d8ee6-112">바인딩 요소가 사용하는 연결 풀의 그룹 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d8ee6-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="d8ee6-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="d8ee6-113">IdleTimeout</span></span>  

 <span data-ttu-id="d8ee6-114">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="d8ee6-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="d8ee6-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="d8ee6-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d8ee6-116">연결이 끊어지기 전에 유휴 상태일 수 있는 최대 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="d8ee6-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="d8ee6-117">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="d8ee6-117">MaxOutboundConnectionsPerEndpoint</span></span>  

 <span data-ttu-id="d8ee6-118">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="d8ee6-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="d8ee6-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="d8ee6-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d8ee6-120">클라이언트에서 각 엔드포인트에 대한 최대 아웃바운드 연결 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d8ee6-120">The maximum number of outbound connections for each endpoint on the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8ee6-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d8ee6-121">Requirements</span></span>  
  
|<span data-ttu-id="d8ee6-122">MOF</span><span class="sxs-lookup"><span data-stu-id="d8ee6-122">MOF</span></span>|<span data-ttu-id="d8ee6-123">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8ee6-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d8ee6-124">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="d8ee6-124">Namespace</span></span>|<span data-ttu-id="d8ee6-125">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8ee6-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d8ee6-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d8ee6-126">See also</span></span>

- <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
