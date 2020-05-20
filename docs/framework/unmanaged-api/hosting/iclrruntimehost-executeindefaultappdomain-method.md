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
ms.openlocfilehash: 070c52258b66dcc352f2beef81b9a0694b8301ce
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703278"
---
# <a name="iclrruntimehostexecuteindefaultappdomain-method"></a><span data-ttu-id="4a0da-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="4a0da-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain Method</span></span>
<span data-ttu-id="4a0da-103">지정 된 관리 되는 어셈블리에서 지정 된 형식의 지정 된 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a0da-103">Calls the specified method of the specified type in the specified managed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a0da-104">구문</span><span class="sxs-lookup"><span data-stu-id="4a0da-104">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteInDefaultAppDomain (  
    [in] LPCWSTR pwzAssemblyPath,  
    [in] LPCWSTR pwzTypeName,
    [in] LPCWSTR pwzMethodName,  
    [in] LPCWSTR pwzArgument,  
    [out] DWORD *pReturnValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a0da-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4a0da-105">Parameters</span></span>  
 `pwzAssemblyPath`  
 <span data-ttu-id="4a0da-106">진행 해당 <xref:System.Reflection.Assembly> 메서드가 호출 될를 정의 하는의 경로입니다 <xref:System.Type> .</span><span class="sxs-lookup"><span data-stu-id="4a0da-106">[in] The path to the <xref:System.Reflection.Assembly> that defines the <xref:System.Type> whose method is to be invoked.</span></span>  
  
 `pwzTypeName`  
 <span data-ttu-id="4a0da-107">진행 <xref:System.Type>호출할 메서드를 정의 하는의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4a0da-107">[in] The name of the <xref:System.Type> that defines the method to invoke.</span></span>  
  
 `pwzMethodName`  
 <span data-ttu-id="4a0da-108">진행 호출할 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4a0da-108">[in] The name of the method to invoke.</span></span>  
  
 `pwzArgument`  
 <span data-ttu-id="4a0da-109">진행 메서드에 전달할 문자열 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="4a0da-109">[in] The string parameter to pass to the method.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="4a0da-110">제한이 호출 된 메서드가 반환 하는 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4a0da-110">[out] The integer value returned by the invoked method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4a0da-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="4a0da-111">Return Value</span></span>  
  
|<span data-ttu-id="4a0da-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4a0da-112">HRESULT</span></span>|<span data-ttu-id="4a0da-113">설명</span><span class="sxs-lookup"><span data-stu-id="4a0da-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4a0da-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="4a0da-114">S_OK</span></span>|<span data-ttu-id="4a0da-115">`ExecuteInDefaultAppDomain`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4a0da-115">`ExecuteInDefaultAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="4a0da-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4a0da-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4a0da-117">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a0da-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4a0da-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4a0da-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4a0da-119">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4a0da-119">The call timed out.</span></span>|  
|<span data-ttu-id="4a0da-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4a0da-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4a0da-121">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4a0da-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4a0da-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4a0da-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4a0da-123">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4a0da-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4a0da-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4a0da-124">E_FAIL</span></span>|<span data-ttu-id="4a0da-125">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4a0da-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4a0da-126">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 CRL을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4a0da-126">If a method returns E_FAIL, the CRL is no longer usable within the process.</span></span> <span data-ttu-id="4a0da-127">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a0da-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a0da-128">설명</span><span class="sxs-lookup"><span data-stu-id="4a0da-128">Remarks</span></span>  
 <span data-ttu-id="4a0da-129">호출 된 메서드의 시그니처는 다음과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a0da-129">The invoked method must have the following signature:</span></span>  
  
```cpp  
static int pwzMethodName (String pwzArgument)  
```  
  
 <span data-ttu-id="4a0da-130">여기서는 `pwzMethodName` 호출 된 메서드의 이름을 나타내고 `pwzArgument` 는 해당 메서드에 매개 변수로 전달 되는 문자열 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4a0da-130">where `pwzMethodName` represents the name of the invoked method, and `pwzArgument` represents the string value passed as a parameter to that method.</span></span> <span data-ttu-id="4a0da-131">HRESULT 값이 S_OK로 설정 된 경우 `pReturnValue` 는 호출 된 메서드에서 반환 되는 정수 값으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a0da-131">If the HRESULT value is set to S_OK, `pReturnValue` is set to the integer value returned by the invoked method.</span></span> <span data-ttu-id="4a0da-132">그렇지 않으면 `pReturnValue` 이 설정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4a0da-132">Otherwise, `pReturnValue` is not set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a0da-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4a0da-133">Requirements</span></span>  
 <span data-ttu-id="4a0da-134">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4a0da-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a0da-135">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="4a0da-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4a0da-136">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a0da-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4a0da-137">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a0da-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a0da-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4a0da-138">See also</span></span>

- [<span data-ttu-id="4a0da-139">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4a0da-139">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
