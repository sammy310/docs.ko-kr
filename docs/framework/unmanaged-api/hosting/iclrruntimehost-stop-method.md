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
ms.openlocfilehash: 55cd444ffedc92ba74239421ae548ffd930e6ab7
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703937"
---
# <a name="iclrruntimehoststop-method"></a><span data-ttu-id="b9adc-102">ICLRRuntimeHost::Stop 메서드</span><span class="sxs-lookup"><span data-stu-id="b9adc-102">ICLRRuntimeHost::Stop Method</span></span>
<span data-ttu-id="b9adc-103">CLR (공용 언어 런타임)에서 코드 실행을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9adc-103">Stops the execution of code by the common language runtime (CLR).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b9adc-104">이 메서드는 호스트에 대 한 리소스를 해제 하거나 응용 프로그램 도메인을 언로드하거나 스레드를 소멸 시 키 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b9adc-104">This method does not release resources to the host, unload application domains, or destroy threads.</span></span> <span data-ttu-id="b9adc-105">이러한 리소스를 해제 하려면 프로세스를 종료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9adc-105">You must terminate the process to release these resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9adc-106">구문</span><span class="sxs-lookup"><span data-stu-id="b9adc-106">Syntax</span></span>  
  
```cpp  
HRESULT Stop();  
```  
  
## <a name="return-value"></a><span data-ttu-id="b9adc-107">Return Value</span><span class="sxs-lookup"><span data-stu-id="b9adc-107">Return Value</span></span>  
  
|<span data-ttu-id="b9adc-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b9adc-108">HRESULT</span></span>|<span data-ttu-id="b9adc-109">설명</span><span class="sxs-lookup"><span data-stu-id="b9adc-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b9adc-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b9adc-110">S_OK</span></span>|<span data-ttu-id="b9adc-111">`Stop`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b9adc-111">`Stop` returned successfully.</span></span>|  
|<span data-ttu-id="b9adc-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b9adc-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b9adc-113">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9adc-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b9adc-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b9adc-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b9adc-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b9adc-115">The call timed out.</span></span>|  
|<span data-ttu-id="b9adc-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b9adc-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b9adc-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b9adc-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b9adc-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b9adc-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b9adc-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b9adc-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b9adc-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b9adc-120">E_FAIL</span></span>|<span data-ttu-id="b9adc-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b9adc-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b9adc-122">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b9adc-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b9adc-123">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9adc-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b9adc-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b9adc-124">Requirements</span></span>  
 <span data-ttu-id="b9adc-125">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b9adc-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9adc-126">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b9adc-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b9adc-127">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9adc-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b9adc-128">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9adc-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9adc-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b9adc-129">See also</span></span>

- [<span data-ttu-id="b9adc-130">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b9adc-130">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
