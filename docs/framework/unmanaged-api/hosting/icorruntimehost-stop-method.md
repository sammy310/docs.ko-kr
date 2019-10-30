---
title: ICorRuntimeHost::Stop 메서드
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.Stop
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::Stop
helpviewer_keywords:
- Stop method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::Stop method [.NET Framework hosting]
ms.assetid: 46a0d450-b516-4bef-8b71-8d3bf265cbed
topic_type:
- apiref
ms.openlocfilehash: 5fcf8bc861b2ef0b8ea9f5a5e46585564cc26615
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127697"
---
# <a name="icorruntimehoststop-method"></a><span data-ttu-id="a64d0-102">ICorRuntimeHost::Stop 메서드</span><span class="sxs-lookup"><span data-stu-id="a64d0-102">ICorRuntimeHost::Stop Method</span></span>
<span data-ttu-id="a64d0-103">런타임에 현재 프로세스에 대 한 코드의 실행을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="a64d0-103">Stops the execution of code in the runtime for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a64d0-104">구문</span><span class="sxs-lookup"><span data-stu-id="a64d0-104">Syntax</span></span>  
  
```cpp  
HRESULT Stop ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a64d0-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="a64d0-105">Return Value</span></span>  
  
|<span data-ttu-id="a64d0-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a64d0-106">HRESULT</span></span>|<span data-ttu-id="a64d0-107">설명</span><span class="sxs-lookup"><span data-stu-id="a64d0-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a64d0-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="a64d0-108">S_OK</span></span>|<span data-ttu-id="a64d0-109">작업에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a64d0-109">The operation was successful.</span></span>|  
|<span data-ttu-id="a64d0-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="a64d0-110">S_FALSE</span></span>|<span data-ttu-id="a64d0-111">작업을 완료 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="a64d0-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="a64d0-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a64d0-112">E_FAIL</span></span>|<span data-ttu-id="a64d0-113">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a64d0-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="a64d0-114">메서드가 E_FAIL을 반환 하는 경우 프로세스에서 CLR (공용 언어 런타임)을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a64d0-114">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="a64d0-115">모든 호스팅 Api에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a64d0-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a64d0-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a64d0-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a64d0-117">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a64d0-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a64d0-118">주의</span><span class="sxs-lookup"><span data-stu-id="a64d0-118">Remarks</span></span>  
 <span data-ttu-id="a64d0-119">프로세스가 종료 될 때 코드의 실행이 중지 되기 때문에 일반적으로 `Stop` 메서드를 호출 하는 것은 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a64d0-119">It is typically unnecessary to call the `Stop` method, because the code stops executing when the process exits.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a64d0-120">`Stop`호출 후에 CLR을 동일한 프로세스로 다시 초기화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a64d0-120">After a call to `Stop`, the CLR cannot be reinitialized into the same process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a64d0-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a64d0-121">Requirements</span></span>  
 <span data-ttu-id="a64d0-122">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a64d0-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a64d0-123">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a64d0-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a64d0-124">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a64d0-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a64d0-125">**.NET Framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="a64d0-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a64d0-126">참조</span><span class="sxs-lookup"><span data-stu-id="a64d0-126">See also</span></span>

- [<span data-ttu-id="a64d0-127">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a64d0-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
