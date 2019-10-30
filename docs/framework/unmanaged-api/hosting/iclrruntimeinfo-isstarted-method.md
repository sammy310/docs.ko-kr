---
title: ICLRRuntimeInfo::IsStarted 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsStarted
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsStarted
helpviewer_keywords:
- IsStarted method [.NET Framework hosting]
- ICLRRuntimeInfo::IsStarted method [.NET Framework hosting]
ms.assetid: ef6f2662-323b-4534-aa82-6d1afb7b9309
ms.openlocfilehash: 34590744407b25d7d53c06c452fff5bac2a95246
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136382"
---
# <a name="iclrruntimeinfoisstarted-method"></a><span data-ttu-id="5b310-102">ICLRRuntimeInfo::IsStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="5b310-102">ICLRRuntimeInfo::IsStarted Method</span></span>
<span data-ttu-id="5b310-103">런타임이 시작 되었는지 여부를 나타냅니다. 즉, [ICLRRuntimeHost:: Start 메서드가](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) 호출 되었고 성공 했는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5b310-103">Indicates whether the runtime has been started (that is, whether the [ICLRRuntimeHost::Start method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) has been called and has succeeded).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b310-104">구문</span><span class="sxs-lookup"><span data-stu-id="5b310-104">Syntax</span></span>  
  
```cpp  
HRESULT IsStarted(  
        [out] BOOL     *pbStarted,  
        [out] DWORD    *pdwStartupFlags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b310-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5b310-105">Parameters</span></span>  
 `pbStarted`  
 <span data-ttu-id="5b310-106">[out]이 런타임이 시작 되 면 `true` 합니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="5b310-106">[out] `true` if this runtime is started; otherwise, `false`.</span></span>  
  
 `pdwStartupFlags`  
 <span data-ttu-id="5b310-107">제한이 런타임을 시작 하는 데 사용 된 플래그를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b310-107">[out] Returns the flags that were used to start the runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5b310-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="5b310-108">Return Value</span></span>  
 <span data-ttu-id="5b310-109">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5b310-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="5b310-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5b310-110">HRESULT</span></span>|<span data-ttu-id="5b310-111">설명</span><span class="sxs-lookup"><span data-stu-id="5b310-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5b310-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="5b310-112">S_OK</span></span>|<span data-ttu-id="5b310-113">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5b310-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="5b310-114">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="5b310-114">E_NOTIMPL</span></span>|<span data-ttu-id="5b310-115">CLR (공용 언어 런타임) 버전은 .NET Framework 4의 CLR 버전 보다 이전 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="5b310-115">The common language runtime (CLR) version is earlier than the CLR version in the .NET Framework 4.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b310-116">주의</span><span class="sxs-lookup"><span data-stu-id="5b310-116">Remarks</span></span>  
 <span data-ttu-id="5b310-117">이 메서드는 .NET Framework 4의 CLR 버전 이전 CLR 버전에서는 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5b310-117">This method does not work with CLR versions earlier than the CLR version in the .NET Framework 4.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b310-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5b310-118">Requirements</span></span>  
 <span data-ttu-id="5b310-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5b310-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b310-120">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="5b310-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="5b310-121">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b310-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5b310-122">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b310-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b310-123">참조</span><span class="sxs-lookup"><span data-stu-id="5b310-123">See also</span></span>

- [<span data-ttu-id="5b310-124">ICLRRuntimeInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5b310-124">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="5b310-125">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5b310-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="5b310-126">호스팅</span><span class="sxs-lookup"><span data-stu-id="5b310-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
