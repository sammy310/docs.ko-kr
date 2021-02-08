---
description: '자세히 알아보기: ICorRuntimeHost:: CloseEnum 메서드'
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
ms.openlocfilehash: 1fc18ff3e00f85a4f047417f880ec2b0e06496b7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789725"
---
# <a name="icorruntimehostcloseenum-method"></a><span data-ttu-id="1d3b9-103">ICorRuntimeHost::CloseEnum 메서드</span><span class="sxs-lookup"><span data-stu-id="1d3b9-103">ICorRuntimeHost::CloseEnum Method</span></span>

<span data-ttu-id="1d3b9-104">도메인 열거자를 도메인 목록의 시작 부분으로 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d3b9-104">Resets a domain enumerator back to the beginning of the domain list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d3b9-105">구문</span><span class="sxs-lookup"><span data-stu-id="1d3b9-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseEnum (  
    [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d3b9-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1d3b9-106">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="1d3b9-107">진행 다시 설정할 열거자입니다.</span><span class="sxs-lookup"><span data-stu-id="1d3b9-107">[in] The enumerator to reset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1d3b9-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="1d3b9-108">Return Value</span></span>  
  
|<span data-ttu-id="1d3b9-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1d3b9-109">HRESULT</span></span>|<span data-ttu-id="1d3b9-110">설명</span><span class="sxs-lookup"><span data-stu-id="1d3b9-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1d3b9-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="1d3b9-111">S_OK</span></span>|<span data-ttu-id="1d3b9-112">작업이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1d3b9-112">The operation was successful.</span></span>|  
|<span data-ttu-id="1d3b9-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="1d3b9-113">S_FALSE</span></span>|<span data-ttu-id="1d3b9-114">작업을 완료 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="1d3b9-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="1d3b9-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1d3b9-115">E_FAIL</span></span>|<span data-ttu-id="1d3b9-116">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1d3b9-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="1d3b9-117">메서드가 E_FAIL 반환 하는 경우 해당 프로세스에서 CLR (공용 언어 런타임)을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d3b9-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="1d3b9-118">호스팅 Api에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d3b9-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1d3b9-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1d3b9-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1d3b9-120">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d3b9-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1d3b9-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1d3b9-121">Requirements</span></span>  

 <span data-ttu-id="1d3b9-122">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d3b9-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d3b9-123">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1d3b9-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1d3b9-124">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d3b9-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1d3b9-125">**.NET Framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="1d3b9-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d3b9-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d3b9-126">See also</span></span>

- [<span data-ttu-id="1d3b9-127">CorBindToRuntimeEx 함수</span><span class="sxs-lookup"><span data-stu-id="1d3b9-127">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="1d3b9-128">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1d3b9-128">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
