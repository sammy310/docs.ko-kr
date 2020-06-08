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
ms.openlocfilehash: 7b09bb9c3abcb23997bfd412c3ea939404e583c1
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504175"
---
# <a name="iclrmetahostenumerateloadedruntimes-method"></a><span data-ttu-id="6dce6-102">ICLRMetaHost::EnumerateLoadedRuntimes 메서드</span><span class="sxs-lookup"><span data-stu-id="6dce6-102">ICLRMetaHost::EnumerateLoadedRuntimes Method</span></span>
<span data-ttu-id="6dce6-103">지정 된 프로세스에 로드 된 CLR (공용 언어 런타임)의 각 버전에 대 한 유효한 [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) 인터페이스 포인터를 포함 하는 열거형을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6dce6-103">Returns an enumeration that includes a valid [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface pointer for each version of the common language runtime (CLR) that is loaded in a given process.</span></span> <span data-ttu-id="6dce6-104">이 메서드는 [Getversionfromprocess](getversionfromprocess-function.md) 함수를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="6dce6-104">This method supersedes the [GetVersionFromProcess](getversionfromprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6dce6-105">구문</span><span class="sxs-lookup"><span data-stu-id="6dce6-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateLoadedRuntimes (  
    [in] HANDLE hndProcess,  
    [out, retval] IEnumUnknown **ppEnumerator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6dce6-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6dce6-106">Parameters</span></span>  
 `hndProcess`  
 <span data-ttu-id="6dce6-107">진행 로드 된 런타임을 검사 하는 프로세스에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="6dce6-107">[in] The handle of the process to inspect for loaded runtimes.</span></span>  
  
 `ppEnumerator`  
 <span data-ttu-id="6dce6-108">제한이 <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown>프로세스에서 로드 한 각 CLR에 해당 하는 [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) 인터페이스의 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="6dce6-108">[out] An <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown> enumeration of [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interfaces corresponding to each CLR that is loaded by the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6dce6-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="6dce6-109">Return Value</span></span>  
 <span data-ttu-id="6dce6-110">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6dce6-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="6dce6-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6dce6-111">HRESULT</span></span>|<span data-ttu-id="6dce6-112">설명</span><span class="sxs-lookup"><span data-stu-id="6dce6-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6dce6-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="6dce6-113">S_OK</span></span>|<span data-ttu-id="6dce6-114">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6dce6-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="6dce6-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="6dce6-115">E_POINTER</span></span>|<span data-ttu-id="6dce6-116">`ppEnumerator`가 null인 경우</span><span class="sxs-lookup"><span data-stu-id="6dce6-116">`ppEnumerator` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6dce6-117">설명</span><span class="sxs-lookup"><span data-stu-id="6dce6-117">Remarks</span></span>  
 <span data-ttu-id="6dce6-118">[CorBindToRuntime](corbindtoruntime-function.md)와 같은 사용 되지 않는 함수를 사용 하 여 로드 된 경우에도이 메서드는 로드 된 모든 런타임을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="6dce6-118">This method is lists all loaded runtimes, even if they were loaded with deprecated functions such as [CorBindToRuntime](corbindtoruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6dce6-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6dce6-119">Requirements</span></span>  
 <span data-ttu-id="6dce6-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6dce6-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6dce6-121">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="6dce6-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6dce6-122">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6dce6-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6dce6-123">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6dce6-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dce6-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6dce6-124">See also</span></span>

- [<span data-ttu-id="6dce6-125">ICLRMetaHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6dce6-125">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="6dce6-126">호스팅</span><span class="sxs-lookup"><span data-stu-id="6dce6-126">Hosting</span></span>](index.md)
