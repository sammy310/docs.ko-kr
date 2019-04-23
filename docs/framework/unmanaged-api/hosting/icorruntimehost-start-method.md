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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e6521f8013bf92f073ab4b6808871c95ac2802b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59072859"
---
# <a name="icorruntimehoststart-method"></a><span data-ttu-id="2666f-102">ICorRuntimeHost::Start 메서드</span><span class="sxs-lookup"><span data-stu-id="2666f-102">ICorRuntimeHost::Start Method</span></span>
<span data-ttu-id="2666f-103">CLR (공용 언어 런타임)을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="2666f-103">Starts the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2666f-104">구문</span><span class="sxs-lookup"><span data-stu-id="2666f-104">Syntax</span></span>  
  
```  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="2666f-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="2666f-105">Return Value</span></span>  
  
|<span data-ttu-id="2666f-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2666f-106">HRESULT</span></span>|<span data-ttu-id="2666f-107">설명</span><span class="sxs-lookup"><span data-stu-id="2666f-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2666f-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="2666f-108">S_OK</span></span>|<span data-ttu-id="2666f-109">작업에 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2666f-109">The operation was successful.</span></span>|  
|<span data-ttu-id="2666f-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="2666f-110">S_FALSE</span></span>|<span data-ttu-id="2666f-111">작업을 완료 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="2666f-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="2666f-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2666f-112">E_FAIL</span></span>|<span data-ttu-id="2666f-113">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2666f-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="2666f-114">메서드가 E_FAIL을 반환 하는 경우 CLR은 프로세스에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2666f-114">If a method returns E_FAIL, the CLR is no longer usable in the process.</span></span> <span data-ttu-id="2666f-115">호스팅 Api에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2666f-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2666f-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2666f-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2666f-117">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2666f-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2666f-118">설명</span><span class="sxs-lookup"><span data-stu-id="2666f-118">Remarks</span></span>  
 <span data-ttu-id="2666f-119">일반적으로 필요 없는 호출 하 여 `Start` 메서드를 CLR은 관리 되는 코드를 실행 하는 첫 번째 요청 시 자동으로 시작 되므로 합니다.</span><span class="sxs-lookup"><span data-stu-id="2666f-119">It is typically not necessary to call the `Start` method, because the CLR starts automatically upon the first request to run managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2666f-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2666f-120">Requirements</span></span>  
 <span data-ttu-id="2666f-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2666f-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2666f-122">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2666f-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2666f-123">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="2666f-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2666f-124">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="2666f-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2666f-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="2666f-125">See also</span></span>

- [<span data-ttu-id="2666f-126">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2666f-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
