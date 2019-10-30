---
title: ICLRRuntimeHost::Stop 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.Stop
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::Stop
helpviewer_keywords:
- ICLRRuntimeHost::Stop method [.NET Framework hosting]
- Stop method, ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: b8fd7daf-8f8d-4ad7-92ae-019db244cec1
topic_type:
- apiref
ms.openlocfilehash: 0b59532d18848f1896977aa37f0a9f54a939aa75
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120371"
---
# <a name="iclrruntimehoststop-method"></a><span data-ttu-id="3eccb-102">ICLRRuntimeHost::Stop 메서드</span><span class="sxs-lookup"><span data-stu-id="3eccb-102">ICLRRuntimeHost::Stop Method</span></span>
<span data-ttu-id="3eccb-103">CLR (공용 언어 런타임)에서 코드 실행을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="3eccb-103">Stops the execution of code by the common language runtime (CLR).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3eccb-104">이 메서드는 호스트에 대 한 리소스를 해제 하거나 응용 프로그램 도메인을 언로드하거나 스레드를 소멸 시 키 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3eccb-104">This method does not release resources to the host, unload application domains, or destroy threads.</span></span> <span data-ttu-id="3eccb-105">이러한 리소스를 해제 하려면 프로세스를 종료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3eccb-105">You must terminate the process to release these resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3eccb-106">구문</span><span class="sxs-lookup"><span data-stu-id="3eccb-106">Syntax</span></span>  
  
```cpp  
HRESULT Stop();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3eccb-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="3eccb-107">Return Value</span></span>  
  
|<span data-ttu-id="3eccb-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3eccb-108">HRESULT</span></span>|<span data-ttu-id="3eccb-109">설명</span><span class="sxs-lookup"><span data-stu-id="3eccb-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3eccb-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3eccb-110">S_OK</span></span>|<span data-ttu-id="3eccb-111">`Stop` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3eccb-111">`Stop` returned successfully.</span></span>|  
|<span data-ttu-id="3eccb-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3eccb-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3eccb-113">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3eccb-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3eccb-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3eccb-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3eccb-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3eccb-115">The call timed out.</span></span>|  
|<span data-ttu-id="3eccb-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3eccb-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3eccb-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3eccb-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3eccb-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3eccb-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3eccb-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3eccb-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3eccb-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3eccb-120">E_FAIL</span></span>|<span data-ttu-id="3eccb-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3eccb-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3eccb-122">메서드가 E_FAIL을 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3eccb-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3eccb-123">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3eccb-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3eccb-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3eccb-124">Requirements</span></span>  
 <span data-ttu-id="3eccb-125">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3eccb-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3eccb-126">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="3eccb-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3eccb-127">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3eccb-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3eccb-128">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3eccb-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3eccb-129">참조</span><span class="sxs-lookup"><span data-stu-id="3eccb-129">See also</span></span>

- [<span data-ttu-id="3eccb-130">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3eccb-130">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
