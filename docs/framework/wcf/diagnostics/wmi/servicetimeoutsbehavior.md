---
title: ServiceTimeoutsBehavior
ms.date: 03/30/2017
ms.assetid: 4412525d-a3cc-4eae-b3e8-a50ce766d09d
ms.openlocfilehash: 58e872f2b15776d65bccdcc47c353ce566cd9d2f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59116014"
---
# <a name="servicetimeoutsbehavior"></a><span data-ttu-id="b048f-102">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="b048f-102">ServiceTimeoutsBehavior</span></span>
<span data-ttu-id="b048f-103">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="b048f-103">ServiceTimeoutsBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b048f-104">구문</span><span class="sxs-lookup"><span data-stu-id="b048f-104">Syntax</span></span>  
  
```csharp
class ServiceTimeoutsBehavior : Behavior  
{  
  datetime TransactionTimeout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b048f-105">메서드</span><span class="sxs-lookup"><span data-stu-id="b048f-105">Methods</span></span>  
 <span data-ttu-id="b048f-106">ServiceTimeoutsBehavior 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b048f-106">The ServiceTimeoutsBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b048f-107">속성</span><span class="sxs-lookup"><span data-stu-id="b048f-107">Properties</span></span>  
 <span data-ttu-id="b048f-108">ServiceTimeoutsBehavior 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b048f-108">The ServiceTimeoutsBehavior class has the following property:</span></span>  
  
### <a name="transactiontimeout"></a><span data-ttu-id="b048f-109">TransactionTimeout</span><span class="sxs-lookup"><span data-stu-id="b048f-109">TransactionTimeout</span></span>  
 <span data-ttu-id="b048f-110">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="b048f-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="b048f-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="b048f-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b048f-112">트랜잭션을 완료해야 하는 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="b048f-112">The period within which a transaction must complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b048f-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b048f-113">Requirements</span></span>  
  
|<span data-ttu-id="b048f-114">MOF</span><span class="sxs-lookup"><span data-stu-id="b048f-114">MOF</span></span>|<span data-ttu-id="b048f-115">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b048f-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b048f-116">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="b048f-116">Namespace</span></span>|<span data-ttu-id="b048f-117">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b048f-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b048f-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="b048f-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
