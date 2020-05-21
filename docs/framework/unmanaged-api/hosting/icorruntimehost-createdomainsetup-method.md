---
title: ICorRuntimeHost::CreateDomainSetup 메서드
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomainSetup
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomainSetup
helpviewer_keywords:
- CreateDomainSetup method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomainSetup method [.NET Framework hosting]
ms.assetid: c21dab60-fb65-47d9-8a94-7fd47ca53b48
topic_type:
- apiref
ms.openlocfilehash: aa1ce70311cd4ef0204c1c31efee8bd7b313c81d
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762333"
---
# <a name="icorruntimehostcreatedomainsetup-method"></a><span data-ttu-id="ff42b-102">ICorRuntimeHost::CreateDomainSetup 메서드</span><span class="sxs-lookup"><span data-stu-id="ff42b-102">ICorRuntimeHost::CreateDomainSetup Method</span></span>
<span data-ttu-id="ff42b-103">인스턴스에 IAppDomainSetup 형식의 인터페이스 포인터를 가져옵니다 <xref:System.AppDomainSetup?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="ff42b-103">Gets an interface pointer of type IAppDomainSetup to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="ff42b-104">`IAppDomainSetup`응용 프로그램 도메인을 만들기 전에 요소를 구성 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff42b-104">`IAppDomainSetup` provides methods to configure aspects of an application domain before it is created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff42b-105">구문</span><span class="sxs-lookup"><span data-stu-id="ff42b-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateDomainSetup (  
    [out] IUnknown** pAppDomainSetup  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff42b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ff42b-106">Parameters</span></span>  
 `pAppDomainSetup`  
 <span data-ttu-id="ff42b-107">제한이 인스턴스에 대 한 인터페이스 포인터 <xref:System.AppDomainSetup?displayProperty=nameWithType> 입니다.</span><span class="sxs-lookup"><span data-stu-id="ff42b-107">[out] An interface pointer to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="ff42b-108">이 매개 변수는로 형식화 `IUnknown` 되므로 호출자는 일반적으로 `QueryInterface` 이 포인터에서를 호출 하 여 형식의 인터페이스 포인터를 가져와야 합니다 `IAppDomainSetup` .</span><span class="sxs-lookup"><span data-stu-id="ff42b-108">This parameter is typed as `IUnknown`, so callers should generally call `QueryInterface` on this pointer to obtain an interface pointer of type `IAppDomainSetup`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ff42b-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="ff42b-109">Return Value</span></span>  
  
|<span data-ttu-id="ff42b-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ff42b-110">HRESULT</span></span>|<span data-ttu-id="ff42b-111">Description</span><span class="sxs-lookup"><span data-stu-id="ff42b-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ff42b-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="ff42b-112">S_OK</span></span>|<span data-ttu-id="ff42b-113">작업이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ff42b-113">The operation was successful.</span></span>|  
|<span data-ttu-id="ff42b-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="ff42b-114">S_FALSE</span></span>|<span data-ttu-id="ff42b-115">작업을 완료 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="ff42b-115">The operation failed to complete.</span></span>|  
|<span data-ttu-id="ff42b-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ff42b-116">E_FAIL</span></span>|<span data-ttu-id="ff42b-117">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ff42b-117">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="ff42b-118">메서드가 E_FAIL 반환 하는 경우 해당 프로세스에서 CLR (공용 언어 런타임)을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ff42b-118">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="ff42b-119">호스팅 Api에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff42b-119">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ff42b-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ff42b-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ff42b-121">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff42b-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff42b-122">설명</span><span class="sxs-lookup"><span data-stu-id="ff42b-122">Remarks</span></span>  
 <span data-ttu-id="ff42b-123">이 메서드에서 반환 된 포인터는 일반적으로 [Createdomainex](icorruntimehost-createdomainex-method.md) 메서드에 매개 변수로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff42b-123">The pointer returned from this method is typically passed as a parameter to the [CreateDomainEx](icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff42b-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ff42b-124">Requirements</span></span>  
 <span data-ttu-id="ff42b-125">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff42b-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff42b-126">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ff42b-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ff42b-127">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff42b-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ff42b-128">**.NET Framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="ff42b-128">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff42b-129">참조</span><span class="sxs-lookup"><span data-stu-id="ff42b-129">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [<span data-ttu-id="ff42b-130">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ff42b-130">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
