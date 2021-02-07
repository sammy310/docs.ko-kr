---
description: '자세히 알아보기: DeliveryRequirementsAttribute'
title: DeliveryRequirementsAttribute
ms.date: 03/30/2017
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
ms.openlocfilehash: ee27ada1c1fb447de3d7a108a4a285ca106e4e8e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757503"
---
# <a name="deliveryrequirementsattribute"></a><span data-ttu-id="26be4-103">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="26be4-103">DeliveryRequirementsAttribute</span></span>

<span data-ttu-id="26be4-104">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="26be4-104">DeliveryRequirementsAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26be4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="26be4-105">Syntax</span></span>  
  
```csharp
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="26be4-106">메서드</span><span class="sxs-lookup"><span data-stu-id="26be4-106">Methods</span></span>  

 <span data-ttu-id="26be4-107">DeliveryRequirementsAttribute 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="26be4-107">The DeliveryRequirementsAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="26be4-108">속성</span><span class="sxs-lookup"><span data-stu-id="26be4-108">Properties</span></span>  

 <span data-ttu-id="26be4-109">DeliveryRequirementsAttribute 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26be4-109">The DeliveryRequirementsAttribute class has the following properties:</span></span>  
  
### <a name="queueddeliveryrequirements"></a><span data-ttu-id="26be4-110">QueuedDeliveryRequirements</span><span class="sxs-lookup"><span data-stu-id="26be4-110">QueuedDeliveryRequirements</span></span>  

 <span data-ttu-id="26be4-111">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="26be4-111">Data type: string</span></span>  
  
 <span data-ttu-id="26be4-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="26be4-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="26be4-113">서비스 바인딩이 계약을 지원할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="26be4-113">Specifies whether the binding for a service supports contracts.</span></span>  
  
### <a name="requireordereddelivery"></a><span data-ttu-id="26be4-114">RequireOrderedDelivery</span><span class="sxs-lookup"><span data-stu-id="26be4-114">RequireOrderedDelivery</span></span>  

 <span data-ttu-id="26be4-115">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="26be4-115">Data type: boolean</span></span>  
  
 <span data-ttu-id="26be4-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="26be4-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="26be4-117">바인딩이 순서가 지정된 메시지를 지원할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="26be4-117">Specifies whether the binding supports ordered messages.</span></span>  
  
### <a name="targetcontract"></a><span data-ttu-id="26be4-118">TargetContract</span><span class="sxs-lookup"><span data-stu-id="26be4-118">TargetContract</span></span>  

 <span data-ttu-id="26be4-119">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="26be4-119">Data type: string</span></span>  
  
 <span data-ttu-id="26be4-120">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="26be4-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="26be4-121">적용할 계약입니다.</span><span class="sxs-lookup"><span data-stu-id="26be4-121">The contract to which it applies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26be4-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="26be4-122">Requirements</span></span>  
  
|<span data-ttu-id="26be4-123">MOF</span><span class="sxs-lookup"><span data-stu-id="26be4-123">MOF</span></span>|<span data-ttu-id="26be4-124">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26be4-124">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="26be4-125">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="26be4-125">Namespace</span></span>|<span data-ttu-id="26be4-126">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26be4-126">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="26be4-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="26be4-127">See also</span></span>

- <xref:System.ServiceModel.DeliveryRequirementsAttribute>
