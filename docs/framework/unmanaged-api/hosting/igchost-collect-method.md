---
description: '자세히 알아보기: IGCHost:: Collect 메서드'
title: IGCHost::Collect 메서드
ms.date: 03/30/2017
api_name:
- IGCHost.Collect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Collect
helpviewer_keywords:
- Collect method, IGCHost interface [.NET Framework hosting]
- IGCHost::Collect method [.NET Framework hosting]
ms.assetid: fc7d9448-3186-494d-9f0d-ea39717e9a82
topic_type:
- apiref
ms.openlocfilehash: b4c249e07709dc443ae7dd6c6a5bfd206b7f1caa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709697"
---
# <a name="igchostcollect-method"></a><span data-ttu-id="88dfc-103">IGCHost::Collect 메서드</span><span class="sxs-lookup"><span data-stu-id="88dfc-103">IGCHost::Collect Method</span></span>

<span data-ttu-id="88dfc-104">현재 가비지 컬렉션의 상태에 관계 없이 지정 된 세대에 대해 컬렉션을 강제로 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="88dfc-104">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88dfc-105">구문</span><span class="sxs-lookup"><span data-stu-id="88dfc-105">Syntax</span></span>  
  
```cpp  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="88dfc-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="88dfc-106">Parameters</span></span>  

 `Generation`  
 <span data-ttu-id="88dfc-107">진행 가비지 수집을 수행할 세대입니다.</span><span class="sxs-lookup"><span data-stu-id="88dfc-107">[in] The generation on which to perform the garbage collection.</span></span> <span data-ttu-id="88dfc-108">값-1은 모든 세대에서 가비지 수집을 수행 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="88dfc-108">A value of -1 indicates that all generations will undergo a garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88dfc-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="88dfc-109">Requirements</span></span>  

 <span data-ttu-id="88dfc-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="88dfc-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88dfc-111">**헤더:** GCHost, GCHost</span><span class="sxs-lookup"><span data-stu-id="88dfc-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="88dfc-112">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88dfc-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="88dfc-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88dfc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88dfc-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="88dfc-114">See also</span></span>

- [<span data-ttu-id="88dfc-115">IGCHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="88dfc-115">IGCHost Interface</span></span>](igchost-interface.md)
