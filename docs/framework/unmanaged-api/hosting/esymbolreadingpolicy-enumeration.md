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
ms.openlocfilehash: 9ba29952fe4a6edfc6e9e80ec02f82de65ef0064
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208425"
---
# <a name="esymbolreadingpolicy-enumeration"></a><span data-ttu-id="10d6f-102">ESymbolReadingPolicy 열거형</span><span class="sxs-lookup"><span data-stu-id="10d6f-102">ESymbolReadingPolicy Enumeration</span></span>
<span data-ttu-id="10d6f-103">프로그램 데이터베이스 (PDB) 파일을 읽기 위한 정책을 설정 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6f-103">Contains values that set the policy for reading program database (PDB) files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10d6f-104">구문</span><span class="sxs-lookup"><span data-stu-id="10d6f-104">Syntax</span></span>  
  
```  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="10d6f-105">멤버</span><span class="sxs-lookup"><span data-stu-id="10d6f-105">Members</span></span>  
  
|<span data-ttu-id="10d6f-106">멤버</span><span class="sxs-lookup"><span data-stu-id="10d6f-106">Member</span></span>|<span data-ttu-id="10d6f-107">설명</span><span class="sxs-lookup"><span data-stu-id="10d6f-107">Description</span></span>|  
|------------|-----------------|  
|`eSymbolReadingAlways`|<span data-ttu-id="10d6f-108">디버거가 PDB 파일을 읽을 항상 해야 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6f-108">Specifies that the debugger should always read PDB files.</span></span>|  
|`eSymbolReadingFullTrustOnly`|<span data-ttu-id="10d6f-109">디버거는 읽기 전용 완전 신뢰 어셈블리와 연관 된 PDB 파일을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6f-109">Specifies that the debugger should read only PDB files that are associated with full-trust assemblies.</span></span>|  
|`eSymbolReadingNever`|<span data-ttu-id="10d6f-110">디버거에 PDB 파일을 읽지 않도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6f-110">Specifies that the debugger should never read PDB files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10d6f-111">설명</span><span class="sxs-lookup"><span data-stu-id="10d6f-111">Remarks</span></span>  
 <span data-ttu-id="10d6f-112">합니다 `ESymbolReadingPolicy` 열거형을 사용 하 여 사용 합니다 [iclrdebugmanager:: Setsymbolreadingpolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="10d6f-112">The `ESymbolReadingPolicy` enumeration is used with the [ICLRDebugManager::SetSymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10d6f-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="10d6f-113">Requirements</span></span>  
 <span data-ttu-id="10d6f-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="10d6f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10d6f-115">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="10d6f-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="10d6f-116">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="10d6f-116">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="10d6f-117">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="10d6f-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="10d6f-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="10d6f-118">See also</span></span>

- [<span data-ttu-id="10d6f-119">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="10d6f-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
