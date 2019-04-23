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
ms.openlocfilehash: 3f3643bf4880532a46fe7f9f57b8077032013728
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59118081"
---
# <a name="econtexttype-enumeration"></a><span data-ttu-id="15ea7-102">EContextType 열거형</span><span class="sxs-lookup"><span data-stu-id="15ea7-102">EContextType Enumeration</span></span>
<span data-ttu-id="15ea7-103">현재 실행 중인 스레드의 보안 컨텍스트를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="15ea7-103">Describes the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15ea7-104">구문</span><span class="sxs-lookup"><span data-stu-id="15ea7-104">Syntax</span></span>  
  
```  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a><span data-ttu-id="15ea7-105">멤버</span><span class="sxs-lookup"><span data-stu-id="15ea7-105">Members</span></span>  
  
|<span data-ttu-id="15ea7-106">멤버</span><span class="sxs-lookup"><span data-stu-id="15ea7-106">Member</span></span>|<span data-ttu-id="15ea7-107">설명</span><span class="sxs-lookup"><span data-stu-id="15ea7-107">Description</span></span>|  
|------------|-----------------|  
|`eCurrentContext`|<span data-ttu-id="15ea7-108">CLR (공용 언어 런타임) 호출 시 현재 스레드에서 컨텍스트를 나타내는 합니다 [ihostsecuritymanager:: Getsecuritycontext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) 메서드 또는 호출에서 CLR에서 요청 컨텍스트는 [ Ihostsecuritymanager:: Setsecuritycontext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="15ea7-108">Indicates the context on the current thread at the time the common language runtime (CLR) calls the [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) method, or the context requested by the CLR in a call to the [IHostSecurityManager::SetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md) method.</span></span>|  
|`eRestrictedContext`|<span data-ttu-id="15ea7-109">그러면 호스트 권한이 낮은 가비지 수집기 또는 클래스나 모듈 생성자와 같은 컨텍스트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="15ea7-109">Indicates a context over which the host has lower privileges, such as the garbage collector, or class or module constructors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15ea7-110">설명</span><span class="sxs-lookup"><span data-stu-id="15ea7-110">Remarks</span></span>  
 <span data-ttu-id="15ea7-111">CLR 중 하나를 제공 합니다 `EContextType` 값에 대 한 호출에서 매개 변수 값으로는 `IHostSecurityManager::GetSecurityContext` 및 `IHostSecurityManager::SetSecurityContext` 메서드.</span><span class="sxs-lookup"><span data-stu-id="15ea7-111">The CLR supplies one of the `EContextType` values as a parameter value in calls to the `IHostSecurityManager::GetSecurityContext` and `IHostSecurityManager::SetSecurityContext` methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15ea7-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="15ea7-112">Requirements</span></span>  
 <span data-ttu-id="15ea7-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="15ea7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15ea7-114">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="15ea7-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="15ea7-115">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="15ea7-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="15ea7-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15ea7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15ea7-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="15ea7-117">See also</span></span>

- [<span data-ttu-id="15ea7-118">IHostSecurityContext 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15ea7-118">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="15ea7-119">IHostSecurityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15ea7-119">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="15ea7-120">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="15ea7-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
