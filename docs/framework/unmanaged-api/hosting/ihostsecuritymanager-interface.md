---
title: IHostSecurityManager 인터페이스
ms.date: 03/30/2017
api_name:
- IHostSecurityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager
helpviewer_keywords:
- IHostSecurityManager interface [.NET Framework hosting]
ms.assetid: c3be2cbd-2d93-438b-9888-9a0251b63c03
topic_type:
- apiref
ms.openlocfilehash: 237fe23493460df77a79ba3aed9f0a809cd8aa23
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501471"
---
# <a name="ihostsecuritymanager-interface"></a><span data-ttu-id="401d5-102">IHostSecurityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="401d5-102">IHostSecurityManager Interface</span></span>
<span data-ttu-id="401d5-103">현재 실행 중인 스레드의 보안 컨텍스트에 대 한 액세스 및 제어를 허용 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="401d5-103">Provides methods that allow access to and control over the security context of the currently executing thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="401d5-104">메서드</span><span class="sxs-lookup"><span data-stu-id="401d5-104">Methods</span></span>  
  
|<span data-ttu-id="401d5-105">방법</span><span class="sxs-lookup"><span data-stu-id="401d5-105">Method</span></span>|<span data-ttu-id="401d5-106">설명</span><span class="sxs-lookup"><span data-stu-id="401d5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="401d5-107">GetSecurityContext 메서드</span><span class="sxs-lookup"><span data-stu-id="401d5-107">GetSecurityContext Method</span></span>](ihostsecuritymanager-getsecuritycontext-method.md)|<span data-ttu-id="401d5-108">호스트에서 요청 된 [IHostSecurityContext](ihostsecuritycontext-interface.md) 를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="401d5-108">Gets the requested [IHostSecurityContext](ihostsecuritycontext-interface.md) from the host.</span></span>|  
|[<span data-ttu-id="401d5-109">ImpersonateLoggedOnUser 메서드</span><span class="sxs-lookup"><span data-stu-id="401d5-109">ImpersonateLoggedOnUser Method</span></span>](ihostsecuritymanager-impersonateloggedonuser-method.md)|<span data-ttu-id="401d5-110">현재 사용자 id의 자격 증명을 사용 하 여 코드를 실행 하도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="401d5-110">Requests that code be executed using the credentials of the current user identity.</span></span>|  
|[<span data-ttu-id="401d5-111">OpenThreadToken 메서드</span><span class="sxs-lookup"><span data-stu-id="401d5-111">OpenThreadToken Method</span></span>](ihostsecuritymanager-openthreadtoken-method.md)|<span data-ttu-id="401d5-112">현재 스레드와 연결 된 임의 액세스 토큰을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="401d5-112">Opens the discretionary access token associated with the current thread.</span></span>|  
|[<span data-ttu-id="401d5-113">RevertToSelf 메서드</span><span class="sxs-lookup"><span data-stu-id="401d5-113">RevertToSelf Method</span></span>](ihostsecuritymanager-reverttoself-method.md)|<span data-ttu-id="401d5-114">현재 사용자 id의 가장을 종료 하 고 원래 스레드 토큰을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="401d5-114">Terminates impersonation of the current user identity and returns the original thread token.</span></span>|  
|[<span data-ttu-id="401d5-115">SetSecurityContext 메서드</span><span class="sxs-lookup"><span data-stu-id="401d5-115">SetSecurityContext Method</span></span>](ihostsecuritymanager-setsecuritycontext-method.md)|<span data-ttu-id="401d5-116">현재 실행 중인 스레드에 대 한 보안 컨텍스트를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="401d5-116">Sets the security context for the currently executing thread.</span></span>|  
|[<span data-ttu-id="401d5-117">SetThreadToken 메서드</span><span class="sxs-lookup"><span data-stu-id="401d5-117">SetThreadToken Method</span></span>](ihostsecuritymanager-setthreadtoken-method.md)|<span data-ttu-id="401d5-118">현재 실행 중인 스레드에 대 한 핸들을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="401d5-118">Sets a handle for the currently executing thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="401d5-119">설명</span><span class="sxs-lookup"><span data-stu-id="401d5-119">Remarks</span></span>  
 <span data-ttu-id="401d5-120">호스트는 CLR (공용 언어 런타임) 및 사용자 코드를 모두 사용 하 여 스레드 토큰에 대 한 모든 코드 액세스를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="401d5-120">A host can control all code access to thread tokens by both the common language runtime (CLR) and user code.</span></span> <span data-ttu-id="401d5-121">또한 코드 액세스가 제한 된 비동기 작업 또는 코드 포인트로 전체 보안 컨텍스트 정보를 전달 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="401d5-121">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="401d5-122">`IHostSecurityContext`는 CLR에 불투명 한이 보안 컨텍스트 정보를 캡슐화 합니다.</span><span class="sxs-lookup"><span data-stu-id="401d5-122">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span>  
  
 <span data-ttu-id="401d5-123">CLR은 내부적으로 관리 되는 스레드 컨텍스트를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="401d5-123">The CLR handles managed thread context internally.</span></span> <span data-ttu-id="401d5-124">프로세스에 따라 `IHostSecurityManager` 다음과 같은 상황에서 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="401d5-124">It queries the process-specific `IHostSecurityManager` in the following situations:</span></span>  
  
- <span data-ttu-id="401d5-125">종료자 스레드에서 종료자를 실행 하는 동안</span><span class="sxs-lookup"><span data-stu-id="401d5-125">On the finalizer thread, during finalizer execution.</span></span>  
  
- <span data-ttu-id="401d5-126">클래스 및 모듈 생성자를 실행 하는 동안</span><span class="sxs-lookup"><span data-stu-id="401d5-126">During class and module constructor execution.</span></span>  
  
- <span data-ttu-id="401d5-127">작업자 스레드의 비동기 지점에서 [IHostThreadPoolManager:: QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md) 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="401d5-127">At asynchronous points on the worker thread, in calls to the [IHostThreadPoolManager::QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md) method.</span></span>  
  
- <span data-ttu-id="401d5-128">I/o 완료 포트의 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="401d5-128">In servicing of I/O completion ports.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="401d5-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="401d5-129">Requirements</span></span>  
 <span data-ttu-id="401d5-130">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="401d5-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="401d5-131">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="401d5-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="401d5-132">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="401d5-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="401d5-133">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="401d5-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="401d5-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="401d5-134">See also</span></span>

- [<span data-ttu-id="401d5-135">IHostSecurityContext 인터페이스</span><span class="sxs-lookup"><span data-stu-id="401d5-135">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="401d5-136">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="401d5-136">Hosting Interfaces</span></span>](hosting-interfaces.md)
