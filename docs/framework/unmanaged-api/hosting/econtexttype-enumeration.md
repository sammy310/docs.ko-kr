---
title: EContextType 열거형
ms.date: 03/30/2017
api_name:
- EContextType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EContextType
helpviewer_keywords:
- EContextType enumeration [.NET Framework hosting]
ms.assetid: 92b926a9-b87e-408a-9036-df7b752c9492
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f93f36a78ff5579e131ef4bb3d48f04e806c14de
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779401"
---
# <a name="econtexttype-enumeration"></a><span data-ttu-id="e95b1-102">EContextType 열거형</span><span class="sxs-lookup"><span data-stu-id="e95b1-102">EContextType Enumeration</span></span>
<span data-ttu-id="e95b1-103">현재 실행 중인 스레드의 보안 컨텍스트를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e95b1-103">Describes the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e95b1-104">구문</span><span class="sxs-lookup"><span data-stu-id="e95b1-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a><span data-ttu-id="e95b1-105">멤버</span><span class="sxs-lookup"><span data-stu-id="e95b1-105">Members</span></span>  
  
|<span data-ttu-id="e95b1-106">멤버</span><span class="sxs-lookup"><span data-stu-id="e95b1-106">Member</span></span>|<span data-ttu-id="e95b1-107">설명</span><span class="sxs-lookup"><span data-stu-id="e95b1-107">Description</span></span>|  
|------------|-----------------|  
|`eCurrentContext`|<span data-ttu-id="e95b1-108">CLR (공용 언어 런타임) 호출 시 현재 스레드에서 컨텍스트를 나타내는 합니다 [ihostsecuritymanager:: Getsecuritycontext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) 메서드 또는 호출에서 CLR에서 요청 컨텍스트는 [ Ihostsecuritymanager:: Setsecuritycontext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="e95b1-108">Indicates the context on the current thread at the time the common language runtime (CLR) calls the [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) method, or the context requested by the CLR in a call to the [IHostSecurityManager::SetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md) method.</span></span>|  
|`eRestrictedContext`|<span data-ttu-id="e95b1-109">그러면 호스트 권한이 낮은 가비지 수집기 또는 클래스나 모듈 생성자와 같은 컨텍스트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e95b1-109">Indicates a context over which the host has lower privileges, such as the garbage collector, or class or module constructors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e95b1-110">설명</span><span class="sxs-lookup"><span data-stu-id="e95b1-110">Remarks</span></span>  
 <span data-ttu-id="e95b1-111">CLR 중 하나를 제공 합니다 `EContextType` 값에 대 한 호출에서 매개 변수 값으로는 `IHostSecurityManager::GetSecurityContext` 및 `IHostSecurityManager::SetSecurityContext` 메서드.</span><span class="sxs-lookup"><span data-stu-id="e95b1-111">The CLR supplies one of the `EContextType` values as a parameter value in calls to the `IHostSecurityManager::GetSecurityContext` and `IHostSecurityManager::SetSecurityContext` methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e95b1-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e95b1-112">Requirements</span></span>  
 <span data-ttu-id="e95b1-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e95b1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e95b1-114">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e95b1-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e95b1-115">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e95b1-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e95b1-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e95b1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e95b1-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="e95b1-117">See also</span></span>

- [<span data-ttu-id="e95b1-118">IHostSecurityContext 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e95b1-118">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="e95b1-119">IHostSecurityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e95b1-119">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="e95b1-120">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="e95b1-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
