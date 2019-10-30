---
title: ICorRuntimeHost::Start 메서드
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::Start
helpviewer_keywords:
- Start method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::Start method [.NET Framework hosting]
ms.assetid: c66f3ac5-6489-484a-9bed-c31b711cee01
topic_type:
- apiref
ms.openlocfilehash: c450d83669a3bc548c15ed5800dc73438b9a84a6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127690"
---
# <a name="icorruntimehoststart-method"></a><span data-ttu-id="ece13-102">ICorRuntimeHost::Start 메서드</span><span class="sxs-lookup"><span data-stu-id="ece13-102">ICorRuntimeHost::Start Method</span></span>
<span data-ttu-id="ece13-103">CLR (공용 언어 런타임)을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="ece13-103">Starts the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ece13-104">구문</span><span class="sxs-lookup"><span data-stu-id="ece13-104">Syntax</span></span>  
  
```cpp  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ece13-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="ece13-105">Return Value</span></span>  
  
|<span data-ttu-id="ece13-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ece13-106">HRESULT</span></span>|<span data-ttu-id="ece13-107">설명</span><span class="sxs-lookup"><span data-stu-id="ece13-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ece13-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="ece13-108">S_OK</span></span>|<span data-ttu-id="ece13-109">작업에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ece13-109">The operation was successful.</span></span>|  
|<span data-ttu-id="ece13-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="ece13-110">S_FALSE</span></span>|<span data-ttu-id="ece13-111">작업을 완료 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="ece13-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="ece13-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ece13-112">E_FAIL</span></span>|<span data-ttu-id="ece13-113">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ece13-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="ece13-114">메서드가 E_FAIL을 반환 하는 경우 해당 프로세스에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ece13-114">If a method returns E_FAIL, the CLR is no longer usable in the process.</span></span> <span data-ttu-id="ece13-115">모든 호스팅 Api에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ece13-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ece13-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ece13-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ece13-117">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ece13-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ece13-118">주의</span><span class="sxs-lookup"><span data-stu-id="ece13-118">Remarks</span></span>  
 <span data-ttu-id="ece13-119">CLR은 관리 코드를 실행 하는 첫 번째 요청 시 자동으로 시작 되기 때문에 일반적으로 `Start` 메서드를 호출할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ece13-119">It is typically not necessary to call the `Start` method, because the CLR starts automatically upon the first request to run managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ece13-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ece13-120">Requirements</span></span>  
 <span data-ttu-id="ece13-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ece13-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ece13-122">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ece13-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ece13-123">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ece13-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ece13-124">**.NET Framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="ece13-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ece13-125">참조</span><span class="sxs-lookup"><span data-stu-id="ece13-125">See also</span></span>

- [<span data-ttu-id="ece13-126">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ece13-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
