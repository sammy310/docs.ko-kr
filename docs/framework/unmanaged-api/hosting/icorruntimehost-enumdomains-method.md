---
title: ICorRuntimeHost::EnumDomains 메서드
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.EnumDomains
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::EnumDomains
helpviewer_keywords:
- ICorRuntimeHost::EnumDomains method [.NET Framework hosting]
- EnumDomains method [.NET Framework hosting]
ms.assetid: 96b74995-0cde-4876-b6df-7fc164e6a5d1
topic_type:
- apiref
ms.openlocfilehash: f4338429dc24bf5196b92d3f18e73c98442f61e7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720664"
---
# <a name="icorruntimehostenumdomains-method"></a><span data-ttu-id="69e01-102">ICorRuntimeHost::EnumDomains 메서드</span><span class="sxs-lookup"><span data-stu-id="69e01-102">ICorRuntimeHost::EnumDomains Method</span></span>

<span data-ttu-id="69e01-103">현재 프로세스의 도메인에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="69e01-103">Gets an enumerator for the domains in the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69e01-104">구문</span><span class="sxs-lookup"><span data-stu-id="69e01-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumDomains (  
    [out] HCORENUM *hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69e01-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="69e01-105">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="69e01-106">제한이 도메인에 대 한 열거자입니다.</span><span class="sxs-lookup"><span data-stu-id="69e01-106">[out] An enumerator for the domains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="69e01-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="69e01-107">Return Value</span></span>  
  
|<span data-ttu-id="69e01-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="69e01-108">HRESULT</span></span>|<span data-ttu-id="69e01-109">설명</span><span class="sxs-lookup"><span data-stu-id="69e01-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="69e01-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="69e01-110">S_OK</span></span>|<span data-ttu-id="69e01-111">작업이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="69e01-111">The operation was successful.</span></span>|  
|<span data-ttu-id="69e01-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="69e01-112">S_FALSE</span></span>|<span data-ttu-id="69e01-113">작업을 완료 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="69e01-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="69e01-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="69e01-114">E_FAIL</span></span>|<span data-ttu-id="69e01-115">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="69e01-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="69e01-116">메서드가 E_FAIL 반환 하는 경우 해당 프로세스에서 CLR (공용 언어 런타임)을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="69e01-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="69e01-117">호스팅 Api에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="69e01-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="69e01-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="69e01-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="69e01-119">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69e01-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="69e01-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="69e01-120">Requirements</span></span>  

 <span data-ttu-id="69e01-121">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69e01-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69e01-122">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="69e01-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="69e01-123">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69e01-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="69e01-124">**.NET Framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="69e01-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69e01-125">참조</span><span class="sxs-lookup"><span data-stu-id="69e01-125">See also</span></span>

- [<span data-ttu-id="69e01-126">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="69e01-126">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
