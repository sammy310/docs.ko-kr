---
description: 다음에 대해 자세히 알아보세요. ServiceToEndpointAssociation
title: ServiceToEndpointAssociation
ms.date: 03/30/2017
ms.assetid: 03c3cd15-e1b2-4dc2-bdc2-59fdccdae110
ms.openlocfilehash: 1ae2ce2bcc0b3494b00fffa750f3ca46d26fe08f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99715342"
---
# <a name="servicetoendpointassociation"></a><span data-ttu-id="a3706-103">ServiceToEndpointAssociation</span><span class="sxs-lookup"><span data-stu-id="a3706-103">ServiceToEndpointAssociation</span></span>

<span data-ttu-id="a3706-104">서비스를 엔드포인트에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="a3706-104">Maps a service to an endpoint.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3706-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a3706-105">Syntax</span></span>  
  
```csharp
class ServiceToEndpointAssociation  
{  
  Service ref;  
  Endpoint ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="a3706-106">메서드</span><span class="sxs-lookup"><span data-stu-id="a3706-106">Methods</span></span>  

 <span data-ttu-id="a3706-107">ServiceToEndpointAssociation 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3706-107">The ServiceToEndpointAssociation class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a3706-108">속성</span><span class="sxs-lookup"><span data-stu-id="a3706-108">Properties</span></span>  

 <span data-ttu-id="a3706-109">ServiceToEndpointAssociation 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3706-109">The ServiceToEndpointAssociation class has the following properties:</span></span>  
  
### <a name="ref"></a><span data-ttu-id="a3706-110">ref</span><span class="sxs-lookup"><span data-stu-id="a3706-110">ref</span></span>  

 <span data-ttu-id="a3706-111">데이터 형식: Service</span><span class="sxs-lookup"><span data-stu-id="a3706-111">Data type: Service</span></span>  
  
 <span data-ttu-id="a3706-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="a3706-112">Access type: Read-only</span></span>  
<span data-ttu-id="a3706-113">한정자: Key</span><span class="sxs-lookup"><span data-stu-id="a3706-113">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="a3706-114">엔드포인트와 연결된 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="a3706-114">The service associated with the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="a3706-115">ref</span><span class="sxs-lookup"><span data-stu-id="a3706-115">ref</span></span>  

 <span data-ttu-id="a3706-116">데이터 형식: Endpoint</span><span class="sxs-lookup"><span data-stu-id="a3706-116">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="a3706-117">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="a3706-117">Access type: Read-only</span></span>  
<span data-ttu-id="a3706-118">한정자: Key</span><span class="sxs-lookup"><span data-stu-id="a3706-118">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="a3706-119">서비스와 연결된 엔드포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="a3706-119">The endpoint associated with the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3706-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a3706-120">Requirements</span></span>  
  
|<span data-ttu-id="a3706-121">MOF</span><span class="sxs-lookup"><span data-stu-id="a3706-121">MOF</span></span>|<span data-ttu-id="a3706-122">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3706-122">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a3706-123">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="a3706-123">Namespace</span></span>|<span data-ttu-id="a3706-124">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3706-124">Defined in root\ServiceModel</span></span>|
