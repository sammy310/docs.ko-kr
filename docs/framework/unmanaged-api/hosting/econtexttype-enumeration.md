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
ms.openlocfilehash: ceb68410e808bf7843149e3f05a39c7a98d0c000
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616296"
---
# <a name="econtexttype-enumeration"></a><span data-ttu-id="7bac7-102">EContextType 열거형</span><span class="sxs-lookup"><span data-stu-id="7bac7-102">EContextType Enumeration</span></span>
<span data-ttu-id="7bac7-103">현재 실행 중인 스레드의 보안 컨텍스트를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bac7-103">Describes the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bac7-104">구문</span><span class="sxs-lookup"><span data-stu-id="7bac7-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a><span data-ttu-id="7bac7-105">멤버</span><span class="sxs-lookup"><span data-stu-id="7bac7-105">Members</span></span>  
  
|<span data-ttu-id="7bac7-106">멤버</span><span class="sxs-lookup"><span data-stu-id="7bac7-106">Member</span></span>|<span data-ttu-id="7bac7-107">설명</span><span class="sxs-lookup"><span data-stu-id="7bac7-107">Description</span></span>|  
|------------|-----------------|  
|`eCurrentContext`|<span data-ttu-id="7bac7-108">CLR (공용 언어 런타임)이 [IHostSecurityManager:: GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) 메서드를 호출할 때 또는 [IHostSecurityManager:: SetSecurityContext](ihostsecuritymanager-setsecuritycontext-method.md) 메서드 호출에서 clr이 요청한 컨텍스트를 호출할 때 현재 스레드의 컨텍스트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7bac7-108">Indicates the context on the current thread at the time the common language runtime (CLR) calls the [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) method, or the context requested by the CLR in a call to the [IHostSecurityManager::SetSecurityContext](ihostsecuritymanager-setsecuritycontext-method.md) method.</span></span>|  
|`eRestrictedContext`|<span data-ttu-id="7bac7-109">호스트에 가비지 수집기, 클래스 또는 모듈 생성자 등의 낮은 권한이 있는 컨텍스트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7bac7-109">Indicates a context over which the host has lower privileges, such as the garbage collector, or class or module constructors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7bac7-110">설명</span><span class="sxs-lookup"><span data-stu-id="7bac7-110">Remarks</span></span>  
 <span data-ttu-id="7bac7-111">CLR은 `EContextType` 및 메서드에 대 한 호출에서 값 중 하나를 매개 변수 값으로 제공 `IHostSecurityManager::GetSecurityContext` `IHostSecurityManager::SetSecurityContext` 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bac7-111">The CLR supplies one of the `EContextType` values as a parameter value in calls to the `IHostSecurityManager::GetSecurityContext` and `IHostSecurityManager::SetSecurityContext` methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bac7-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7bac7-112">Requirements</span></span>  
 <span data-ttu-id="7bac7-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7bac7-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bac7-114">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="7bac7-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7bac7-115">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="7bac7-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7bac7-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bac7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bac7-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7bac7-117">See also</span></span>

- [<span data-ttu-id="7bac7-118">IHostSecurityContext 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7bac7-118">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="7bac7-119">IHostSecurityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7bac7-119">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="7bac7-120">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="7bac7-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
