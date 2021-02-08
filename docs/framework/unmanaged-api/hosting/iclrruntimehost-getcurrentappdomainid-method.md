---
description: '자세히 알아보기: ICLRRuntimeHost:: GetCurrentAppDomainId 메서드'
title: ICLRRuntimeHost::GetCurrentAppDomainId 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.GetCurrentAppDomainId
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::GetCurrentAppDomainId
helpviewer_keywords:
- ICLRRuntimeHost::GetCurrentAppDomainId method [.NET Framework hosting]
- GetCurrentAppDomainId method [.NET Framework hosting]
ms.assetid: 33800475-7815-4976-8aca-a1038761a2ef
topic_type:
- apiref
ms.openlocfilehash: 88d5288e2e8ee7d8d1f5430261e21052334240be
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799730"
---
# <a name="iclrruntimehostgetcurrentappdomainid-method"></a><span data-ttu-id="62282-103">ICLRRuntimeHost::GetCurrentAppDomainId 메서드</span><span class="sxs-lookup"><span data-stu-id="62282-103">ICLRRuntimeHost::GetCurrentAppDomainId Method</span></span>

<span data-ttu-id="62282-104">현재 실행 중인의 숫자 식별자를 가져옵니다 <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="62282-104">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62282-105">구문</span><span class="sxs-lookup"><span data-stu-id="62282-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentAppDomainId(  
    [out] DWORD* pdwAppDomainId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62282-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="62282-106">Parameters</span></span>  

 `pdwAppDomainId`  
 <span data-ttu-id="62282-107">제한이 현재 실행 중인의 숫자 식별자입니다 <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="62282-107">[out] The numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="62282-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="62282-108">Return Value</span></span>  
  
|<span data-ttu-id="62282-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="62282-109">HRESULT</span></span>|<span data-ttu-id="62282-110">설명</span><span class="sxs-lookup"><span data-stu-id="62282-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="62282-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="62282-111">S_OK</span></span>|<span data-ttu-id="62282-112">`GetCurrentAppDomainId` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="62282-112">`GetCurrentAppDomainId` returned successfully.</span></span>|  
|<span data-ttu-id="62282-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="62282-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="62282-114">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62282-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="62282-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="62282-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="62282-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="62282-116">The call timed out.</span></span>|  
|<span data-ttu-id="62282-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="62282-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="62282-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="62282-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="62282-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="62282-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="62282-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="62282-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="62282-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="62282-121">E_FAIL</span></span>|<span data-ttu-id="62282-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="62282-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="62282-123">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="62282-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="62282-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62282-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62282-125">설명</span><span class="sxs-lookup"><span data-stu-id="62282-125">Remarks</span></span>  

 <span data-ttu-id="62282-126">`pdwAppDomainId`매개 변수는 <xref:System.AppDomain.Id%2A> 현재 스레드가 실행 중인의 속성 값으로 설정 됩니다 <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="62282-126">The `pdwAppDomainId` parameter is set to the value of the <xref:System.AppDomain.Id%2A> property of the <xref:System.AppDomain> in which the current thread is executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62282-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="62282-127">Requirements</span></span>  

 <span data-ttu-id="62282-128">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="62282-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62282-129">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="62282-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="62282-130">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62282-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="62282-131">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62282-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62282-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="62282-132">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [<span data-ttu-id="62282-133">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="62282-133">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
