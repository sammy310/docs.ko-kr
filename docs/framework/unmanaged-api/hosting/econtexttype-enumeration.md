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
ms.openlocfilehash: 5e82f542bdc364a52fc558e582134a7d8d554ec3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131152"
---
# <a name="econtexttype-enumeration"></a><span data-ttu-id="6452c-102">EContextType 열거형</span><span class="sxs-lookup"><span data-stu-id="6452c-102">EContextType Enumeration</span></span>
<span data-ttu-id="6452c-103">현재 실행 중인 스레드의 보안 컨텍스트를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6452c-103">Describes the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6452c-104">구문</span><span class="sxs-lookup"><span data-stu-id="6452c-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a><span data-ttu-id="6452c-105">멤버</span><span class="sxs-lookup"><span data-stu-id="6452c-105">Members</span></span>  
  
|<span data-ttu-id="6452c-106">멤버</span><span class="sxs-lookup"><span data-stu-id="6452c-106">Member</span></span>|<span data-ttu-id="6452c-107">설명</span><span class="sxs-lookup"><span data-stu-id="6452c-107">Description</span></span>|  
|------------|-----------------|  
|`eCurrentContext`|<span data-ttu-id="6452c-108">CLR (공용 언어 런타임)이 [IHostSecurityManager:: GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) 메서드를 호출할 때 또는 [IHostSecurityManager:: SETSECURITYCONTEXT 호출에서 clr이 요청한 컨텍스트를 호출할 때 현재 스레드의 컨텍스트를 나타냅니다. ](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md)메서드.</span><span class="sxs-lookup"><span data-stu-id="6452c-108">Indicates the context on the current thread at the time the common language runtime (CLR) calls the [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) method, or the context requested by the CLR in a call to the [IHostSecurityManager::SetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md) method.</span></span>|  
|`eRestrictedContext`|<span data-ttu-id="6452c-109">호스트에 가비지 수집기, 클래스 또는 모듈 생성자 등의 낮은 권한이 있는 컨텍스트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6452c-109">Indicates a context over which the host has lower privileges, such as the garbage collector, or class or module constructors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6452c-110">주의</span><span class="sxs-lookup"><span data-stu-id="6452c-110">Remarks</span></span>  
 <span data-ttu-id="6452c-111">CLR은 `IHostSecurityManager::GetSecurityContext` 및 `IHostSecurityManager::SetSecurityContext` 메서드에 대 한 호출에서 `EContextType` 값 중 하나를 매개 변수 값으로 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6452c-111">The CLR supplies one of the `EContextType` values as a parameter value in calls to the `IHostSecurityManager::GetSecurityContext` and `IHostSecurityManager::SetSecurityContext` methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6452c-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6452c-112">Requirements</span></span>  
 <span data-ttu-id="6452c-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6452c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6452c-114">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="6452c-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6452c-115">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="6452c-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6452c-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6452c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6452c-117">참조</span><span class="sxs-lookup"><span data-stu-id="6452c-117">See also</span></span>

- [<span data-ttu-id="6452c-118">IHostSecurityContext 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6452c-118">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="6452c-119">IHostSecurityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6452c-119">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="6452c-120">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="6452c-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
