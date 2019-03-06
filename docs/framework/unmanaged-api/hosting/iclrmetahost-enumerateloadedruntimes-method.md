---
title: ICLRMetaHost::EnumerateLoadedRuntimes 메서드
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.EnumerateLoadedRuntimes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::EnumerateLoadedRuntimes
helpviewer_keywords:
- EnumerateLoadedRuntimes method [.NET Framework hosting]
- ICLRMetaHost::EnumerateLoadedRuntimes method [.NET Framework hosting]
ms.assetid: 22fc0a3f-dce4-4766-9a3c-9fab15f4b4ca
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c5a0c577975b1c16234fda649b54bcdd9f1ae59e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494873"
---
# <a name="iclrmetahostenumerateloadedruntimes-method"></a><span data-ttu-id="27cde-102">ICLRMetaHost::EnumerateLoadedRuntimes 메서드</span><span class="sxs-lookup"><span data-stu-id="27cde-102">ICLRMetaHost::EnumerateLoadedRuntimes Method</span></span>
<span data-ttu-id="27cde-103">유효한를 포함 하는 열거자를 반환 합니다 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 주어진된 프로세스에서 로드 되는 공용 언어 런타임 (CLR)의 각 버전에 대 한 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="27cde-103">Returns an enumeration that includes a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface pointer for each version of the common language runtime (CLR) that is loaded in a given process.</span></span> <span data-ttu-id="27cde-104">이 메서드를 대체 합니다 [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="27cde-104">This method supersedes the [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27cde-105">구문</span><span class="sxs-lookup"><span data-stu-id="27cde-105">Syntax</span></span>  
  
```  
HRESULT EnumerateLoadedRuntimes (  
    [in] HANDLE hndProcess,  
    [out, retval] IEnumUnknown **ppEnumerator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27cde-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="27cde-106">Parameters</span></span>  
 `hndProcess`  
 <span data-ttu-id="27cde-107">[in] 로드 된 런타임을 대 한 검사 프로세스의 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="27cde-107">[in] The handle of the process to inspect for loaded runtimes.</span></span>  
  
 `ppEnumerator`  
 <span data-ttu-id="27cde-108">[out] <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown> 열거 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 프로세스로 로드 되는 각 CLR에 해당 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="27cde-108">[out] An <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown> enumeration of [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaces corresponding to each CLR that is loaded by the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="27cde-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="27cde-109">Return Value</span></span>  
 <span data-ttu-id="27cde-110">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="27cde-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="27cde-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="27cde-111">HRESULT</span></span>|<span data-ttu-id="27cde-112">설명</span><span class="sxs-lookup"><span data-stu-id="27cde-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="27cde-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="27cde-113">S_OK</span></span>|<span data-ttu-id="27cde-114">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="27cde-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="27cde-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="27cde-115">E_POINTER</span></span>|<span data-ttu-id="27cde-116">`ppEnumerator`가 null입니다.</span><span class="sxs-lookup"><span data-stu-id="27cde-116">`ppEnumerator` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27cde-117">설명</span><span class="sxs-lookup"><span data-stu-id="27cde-117">Remarks</span></span>  
 <span data-ttu-id="27cde-118">와 같은 사용 되지 않는 함수를 사용 하 여 로드 된 해당 하는 경우에이 메서드는 로드는 모든 런타임을 [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="27cde-118">This method is lists all loaded runtimes, even if they were loaded with deprecated functions such as [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27cde-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="27cde-119">Requirements</span></span>  
 <span data-ttu-id="27cde-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="27cde-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27cde-121">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="27cde-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="27cde-122">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="27cde-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="27cde-123">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27cde-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27cde-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="27cde-124">See also</span></span>
- [<span data-ttu-id="27cde-125">ICLRMetaHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="27cde-125">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="27cde-126">호스팅</span><span class="sxs-lookup"><span data-stu-id="27cde-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
