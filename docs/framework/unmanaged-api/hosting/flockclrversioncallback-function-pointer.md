---
title: FLockClrVersionCallback 함수 포인터
ms.date: 03/30/2017
api_name:
- FLockClrVersionCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FLockClrVersionCallback
helpviewer_keywords:
- FLockClrVersionCallback function pointer [.NET Framework hosting]
ms.assetid: 98a4762d-9ad2-45bd-9d03-39064a028b44
topic_type:
- apiref
ms.openlocfilehash: f1ad414c30788801e14a33e98a0893e2a0f58d0c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136511"
---
# <a name="flockclrversioncallback-function-pointer"></a><span data-ttu-id="d5a0e-102">FLockClrVersionCallback 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="d5a0e-102">FLockClrVersionCallback Function Pointer</span></span>
<span data-ttu-id="d5a0e-103">초기화가 시작 되거나 완료 되었음을 나타내기 위해 CLR (공용 언어 런타임)에서 호출 하는 함수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="d5a0e-103">Points to a function that the common language runtime (CLR) calls to indicate that initialization has either started or completed.</span></span>  
  
 <span data-ttu-id="d5a0e-104">이 함수 포인터는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d5a0e-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5a0e-105">구문</span><span class="sxs-lookup"><span data-stu-id="d5a0e-105">Syntax</span></span>  
  
```cpp  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="d5a0e-106">주의</span><span class="sxs-lookup"><span data-stu-id="d5a0e-106">Remarks</span></span>  
 <span data-ttu-id="d5a0e-107">이 함수는 호스트에 의해 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5a0e-107">This function is implemented by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5a0e-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d5a0e-108">Requirements</span></span>  
 <span data-ttu-id="d5a0e-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d5a0e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5a0e-110">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d5a0e-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d5a0e-111">**라이브러리:** Mscorwks.dll</span><span class="sxs-lookup"><span data-stu-id="d5a0e-111">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="d5a0e-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5a0e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5a0e-113">참조</span><span class="sxs-lookup"><span data-stu-id="d5a0e-113">See also</span></span>

- [<span data-ttu-id="d5a0e-114">LockClrVersion 함수</span><span class="sxs-lookup"><span data-stu-id="d5a0e-114">LockClrVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)
- [<span data-ttu-id="d5a0e-115">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="d5a0e-115">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
