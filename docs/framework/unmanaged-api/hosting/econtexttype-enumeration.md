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
ms.openlocfilehash: c6d1ace12bd07fa1f14c8570eca1f950a5c22be9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686334"
---
# <a name="econtexttype-enumeration"></a><span data-ttu-id="c6fba-102">EContextType 열거형</span><span class="sxs-lookup"><span data-stu-id="c6fba-102">EContextType Enumeration</span></span>

<span data-ttu-id="c6fba-103">현재 실행 중인 스레드의 보안 컨텍스트를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6fba-103">Describes the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6fba-104">구문</span><span class="sxs-lookup"><span data-stu-id="c6fba-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a><span data-ttu-id="c6fba-105">멤버</span><span class="sxs-lookup"><span data-stu-id="c6fba-105">Members</span></span>  
  
|<span data-ttu-id="c6fba-106">멤버</span><span class="sxs-lookup"><span data-stu-id="c6fba-106">Member</span></span>|<span data-ttu-id="c6fba-107">설명</span><span class="sxs-lookup"><span data-stu-id="c6fba-107">Description</span></span>|  
|------------|-----------------|  
|`eCurrentContext`|<span data-ttu-id="c6fba-108">CLR (공용 언어 런타임)이 [IHostSecurityManager:: GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md) 메서드를 호출할 때 또는 [IHostSecurityManager:: SetSecurityContext](ihostsecuritymanager-setsecuritycontext-method.md) 메서드 호출에서 clr이 요청한 컨텍스트를 호출할 때 현재 스레드의 컨텍스트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c6fba-108">Indicates the context on the current thread at the time the common language runtime (CLR) calls the [IHostSecurityManager::GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md) method, or the context requested by the CLR in a call to the [IHostSecurityManager::SetSecurityContext](ihostsecuritymanager-setsecuritycontext-method.md) method.</span></span>|  
|`eRestrictedContext`|<span data-ttu-id="c6fba-109">호스트에 가비지 수집기, 클래스 또는 모듈 생성자 등의 낮은 권한이 있는 컨텍스트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c6fba-109">Indicates a context over which the host has lower privileges, such as the garbage collector, or class or module constructors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6fba-110">설명</span><span class="sxs-lookup"><span data-stu-id="c6fba-110">Remarks</span></span>  

 <span data-ttu-id="c6fba-111">CLR은 `EContextType` 및 메서드에 대 한 호출에서 값 중 하나를 매개 변수 값으로 제공 `IHostSecurityManager::GetSecurityContext` `IHostSecurityManager::SetSecurityContext` 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6fba-111">The CLR supplies one of the `EContextType` values as a parameter value in calls to the `IHostSecurityManager::GetSecurityContext` and `IHostSecurityManager::SetSecurityContext` methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6fba-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c6fba-112">Requirements</span></span>  

 <span data-ttu-id="c6fba-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c6fba-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6fba-114">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c6fba-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c6fba-115">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c6fba-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c6fba-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6fba-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6fba-117">참조</span><span class="sxs-lookup"><span data-stu-id="c6fba-117">See also</span></span>

- [<span data-ttu-id="c6fba-118">IHostSecurityContext 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c6fba-118">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="c6fba-119">IHostSecurityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c6fba-119">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="c6fba-120">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="c6fba-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
