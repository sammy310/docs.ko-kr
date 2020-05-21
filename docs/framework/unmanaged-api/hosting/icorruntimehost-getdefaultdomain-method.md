---
title: ICorRuntimeHost::GetDefaultDomain 메서드
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.GetDefaultDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::GetDefaultDomain
helpviewer_keywords:
- ICorRuntimeHost::GetDefaultDomain method [.NET Framework hosting]
- GetDefaultDomain method [.NET Framework hosting]
ms.assetid: 5e17a6fc-f335-4aae-9bb0-c3e1271a9426
topic_type:
- apiref
ms.openlocfilehash: a23083777d0cd5965511f3689578a60220008420
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762232"
---
# <a name="icorruntimehostgetdefaultdomain-method"></a><span data-ttu-id="3cec1-102">ICorRuntimeHost::GetDefaultDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="3cec1-102">ICorRuntimeHost::GetDefaultDomain Method</span></span>
<span data-ttu-id="3cec1-103"><xref:System._AppDomain?displayProperty=nameWithType>현재 프로세스에 대 한 기본 도메인을 나타내는 형식의 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3cec1-103">Gets an interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the default domain for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cec1-104">구문</span><span class="sxs-lookup"><span data-stu-id="3cec1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDefaultDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3cec1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3cec1-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="3cec1-106">제한이 <xref:System._AppDomain?displayProperty=nameWithType> <xref:System.AppDomain> 프로세스의 기본 응용 프로그램 도메인을 나타내는 인스턴스에 대 한 형식의 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3cec1-106">[out] An interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType> to the <xref:System.AppDomain> instance that represents the default application domain for the process.</span></span>  
  
 <span data-ttu-id="3cec1-107">이 포인터는 형식화 되어 `IUnknown` 있으므로 호출자는 일반적으로 `QueryInterface` 형식의 인터페이스 포인터를 가져오기 위해를 호출 해야 합니다 <xref:System._AppDomain?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="3cec1-107">This pointer is typed `IUnknown`, so callers should generally call `QueryInterface` to obtain an interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3cec1-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="3cec1-108">Return Value</span></span>  
  
|<span data-ttu-id="3cec1-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3cec1-109">HRESULT</span></span>|<span data-ttu-id="3cec1-110">Description</span><span class="sxs-lookup"><span data-stu-id="3cec1-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3cec1-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3cec1-111">S_OK</span></span>|<span data-ttu-id="3cec1-112">작업이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3cec1-112">The operation was successful.</span></span>|  
|<span data-ttu-id="3cec1-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="3cec1-113">S_FALSE</span></span>|<span data-ttu-id="3cec1-114">작업을 완료 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="3cec1-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="3cec1-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3cec1-115">E_FAIL</span></span>|<span data-ttu-id="3cec1-116">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3cec1-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="3cec1-117">메서드가 E_FAIL 반환 하는 경우 해당 프로세스에서 CLR (공용 언어 런타임)을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3cec1-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="3cec1-118">호스팅 Api에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cec1-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3cec1-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3cec1-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3cec1-120">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cec1-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3cec1-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3cec1-121">Requirements</span></span>  
 <span data-ttu-id="3cec1-122">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3cec1-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cec1-123">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="3cec1-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3cec1-124">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cec1-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3cec1-125">**.NET Framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="3cec1-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cec1-126">참조</span><span class="sxs-lookup"><span data-stu-id="3cec1-126">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="3cec1-127">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3cec1-127">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
