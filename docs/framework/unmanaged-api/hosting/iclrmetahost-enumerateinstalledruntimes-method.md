---
title: ICLRMetaHost::EnumerateInstalledRuntimes 메서드
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.EnumerateInstalledRuntimes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::EnumerateInstalledRuntimes
helpviewer_keywords:
- ICLRMetaHost::EnumerateInstalledRuntimes method [.NET Framework hosting]
- EnumerateInstalledRuntimes method [.NET Framework hosting]
ms.assetid: 9e359384-0d3d-451c-807e-5d7fcebf2be7
topic_type:
- apiref
ms.openlocfilehash: 9415d5189edb901822abad9269e0150e7601a963
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140959"
---
# <a name="iclrmetahostenumerateinstalledruntimes-method"></a><span data-ttu-id="e61c9-102">ICLRMetaHost::EnumerateInstalledRuntimes 메서드</span><span class="sxs-lookup"><span data-stu-id="e61c9-102">ICLRMetaHost::EnumerateInstalledRuntimes Method</span></span>
<span data-ttu-id="e61c9-103">컴퓨터에 설치 된 CLR (공용 언어 런타임)의 각 버전에 대 한 유효한 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 인터페이스를 포함 하는 열거형을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e61c9-103">Returns an enumeration that contains a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface for each version of the common language runtime (CLR) that is installed on a computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e61c9-104">구문</span><span class="sxs-lookup"><span data-stu-id="e61c9-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateInstalledRuntimes (  
    [out, retval] IEnumUnknown **ppEnumerator);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e61c9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e61c9-105">Parameters</span></span>  
 `ppEnumerator`  
 <span data-ttu-id="e61c9-106">제한이 컴퓨터에 설치 된 각 CLR 버전에 해당 하는 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 인터페이스의 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="e61c9-106">[out] An enumeration of [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaces corresponding to each version of the CLR that is installed on the computer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e61c9-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="e61c9-107">Return Value</span></span>  
 <span data-ttu-id="e61c9-108">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e61c9-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="e61c9-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e61c9-109">HRESULT</span></span>|<span data-ttu-id="e61c9-110">설명</span><span class="sxs-lookup"><span data-stu-id="e61c9-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e61c9-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e61c9-111">S_OK</span></span>|<span data-ttu-id="e61c9-112">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e61c9-112">The method completed successfully.</span></span>|  
|<span data-ttu-id="e61c9-113">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="e61c9-113">E_POINTER</span></span>|<span data-ttu-id="e61c9-114">`ppEnumerator`가 null입니다.</span><span class="sxs-lookup"><span data-stu-id="e61c9-114">`ppEnumerator` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e61c9-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e61c9-115">Requirements</span></span>  
 <span data-ttu-id="e61c9-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e61c9-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e61c9-117">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="e61c9-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e61c9-118">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e61c9-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e61c9-119">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e61c9-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e61c9-120">참조</span><span class="sxs-lookup"><span data-stu-id="e61c9-120">See also</span></span>

- [<span data-ttu-id="e61c9-121">ICLRMetaHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e61c9-121">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="e61c9-122">호스팅</span><span class="sxs-lookup"><span data-stu-id="e61c9-122">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
