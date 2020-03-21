---
title: ICLRRuntimeHost::ExecuteInDefaultAppDomain 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteInDefaultAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain method [.NET Framework hosting]
- ExecuteInDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 30b5cf9a-a762-4bd4-be12-d6c1442b78b1
topic_type:
- apiref
ms.openlocfilehash: 1a1bc7609042422de876fe167a9e61655aaf62b4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176411"
---
# <a name="iclrruntimehostexecuteindefaultappdomain-method"></a><span data-ttu-id="6b3c3-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="6b3c3-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain Method</span></span>
<span data-ttu-id="6b3c3-103">지정된 관리 되는 어셈블리에서 지정 된 형식의 지정된된 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3c3-103">Calls the specified method of the specified type in the specified managed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b3c3-104">구문</span><span class="sxs-lookup"><span data-stu-id="6b3c3-104">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteInDefaultAppDomain (  
    [in] LPCWSTR pwzAssemblyPath,  
    [in] LPCWSTR pwzTypeName,
    [in] LPCWSTR pwzMethodName,  
    [in] LPCWSTR pwzArgument,  
    [out] DWORD *pReturnValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b3c3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6b3c3-105">Parameters</span></span>  
 `pwzAssemblyPath`  
 <span data-ttu-id="6b3c3-106">【인】 호출할 메서드를 정의하는 <xref:System.Reflection.Assembly> 경로입니다. <xref:System.Type></span><span class="sxs-lookup"><span data-stu-id="6b3c3-106">[in] The path to the <xref:System.Reflection.Assembly> that defines the <xref:System.Type> whose method is to be invoked.</span></span>  
  
 `pwzTypeName`  
 <span data-ttu-id="6b3c3-107">【인】 호출할 <xref:System.Type> 메서드를 정의하는 의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6b3c3-107">[in] The name of the <xref:System.Type> that defines the method to invoke.</span></span>  
  
 `pwzMethodName`  
 <span data-ttu-id="6b3c3-108">【인】 호출할 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6b3c3-108">[in] The name of the method to invoke.</span></span>  
  
 `pwzArgument`  
 <span data-ttu-id="6b3c3-109">【인】 메서드에 전달할 문자열 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="6b3c3-109">[in] The string parameter to pass to the method.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="6b3c3-110">【아웃】 호출된 메서드에서 반환되는 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6b3c3-110">[out] The integer value returned by the invoked method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6b3c3-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="6b3c3-111">Return Value</span></span>  
  
|<span data-ttu-id="6b3c3-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6b3c3-112">HRESULT</span></span>|<span data-ttu-id="6b3c3-113">Description</span><span class="sxs-lookup"><span data-stu-id="6b3c3-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6b3c3-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="6b3c3-114">S_OK</span></span>|<span data-ttu-id="6b3c3-115">`ExecuteInDefaultAppDomain`성공적으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b3c3-115">`ExecuteInDefaultAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="6b3c3-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6b3c3-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6b3c3-117">공통 언어 런타임(CLR)이 프로세스에 로드되지 않았거나 CLR이 관리 코드를 실행하거나 호출을 성공적으로 처리할 수 없는 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="6b3c3-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6b3c3-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6b3c3-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6b3c3-119">통화 시간이 시간 미정으로 확인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6b3c3-119">The call timed out.</span></span>|  
|<span data-ttu-id="6b3c3-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6b3c3-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6b3c3-121">호출자는 잠금을 소유하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6b3c3-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6b3c3-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6b3c3-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6b3c3-123">차단된 스레드 또는 파이버가 대기하는 동안 이벤트가 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6b3c3-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6b3c3-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6b3c3-124">E_FAIL</span></span>|<span data-ttu-id="6b3c3-125">알 수 없는 치명적인 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="6b3c3-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6b3c3-126">메서드가 E_FAIL 반환하면 프로세스 내에서 CRL을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6b3c3-126">If a method returns E_FAIL, the CRL is no longer usable within the process.</span></span> <span data-ttu-id="6b3c3-127">호스팅 메서드에 대한 후속 호출은 HOST_E_CLRNOTAVAILABLE 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3c3-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b3c3-128">설명</span><span class="sxs-lookup"><span data-stu-id="6b3c3-128">Remarks</span></span>  
 <span data-ttu-id="6b3c3-129">호출된 메서드에는 다음 서명이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3c3-129">The invoked method must have the following signature:</span></span>  
  
```cpp  
static int pwzMethodName (String pwzArgument)  
```  
  
 <span data-ttu-id="6b3c3-130">여기서 `pwzMethodName` 호출된 메서드의 이름을 나타내고 `pwzArgument` 해당 메서드에 대한 매개 변수로 전달된 문자열 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6b3c3-130">where `pwzMethodName` represents the name of the invoked method, and `pwzArgument` represents the string value passed as a parameter to that method.</span></span> <span data-ttu-id="6b3c3-131">HRESULT 값이 S_OK 설정된 경우 `pReturnValue` 호출된 메서드에서 반환되는 정수 값으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b3c3-131">If the HRESULT value is set to S_OK, `pReturnValue` is set to the integer value returned by the invoked method.</span></span> <span data-ttu-id="6b3c3-132">`pReturnValue` 그렇지 않으면 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6b3c3-132">Otherwise, `pReturnValue` is not set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b3c3-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6b3c3-133">Requirements</span></span>  
 <span data-ttu-id="6b3c3-134">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6b3c3-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b3c3-135">**헤더:** MSCorE.h</span><span class="sxs-lookup"><span data-stu-id="6b3c3-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6b3c3-136">**라이브러리:** MSCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="6b3c3-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6b3c3-137">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b3c3-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b3c3-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6b3c3-138">See also</span></span>

- [<span data-ttu-id="6b3c3-139">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6b3c3-139">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
