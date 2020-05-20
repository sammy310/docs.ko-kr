---
title: EInitializeNewDomainFlags 열거형
ms.date: 03/30/2017
api_name:
- EInitializeNewDomainFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EInitializeNewDomainFlags
helpviewer_keywords:
- EInitializeNewDomainFlags enumeration [.NET Framework hosting]
ms.assetid: 3a120ab2-f5ef-4c9b-8595-d3ed7247c342
ms.openlocfilehash: 7ff10f84d8d270d31c5d560fb3c9bd3c81cf3e24
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616231"
---
# <a name="einitializenewdomainflags-enumeration"></a><span data-ttu-id="a1117-102">EInitializeNewDomainFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="a1117-102">EInitializeNewDomainFlags Enumeration</span></span>
<span data-ttu-id="a1117-103">호스트에서 응용 프로그램 도메인 초기화에 대 한 정보를 런타임에 제공할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1117-103">Enables the host to provide the runtime with information about the initialization of an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1117-104">구문</span><span class="sxs-lookup"><span data-stu-id="a1117-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="a1117-105">멤버</span><span class="sxs-lookup"><span data-stu-id="a1117-105">Members</span></span>  
  
|<span data-ttu-id="a1117-106">멤버</span><span class="sxs-lookup"><span data-stu-id="a1117-106">Member</span></span>|<span data-ttu-id="a1117-107">설명</span><span class="sxs-lookup"><span data-stu-id="a1117-107">Description</span></span>|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|<span data-ttu-id="a1117-108">플래그가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1117-108">No flags.</span></span>|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|<span data-ttu-id="a1117-109">호스트가 메서드에서 응용 프로그램 도메인의 보안 상태를 변경 하지 않는다는 것을 CLR (공용 언어 런타임)에 알립니다 <xref:System.AppDomainManager.InitializeNewDomain%2A> .</span><span class="sxs-lookup"><span data-stu-id="a1117-109">Informs the common language runtime (CLR) that the host will not make changes to the security state of the application domain in the <xref:System.AppDomainManager.InitializeNewDomain%2A> method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1117-110">설명</span><span class="sxs-lookup"><span data-stu-id="a1117-110">Remarks</span></span>  
 <span data-ttu-id="a1117-111">[ICLRDomainManager:: SetAppDomainManagerType](iclrdomainmanager-setappdomainmanagertype-method.md) 메서드는 형식의 매개 변수를 사용 합니다 `EInitializeNewDomainFlags` .</span><span class="sxs-lookup"><span data-stu-id="a1117-111">The [ICLRDomainManager::SetAppDomainManagerType](iclrdomainmanager-setappdomainmanagertype-method.md) method takes a parameter of type `EInitializeNewDomainFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1117-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a1117-112">Requirements</span></span>  
 <span data-ttu-id="a1117-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a1117-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1117-114">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a1117-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a1117-115">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a1117-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a1117-116">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1117-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1117-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a1117-117">See also</span></span>

- [<span data-ttu-id="a1117-118">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="a1117-118">Hosting Enumerations</span></span>](hosting-enumerations.md)
- [<span data-ttu-id="a1117-119">SetAppDomainManagerType 메서드</span><span class="sxs-lookup"><span data-stu-id="a1117-119">SetAppDomainManagerType Method</span></span>](iclrdomainmanager-setappdomainmanagertype-method.md)
