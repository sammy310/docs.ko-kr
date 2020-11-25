---
title: ICLRDebugManager::SetDacl 메서드
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.SetDacl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::SetDacl
helpviewer_keywords:
- SetDacl method [.NET Framework hosting]
- ICLRDebugManager::SetDacl method [.NET Framework hosting]
ms.assetid: 52f4af3f-e02b-4c20-9fd9-e8e4f4d6fc31
topic_type:
- apiref
ms.openlocfilehash: 92134396d9f9d869866a73cdd31278f4ac1e6355
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719023"
---
# <a name="iclrdebugmanagersetdacl-method"></a><span data-ttu-id="90de3-102">ICLRDebugManager::SetDacl 메서드</span><span class="sxs-lookup"><span data-stu-id="90de3-102">ICLRDebugManager::SetDacl Method</span></span>

<span data-ttu-id="90de3-103">이 메서드가 구현되지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="90de3-103">This method is not implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90de3-104">구문</span><span class="sxs-lookup"><span data-stu-id="90de3-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDacl (  
    [in] PACL pacl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90de3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="90de3-105">Parameters</span></span>  

 `pacl`  
 <span data-ttu-id="90de3-106">진행 ACL (Access Control 목록)에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="90de3-106">[in] A pointer to the Access Control List (ACL).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="90de3-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="90de3-107">Return Value</span></span>  
  
|<span data-ttu-id="90de3-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="90de3-108">HRESULT</span></span>|<span data-ttu-id="90de3-109">설명</span><span class="sxs-lookup"><span data-stu-id="90de3-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="90de3-110">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="90de3-110">E_NOTIMPL</span></span>|<span data-ttu-id="90de3-111">메서드가 구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="90de3-111">The method is not implemented.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="90de3-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="90de3-112">Requirements</span></span>  

 <span data-ttu-id="90de3-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="90de3-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90de3-114">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="90de3-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="90de3-115">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90de3-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="90de3-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90de3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90de3-117">참조</span><span class="sxs-lookup"><span data-stu-id="90de3-117">See also</span></span>

- [<span data-ttu-id="90de3-118">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="90de3-118">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="90de3-119">ICLRDebugManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="90de3-119">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
- [<span data-ttu-id="90de3-120">GetDacl 메서드</span><span class="sxs-lookup"><span data-stu-id="90de3-120">GetDacl Method</span></span>](iclrdebugmanager-getdacl-method.md)
- [<span data-ttu-id="90de3-121">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="90de3-121">IHostControl Interface</span></span>](ihostcontrol-interface.md)
