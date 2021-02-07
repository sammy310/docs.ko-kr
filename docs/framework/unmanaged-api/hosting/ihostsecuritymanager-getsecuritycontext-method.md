---
description: '자세히 알아보기: IHostSecurityManager:: GetSecurityContext 메서드'
title: IHostSecurityManager::GetSecurityContext 메서드
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.GetSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::GetSecurityContext
helpviewer_keywords:
- GetSecurityContext method [.NET Framework hosting]
- IHostSecurityManager::GetSecurityContext method [.NET Framework hosting]
ms.assetid: 958970d6-f6a2-4b84-b32a-f555cbaf8f61
topic_type:
- apiref
ms.openlocfilehash: 0dc9e0380d2fb218b68f6beb85fa1ccba8826d85
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671566"
---
# <a name="ihostsecuritymanagergetsecuritycontext-method"></a><span data-ttu-id="1159b-103">IHostSecurityManager::GetSecurityContext 메서드</span><span class="sxs-lookup"><span data-stu-id="1159b-103">IHostSecurityManager::GetSecurityContext Method</span></span>

<span data-ttu-id="1159b-104">호스트에서 요청 된 [IHostSecurityContext](ihostsecuritycontext-interface.md) 를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1159b-104">Gets the requested [IHostSecurityContext](ihostsecuritycontext-interface.md) from the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1159b-105">구문</span><span class="sxs-lookup"><span data-stu-id="1159b-105">Syntax</span></span>  
  
```cpp
HRESULT GetSecurityContext (  
    [in]  EContextType eContextType,
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1159b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1159b-106">Parameters</span></span>  

 `eContextType`  
 <span data-ttu-id="1159b-107">진행 반환할 보안 컨텍스트의 유형을 나타내는 [EContextType](econtexttype-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="1159b-107">[in] One of the [EContextType](econtexttype-enumeration.md) values, indicating what type of security context to return.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="1159b-108">제한이 의에 대 한 인터페이스 포인터의 주소 `IHostSecurityContext` 입니다 `eContextType` .</span><span class="sxs-lookup"><span data-stu-id="1159b-108">[out] The address of an interface pointer to the `IHostSecurityContext` of `eContextType`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1159b-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="1159b-109">Return Value</span></span>  
  
|<span data-ttu-id="1159b-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1159b-110">HRESULT</span></span>|<span data-ttu-id="1159b-111">설명</span><span class="sxs-lookup"><span data-stu-id="1159b-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1159b-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="1159b-112">S_OK</span></span>|<span data-ttu-id="1159b-113">`GetSecurityContext` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1159b-113">`GetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="1159b-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1159b-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1159b-115">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1159b-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1159b-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1159b-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1159b-117">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1159b-117">The call timed out.</span></span>|  
|<span data-ttu-id="1159b-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1159b-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1159b-119">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1159b-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1159b-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1159b-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1159b-121">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1159b-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1159b-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1159b-122">E_FAIL</span></span>|<span data-ttu-id="1159b-123">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1159b-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1159b-124">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1159b-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1159b-125">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1159b-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1159b-126">설명</span><span class="sxs-lookup"><span data-stu-id="1159b-126">Remarks</span></span>  

 <span data-ttu-id="1159b-127">호스트는 CLR 및 사용자 코드를 모두 사용 하 여 스레드 토큰에 대 한 모든 코드 액세스를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1159b-127">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="1159b-128">또한 코드 액세스가 제한 된 비동기 작업 또는 코드 포인트로 전체 보안 컨텍스트 정보를 전달 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1159b-128">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="1159b-129">`IHostSecurityContext` 는 CLR에 불투명 한이 보안 컨텍스트 정보를 캡슐화 합니다.</span><span class="sxs-lookup"><span data-stu-id="1159b-129">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span> <span data-ttu-id="1159b-130">CLR은이 정보를 캡처하여 스레드 풀 작업자 항목 디스패치, 종료자 실행 및 모듈 및 클래스 생성 간에 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1159b-130">The CLR captures this information and moves it across thread pool worker item dispatch, finalizer execution, and module and class construction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1159b-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1159b-131">Requirements</span></span>  

 <span data-ttu-id="1159b-132">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1159b-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1159b-133">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1159b-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1159b-134">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1159b-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1159b-135">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1159b-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1159b-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1159b-136">See also</span></span>

- [<span data-ttu-id="1159b-137">EContextType 열거형</span><span class="sxs-lookup"><span data-stu-id="1159b-137">EContextType Enumeration</span></span>](econtexttype-enumeration.md)
- [<span data-ttu-id="1159b-138">IHostSecurityContext 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1159b-138">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="1159b-139">IHostSecurityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1159b-139">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
