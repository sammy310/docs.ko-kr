---
title: IDebuggerInfo::IsDebuggerAttached 메서드
ms.date: 03/30/2017
api_name:
- IDebuggerInfo.IsDebuggerAttached
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IsDebuggerAttached
helpviewer_keywords:
- IDebuggerInfo::IsDebuggerAttached method [.NET Framework hosting]
- IsDebuggerAttached method, IDebuggerInfo interface [.NET Framework hosting]
ms.assetid: 6e21872f-602f-411a-a423-bff5cdf27000
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f381cc687b4c28dd58a02aea8cf931f569cf9611
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780530"
---
# <a name="idebuggerinfoisdebuggerattached-method"></a><span data-ttu-id="cdd64-102">IDebuggerInfo::IsDebuggerAttached 메서드</span><span class="sxs-lookup"><span data-stu-id="cdd64-102">IDebuggerInfo::IsDebuggerAttached Method</span></span>
<span data-ttu-id="cdd64-103">관리 되는 디버거가이 프로세스에 연결 되어 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cdd64-103">Gets a value that indicates whether a managed debugger is attached to this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdd64-104">구문</span><span class="sxs-lookup"><span data-stu-id="cdd64-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cdd64-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cdd64-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="cdd64-106">[out] 값에 대 한 포인터 `true` 관리 되는 디버거가 고, 그렇지 않으면 프로세스에 연결 된 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="cdd64-106">[out] A pointer to a value that is `true` if a managed debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdd64-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cdd64-107">Requirements</span></span>  
 <span data-ttu-id="cdd64-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cdd64-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cdd64-109">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cdd64-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cdd64-110">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="cdd64-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cdd64-111">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cdd64-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdd64-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="cdd64-112">See also</span></span>

- [<span data-ttu-id="cdd64-113">IDebuggerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cdd64-113">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)
