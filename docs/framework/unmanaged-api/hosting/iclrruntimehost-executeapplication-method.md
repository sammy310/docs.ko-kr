---
description: '자세히 알아보기: ICLRRuntimeHost:: ExecuteApplication 메서드'
title: ICLRRuntimeHost::ExecuteApplication 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteApplication
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteApplication
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteApplication method [.NET Framework hosting]
- ExecuteApplication method [.NET Framework hosting]
ms.assetid: 5f28cc4e-7176-4e00-aa1f-58ae6ee52fe4
topic_type:
- apiref
ms.openlocfilehash: 1511cc3dcf05c3f2243f4080143789e456c39167
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688977"
---
# <a name="iclrruntimehostexecuteapplication-method"></a><span data-ttu-id="bf580-103">ICLRRuntimeHost::ExecuteApplication 메서드</span><span class="sxs-lookup"><span data-stu-id="bf580-103">ICLRRuntimeHost::ExecuteApplication Method</span></span>

<span data-ttu-id="bf580-104">매니페스트 기반 ClickOnce 배포 시나리오에서 새 도메인에 활성화 될 응용 프로그램을 지정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf580-104">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span> <span data-ttu-id="bf580-105">이러한 시나리오에 대 한 자세한 내용은 [ClickOnce 보안 및 배포](/visualstudio/deployment/clickonce-security-and-deployment)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bf580-105">For more information about these scenarios, see [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf580-106">구문</span><span class="sxs-lookup"><span data-stu-id="bf580-106">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteApplication(  
    [in] LPCWSTR   pwzAppFullName,  
    [in] DWORD     dwManifestPaths,  
    [in] LPCWSTR   *ppwzManifestPaths,  
    [in] DWORD     dwActivationData,  
    [in] LPCWSTR   *ppwzActivationData,  
    [out] int      *pReturnValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf580-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bf580-107">Parameters</span></span>  

 `pwzAppFullName`  
 <span data-ttu-id="bf580-108">진행 에 대해 정의 된 응용 프로그램의 전체 이름 <xref:System.ApplicationIdentity> 입니다.</span><span class="sxs-lookup"><span data-stu-id="bf580-108">[in] The full name of the application, as defined for <xref:System.ApplicationIdentity>.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="bf580-109">진행 배열에 포함 된 문자열의 수 `ppwzManifestPaths` 입니다.</span><span class="sxs-lookup"><span data-stu-id="bf580-109">[in] The number of strings contained in the `ppwzManifestPaths` array.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="bf580-110">[in] 선택적 항목으로,</span><span class="sxs-lookup"><span data-stu-id="bf580-110">[in] Optional.</span></span> <span data-ttu-id="bf580-111">응용 프로그램에 대 한 매니페스트 경로를 포함 하는 문자열 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="bf580-111">A string array that contains manifest paths for the application.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="bf580-112">진행 배열에 포함 된 문자열의 수 `ppwzActivationData` 입니다.</span><span class="sxs-lookup"><span data-stu-id="bf580-112">[in] The number of strings contained in the `ppwzActivationData` array.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="bf580-113">[in] 선택적 항목으로,</span><span class="sxs-lookup"><span data-stu-id="bf580-113">[in] Optional.</span></span> <span data-ttu-id="bf580-114">웹을 통해 배포 된 응용 프로그램에 대 한 URL의 쿼리 문자열 부분과 같은 응용 프로그램의 활성화 데이터를 포함 하는 문자열 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="bf580-114">A string array that contains the application's activation data, such as the query string portion of the URL for applications deployed over the Web.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="bf580-115">제한이 응용 프로그램의 진입점에서 반환 된 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bf580-115">[out] The value returned from the entry point of the application.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bf580-116">Return Value</span><span class="sxs-lookup"><span data-stu-id="bf580-116">Return Value</span></span>  
  
|<span data-ttu-id="bf580-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bf580-117">HRESULT</span></span>|<span data-ttu-id="bf580-118">설명</span><span class="sxs-lookup"><span data-stu-id="bf580-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bf580-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="bf580-119">S_OK</span></span>|<span data-ttu-id="bf580-120">`ExecuteApplication` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bf580-120">`ExecuteApplication` returned successfully.</span></span>|  
|<span data-ttu-id="bf580-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bf580-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bf580-122">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf580-122">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bf580-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bf580-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bf580-124">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bf580-124">The call timed out.</span></span>|  
|<span data-ttu-id="bf580-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bf580-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bf580-126">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bf580-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bf580-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bf580-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bf580-128">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bf580-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bf580-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bf580-129">E_FAIL</span></span>|<span data-ttu-id="bf580-130">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bf580-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bf580-131">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bf580-131">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bf580-132">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf580-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf580-133">설명</span><span class="sxs-lookup"><span data-stu-id="bf580-133">Remarks</span></span>  

 <span data-ttu-id="bf580-134">`ExecuteApplication` 는 새로 만든 응용 프로그램 도메인에서 ClickOnce 응용 프로그램을 활성화 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf580-134">`ExecuteApplication` is used to activate ClickOnce applications in a newly created application domain.</span></span>  
  
 <span data-ttu-id="bf580-135">`pReturnValue`출력 매개 변수는 응용 프로그램에서 반환 된 값으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf580-135">The `pReturnValue` output parameter is set to the value returned by the application.</span></span> <span data-ttu-id="bf580-136">에 null 값을 제공 하는 경우 `pReturnValue` `ExecuteApplication` 는 실패 하지 않지만는 값을 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bf580-136">If you supply a value of null for `pReturnValue`, `ExecuteApplication` does not fail, but it does not return a value.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="bf580-137">매니페스트 기반 응용 프로그램을 활성화 하기 위해 메서드를 호출 하기 전에 [Start 메서드](iclrruntimehost-start-method.md) 메서드를 호출 하지 마세요 `ExecuteApplication` .</span><span class="sxs-lookup"><span data-stu-id="bf580-137">Do not call the [Start Method](iclrruntimehost-start-method.md) method before calling the `ExecuteApplication` method to activate a manifest-based application.</span></span> <span data-ttu-id="bf580-138">메서드를 `Start` 먼저 호출 하면 `ExecuteApplication` 메서드 호출이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf580-138">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf580-139">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bf580-139">Requirements</span></span>  

 <span data-ttu-id="bf580-140">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bf580-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf580-141">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="bf580-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bf580-142">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf580-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bf580-143">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf580-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf580-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bf580-144">See also</span></span>

- <xref:System.ActivationContext>
- <xref:System.AppDomainManager>
- <xref:System.ApplicationIdentity>
- [<span data-ttu-id="bf580-145">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bf580-145">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
- [<span data-ttu-id="bf580-146">SetAppDomainManager 메서드</span><span class="sxs-lookup"><span data-stu-id="bf580-146">SetAppDomainManager Method</span></span>](ihostcontrol-setappdomainmanager-method.md)
- [<span data-ttu-id="bf580-147">연습: 디자이너를 사용 하 여 ClickOnce 배포 API에서 요청 시 어셈블리 다운로드</span><span class="sxs-lookup"><span data-stu-id="bf580-147">Walkthrough: Downloading Assemblies on Demand with the ClickOnce Deployment API Using the Designer</span></span>](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer)
