---
title: IGCHost::SetVirtualMemLimit 메서드
ms.date: 03/30/2017
api_name:
- IGCHost.SetVirtualMemLimit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetVirtualMemLimit
helpviewer_keywords:
- IGCHost::SetVirtualMemLimit method [.NET Framework hosting]
- SetVirtualMemLimit method [.NET Framework hosting]
ms.assetid: c7e7c2d0-e58c-4650-b40c-47b2be2cda45
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b5b4210bda7d41b190f1025b62132c5df896a2a1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59088394"
---
# <a name="igchostsetvirtualmemlimit-method"></a><span data-ttu-id="55a5f-102">IGCHost::SetVirtualMemLimit 메서드</span><span class="sxs-lookup"><span data-stu-id="55a5f-102">IGCHost::SetVirtualMemLimit Method</span></span>
<span data-ttu-id="55a5f-103">런타임의 가상 메모리의 최대 크기를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="55a5f-103">Sets the maximum size of the runtime's virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55a5f-104">구문</span><span class="sxs-lookup"><span data-stu-id="55a5f-104">Syntax</span></span>  
  
```  
HRESULT SetVirtualMemLimit (  
    [in] SIZE_T sztMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55a5f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="55a5f-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="55a5f-106">[in] \(메가바이트) 런타임 가상 메모리의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="55a5f-106">[in] The maximum size, in megabytes, of the runtime's virtual memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55a5f-107">설명</span><span class="sxs-lookup"><span data-stu-id="55a5f-107">Remarks</span></span>  
 <span data-ttu-id="55a5f-108">런타임의 가상 메모리의 최대 크기를 동적으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55a5f-108">The maximum size of the runtime's virtual memory can be changed dynamically.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55a5f-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="55a5f-109">Requirements</span></span>  
 <span data-ttu-id="55a5f-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="55a5f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55a5f-111">**헤더:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="55a5f-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="55a5f-112">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="55a5f-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="55a5f-113">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="55a5f-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="55a5f-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="55a5f-114">See also</span></span>

- [<span data-ttu-id="55a5f-115">IGCHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="55a5f-115">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
