---
title: ICLRDebugManager::GetDacl 메서드
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.GetDacl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::GetDacl
helpviewer_keywords:
- GetDacl method [.NET Framework hosting]
- ICLRDebugManager::GetDacl method [.NET Framework hosting]
ms.assetid: 7115e920-aaff-440a-824e-39497139c6f6
topic_type:
- apiref
ms.openlocfilehash: a18e1efd246b0d6895d18ae0e7089a78703eae0e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129435"
---
# <a name="iclrdebugmanagergetdacl-method"></a><span data-ttu-id="aa30e-102">ICLRDebugManager::GetDacl 메서드</span><span class="sxs-lookup"><span data-stu-id="aa30e-102">ICLRDebugManager::GetDacl Method</span></span>
<span data-ttu-id="aa30e-103">이 메서드는 구현 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aa30e-103">This method is not implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa30e-104">구문</span><span class="sxs-lookup"><span data-stu-id="aa30e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDacl (  
    [out] PACL* ppacl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa30e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="aa30e-105">Parameters</span></span>  
 `ppacl`  
 <span data-ttu-id="aa30e-106">제한이 ACL (Access Control 목록)에 대 한 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="aa30e-106">[out] An interface pointer to the Access Control List (ACL).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aa30e-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="aa30e-107">Return Value</span></span>  
  
|<span data-ttu-id="aa30e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="aa30e-108">HRESULT</span></span>|<span data-ttu-id="aa30e-109">설명</span><span class="sxs-lookup"><span data-stu-id="aa30e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="aa30e-110">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="aa30e-110">E_NOTIMPL</span></span>|<span data-ttu-id="aa30e-111">메서드가 구현 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="aa30e-111">The method is not implemented.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="aa30e-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="aa30e-112">Requirements</span></span>  
 <span data-ttu-id="aa30e-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa30e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa30e-114">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="aa30e-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aa30e-115">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa30e-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aa30e-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa30e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa30e-117">참조</span><span class="sxs-lookup"><span data-stu-id="aa30e-117">See also</span></span>

- [<span data-ttu-id="aa30e-118">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aa30e-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="aa30e-119">ICLRDebugManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aa30e-119">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="aa30e-120">SetDacl 메서드</span><span class="sxs-lookup"><span data-stu-id="aa30e-120">SetDacl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setdacl-method.md)
- [<span data-ttu-id="aa30e-121">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aa30e-121">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
