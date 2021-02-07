---
description: '자세히 알아보기: Channel 클래스'
title: Channel 클래스
ms.date: 03/30/2017
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
ms.openlocfilehash: dcc92f78f09e9a73a24134c6c0685949f46f38dd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757724"
---
# <a name="channel-class"></a><span data-ttu-id="ede22-103">Channel 클래스</span><span class="sxs-lookup"><span data-stu-id="ede22-103">Channel class</span></span>

<span data-ttu-id="ede22-104">채널</span><span class="sxs-lookup"><span data-stu-id="ede22-104">Channel</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ede22-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ede22-105">Syntax</span></span>  
  
```csharp
class Channel  
{  
  string LocalAddress;  
  Endpoint ref;  
  string RemoteAddress;  
  string SessionId;  
  string Type;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ede22-106">메서드</span><span class="sxs-lookup"><span data-stu-id="ede22-106">Methods</span></span>  

 <span data-ttu-id="ede22-107">Channel 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ede22-107">The Channel class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ede22-108">속성</span><span class="sxs-lookup"><span data-stu-id="ede22-108">Properties</span></span>  

 <span data-ttu-id="ede22-109">Channel 클래스에는 다음 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ede22-109">The Channel class has the following properties.</span></span>  
  
### <a name="localaddress"></a><span data-ttu-id="ede22-110">LocalAddress</span><span class="sxs-lookup"><span data-stu-id="ede22-110">LocalAddress</span></span>  

 <span data-ttu-id="ede22-111">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="ede22-111">Data type: string</span></span>  
  
 <span data-ttu-id="ede22-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="ede22-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ede22-113">채널에 대한 로컬 엔드포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="ede22-113">The local endpoint for the channel.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="ede22-114">ref</span><span class="sxs-lookup"><span data-stu-id="ede22-114">ref</span></span>  

 <span data-ttu-id="ede22-115">데이터 형식: Endpoint</span><span class="sxs-lookup"><span data-stu-id="ede22-115">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="ede22-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="ede22-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ede22-117">채널이 연결되는 엔드포인트에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="ede22-117">A reference to the endpoint the channel connects to.</span></span>  
  
### <a name="remoteaddress"></a><span data-ttu-id="ede22-118">RemoteAddress</span><span class="sxs-lookup"><span data-stu-id="ede22-118">RemoteAddress</span></span>  

 <span data-ttu-id="ede22-119">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="ede22-119">Data type: string</span></span>  
  
 <span data-ttu-id="ede22-120">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="ede22-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ede22-121">채널과 연결된 원격 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="ede22-121">The remote address associated with the channel.</span></span>  
  
### <a name="sessionid"></a><span data-ttu-id="ede22-122">SessionId</span><span class="sxs-lookup"><span data-stu-id="ede22-122">SessionId</span></span>  

 <span data-ttu-id="ede22-123">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="ede22-123">Data type: string</span></span>  
  
 <span data-ttu-id="ede22-124">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="ede22-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ede22-125">현재 세션 ID(있는 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="ede22-125">The current session Id, if any.</span></span>  
  
### <a name="type"></a><span data-ttu-id="ede22-126">Type</span><span class="sxs-lookup"><span data-stu-id="ede22-126">Type</span></span>  

 <span data-ttu-id="ede22-127">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="ede22-127">Data type: string</span></span>  
  
 <span data-ttu-id="ede22-128">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="ede22-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ede22-129">채널 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ede22-129">The type of the channel.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ede22-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ede22-130">Requirements</span></span>  
  
|<span data-ttu-id="ede22-131">MOF</span><span class="sxs-lookup"><span data-stu-id="ede22-131">MOF</span></span>|<span data-ttu-id="ede22-132">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ede22-132">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ede22-133">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="ede22-133">Namespace</span></span>|<span data-ttu-id="ede22-134">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ede22-134">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ede22-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ede22-135">See also</span></span>

- <xref:System.ServiceModel.Channels.ChannelBase>
