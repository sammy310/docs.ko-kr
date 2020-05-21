---
title: ICorRuntimeHost::CloseEnum 메서드
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CloseEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CloseEnum
helpviewer_keywords:
- CloseEnum method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::CloseEnum method [.NET Framework hosting]
ms.assetid: f7ce7e8c-0a3e-4587-a180-063e2b85940e
topic_type:
- apiref
ms.openlocfilehash: a5a86df3ac1f50ca624490ad80a6fed903433436
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762372"
---
# <a name="icorruntimehostcloseenum-method"></a><span data-ttu-id="6d43e-102">ICorRuntimeHost::CloseEnum 메서드</span><span class="sxs-lookup"><span data-stu-id="6d43e-102">ICorRuntimeHost::CloseEnum Method</span></span>
<span data-ttu-id="6d43e-103">도메인 열거자를 도메인 목록의 시작 부분으로 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d43e-103">Resets a domain enumerator back to the beginning of the domain list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d43e-104">구문</span><span class="sxs-lookup"><span data-stu-id="6d43e-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseEnum (  
    [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d43e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6d43e-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="6d43e-106">진행 다시 설정할 열거자입니다.</span><span class="sxs-lookup"><span data-stu-id="6d43e-106">[in] The enumerator to reset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6d43e-107">Return Value</span><span class="sxs-lookup"><span data-stu-id="6d43e-107">Return Value</span></span>  
  
|<span data-ttu-id="6d43e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6d43e-108">HRESULT</span></span>|<span data-ttu-id="6d43e-109">Description</span><span class="sxs-lookup"><span data-stu-id="6d43e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6d43e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6d43e-110">S_OK</span></span>|<span data-ttu-id="6d43e-111">작업이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6d43e-111">The operation was successful.</span></span>|  
|<span data-ttu-id="6d43e-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="6d43e-112">S_FALSE</span></span>|<span data-ttu-id="6d43e-113">작업을 완료 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="6d43e-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="6d43e-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6d43e-114">E_FAIL</span></span>|<span data-ttu-id="6d43e-115">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6d43e-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="6d43e-116">메서드가 E_FAIL 반환 하는 경우 해당 프로세스에서 CLR (공용 언어 런타임)을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6d43e-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="6d43e-117">호스팅 Api에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d43e-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6d43e-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6d43e-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6d43e-119">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d43e-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6d43e-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6d43e-120">Requirements</span></span>  
 <span data-ttu-id="6d43e-121">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6d43e-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d43e-122">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="6d43e-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6d43e-123">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d43e-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6d43e-124">**.NET Framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="6d43e-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d43e-125">참조</span><span class="sxs-lookup"><span data-stu-id="6d43e-125">See also</span></span>

- [<span data-ttu-id="6d43e-126">CorBindToRuntimeEx 함수</span><span class="sxs-lookup"><span data-stu-id="6d43e-126">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="6d43e-127">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6d43e-127">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
