---
description: '자세히 알아보기: ICLRDebugManager:: SetDacl 메서드'
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
ms.openlocfilehash: b507d94f9e23e509d279a0fd4e32c8c996a4668b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689575"
---
# <a name="iclrdebugmanagersetdacl-method"></a><span data-ttu-id="c998b-103">ICLRDebugManager::SetDacl 메서드</span><span class="sxs-lookup"><span data-stu-id="c998b-103">ICLRDebugManager::SetDacl Method</span></span>

<span data-ttu-id="c998b-104">이 메서드가 구현되지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="c998b-104">This method is not implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c998b-105">구문</span><span class="sxs-lookup"><span data-stu-id="c998b-105">Syntax</span></span>  
  
```cpp  
HRESULT SetDacl (  
    [in] PACL pacl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c998b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c998b-106">Parameters</span></span>  

 `pacl`  
 <span data-ttu-id="c998b-107">진행 ACL (Access Control 목록)에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c998b-107">[in] A pointer to the Access Control List (ACL).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c998b-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="c998b-108">Return Value</span></span>  
  
|<span data-ttu-id="c998b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c998b-109">HRESULT</span></span>|<span data-ttu-id="c998b-110">설명</span><span class="sxs-lookup"><span data-stu-id="c998b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c998b-111">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="c998b-111">E_NOTIMPL</span></span>|<span data-ttu-id="c998b-112">메서드가 구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="c998b-112">The method is not implemented.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c998b-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c998b-113">Requirements</span></span>  

 <span data-ttu-id="c998b-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c998b-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c998b-115">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c998b-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c998b-116">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c998b-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c998b-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c998b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c998b-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c998b-118">See also</span></span>

- [<span data-ttu-id="c998b-119">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c998b-119">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="c998b-120">ICLRDebugManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c998b-120">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
- [<span data-ttu-id="c998b-121">GetDacl 메서드</span><span class="sxs-lookup"><span data-stu-id="c998b-121">GetDacl Method</span></span>](iclrdebugmanager-getdacl-method.md)
- [<span data-ttu-id="c998b-122">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c998b-122">IHostControl Interface</span></span>](ihostcontrol-interface.md)
