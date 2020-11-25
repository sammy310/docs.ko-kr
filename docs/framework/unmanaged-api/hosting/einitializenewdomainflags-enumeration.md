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
ms.openlocfilehash: 8350b507609e63c060cda08514200d386c37a6b3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724327"
---
# <a name="einitializenewdomainflags-enumeration"></a><span data-ttu-id="fa7a6-102">EInitializeNewDomainFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="fa7a6-102">EInitializeNewDomainFlags Enumeration</span></span>

<span data-ttu-id="fa7a6-103">호스트에서 응용 프로그램 도메인 초기화에 대 한 정보를 런타임에 제공할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa7a6-103">Enables the host to provide the runtime with information about the initialization of an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa7a6-104">구문</span><span class="sxs-lookup"><span data-stu-id="fa7a6-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="fa7a6-105">멤버</span><span class="sxs-lookup"><span data-stu-id="fa7a6-105">Members</span></span>  
  
|<span data-ttu-id="fa7a6-106">멤버</span><span class="sxs-lookup"><span data-stu-id="fa7a6-106">Member</span></span>|<span data-ttu-id="fa7a6-107">설명</span><span class="sxs-lookup"><span data-stu-id="fa7a6-107">Description</span></span>|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|<span data-ttu-id="fa7a6-108">플래그가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa7a6-108">No flags.</span></span>|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|<span data-ttu-id="fa7a6-109">호스트가 메서드에서 응용 프로그램 도메인의 보안 상태를 변경 하지 않는다는 것을 CLR (공용 언어 런타임)에 알립니다 <xref:System.AppDomainManager.InitializeNewDomain%2A> .</span><span class="sxs-lookup"><span data-stu-id="fa7a6-109">Informs the common language runtime (CLR) that the host will not make changes to the security state of the application domain in the <xref:System.AppDomainManager.InitializeNewDomain%2A> method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa7a6-110">설명</span><span class="sxs-lookup"><span data-stu-id="fa7a6-110">Remarks</span></span>  

 <span data-ttu-id="fa7a6-111">[ICLRDomainManager:: SetAppDomainManagerType](iclrdomainmanager-setappdomainmanagertype-method.md) 메서드는 형식의 매개 변수를 사용 합니다 `EInitializeNewDomainFlags` .</span><span class="sxs-lookup"><span data-stu-id="fa7a6-111">The [ICLRDomainManager::SetAppDomainManagerType](iclrdomainmanager-setappdomainmanagertype-method.md) method takes a parameter of type `EInitializeNewDomainFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa7a6-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fa7a6-112">Requirements</span></span>  

 <span data-ttu-id="fa7a6-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa7a6-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa7a6-114">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="fa7a6-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fa7a6-115">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fa7a6-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fa7a6-116">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa7a6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa7a6-117">참조</span><span class="sxs-lookup"><span data-stu-id="fa7a6-117">See also</span></span>

- [<span data-ttu-id="fa7a6-118">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="fa7a6-118">Hosting Enumerations</span></span>](hosting-enumerations.md)
- [<span data-ttu-id="fa7a6-119">SetAppDomainManagerType 메서드</span><span class="sxs-lookup"><span data-stu-id="fa7a6-119">SetAppDomainManagerType Method</span></span>](iclrdomainmanager-setappdomainmanagertype-method.md)
