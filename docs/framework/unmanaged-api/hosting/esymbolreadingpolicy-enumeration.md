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
ms.openlocfilehash: 42ce1f02294db98c5c593a5f16de5226703d5f9d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733713"
---
# <a name="esymbolreadingpolicy-enumeration"></a><span data-ttu-id="bce15-102">ESymbolReadingPolicy 열거형</span><span class="sxs-lookup"><span data-stu-id="bce15-102">ESymbolReadingPolicy Enumeration</span></span>

<span data-ttu-id="bce15-103">PDB (프로그램 데이터베이스) 파일을 읽기 위한 정책을 설정 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="bce15-103">Contains values that set the policy for reading program database (PDB) files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bce15-104">구문</span><span class="sxs-lookup"><span data-stu-id="bce15-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="bce15-105">멤버</span><span class="sxs-lookup"><span data-stu-id="bce15-105">Members</span></span>  
  
|<span data-ttu-id="bce15-106">멤버</span><span class="sxs-lookup"><span data-stu-id="bce15-106">Member</span></span>|<span data-ttu-id="bce15-107">설명</span><span class="sxs-lookup"><span data-stu-id="bce15-107">Description</span></span>|  
|------------|-----------------|  
|`eSymbolReadingAlways`|<span data-ttu-id="bce15-108">디버거가 항상 PDB 파일을 읽도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bce15-108">Specifies that the debugger should always read PDB files.</span></span>|  
|`eSymbolReadingFullTrustOnly`|<span data-ttu-id="bce15-109">디버거가 완전 신뢰 어셈블리와 연결 된 PDB 파일만 읽도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bce15-109">Specifies that the debugger should read only PDB files that are associated with full-trust assemblies.</span></span>|  
|`eSymbolReadingNever`|<span data-ttu-id="bce15-110">디버거가 PDB 파일을 읽지 않도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bce15-110">Specifies that the debugger should never read PDB files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bce15-111">설명</span><span class="sxs-lookup"><span data-stu-id="bce15-111">Remarks</span></span>  

 <span data-ttu-id="bce15-112">`ESymbolReadingPolicy`열거형은 [ICLRDebugManager:: SetSymbolReadingPolicy](iclrdebugmanager-setsymbolreadingpolicy-method.md) 메서드와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bce15-112">The `ESymbolReadingPolicy` enumeration is used with the [ICLRDebugManager::SetSymbolReadingPolicy](iclrdebugmanager-setsymbolreadingpolicy-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bce15-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bce15-113">Requirements</span></span>  

 <span data-ttu-id="bce15-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bce15-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bce15-115">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="bce15-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bce15-116">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bce15-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bce15-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bce15-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bce15-118">참조</span><span class="sxs-lookup"><span data-stu-id="bce15-118">See also</span></span>

- [<span data-ttu-id="bce15-119">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="bce15-119">Hosting Enumerations</span></span>](hosting-enumerations.md)
