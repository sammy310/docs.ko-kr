---
title: IApartmentCallback::DoCallback 메서드
ms.date: 03/30/2017
api_name:
- IApartmentCallback.DoCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- DoCallback
helpviewer_keywords:
- IApartmentCallback::DoCallback method [.NET Framework hosting]
- DoCallback method [.NET Framework hosting]
ms.assetid: 8edad30c-30ff-4bee-813c-75525a82fc93
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7bd983a41307a4244b5426b8f6b997569cd631e9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770503"
---
# <a name="iapartmentcallbackdocallback-method"></a><span data-ttu-id="2791a-102">IApartmentCallback::DoCallback 메서드</span><span class="sxs-lookup"><span data-stu-id="2791a-102">IApartmentCallback::DoCallback Method</span></span>
<span data-ttu-id="2791a-103">아파트 내의 지정된 된 함수를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2791a-103">Executes the specified function within an apartment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2791a-104">구문</span><span class="sxs-lookup"><span data-stu-id="2791a-104">Syntax</span></span>  
  
```cpp  
HRESULT _stdcall DoCallback(  
    [in] SIZE_T pFunc,  
    [in] SIZE_T pData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2791a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2791a-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="2791a-106">[in] 아파트 내에서 실행 되는 함수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2791a-106">[in] A pointer to the function to be executed within the apartment.</span></span>  
  
 `pData`  
 <span data-ttu-id="2791a-107">[in] 함수의 인수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2791a-107">[in] A pointer to the function's argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2791a-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2791a-108">Requirements</span></span>  
 <span data-ttu-id="2791a-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2791a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2791a-110">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2791a-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2791a-111">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="2791a-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2791a-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2791a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2791a-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="2791a-113">See also</span></span>

- [<span data-ttu-id="2791a-114">IApartmentCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2791a-114">IApartmentCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)
