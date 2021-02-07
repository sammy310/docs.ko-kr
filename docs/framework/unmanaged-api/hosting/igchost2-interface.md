---
description: '자세히 알아보기: IGCHost2 인터페이스'
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
ms.openlocfilehash: e32a4894fcff3600c9385f0f559443e23b2bc307
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709323"
---
# <a name="igchost2-interface"></a><span data-ttu-id="f0853-103">IGCHost2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f0853-103">IGCHost2 Interface</span></span>

<span data-ttu-id="f0853-104">가비지 컬렉션 시스템에 대 한 정보를 가져오고 가비지 수집의 일부 측면을 제어 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0853-104">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f0853-105">새 개발을 위해 [ICLRGCManager2](iclrgcmanager2-interface.md) 인터페이스를 대신 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f0853-105">For new development, we recommend that you use the [ICLRGCManager2](iclrgcmanager2-interface.md) interface instead.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f0853-106">메서드</span><span class="sxs-lookup"><span data-stu-id="f0853-106">Methods</span></span>  
  
|<span data-ttu-id="f0853-107">메서드</span><span class="sxs-lookup"><span data-stu-id="f0853-107">Method</span></span>|<span data-ttu-id="f0853-108">설명</span><span class="sxs-lookup"><span data-stu-id="f0853-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f0853-109">SetGCStartupLimitsEx 메서드</span><span class="sxs-lookup"><span data-stu-id="f0853-109">SetGCStartupLimitsEx Method</span></span>](igchost2-setgcstartuplimitsex-method.md)|<span data-ttu-id="f0853-110">0 세대의 세그먼트 크기와 최대 크기를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0853-110">Sets the segment size and the maximum size for generation 0.</span></span> <span data-ttu-id="f0853-111">0 세대 및 세그먼트 크기를 보다 크게 설정 `DWORD` 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0853-111">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f0853-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f0853-112">Requirements</span></span>  

 <span data-ttu-id="f0853-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0853-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0853-114">**헤더:** GCHost, GCHost</span><span class="sxs-lookup"><span data-stu-id="f0853-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="f0853-115">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0853-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f0853-116">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0853-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0853-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f0853-117">See also</span></span>

- [<span data-ttu-id="f0853-118">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f0853-118">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="f0853-119">CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f0853-119">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)
- [<span data-ttu-id="f0853-120">CorRuntimeHost Coclass</span><span class="sxs-lookup"><span data-stu-id="f0853-120">CorRuntimeHost Coclass</span></span>](corruntimehost-coclass.md)
