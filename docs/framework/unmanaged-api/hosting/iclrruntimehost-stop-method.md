---
description: '자세히 알아보기: ICLRRuntimeHost:: Stop 메서드'
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
ms.openlocfilehash: 3e6b1cf2aee95af6354905f6dcdcb678ff785aa6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799732"
---
# <a name="iclrruntimehoststop-method"></a><span data-ttu-id="9cb1e-103">ICLRRuntimeHost::Stop 메서드</span><span class="sxs-lookup"><span data-stu-id="9cb1e-103">ICLRRuntimeHost::Stop Method</span></span>

<span data-ttu-id="9cb1e-104">CLR (공용 언어 런타임)에서 코드 실행을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cb1e-104">Stops the execution of code by the common language runtime (CLR).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="9cb1e-105">이 메서드는 호스트에 대 한 리소스를 해제 하거나 응용 프로그램 도메인을 언로드하거나 스레드를 소멸 시 키 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9cb1e-105">This method does not release resources to the host, unload application domains, or destroy threads.</span></span> <span data-ttu-id="9cb1e-106">이러한 리소스를 해제 하려면 프로세스를 종료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cb1e-106">You must terminate the process to release these resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cb1e-107">구문</span><span class="sxs-lookup"><span data-stu-id="9cb1e-107">Syntax</span></span>  
  
```cpp  
HRESULT Stop();  
```  
  
## <a name="return-value"></a><span data-ttu-id="9cb1e-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="9cb1e-108">Return Value</span></span>  
  
|<span data-ttu-id="9cb1e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9cb1e-109">HRESULT</span></span>|<span data-ttu-id="9cb1e-110">설명</span><span class="sxs-lookup"><span data-stu-id="9cb1e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9cb1e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="9cb1e-111">S_OK</span></span>|<span data-ttu-id="9cb1e-112">`Stop` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9cb1e-112">`Stop` returned successfully.</span></span>|  
|<span data-ttu-id="9cb1e-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9cb1e-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9cb1e-114">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cb1e-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9cb1e-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9cb1e-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9cb1e-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9cb1e-116">The call timed out.</span></span>|  
|<span data-ttu-id="9cb1e-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9cb1e-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9cb1e-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9cb1e-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9cb1e-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9cb1e-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9cb1e-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9cb1e-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9cb1e-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9cb1e-121">E_FAIL</span></span>|<span data-ttu-id="9cb1e-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9cb1e-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9cb1e-123">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9cb1e-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9cb1e-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9cb1e-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9cb1e-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9cb1e-125">Requirements</span></span>  

 <span data-ttu-id="9cb1e-126">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9cb1e-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cb1e-127">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9cb1e-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9cb1e-128">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9cb1e-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9cb1e-129">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cb1e-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cb1e-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9cb1e-130">See also</span></span>

- [<span data-ttu-id="9cb1e-131">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9cb1e-131">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
