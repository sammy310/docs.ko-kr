---
title: ICorRuntimeHost::CreateDomain 메서드
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomain
helpviewer_keywords:
- CreateDomain method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomain method [.NET Framework hosting]
ms.assetid: b96c5ef3-a9df-4c7c-9952-432d3272cb5c
topic_type:
- apiref
ms.openlocfilehash: 74f17c77e74edb1226dda2d9ebaa9486e1769ce4
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762359"
---
# <a name="icorruntimehostcreatedomain-method"></a><span data-ttu-id="a2ee5-102">ICorRuntimeHost::CreateDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="a2ee5-102">ICorRuntimeHost::CreateDomain Method</span></span>
<span data-ttu-id="a2ee5-103">응용 프로그램 도메인을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a2ee5-103">Creates an application domain.</span></span> <span data-ttu-id="a2ee5-104">호출자는 형식의 인스턴스에 대 한 인터페이스 포인터 <xref:System._AppDomain> 를 받습니다 <xref:System.AppDomain?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="a2ee5-104">The caller receives an interface pointer of type <xref:System._AppDomain> to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2ee5-105">구문</span><span class="sxs-lookup"><span data-stu-id="a2ee5-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateDomain (  
    [in] LPWSTR    pwzFriendlyName,  
    [in] IUnknown* pIdentityArray,  
    [out] void   **pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2ee5-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a2ee5-106">Parameters</span></span>  
 `pwzFriendlyName`  
 <span data-ttu-id="a2ee5-107">진행 도메인에 친숙 한 이름을 지정 하는 데 사용 되는 선택적 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="a2ee5-107">[in] An optional parameter used to give a friendly name to the domain.</span></span> <span data-ttu-id="a2ee5-108">이 이름은 디버거와 같은 사용자 인터페이스에 표시 되어 도메인을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2ee5-108">This friendly name can be displayed in user interfaces such as debuggers to identify the domain.</span></span>  
  
 `pIdentityArray`  
 <span data-ttu-id="a2ee5-109">진행 `IIdentity`권한 집합을 설정 하기 위해 보안 정책을 통해 매핑된 증명 정보를 나타내는 인스턴스에 대 한 포인터의 선택적 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="a2ee5-109">[in] An optional array of pointers to `IIdentity` instances that represent evidence mapped through security policy to establish a  permission set.</span></span> <span data-ttu-id="a2ee5-110">`IIdentity` [Createevidence](icorruntimehost-createevidence-method.md) 메서드를 호출 하 여 개체를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2ee5-110">An `IIdentity` object can be obtained by calling the [CreateEvidence](icorruntimehost-createevidence-method.md) method.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="a2ee5-111">제한이 <xref:System._AppDomain> <xref:System.AppDomain?displayProperty=nameWithType> 도메인을 추가로 제어 하는 데 사용할 수 있는 인스턴스에 대 한 형식의 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a2ee5-111">[out] An interface pointer of type <xref:System._AppDomain> to an instance of <xref:System.AppDomain?displayProperty=nameWithType> that can be used to further control the domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a2ee5-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="a2ee5-112">Return Value</span></span>  
  
|<span data-ttu-id="a2ee5-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a2ee5-113">HRESULT</span></span>|<span data-ttu-id="a2ee5-114">Description</span><span class="sxs-lookup"><span data-stu-id="a2ee5-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a2ee5-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="a2ee5-115">S_OK</span></span>|<span data-ttu-id="a2ee5-116">작업이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a2ee5-116">The operation was successful.</span></span>|  
|<span data-ttu-id="a2ee5-117">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="a2ee5-117">S_FALSE</span></span>|<span data-ttu-id="a2ee5-118">작업을 완료 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="a2ee5-118">The operation failed to complete.</span></span>|  
|<span data-ttu-id="a2ee5-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a2ee5-119">E_FAIL</span></span>|<span data-ttu-id="a2ee5-120">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a2ee5-120">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="a2ee5-121">메서드가 E_FAIL 반환 하는 경우 해당 프로세스에서 CLR (공용 언어 런타임)을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a2ee5-121">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="a2ee5-122">호스팅 Api에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2ee5-122">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a2ee5-123">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a2ee5-123">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a2ee5-124">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2ee5-124">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a2ee5-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a2ee5-125">Requirements</span></span>  
 <span data-ttu-id="a2ee5-126">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a2ee5-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2ee5-127">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a2ee5-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a2ee5-128">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2ee5-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a2ee5-129">**.NET Framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="a2ee5-129">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2ee5-130">참조</span><span class="sxs-lookup"><span data-stu-id="a2ee5-130">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="a2ee5-131">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a2ee5-131">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
