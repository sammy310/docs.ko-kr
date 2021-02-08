---
description: '자세히 알아보기: IReferenceAppId 인터페이스'
title: IReferenceAppId 인터페이스
ms.date: 03/30/2017
api_name:
- IReferenceAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IReferenceAppId
helpviewer_keywords:
- IReferenceAppId interface [.NET Framework fusion]
ms.assetid: 8eb9e565-f358-43ce-900e-a8f8a5aa6cfb
topic_type:
- apiref
ms.openlocfilehash: 66838d6ae66aa7de05d899e9fa980308718e2a38
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800073"
---
# <a name="ireferenceappid-interface"></a><span data-ttu-id="db5af-103">IReferenceAppId 인터페이스</span><span class="sxs-lookup"><span data-stu-id="db5af-103">IReferenceAppId Interface</span></span>

<span data-ttu-id="db5af-104">현재 범위의 응용 프로그램에 대 한 고유 식별자에 대 한 참조를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="db5af-104">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="db5af-105">메서드</span><span class="sxs-lookup"><span data-stu-id="db5af-105">Methods</span></span>  
  
|<span data-ttu-id="db5af-106">메서드</span><span class="sxs-lookup"><span data-stu-id="db5af-106">Method</span></span>|<span data-ttu-id="db5af-107">설명</span><span class="sxs-lookup"><span data-stu-id="db5af-107">Description</span></span>|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|<span data-ttu-id="db5af-108">이에서 참조 하는 응용 프로그램의 코드 식별자에 대 한 문자열 표현에 대 한 포인터를 가져옵니다 `IReferenceAppId` .</span><span class="sxs-lookup"><span data-stu-id="db5af-108">Gets a pointer to a string representation of the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_CodeBase`|<span data-ttu-id="db5af-109">이에서 참조 하는 응용 프로그램에 대 한 코드 식별자를 설정 합니다 `IReferenceAppId` .</span><span class="sxs-lookup"><span data-stu-id="db5af-109">Sets the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::EnumAppPath`|<span data-ttu-id="db5af-110">`IEnumReferenceIdentity`이의 멤버를 나타내는 인스턴스를 포함 하는 인스턴스에 대 한 인터페이스 포인터를 가져옵니다 `IReferenceIdentity` `IReferenceAppId` .</span><span class="sxs-lookup"><span data-stu-id="db5af-110">Gets an interface pointer to an `IEnumReferenceIdentity` instance containing the `IReferenceIdentity` instances that represent members of this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::get_SubscriptionId`|<span data-ttu-id="db5af-111">이에 대 한 구독의 토큰 식별자에 대 한 문자열 표현에 대 한 포인터를 가져옵니다 `IReferenceAppId` .</span><span class="sxs-lookup"><span data-stu-id="db5af-111">Gets a pointer to a string representation of the token identifier for a subscription to this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_SubscriptionId`|<span data-ttu-id="db5af-112">이에 대 한 구독의 토큰 식별자를 `IReferenceAppId` 지정 된 문자열 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="db5af-112">Sets the token identifier for a subscription to this `IReferenceAppId` to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="db5af-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="db5af-113">Requirements</span></span>  

 <span data-ttu-id="db5af-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="db5af-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db5af-115">**헤더:** 격리. h</span><span class="sxs-lookup"><span data-stu-id="db5af-115">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="db5af-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db5af-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db5af-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="db5af-117">See also</span></span>

- [<span data-ttu-id="db5af-118">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="db5af-118">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="db5af-119">IEnumReferenceIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="db5af-119">IEnumReferenceIdentity Interface</span></span>](ienumreferenceidentity-interface.md)
- [<span data-ttu-id="db5af-120">IReferenceIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="db5af-120">IReferenceIdentity Interface</span></span>](ireferenceidentity-interface.md)
