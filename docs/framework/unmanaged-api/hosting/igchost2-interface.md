---
title: IGCHost2 인터페이스
ms.date: 03/30/2017
api_name:
- IGCHost2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost2
helpviewer_keywords:
- IGCHost2 interface [.NET Framework hosting]
ms.assetid: e5323fa4-18ac-424d-859d-a65a550d08d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 21ce9cbd007858c0f39e12622eff819154ab83f0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928613"
---
# <a name="igchost2-interface"></a><span data-ttu-id="f9014-102">IGCHost2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f9014-102">IGCHost2 Interface</span></span>
<span data-ttu-id="f9014-103">가비지 컬렉션 시스템에 대 한 정보를 가져오고 가비지 수집의 일부 측면을 제어 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9014-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f9014-104">새 개발을 위해 [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) 인터페이스를 대신 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f9014-104">For new development, we recommend that you use the [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) interface instead.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f9014-105">메서드</span><span class="sxs-lookup"><span data-stu-id="f9014-105">Methods</span></span>  
  
|<span data-ttu-id="f9014-106">메서드</span><span class="sxs-lookup"><span data-stu-id="f9014-106">Method</span></span>|<span data-ttu-id="f9014-107">설명</span><span class="sxs-lookup"><span data-stu-id="f9014-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f9014-108">SetGCStartupLimitsEx 메서드</span><span class="sxs-lookup"><span data-stu-id="f9014-108">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)|<span data-ttu-id="f9014-109">0 세대의 세그먼트 크기와 최대 크기를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9014-109">Sets the segment size and the maximum size for generation 0.</span></span> <span data-ttu-id="f9014-110">0 세대 및 세그먼트 크기를 보다 `DWORD`크게 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9014-110">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f9014-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f9014-111">Requirements</span></span>  
 <span data-ttu-id="f9014-112">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f9014-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9014-113">**헤더:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="f9014-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="f9014-114">**라이브러리** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9014-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f9014-115">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9014-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9014-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="f9014-116">See also</span></span>

- [<span data-ttu-id="f9014-117">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f9014-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="f9014-118">CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f9014-118">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="f9014-119">CorRuntimeHost Coclass</span><span class="sxs-lookup"><span data-stu-id="f9014-119">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
