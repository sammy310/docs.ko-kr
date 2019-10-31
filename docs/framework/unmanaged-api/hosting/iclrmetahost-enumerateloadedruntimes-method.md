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
ms.openlocfilehash: f89307ad7ed41f872ad66a99be03663ac1f30f13
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140978"
---
# <a name="iclrmetahostenumerateloadedruntimes-method"></a><span data-ttu-id="13ea5-102">ICLRMetaHost::EnumerateLoadedRuntimes 메서드</span><span class="sxs-lookup"><span data-stu-id="13ea5-102">ICLRMetaHost::EnumerateLoadedRuntimes Method</span></span>
<span data-ttu-id="13ea5-103">지정 된 프로세스에 로드 된 CLR (공용 언어 런타임)의 각 버전에 대 한 유효한 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 인터페이스 포인터를 포함 하는 열거형을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="13ea5-103">Returns an enumeration that includes a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface pointer for each version of the common language runtime (CLR) that is loaded in a given process.</span></span> <span data-ttu-id="13ea5-104">이 메서드는 [Getversionfromprocess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) 함수를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="13ea5-104">This method supersedes the [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13ea5-105">구문</span><span class="sxs-lookup"><span data-stu-id="13ea5-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateLoadedRuntimes (  
    [in] HANDLE hndProcess,  
    [out, retval] IEnumUnknown **ppEnumerator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13ea5-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="13ea5-106">Parameters</span></span>  
 `hndProcess`  
 <span data-ttu-id="13ea5-107">진행 로드 된 런타임을 검사 하는 프로세스에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="13ea5-107">[in] The handle of the process to inspect for loaded runtimes.</span></span>  
  
 `ppEnumerator`  
 <span data-ttu-id="13ea5-108">제한이 프로세스에서 로드 하는 각 CLR에 해당 하는 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 인터페이스의 <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown> 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="13ea5-108">[out] An <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown> enumeration of [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaces corresponding to each CLR that is loaded by the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="13ea5-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="13ea5-109">Return Value</span></span>  
 <span data-ttu-id="13ea5-110">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="13ea5-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="13ea5-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="13ea5-111">HRESULT</span></span>|<span data-ttu-id="13ea5-112">설명</span><span class="sxs-lookup"><span data-stu-id="13ea5-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="13ea5-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="13ea5-113">S_OK</span></span>|<span data-ttu-id="13ea5-114">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="13ea5-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="13ea5-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="13ea5-115">E_POINTER</span></span>|<span data-ttu-id="13ea5-116">`ppEnumerator`가 null입니다.</span><span class="sxs-lookup"><span data-stu-id="13ea5-116">`ppEnumerator` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13ea5-117">주의</span><span class="sxs-lookup"><span data-stu-id="13ea5-117">Remarks</span></span>  
 <span data-ttu-id="13ea5-118">[CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)와 같은 사용 되지 않는 함수를 사용 하 여 로드 된 경우에도이 메서드는 로드 된 모든 런타임을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="13ea5-118">This method is lists all loaded runtimes, even if they were loaded with deprecated functions such as [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13ea5-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="13ea5-119">Requirements</span></span>  
 <span data-ttu-id="13ea5-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="13ea5-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13ea5-121">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="13ea5-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="13ea5-122">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13ea5-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="13ea5-123">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13ea5-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13ea5-124">참조</span><span class="sxs-lookup"><span data-stu-id="13ea5-124">See also</span></span>

- [<span data-ttu-id="13ea5-125">ICLRMetaHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="13ea5-125">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="13ea5-126">호스팅</span><span class="sxs-lookup"><span data-stu-id="13ea5-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
