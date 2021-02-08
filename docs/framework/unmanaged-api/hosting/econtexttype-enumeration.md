---
description: '자세히 알아보기: EContextType 열거형'
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
ms.openlocfilehash: b7d6ddb385386bb0616a01ef6fcc432f2c925d51
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785535"
---
# <a name="econtexttype-enumeration"></a><span data-ttu-id="b6ba8-103">EContextType 열거형</span><span class="sxs-lookup"><span data-stu-id="b6ba8-103">EContextType Enumeration</span></span>

<span data-ttu-id="b6ba8-104">현재 실행 중인 스레드의 보안 컨텍스트를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-104">Describes the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6ba8-105">구문</span><span class="sxs-lookup"><span data-stu-id="b6ba8-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a><span data-ttu-id="b6ba8-106">구성원</span><span class="sxs-lookup"><span data-stu-id="b6ba8-106">Members</span></span>  
  
|<span data-ttu-id="b6ba8-107">멤버</span><span class="sxs-lookup"><span data-stu-id="b6ba8-107">Member</span></span>|<span data-ttu-id="b6ba8-108">설명</span><span class="sxs-lookup"><span data-stu-id="b6ba8-108">Description</span></span>|  
|------------|-----------------|  
|`eCurrentContext`|<span data-ttu-id="b6ba8-109">CLR (공용 언어 런타임)이 [IHostSecurityManager:: GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md) 메서드를 호출할 때 또는 [IHostSecurityManager:: SetSecurityContext](ihostsecuritymanager-setsecuritycontext-method.md) 메서드 호출에서 clr이 요청한 컨텍스트를 호출할 때 현재 스레드의 컨텍스트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-109">Indicates the context on the current thread at the time the common language runtime (CLR) calls the [IHostSecurityManager::GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md) method, or the context requested by the CLR in a call to the [IHostSecurityManager::SetSecurityContext](ihostsecuritymanager-setsecuritycontext-method.md) method.</span></span>|  
|`eRestrictedContext`|<span data-ttu-id="b6ba8-110">호스트에 가비지 수집기, 클래스 또는 모듈 생성자 등의 낮은 권한이 있는 컨텍스트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-110">Indicates a context over which the host has lower privileges, such as the garbage collector, or class or module constructors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6ba8-111">설명</span><span class="sxs-lookup"><span data-stu-id="b6ba8-111">Remarks</span></span>  

 <span data-ttu-id="b6ba8-112">CLR은 `EContextType` 및 메서드에 대 한 호출에서 값 중 하나를 매개 변수 값으로 제공 `IHostSecurityManager::GetSecurityContext` `IHostSecurityManager::SetSecurityContext` 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-112">The CLR supplies one of the `EContextType` values as a parameter value in calls to the `IHostSecurityManager::GetSecurityContext` and `IHostSecurityManager::SetSecurityContext` methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6ba8-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b6ba8-113">Requirements</span></span>  

 <span data-ttu-id="b6ba8-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6ba8-115">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b6ba8-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b6ba8-116">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b6ba8-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b6ba8-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6ba8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6ba8-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b6ba8-118">See also</span></span>

- [<span data-ttu-id="b6ba8-119">IHostSecurityContext 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b6ba8-119">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="b6ba8-120">IHostSecurityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b6ba8-120">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="b6ba8-121">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="b6ba8-121">Hosting Enumerations</span></span>](hosting-enumerations.md)
