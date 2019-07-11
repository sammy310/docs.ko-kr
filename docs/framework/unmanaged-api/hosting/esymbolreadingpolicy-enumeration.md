---
title: ESymbolReadingPolicy 열거형
ms.date: 03/30/2017
api_name:
- ESymbolReadingPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ESymbolReadingPolicy
helpviewer_keywords:
- ESymbolReadingPolicy enumeration [.NET Framework hosting]
ms.assetid: 4dc6c80d-b694-480b-a378-d5b18420ce17
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45b6b8593331801dd237d0a730afbd5a6a714bbf
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774186"
---
# <a name="esymbolreadingpolicy-enumeration"></a><span data-ttu-id="e3f56-102">ESymbolReadingPolicy 열거형</span><span class="sxs-lookup"><span data-stu-id="e3f56-102">ESymbolReadingPolicy Enumeration</span></span>
<span data-ttu-id="e3f56-103">프로그램 데이터베이스 (PDB) 파일을 읽기 위한 정책을 설정 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f56-103">Contains values that set the policy for reading program database (PDB) files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3f56-104">구문</span><span class="sxs-lookup"><span data-stu-id="e3f56-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="e3f56-105">멤버</span><span class="sxs-lookup"><span data-stu-id="e3f56-105">Members</span></span>  
  
|<span data-ttu-id="e3f56-106">멤버</span><span class="sxs-lookup"><span data-stu-id="e3f56-106">Member</span></span>|<span data-ttu-id="e3f56-107">설명</span><span class="sxs-lookup"><span data-stu-id="e3f56-107">Description</span></span>|  
|------------|-----------------|  
|`eSymbolReadingAlways`|<span data-ttu-id="e3f56-108">디버거가 PDB 파일을 읽을 항상 해야 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f56-108">Specifies that the debugger should always read PDB files.</span></span>|  
|`eSymbolReadingFullTrustOnly`|<span data-ttu-id="e3f56-109">디버거는 읽기 전용 완전 신뢰 어셈블리와 연관 된 PDB 파일을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f56-109">Specifies that the debugger should read only PDB files that are associated with full-trust assemblies.</span></span>|  
|`eSymbolReadingNever`|<span data-ttu-id="e3f56-110">디버거에 PDB 파일을 읽지 않도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f56-110">Specifies that the debugger should never read PDB files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e3f56-111">설명</span><span class="sxs-lookup"><span data-stu-id="e3f56-111">Remarks</span></span>  
 <span data-ttu-id="e3f56-112">합니다 `ESymbolReadingPolicy` 열거형을 사용 하 여 사용 합니다 [iclrdebugmanager:: Setsymbolreadingpolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="e3f56-112">The `ESymbolReadingPolicy` enumeration is used with the [ICLRDebugManager::SetSymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3f56-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e3f56-113">Requirements</span></span>  
 <span data-ttu-id="e3f56-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e3f56-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3f56-115">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e3f56-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e3f56-116">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e3f56-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e3f56-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3f56-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3f56-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="e3f56-118">See also</span></span>

- [<span data-ttu-id="e3f56-119">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="e3f56-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
