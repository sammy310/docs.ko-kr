---
description: '자세한 정보: ServiceTimeoutsBehavior'
title: ServiceTimeoutsBehavior
ms.date: 03/30/2017
ms.assetid: 4412525d-a3cc-4eae-b3e8-a50ce766d09d
ms.openlocfilehash: 147d249af0e87bc41da93a4a31355da7053caaf6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99715420"
---
# <a name="servicetimeoutsbehavior"></a><span data-ttu-id="fb544-103">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="fb544-103">ServiceTimeoutsBehavior</span></span>

<span data-ttu-id="fb544-104">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="fb544-104">ServiceTimeoutsBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb544-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="fb544-105">Syntax</span></span>  
  
```csharp
class ServiceTimeoutsBehavior : Behavior  
{  
  datetime TransactionTimeout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="fb544-106">메서드</span><span class="sxs-lookup"><span data-stu-id="fb544-106">Methods</span></span>  

 <span data-ttu-id="fb544-107">ServiceTimeoutsBehavior 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb544-107">The ServiceTimeoutsBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="fb544-108">속성</span><span class="sxs-lookup"><span data-stu-id="fb544-108">Properties</span></span>  

 <span data-ttu-id="fb544-109">ServiceTimeoutsBehavior 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb544-109">The ServiceTimeoutsBehavior class has the following property:</span></span>  
  
### <a name="transactiontimeout"></a><span data-ttu-id="fb544-110">TransactionTimeout</span><span class="sxs-lookup"><span data-stu-id="fb544-110">TransactionTimeout</span></span>  

 <span data-ttu-id="fb544-111">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="fb544-111">Data type: datetime</span></span>  
  
 <span data-ttu-id="fb544-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="fb544-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fb544-113">트랜잭션을 완료해야 하는 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="fb544-113">The period within which a transaction must complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb544-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fb544-114">Requirements</span></span>  
  
|<span data-ttu-id="fb544-115">MOF</span><span class="sxs-lookup"><span data-stu-id="fb544-115">MOF</span></span>|<span data-ttu-id="fb544-116">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb544-116">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="fb544-117">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="fb544-117">Namespace</span></span>|<span data-ttu-id="fb544-118">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb544-118">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fb544-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fb544-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
