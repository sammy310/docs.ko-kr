---
description: '자세히 알아보기: EInitializeNewDomainFlags 열거형'
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
ms.openlocfilehash: b856d061e86c0c79b35f842975378307b79a37e7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785467"
---
# <a name="einitializenewdomainflags-enumeration"></a><span data-ttu-id="09d33-103">EInitializeNewDomainFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="09d33-103">EInitializeNewDomainFlags Enumeration</span></span>

<span data-ttu-id="09d33-104">호스트에서 응용 프로그램 도메인 초기화에 대 한 정보를 런타임에 제공할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="09d33-104">Enables the host to provide the runtime with information about the initialization of an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09d33-105">구문</span><span class="sxs-lookup"><span data-stu-id="09d33-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="09d33-106">구성원</span><span class="sxs-lookup"><span data-stu-id="09d33-106">Members</span></span>  
  
|<span data-ttu-id="09d33-107">멤버</span><span class="sxs-lookup"><span data-stu-id="09d33-107">Member</span></span>|<span data-ttu-id="09d33-108">설명</span><span class="sxs-lookup"><span data-stu-id="09d33-108">Description</span></span>|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|<span data-ttu-id="09d33-109">플래그가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="09d33-109">No flags.</span></span>|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|<span data-ttu-id="09d33-110">호스트가 메서드에서 응용 프로그램 도메인의 보안 상태를 변경 하지 않는다는 것을 CLR (공용 언어 런타임)에 알립니다 <xref:System.AppDomainManager.InitializeNewDomain%2A> .</span><span class="sxs-lookup"><span data-stu-id="09d33-110">Informs the common language runtime (CLR) that the host will not make changes to the security state of the application domain in the <xref:System.AppDomainManager.InitializeNewDomain%2A> method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09d33-111">설명</span><span class="sxs-lookup"><span data-stu-id="09d33-111">Remarks</span></span>  

 <span data-ttu-id="09d33-112">[ICLRDomainManager:: SetAppDomainManagerType](iclrdomainmanager-setappdomainmanagertype-method.md) 메서드는 형식의 매개 변수를 사용 합니다 `EInitializeNewDomainFlags` .</span><span class="sxs-lookup"><span data-stu-id="09d33-112">The [ICLRDomainManager::SetAppDomainManagerType](iclrdomainmanager-setappdomainmanagertype-method.md) method takes a parameter of type `EInitializeNewDomainFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09d33-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="09d33-113">Requirements</span></span>  

 <span data-ttu-id="09d33-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09d33-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09d33-115">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="09d33-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="09d33-116">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="09d33-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="09d33-117">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09d33-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09d33-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="09d33-118">See also</span></span>

- [<span data-ttu-id="09d33-119">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="09d33-119">Hosting Enumerations</span></span>](hosting-enumerations.md)
- [<span data-ttu-id="09d33-120">SetAppDomainManagerType 메서드</span><span class="sxs-lookup"><span data-stu-id="09d33-120">SetAppDomainManagerType Method</span></span>](iclrdomainmanager-setappdomainmanagertype-method.md)
